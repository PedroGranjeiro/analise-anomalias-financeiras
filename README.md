# 🚨 Analisando Fraudes em Cartão de Crédito com Machine Learning

<div align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
</div>

## 📌 O que eu busquei resolver aqui
Decidi rodar esse projeto porque a detecção de fraudes é um dos desafios mais reais (e ingratos) da ciência de dados. O buraco é mais embaixo: não é só sobre rodar um modelo, é entender que, no mundo real, os dados quase nunca estão equilibrados.  

Neste dataset, temos milhares de transações normais e apenas um punhado de fraudes (0,17% do total). Se eu focasse em "Acurácia", o modelo seria um mentiroso: ele diria que acerta 99% das vezes simplesmente por ignorar as fraudes. Por isso, meu foco total aqui foi no Recall — que é o que realmente importa para rastrear os criminosos sem bloquear o cliente legítimo.  

## 🎯 O Objetivo
O foco principal aqui foi identificar padrões que diferenciam transações legítimas de tentativas de golpe. Mais do que um número alto de acertos gerais, o objetivo foi treinar o modelo para encontrar especificamente a "classe rara" (a fraude) no meio de milhões de operações comuns, equilibrando o custo de deixar uma fraude passar contra o incômodo de bloquear um cliente honesto.

## 🛠️ Tecnologias e Técnicas Aplicadas
Para chegar num resultado que fizesse sentido para um banco, segui esses passos:

**- Engenharia de Dados:** Como os valores das transações **(Amount)** variam demais, usei transformação logarítmica e StandardScaler para deixar tudo na mesma escala e não viciar o aprendizado.  

**- A "briga" dos modelos:** Testei desde a **Regressão Logística (meu ponto de partida)** até modelos mais robustos como **Random Forest e XGBoost**.  

**- O pulo do gato (Threshold):** Ajustei o limiar de decisão (threshold) para 0.3. Com isso, o modelo ficou mais rigoroso, aumentando consideravelmente a nossa taxa de detecção **(Recall)**.

## 📈 Resultados e Insights
**1. Métricas são relativas:** Em fraudes, **Precision e Recall** valem muito mais que Acurácia.  

**2. O equilíbrio é a chave:** Quando tentamos pegar mais fraudes (aumentar o Recall), acabamos incomodando alguns clientes legítimos (cai a Precision). O segredo é achar o ponto que o negócio suporta.  

**3. Por que o modelo decidiu isso?:** Usei o **SHAP** para entender quais variáveis (como V4 ou V14) mais pesaram na decisão, o que é fundamental para auditoria e confiança no sistema.  

## 🚀 Como executar este projeto
O projeto foi estruturado para ser leve, rodando tanto em ambientes locais quanto direto no navegador (WASM/JupyterLite).

1. Clone o repositório.
2. Instale as dependências: `pip install pandas numpy scikit-learn matplotlib`.  
3. Execute o Notebook na pasta /notebooks.
    
    **- Nota: O dataset original é pesado, por isso o arquivo .gitignore está configurado para não subir os CSVs.**

---
*Projeto desenvolvido para consolidar habilidades em Ciência de Dados, Machine Learning e resolução de problemas analíticos.*
