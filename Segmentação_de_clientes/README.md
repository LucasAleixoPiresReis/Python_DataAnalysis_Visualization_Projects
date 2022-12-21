# Análise exploratória e clusterização dos frequentadores de um shopping

## Etapa 1 - Entendendo o Problema ##
 
- **Contexto:** Você foi contratato pela Multiplan (Administradora de Shoppings Centers) como Analista de Dados. A equipe de marketing precisa que você identifique as principais caracterísitcas do público de frequentadores do shopping e os grupos de compras mais importantes com base na renda, na idade e na pontuação de compras no shopping.

- **Problema:** Entender os clientes-alvo de um shopping para que a equipe de marketing planeje a estratégia da próxima campanha de marketing. 

- **Solução:** Dividisão do público do shopping em grupos acessíveis. Criação de subconjuntos do mercado com base em critérios demográficos e comportamentais para entender melhor o público-alvo das atividades de marketing


- **Quais perguntas podemos responder?**
    - [ ]  Quantos visitantes existem no conjunto de dados disponilizado? 
    - [ ]  Desses visitantes quantos são do gênero masculino? E do feminino?
    - [ ]  Como a idade se distribui entre os visitantes?
    - [ ]  Como a renda se distribui entre os visitantes?
    - [ ]  Como o score se distribui entre os visitantes?
    - [ ]  Como as variáveis se relacionam entre si?
    - [ ]  Como a idade varia em relação ao gênero?
    - [ ]  Como a renda varia em relação ao gênero?
    - [ ]  Como a renda varia em relação à idade?


- **Ferramentas:**
  - Linguagem de Programação: Python
  - Ambiente: Google Colab
  - Bibliotecas: 
    - Análise de dados: Pandas 
    - Visualização de dados: Matplotlib e Seaborn
    - Machine Learning: Scikit-Learn

