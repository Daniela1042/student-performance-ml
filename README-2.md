# Previsão do Desempenho de Estudantes

Projeto desenvolvido no âmbito do Mestrado em Sistemas Integrados em Business Intelligence (ISCTE-IUL), em Python e Jupyter Notebook.

## Objetivo

Analisar os fatores associados ao desempenho académico de estudantes e testar se o **tempo de estudo semanal** e as **faltas** permitem prever a classificação final (GPA, convertido em notas de A a F).

## Dados

- Dataset de desempenho de estudantes com **2.392 registos** e **14 variáveis**, incluindo idade, género, tempo de estudo semanal, faltas, apoio parental, tutoria, atividades extracurriculares e GPA.
- Os dados **não estão incluídos neste repositório**.

## Metodologia

1. **Exploração inicial:** estrutura do dataset, valores únicos por variável e estatística descritiva.
2. **Limpeza dos dados:**
   - Valores em falta em `ParentalEducation` e `ParentalSupport` preenchidos com a moda.
   - Deteção e remoção de outliers pelo método IQR (de 2.392 para 1.625 registos).
   - Verificação de duplicados e normalização de texto (remoção de espaços e minúsculas).
3. **Transformação:** conversão do GPA em notas de A a F (`GPA_letter`).
4. **Análise exploratória:** histogramas, *pairplot*, *scatterplots* e gráficos de densidade da relação entre tempo de estudo, faltas e nota.
5. **Modelação:** Árvore de Decisão (profundidade 3) com divisão 80/20 entre treino e teste, usando `StudyTimeWeekly` e `Absences` como variáveis explicativas.

## Resultados

- A Árvore de Decisão atingiu uma **accuracy de cerca de 68%** no conjunto de teste (325 registos).
- O desempenho foi avaliado com matriz de confusão, e a árvore de decisão foi visualizada graficamente.

## Limitações

- O modelo usa apenas duas variáveis explicativas e só foi testado um algoritmo.
- A remoção de outliers eliminou cerca de um terço dos registos, o que pode ter retirado casos legítimos.

## Ferramentas

- **Python**, **Jupyter Notebook**
- **Pandas**, **NumPy**
- **Scikit-learn**
- **Matplotlib**, **Seaborn**

## Conteúdo do repositório

- O notebook Jupyter (`.ipynb`) com todo o código, visualizações e resultados.
