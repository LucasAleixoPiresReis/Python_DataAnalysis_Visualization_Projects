# Análise exploratória e clusterização dos frequentadores de um shopping

## Etapa 1 - Entendendo o Problema ##
 
- **Contexto:** Você foi contratato pela Multiplan (Administradora de Shoppings Centers) como Analista de Dados. A equipe de marketing precisa que você identifique as principais caracterísitcas do público de frequentadores do shopping e os grupos de compras mais importantes com base na renda, na idade e na pontuação de compras no shopping.

- **Problema:** Entender os clientes-alvo de um shopping para que a equipe de marketing planeje a estratégia da próxima campanha de marketing. 

- **Solução:** Dividisão do público do shopping em grupos acessíveis. Criação de subconjuntos do mercado com base em critérios demográficos e comportamentais para entender melhor o público-alvo das atividades de marketing


- **Quais perguntas podemos responder?**
    - [ ]  Quantos visitantes existem no conjunto de dados disponilizado?
    - [ ]  Desses visitantes quantos são do gênero masculino masculino? E do feminino?
    - [ ]  Como a idade se distribui entre os visitantes?
    - [ ]  Como a renda se distribui entre os visitantes?
    - [ ]  Como o score se distribui entre os visitantes?
    - [ ]  Como as variáveis se relacionam entre si?
    - [ ]  Como a idade varia em relação ao gênero?
    - [ ]  Como a renda varia em relação ao gênero?
    - [ ]  Como a renda varia em relação à idade?


- **Ferramentas:**
  - Linguagem de Programação: Python
  - Bibliotecas: 
    - Análise de dados: Pandas 
    - Visualização de dados: Matplotlib e Seaborn
    - Machine Learning: Scikit-Learn


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
  - A coluna CustomerID não é imnportante para a análise futura e por isso foi removida.
  - Tradução/mudança dos nomes das colunas: Genre -> Genero; Age -> Idade; Annuak Income (k$) -> Renda_Anual(kR$); Spending Score (1-100) -> Score(1-100)
  - Tradução das categorias da coluna Genero: Male -> Masculino; Female -> Feminino
    - Resultado:
    
    ![Screenshot from 2022-12-20 19-06-36](https://user-images.githubusercontent.com/117869039/208776602-cada9dcd-6db5-465d-b5b0-79a4ac978105.png)
   
- Não foram encontrados valores nulos, NaN e duplicatas.


## Etapa 4 - Análise Exploratória dos Dados

- Descrição estatística:

![Screenshot from 2022-12-20 19-15-52](https://user-images.githubusercontent.com/117869039/208777347-55b5335a-44cc-4585-ac51-bb9112e08bce.png)


- Perguntas:
    - [x]  Quantos visitantes existem no conjunto de dados disponilizado?
    - [x]  Desses visitantes quantos são masculino e feminino?
    - [x]  Como a idade se distribui entre os visitantes?
    - [x]  Como a renda se distribui entre os visitantes?
    - [x]  Como o score se distribui entre os visitantes?
    - [x]  Como as variáveis se relacionam entre si?
    - [x]  Como a idade varia em relação ao gênero?
    - [x]  Como a renda varia em relação ao gênero?
    - [x]  Como a renda varia em relação ao idade?



    
## Etapa 5 - Clustering

- Técnica de aprendizado não-supervisionado
- Algoritimo utilizado: K-Means

## Etapa 6 - Apresentação

