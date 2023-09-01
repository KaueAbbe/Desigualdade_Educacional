<h1 align="center"> Tratamento e Exploração dos dados😊 </h1>

## **Resumo do Notebook:**

Realizei o *tratamento e a exploração dos dados*. Os dados obtidos pelo Kaggle foram analisados com objetivo de tratamento, investigando quais os tipos de dados eram apresentados. Investiguei *quais eram os dados
categóricos e quais eram os contínuos*, além de, usando o dicionário de dados entender qual o *significo para cada variável*. Renomeei as colunas, diminuindo o título com intuito de facilitar os códigos e tradução 
de palavras da língua inglesa. A mesma tradução foi feita para dados de grupo de desenvolvimento humano. Após *analisar dados faltantes*, pesquisar se a falta atrapalharia as análises,  decidi por *alterar 
dados faltantes por valores médios, enquanto outro eu retirei*. Combinei minha base de dados com outra base, adicionando variáveis de expectativa de vida, expectativa de anos de educação e anos estudados para cada país.
Para finalizar explorei a distribuição das variáveis realizando agrupamentos por regiões do mundo e por grupo de desenvolvimento humano. 


## **Detalhando Metodologia de Tratamento**

<h3 align ="left">1 Compreensão dos Dados</h2>

Utilizei o *comando info() do pandas* para verificar quais os tipos de dados no dataframe, e com conjunto com a leitura do dicionário de dados e da própria base de dados descobri o que as variáveis representavam e como
estavam disposta, compreendendo a qual categoria, discretos ou contínuos, os dados se encaixavam. Além disso, descobri quais variáveis continham valores faltantes. 

<h3 align ="left">2 Tratando os Dados</h2>

Com comando *rename()* e *função loop for* renomeei os nomes das variáveis. O objetivo da renomeação foi facilitar nos códigos e tradução nome do inglês para o português. 

Para *tratar os valores faltantes* primeiro *investiguei onde estavam faltando, por qual motivo poderiam estar faltando e qual o problema me acarretaria retirar eles*. Os dados faltantes das taxa de desigualdade 
acarretariam em menos países para avaliar, por consequência as *análises estatísticas* estariam comprometidas e faltando países. *Substitui*, então, os dados faltantes das variáveis
taxa de desigualdade apenas para os valores médios dos anos seguintes. *Esse feito significa que o país sem informação não apresentou alteração na taxa desigualdade*. Os países que *não apresentaram nenhum valor de taxa
foram excluídos*. 

Valores faltantes de regiões foram deixas na base de dados, pois não foi encontrada forma de completar com outra base de dados.

<h3 align ="left">3 Adição de Dados</h2>

Com o objetivo de adicionar informações aos dados, pesquisei sobre a UNPD que aparece como variável. no [site da UNDP](https://hdr.undp.org/inequality-adjusted-human-development-index#/indicies/IHDI)
realizei o download de uma nova base de dados, e adicionei três variáveis no dataframe tratado: *expectativa de vida, expectativa de anos de escola e realidade de anos de escola*.

A nova base de dados estava em formato excel, com bastantes valores vazios, título de cabeçalho, subtítulo e separação de categorias no meio da tabela. Para realizar a leitura dessa base de dados utilizei os *parâmetros
dentro do read_excel()* do pandas. Os parâmetros usados foram: *header, usecol, names, skiprows*.

<h3 align ="left">4 Salvar os Dados</h2>

Usando *comando to_csv()* do pandas salvei meus dados no meu drive para futuras análises exploratórios, descritivas e estatística, além de realizar um modelo de classificação de grupo de desenvolvimento humano. 

## **Detalhando Metodologia de Exploração**

<h3 align ="left">1 Compreensão dos Dados</h2>

Usando o *boxplot do pandas* verifiquei o tipo de distribuição das taxas de desigualdade, descobrindo não ser uma distribuição normal, e sim uma distribuição com cauda enviesada para a direita. 
Do boxplot também percebi uma tendência de diminuir os valores médios das taxas de desigualdade mundiais ao passar dos anos.

Com o *Boxplot do Seaborn* verifiquei a distribuição da taxa de desigualdade de 2021 agrupando por grupos de desenvolvimento humano e por regiões da UNDP. Também não são distribuições normais.
Em adição, analisei a distribuição da expecativa de vida, expecativa de anos de estudo e realidade de anos de estudos agrupando por grupos de desenvolvimento humano. Esta analise mostrou diferenças significativas entre
os grupos. Por fim, realizei o um *mapa de cor da correlação* dos dados, mostrando que os dados apresentando altas correlações, tanto negativas quanto positivas. 


<h3 align ="left"> Origem dos Dados:</h2>

1. [Inequality in Education Around the Workd](https://www.kaggle.com/datasets/iamsouravbanerjee/inequality-in-education-around-the-world)
2. [Humam Development Reports](https://hdr.undp.org/data-center/documentation-and-downloads)



<h3 align ="left"> Quais bibliotecas usei</h2>
1. Para ler dados: Pandas 🐼
2. Para Gráficos: Pandas, Seaborn e Matplolib

