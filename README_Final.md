# 🛠️ Desafio Hermes Reply – Simulação de Coleta de Dados com ESP32  
## Sprint 2 – Fase 4 FIAP

---

## 📌 Introdução

Este projeto tem como objetivo simular um ambiente industrial inteligente, utilizando o ESP32 com sensores virtuais para coletar dados ambientais. Essa simulação representa um cenário típico da Indústria 4.0, onde sensores em tempo real monitoram variáveis críticas como temperatura e umidade, permitindo decisões automatizadas e manutenção preditiva.

---

## 🧪 Sensor Utilizado

**Sensor:** DHT22 (Temperatura e Umidade)

**Justificativa:** O DHT22 foi escolhido por sua ampla utilização em ambientes industriais, devido à boa precisão na leitura de temperatura e umidade, além da facilidade de integração com o ESP32. É ideal para simulações de controle climático em ambientes que exigem estabilidade térmica, como laboratórios, salas técnicas e linhas de produção.

---

## 🔌 Montagem do Circuito (Tarefa 1)

O circuito foi montado no simulador **Wokwi**, com o sensor DHT22 conectado ao pino GPIO 15 do ESP32. Um resistor de 10kΩ foi adicionado entre VCC e DATA para estabilizar a leitura.

📷 **Print da Simulação no Wokwi:**  
![Circuito no Wokwi](./imgs/circuito_wokwi.png)

🔗 **Link do Projeto no Wokwi:**  
[https://wokwi.com/projects/EXEMPLO](https://wokwi.com/projects/EXEMPLO)

---

## 💻 Código do Sensor (Tarefa 2)

```cpp
#include "DHT.h"
#define DHTPIN 15
#define DHTTYPE DHT22

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(115200);
  dht.begin();
}

void loop() {
  float temp = dht.readTemperature();
  float hum = dht.readHumidity();

  Serial.print(millis());
  Serial.print(",");
  Serial.print(temp);
  Serial.print(",");
  Serial.println(hum);

  delay(2000);
}
```

📷 **Print do Monitor Serial:**  
![Serial Monitor](./imgs/print_serial.png)

---

## 📊 Análise de Dados (Tarefa 3)

Os dados foram processados em Python e organizados em 3 gráficos:

### 📈 Gráfico de Linha – Temperatura e Umidade

![Gráfico Linha](./imgs/grafico_linha_temperatura_umidade.jpg)

### 📊 Boxplot – Distribuição das Leituras

![Gráfico Boxplot](./imgs/grafico_boxplot_temperatura_umidade.jpg)

### 📊 Gráfico de Barras – Médias Agrupadas

![Gráfico Barras](./imgs/grafico_barras_temperatura_umidade.jpg)

---

## 📋 Estatísticas Resumidas

*(Fonte: dados_salvos_texto.txt)*

- **Temperatura:** Média: 33,17 °C | Máx: 40,00 °C | Mín: 25,00 °C | Mediana: 33,17 °C  
- **Umidade:** Média: 46,10% | Máx: 57,20% | Mín: 35,00% | Mediana: 46,10%

---

## 🔍 Insights Críticos

- Os gráficos revelam uma **forte correlação** entre o aumento de temperatura e umidade ao longo do tempo.
- O aumento gradual de ambos sugere **influência climática externa**, não um esforço interno de máquinas.
- A amplitude da **umidade** é maior, mas isso deve ser analisado proporcionalmente à sua escala.
- Um possível **outlier na umidade (~68%)** sugere um pico anômalo que, em contexto real, indicaria a necessidade de investigação.

---

## ✅ Conclusão

Este projeto simulou com sucesso o processo completo de monitoramento ambiental em um ambiente industrial digitalizado. Utilizando o sensor DHT22 com ESP32, foi possível coletar, registrar e analisar dados reais simulados. A análise demonstrou como a leitura precisa de sensores pode gerar **insights valiosos para manutenção, controle de qualidade e prevenção de falhas**, princípios fundamentais da Indústria 4.0.

---

## 📁 Estrutura do Projeto

```
/Sprint-2/
├── README.md
├── imgs/
│   ├── circuito_wokwi.png
│   ├── print_serial.png
│   ├── grafico_linha_temperatura_umidade.jpg
│   ├── grafico_boxplot_temperatura_umidade.jpg
│   └── grafico_barras_temperatura_umidade.jpg
├── code/
│   └── codigo_sensor.ino
├── dados/
│   ├── dados_sensor.csv
│   └── dados_salvos_texto.txt
├── analise/
│   └── graficos.py
```
