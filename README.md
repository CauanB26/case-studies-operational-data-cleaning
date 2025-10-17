> **⚠️ Observação:** Este é um case study de um pipeline de processamento de dados. Por motivos de confidencialidade, os demais arquivos não são compartilhados.

---

### 🎯 Objetivo do Projeto

O objetivo deste projeto foi desenvolver um pipeline de análise de dados robusto para automatizar o processamento e a interpretação de dados. A solução trata dados brutos extraídos de planilhas Excel, em uma série limpa e confiável, permitindo o cálculos e avaliações mais precisas, auxiliando na tomada de decisões sobre manutenção e operação.

---

### 📈 O Cenário: Um Desafio Operacional Diário

A análise manual de dados é um processo complexo e impreciso. Os dados brutos frequentemente contêm anomalias como:

**Valores Inválidos:** Leituras fora de um espectro realista. 
**Ruído e Picos:** Flutuações momentâneas que não representam a tendência real 
**Lacunas de Dados:** Períodos com falha de leituras ou comunicação interrompida.  
**Eventos de Reset:** Quedas bruscas nos valores que "resetam" o ciclo e precisam ser tratadas de forma distinta. 

A análise manual desses dados é demorada e subjetiva, dificultando a obtenção de um indicadores diários confiável para planejar as ações operacionais.

---

### ✨ A Solução: Um Pipeline de Análise em Python

Para resolver este problema, desenvolvi um script em Python que implementa um pipeline de processamento de dados sequencial e altamente especializado. A ferramenta ingere os dados, aplica uma série de correções estatísticas e heurísticas, e gera um relatório final acionável. Os recursos técnicos incluem:

**✅ Pipeline de Correção de Dados:**
    * Executa uma sequência de 8 etapas lógicas e configuráveis, onde a saída de uma etapa serve como entrada para a próxima, garantindo um tratamento de dados consistente e auditável.

**✅ Tratamento Estatístico de Outliers:**
    * Utiliza a média aparada (scipy.stats.trim_mean) para calcular o valor diário agregado, removendo os 20% de dados mais extremos de cada dia para mitigar o efeito de leituras anômalas.

**✅ Algoritmos de Detecção de Anomalias:**
    * Implementa lógicas customizadas para identificar e corrigir picos de dados que não se sustentam ao longo do tempo, bem como pequenas quedas (ruídos) que não correspondem a eventos de sistema reais.

**✅ Normalização por Ciclos de Performance:**
    * A etapa mais complexa do pipeline: o script identifica automaticamente "eventos de reset" e usa esses pontos para segmentar a série temporal em "ciclos". Dentro de cada ciclo, ele reconstrói uma rampa linear, do início do ciclo até seu pico, criando um modelo idealizado e limpo da tendência.

---

### 🔬 Validação Visual do Pipeline

Os gráficos abaixo são uma saída direta do modo de depuração do script, demonstrando visualmente a eficácia dos algoritmos de tratamento de dados em diferentes fases.


Estes gráficos mostram o "antes" (linha tracejada) e o "depois" (linha sólida) dos dados em cada fase crítica, fornecendo uma prova tangível do valor do pipeline ao transformar dados brutos e ruidosos em uma série temporal limpa e acionável.

---

### 🚀 Resultados e Impacto

A implementação deste pipeline automatizado gerou um salto de qualidade e eficiência na análise dos dados.

| Área | Antes da Automação | Depois da Automação |
| :--- | :--- | :--- |
| **Qualidade dos Dados** | Dados brutos, com ruídos e lacunas | Série temporal limpa, corrigida e normalizada |
| **Análise** | Subjetiva e baseada em inspeção visual | Objetiva e baseada em algoritmos estatísticos |
| **Confiabilidade** | Baixa confiança no indicador de performance diário | Cálculo de um indicador diário robusto e defensável |
| **Tempo de Análise** | Horas de trabalho manual por análise | Segundos de execução do script |

O principal resultado foi a capacidade de gerar, de forma rápida e confiável, um indicadores, permitindo um melhor planejamento operacional.

---

### 💡 Habilidades e Competências Demonstradas

**Engenharia de Dados:** Concepção e implementação de um pipeline de ETL (Extração, Transformação e Carga) e processamento de dados.
**Análise Estatística de Dados:** Uso avançado das bibliotecas pandas, numpy e scipy para limpeza, transformação, interpolação e análise estatística.
**Desenvolvimento de Algoritmos:** Criação de heurísticas e algoritmos customizados para detecção de anomalias e normalização de séries temporais.
**Desenvolvimento em Python:** Estruturação de um script modular, parametrizado e com boas práticas para manutenção.
