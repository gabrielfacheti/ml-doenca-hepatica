<!DOCTYPE html>
<html>
		
<body>

<h1>Machine Learning: Previsão de doença hepática</h1>
Este notebook foi desenvolvido como parte da especialização em Ciência de Dados que eu estou cursando na Data Science Academy.<br>
O objetivo é prever se um paciente terá ou não uma doença hepática com base em dados de exames médicos.<br>

<h2>Dataset</h2>
O dataset é composto por 583 linhas e 11 colunas, com informações médicas dos pacientes.

<h2>Metodologia</h2>

<h3>Exploratory Data Analysis</h3>
Aqui foi feita a separação entre variáveis categóricas e numéricas, para que ambos os tipos de variáveis pudessem ser avaliados separadamente. A exploração foi feita através de histogramas na análise univariada e de gráficos de dispersão na análise bivariada. Além disso, foi feita uma análise para identificação e remoção de dados duplicados e ausentes. Outliers foram removidos e os valores ausentes foram imputados com a função <code>KNNImputer</code>.

<h3>Pré-Processamento de dados</h3>
Durante o pré-processamento, uma das variáveis foi removida por apresentar elevada correlação com outra variável preditora, o que pode indicar colinearidade – ocorre quando duas variáveis carregam basicamente a mesma informação, o que pode tornar o modelo tendencioso. Ademais, os dados foram divididos em dados de treino e teste, usando a proporção de 75/25, respectivamente.
<ul>
	<li><b>Balanceamento de classes:</b> O subset de treino teve de ser balanceado por conta da grande diferença entre as classes positivas e negativas. Tal balanceamento é importante para que o modelo não favoreça uma das classes durante o treinamento. Para isso, usou-se a função <code>SMOTE</code> da biblioteca <b>imblearn</b>. </li>
	<li><b>Padronização:</b> As variáveis numéricas foram padronizadas usando a função <code>StandardScaler</code>, para garantir que todas tivessem uma distribuição parecida (próxima de uma normal).</li>
</ul>

<h3>Seleção dos modelos</h3>
Cinco algoritmos diferentes – Regressão Logística, Decision Tree, Random Forest, K-Nearest Neighbors e Support Vector Machines (SVM) – foram testados e avaliados em uma validação cruzada (com <code>StratifiedKFold</code>), usando métricas como acurácia, ROC AUC Score e F1 Score. Os resultados foram guardados em um DataFrame para posterior comparação.<br>
O modelo com os melhores resultados foi o Random Forest. Com isso, foi feita a tunagem dos principais hiperparâmetros, a fim de garantir o melhor desempenho possível em teste.

<h2>Resultados</h2>
Por fim, utilizando o modelo já treinado e com os melhores hiperparâmetros, foi feita uma previsão utilizando dados hipotéticos, que passaram pelos mesmos processamentos que os dados de treino e teste. Nesta análise foi previsto que o paciente deve apresentar doença hepática.<br>

</body>
</html>
