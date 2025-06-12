#  Desafio Hermes Reply – Simulação de Coleta de Dados com ESP32  
## Sprint 2 – Fase 4 FIAP

---

##  Introdução

Este projeto tem como objetivo simular um ambiente industrial inteligente, utilizando o ESP32 com sensores virtuais para coletar dados ambientais. Essa simulação representa um cenário típico da Indústria 4.0, onde sensores em tempo real monitoram variáveis críticas como temperatura e umidade, permitindo decisões automatizadas e manutenção preditiva.

---

##  Sensor Utilizado

**Sensor:** DHT22 (Temperatura e Umidade)

**Justificativa:** O DHT22 foi escolhido por sua ampla utilização em ambientes industriais, devido à boa precisão na leitura de temperatura e umidade, além da facilidade de integração com o ESP32. É ideal para simulações de controle climático em ambientes que exigem estabilidade térmica, como laboratórios, salas técnicas e linhas de produção.

---

##  Montagem do Circuito

O circuito foi montado no simulador **Wokwi**, com o sensor DHT22 conectado ao pino GPIO 15 do ESP32. Um resistor de 10kΩ foi adicionado entre VCC e DATA para estabilizar a leitura.

 **Print da Simulação no Wokwi:**  
![Captura_de_tela_2025-06-09_185427 1](https://github.com/user-attachments/assets/91146396-81c0-4087-8a52-b400d517b3a6)


---

 **Print do Monitor Serial:**  
![Captura_de_tela_2025-06-09_185510 1](https://github.com/user-attachments/assets/a81b04cb-6d32-4f8a-a5a1-b1ac39022cc6)

---


##  Análise de Dados

Os dados foram processados em Python e organizados em 3 gráficos:

###  Gráfico de Linha – Temperatura e Umidade
![Imagem do WhatsApp de 2025-06-11 à(s) 15 55 15_7aab8d74](https://github.com/user-attachments/assets/c1ddd49c-c373-4cdc-a7e2-e46124bfff09)



###  Boxplot – Distribuição das Leituras

![Imagem do WhatsApp de 2025-06-11 à(s) 15 55 15_6e99ed59](https://github.com/user-attachments/assets/d09565ff-3ddc-48ae-9bba-0e68fb84fbc4)


###  Gráfico de Barras – Médias Agrupadas

![Imagem do WhatsApp de 2025-06-11 à(s) 15 55 15_3495747c](https://github.com/user-attachments/assets/9c7a02fa-5781-46de-b5b6-e2890a3cea20)


---

##  Estatísticas Resumidas

- **Temperatura:** Média: 33,17 °C | Máx: 40,00 °C | Mín: 25,00 °C | Mediana: 33,17 °C  
- **Umidade:** Média: 46,10% | Máx: 57,20% | Mín: 35,00% | Mediana: 46,10%

---

##  Insights Críticos

- Os gráficos revelam uma **forte correlação** entre o aumento de temperatura e umidade ao longo do tempo.
- O aumento gradual de ambos sugere **influência climática externa**, não um esforço interno de máquinas.
- A amplitude da **umidade** é maior, mas isso deve ser analisado proporcionalmente à sua escala.
- Um possível **outlier na umidade (~68%)** sugere um pico anômalo que, em contexto real, indicaria a necessidade de investigação.

---

##  Conclusão

Este projeto simulou com sucesso o processo completo de monitoramento ambiental em um ambiente industrial digitalizado. Utilizando o sensor DHT22 com ESP32, foi possível coletar, registrar e analisar dados reais simulados. A análise demonstrou como a leitura precisa de sensores pode gerar **insights valiosos para manutenção, controle de qualidade e prevenção de falhas**, princípios fundamentais da Indústria 4.0.
