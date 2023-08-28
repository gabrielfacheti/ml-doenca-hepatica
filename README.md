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
Neste momento foi feita a separação entre variáveis categóricas e numéricas, para que ambos os tipos de variáveis pudessem ser avaliados separadamente. A exploração foi feita através de gráficos de distribuição de frequência e de estudos das relações entre as variáveis. Além disso, foi feita uma análise para identificação e remoção de dados duplicados e ausentes.

<h3>Data Preprocessing</h3>
During data preprocessing, the following steps were applied to prepare the dataset for clustering:
<ul>
	<li><b>Missing Value Imputation:</b> Missing values in the dataset were handled using <code>KNNImputer</code>, which utilizes the k-nearest neighbors algorithm to impute missing values based on the information from neighboring samples.</li>
	<li><b>Standardization:</b> Numerical features were standardized using <code>StandardScaler</code>, ensuring that all features were on a similar scale. Standardization is crucial for clustering algorithms to work effectively, as it prevents features with larger scales from dominating the clustering process.</li>
  <li><b>Dimensionality Reduction:</b> Principal Component Analysis (PCA) was utilized to reduce the dimensionality of the data to 2. This transformation allowed for visualization of the data in a 2D space, making it easier to interpret the results of clustering.</li>
</ul>

<h3>Clustering Models</h3>
Two clustering algorithms, <code>K-Means</code> and <code>DBSCAN</code>, were experimented with to group customers based on their behavioral variables. K-Means is a centroid-based clustering algorithm, while DBSCAN is a density-based clustering algorithm. Both approaches have different strengths and may yield different cluster structures.

<h3>Model Selection and Profiling</h3>
After evaluating the performance of both clustering models, the K-Means model was selected for customer segmentation. The K-Means model was used to create distinct clusters of customers based on their credit card usage behavior. Once the clusters were defined, profiling of each cluster was conducted to gain insights into the characteristics and preferences of customers within each group. This information can be used to tailor marketing strategies and improve customer engagement.

<h2>Results</h2>
<p>Below are the clusters obtained by each algorithm. Since K-Means had a better performance, it was chosen to do profiling.</p><br>

<b>K-Means</b>
![K-Means](kmeans_clusters.png)

<b>DBSCAN</b>
![K-Means](dbscan_clusters.png)

</body>
</html>
