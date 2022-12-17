# Análise exploratória e clusterização dos frequentadores de um shopping

## Etapa 1 - Entendendo o Problema ##
 
- **Contexto:** Você foi contratato pela Multiplan (Administradora de Shoppings Centers) como Analista de Dados. A equipe de marketing precisa que você identifique as principais caracterísitcas do público de frequentadores do shopping e os grupos de compras mais importantes com base na renda, na idade e na pontuação de compras no shopping.

- **Problema:** Entender os clientes-alvo de um shopping para que a equipe de marketing planeje a estratégia da próxima campanha de marketing. 

- **Solução:** Dividisão do público do shopping em grupos acessíveis. Criação de subconjuntos do mercado com base em critérios demográficos e comportamentais para entender melhor o público-alvo das atividades de marketing


- **Quais perguntas podemos responder?**
    - [ ]  Quantos visitantes existem no conjunto de dados disponilizado?
    - [ ]  Desses visitantes quantos são masculino e feminino?
    - [ ]  Como a idade se distribui entre os visitantes?
    - [ ]  Como a renda se distribui entre os visitantes?
    - [ ]  Como o score se distribui entre os visitantes?
    - [ ]  Como as variáveis se relacionam entre si?
    - [ ]  Como a idade varia em relação ao gênero?
    - [ ]  Como a renda varia em relação ao gênero?
    - [ ]  Como a renda varia em relação ao idade?


- **Ferramentas:**
  - Linguagem de Programação: Python
  - Bibliotecas: 
    - Análise de dados: Pandas 
    - Visualização de dados: Matplotlib e Seaborn
    - Machine Learning: Scikit-Learn


## Etapa 2 - Coletando os Dados


- Um profissional da área de dados realizou a extração dos dados diretamente do Banco e forneceu a você um dataset no formato csv contendo variáveis importantes e que podem ser úteis para responder essas perguntas.
    - CustomerID - Identificação do Visitante
    - Genre - Gênero do Visitante
    - Age - Idade do Visitante
    - Annual Income (kR$) - Renda anual do visitante
    - Spending Score (1-100) - Score do Visitante
    
    Base de Dados: [clientes_shopping.csv](https://github.com/LucasAleixoPiresReis/python-data-analysis-projects/blob/main/Segmenta%C3%A7%C3%A3o_de_clientes/clientes_shopping.csv)
    

## Etapa 3 - LImpeza dos Dados



## Etapa 4 - Análise Exploratória dos Dados

- Na maioria dos casos a gente entra nessa etapa sem saber o que tem nas mãos.
    - Seu trabalho é mergulhar nos dados que coletou visando extrair informação
        - Dados → Informação → Insights
    - Dar sentido aos dados.
- Foco nas perguntas que preciso responder:
    - [x]  Quantos visitantes existem no conjunto de dados disponilizado?
    - [x]  Desses visitantes quantos são masculino e feminino?
    - [x]  Como a idade se distribui entre os visitantes?
    - [x]  Como a renda se distribui entre os visitantes?
    - [x]  Como o score se distribui entre os visitantes?
    - [x]  Como as variáveis se relacionam entre si?
    - [x]  Como a idade varia em relação ao gênero?
    - [ ]  Como a renda varia em relação ao gênero?
    - [ ]  Como a renda varia em relação ao idade?

- **Análise univariável**


    
## Etapa 5 - Clustering

- Técnica de aprendizado não-supervisionado
- Algoritimo utilizado: K-Means

## Etapa 6 - Apresentação

