---

# Análise de Classificação e Estabilidade de Modelo com Dataset Pima Diabetes

Este repositório contém uma análise aprofundada do dataset "Pima Indians Diabetes". O notebook foca não apenas na classificação, mas na investigação da **estabilidade e confiabilidade** das métricas de avaliação do modelo.

Esta é a **nova versão**, mais detalhada, de um projeto de pesquisa apresentado no congresso **UMC Summit**.

## 🏅 Versão do Congresso (Versão Antiga)

A versão original deste projeto, que foi formatada e apresentada no congresso (e está vinculada ao QR code da apresentação), está disponível no link abaixo.

➡️ **Repositório do Congresso (Versão Antiga): [https://github.com/ArthurS357/Collab](https://github.com/ArthurS357/Collab)**

O notebook *deste* repositório (`Pima_Indians_Diabetes.ipynb`) é a **versão nova e atualizada**, contendo uma análise mais aprofundada.

---

## 🚀 Objetivos do Estudo Atual

O notebook *deste* repositório (`Pima_Indians_Diabetes.ipynb`) foca em:

1.  **Limpeza e Preparação:** Realizar um pré-processamento robusto dos dados, tratando valores ausentes (representados por '0') e outliers (usando IQR).
2.  **Modelagem SVM:** Treinar e otimizar um modelo de Support Vector Machine (SVM) com kernel `rbf`.
3.  **Análise de Estabilidade:** Comparar a variância e a confiabilidade da acurácia usando `K-Fold` padrão contra o `Repeated Stratified K-Fold`.

## 🛠️ Tecnologias e Bibliotecas

* **Python**
* **Pandas** (para manipulação de dados)
* **Scikit-learn (sklearn)** (para pré-processamento, modelagem e avaliação)
* **Matplotlib / Seaborn** (para visualização de dados)

## 📈 Metodologia e Pipeline

O notebook segue um pipeline estruturado em 5 fases:

1.  **Carga e Configuração:** Carregamento do dataset e tratamento inicial de valores nulos (zeros).
2.  **Análise Exploratória (EDA):** Investigação da distribuição dos dados.
3.  **Pré-processamento:**
    * Tratamento de outliers com base no método IQR.
    * Padronização dos dados com `StandardScaler`.
4.  **Modelagem (SVM):**
    * Uso do `GridSearchCV` para encontrar os melhores hiperparâmetros (C=10, gamma=0.01).
    * Treinamento do modelo `SVC` final.
5.  **Avaliação de Estabilidade:**
    * Execução do `K-Fold` (10 splits).
    * Execução do `Repeated Stratified K-Fold` (10 splits, 3 repetições).

## 📊 Resultados e Conclusão (Deste Notebook)

* **Desempenho do Modelo:** O modelo SVM otimizado alcançou uma acurácia de **81.17%** nos dados de teste.
* **Estabilidade da Validação:** A análise de validação cruzada demonstrou que o `Repeated Stratified K-Fold` é uma métrica mais estável:
    * **K-Fold (10 splits):** Acurácia Média de 79.94% (std: 0.05).
    * **Repeated K-Fold (10 splits, 3 repeats):** Acurácia Média de 80.09% (std: 0.04).

A conclusão é que, embora as médias sejam similares, o **`Repeated Stratified K-Fold`** oferece uma estimativa de desempenho mais confiável e com menor variância (desvio padrão menor), sendo preferível para avaliar a real capacidade de generalização do modelo.