- **Código:**Código: [eda_clusterizacao_clientes_shopping.ipynb](https://github.com/LucasAleixoPiresReis/python-data-analysis-projects/blob/main/Segmenta%C3%A7%C3%A3o_de_clientes/eda_clusterizacao_clientes_shopping.ipynb) 


## Etapa 2 - Coletando os Dados


- Um profissional da área de dados realizou a extração dos dados diretamente do Banco e forneceu a você um dataset no formato csv. O dataset 200 linhas/observações e os seguintes atributos:
    - CustomerID - Identificação do Visitante
    - Genre - Gênero do Visitante
    - Age - Idade do Visitante
    - Annual Income (kR$) - Renda anual do visitante
    - Spending Score (1-100) - Score do Visitante
    
    Base de Dados: [clientes_shopping.csv](https://github.com/LucasAleixoPiresReis/python-data-analysis-projects/blob/main/Segmenta%C3%A7%C3%A3o_de_clientes/clientes_shopping.csv)
    

## Etapa 3 - Limpeza dos Dados

Nesta etapa, realizou-se a preparação dos dados para a etapa de análise exploratória.
- Conferindo os tipos de dados presentes no dataset:

![Screenshot from 2022-12-20 18-47-55](https://user-images.githubusercontent.com/117869039/208773936-00288952-1ba4-4c74-9893-097ff88f3438.png)  
O dataset possui variáveis do tipo Integer e Object (String). Não há necessidade de alteração dos tipos de variáveis, uma vez que os formatos atendem perfeitamente os tipos de dados presentes. Idade, Renda e Score são números inteiros e Gênero é uma string.

- Alterações:
  - A coluna CustomerID não é importante para a análise futura e por isso foi removida.
  - Tradução/mudança dos nomes das colunas: Genre -> Genero; Age -> Idade; Annuak Income (k$) -> Renda_Anual(kR$); Spending Score (1-100) -> Score(1-100)
  - Tradução das categorias da coluna Genero: Male -> Masculino; Female -> Feminino
    - Resultado:
    
    ![Screenshot from 2022-12-20 19-06-36](https://user-images.githubusercontent.com/117869039/208776602-cada9dcd-6db5-465d-b5b0-79a4ac978105.png)
   
- Não foram encontrados valores nulos, NaN e duplicatas.


## Etapa 4 - Análise Exploratória dos Dados

- Descrição estatística:

![Screenshot from 2022-12-20 19-15-52](https://user-images.githubusercontent.com/117869039/208777347-55b5335a-44cc-4585-ac51-bb9112e08bce.png)

**Análise univariável:**
- Perguntas:
    - [x]  **Quantos visitantes existem no conjunto de dados disponilizado?** 200 visitantes
    - [x]  **Desses visitantes, quantos são masculino e feminino?**
      - Feminino: 112
      - Masculino: 88

   ![Screenshot from 2022-12-20 19-29-23](https://user-images.githubusercontent.com/117869039/208779094-0a5bf231-583f-4839-b8d8-2ba6cb0d95a5.png)

    - [x]  **Como a idade se distribui entre os visitantes?**
    
    ![Screenshot from 2022-12-20 19-36-59](https://user-images.githubusercontent.com/117869039/208780054-a95cf61a-03a8-400f-9b83-1eb2f62c1919.png)
    ![Screenshot from 2022-12-20 19-36-04](https://user-images.githubusercontent.com/117869039/208780091-cb9a74be-470d-426d-9d59-8e83ecef914b.png)
 
    - [x]  **Como a renda se distribui entre os visitantes?**
    
    ![Screenshot from 2022-12-20 19-41-34](https://user-images.githubusercontent.com/117869039/208780597-cf825840-9dd8-466f-8b67-a4a29189077d.png)
    ![Screenshot from 2022-12-20 19-42-11](https://user-images.githubusercontent.com/117869039/208780705-5c6555d6-e187-47c2-95c1-396b97cc072d.png)
    
    Observa-se a presença de um outlier na amostra: o valor máximo de R$137.000
    
    - [x]  **Como o score se distribui entre os visitantes?**
    
    ![Screenshot from 2022-12-20 19-53-19](https://user-images.githubusercontent.com/117869039/208781902-af651ac7-89c2-4246-b519-9ef9727837c5.png)
    ![Screenshot from 2022-12-20 19-54-04](https://user-images.githubusercontent.com/117869039/208781974-6cc7be0c-7b4c-41eb-8568-74bb32cca49e.png)
    
    O Score tem uma distribuição próxima da normal. Os valores de média e mediana são bem próximos.
    
    
**Análise bivariável:**
 - Perguntas:
    - [x]  Como a idade varia em relação ao gênero?
    
    ![Screenshot from 2022-12-20 19-57-10](https://user-images.githubusercontent.com/117869039/208782367-faa769d9-f522-43b7-bb7a-bbe7b57d1eee.png)
    
    - [x]  Como a renda varia em relação ao gênero?
    
    ![Screenshot from 2022-12-20 19-59-09](https://user-images.githubusercontent.com/117869039/208782581-53fd6d25-6dd5-4d16-be13-22e243256335.png)
    ![Screenshot from 2022-12-20 19-59-53](https://user-images.githubusercontent.com/117869039/208782650-b9e609af-db25-4674-a71a-bf50517264d5.png)
    
    - [x]  Como o Score varia em relação ao gênero?
    
    ![Screenshot from 2022-12-20 20-02-39](https://user-images.githubusercontent.com/117869039/208782951-53806546-9a9e-4134-a2b2-e65b4f931efb.png)
    ![Screenshot from 2022-12-20 20-03-50](https://user-images.githubusercontent.com/117869039/208783072-08792f96-737c-4ecb-8487-5cc9eab2e2ff.png)
    
   **Importante destacar que, em geral, as mulheres apresentam uma maior frequencia do que os homens na distribuição de cada um dos atributos. A média da renda anual do genero masculino está maior que a média feminina devido ao outlier**
    
     - [x]  Como as variáveis contínuas se relacionam entre si?
    ![Screenshot from 2022-12-20 20-15-05](https://user-images.githubusercontent.com/117869039/208784245-1983b52c-5d6e-4914-81ca-34222dc4709e.png)
    ![Screenshot from 2022-12-20 20-15-43](https://user-images.githubusercontent.com/117869039/208784316-c77774ba-b0c5-47f6-b022-8392f251aada.png)
    
    **Observa-se que não há uma correlação forte entre os atributos.**

    
## Etapa 5 - Agrupamento

Deve-se realizar o agrupamento (com um número ideal de grupos) da amostra de frequentadores do shopping grupos de compras mais importantes com base na renda, na idade e na pontuação de compras no shopping.

- **Técnica utilizada:** Será utilizado a clusterização, técnica de machine learning não-supervisionado que tem como objetivo agrupar os dados em determinados conjuntos distintos entre si.
- **Algoritimo utilizado:** K-Means
   - Seleciona k pontos (número de centro de clusters) como centróides (posição média) iniciais
   - Calcula a distância de todos os pontos aos centróides iniciais
   - Forma k grupos associando os pontos aos centróides mais próximos
   - Recalcula o centróide de cada grupo obtido
   - Repete o processo até que os centróides não mudem mais. 
- **Método para definição nº ideal de clusters:** Elbow method (método do cotovelo)
   - Usa a distância média dos pontos de um cluster até o seu centróide (WCSS - within cluster sum of squares) para diferentes valores de k.
   - o WCSS deve ser entendido como a métrica de compactação de determinado cluster. Quanto menor o seu valor, mais compacto é o agrupamento.
   - Para determinar o número ideal de cluster, devemos escolher o ponto em que não há mais grandes alterações no valor de WCSS com o aumento do número de clusters.

#### Clusterização com base na Idade, Renda e Score

- Calculando os valores de WCSS para cada número de clusters (1 à 10) formados pelo algoritmo K-Means:
![Screenshot from 2022-12-20 22-04-57](https://user-images.githubusercontent.com/117869039/208796383-425d0d40-5940-471d-a352-3605c599b66c.png)

- Visualização WCSS x número de Clusters:

![Screenshot from 2022-12-20 22-09-39](https://user-images.githubusercontent.com/117869039/208796879-fc89cd6e-5e85-4f9d-8c78-0ee173a841f8.png)

É possível perceber que a última mudança significativa de inclinação no gráfico está localizado no x=4, ou seja, o número ideal de agrupamentos para esse dataset é 4. A partir de 4, não há mais alterações significativas na medida de compactação dos clusters, sendo assim desnecessário utilizar um número maaior de agrupamentos. 

- Visualização:

![Screenshot from 2022-12-20 22-22-38](https://user-images.githubusercontent.com/117869039/208798342-5751b0c7-adec-426f-a1a1-1c66b4838613.png)

Cluster 0: Azul

Cluster 1: Roxo

Cluster 2: Laranja

Cluster 3: Amarelo

## Etapa 6 - Apresentação

- Informações sobre cada agrupamento de clientes:
  - Quantidade de clientes em cada cluster:
    - Cluster 0: 28
    - Cluster 1: 38
    - Cluster 2: 39
    - Cluster 3: 95
  - Porcentagem de homens e mulheres em cada agrupamento:
  
   ![Screenshot from 2022-12-20 22-30-33](https://user-images.githubusercontent.com/117869039/208799263-e230c34f-5c46-4188-a66a-8ed77eac8399.png)
  
  - Descrição estatística de cada agrupamento:
    - Cluster 0:
    
    ![Screenshot from 2022-12-20 22-56-19](https://user-images.githubusercontent.com/117869039/208802312-0ac020b9-b0a5-4e7e-b8e4-8eb941da8694.png)
    
    - Cluster 1:
    
    ![Screenshot from 2022-12-20 22-57-11](https://user-images.githubusercontent.com/117869039/208802420-c2f54f05-e022-4289-941f-945c1fb36638.png)
    
    - Cluster 2:
    
    ![Screenshot from 2022-12-20 22-57-43](https://user-images.githubusercontent.com/117869039/208802498-2dcb630c-e308-4153-b0b7-e0716637bc39.png)
    
    - Cluster 3:
    
    ![Screenshot from 2022-12-20 22-58-16](https://user-images.githubusercontent.com/117869039/208802585-affbec7a-42ab-4534-8739-f901c82d0c74.png)
    
