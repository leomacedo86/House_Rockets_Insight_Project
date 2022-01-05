# O Problema
A House Rocket é uma plataforma digital que tem como modelo de negócio, a compra e a venda de imóveis usando tecnologia.

Como Data Scientist, vou análisar o Dataset para encontrar as melhores oportunidades de negócio no mercado de imóveis. O CEO da House Rocket gostaria de maximizar a receita da empresa encontrando boas oportunidades de negócio.

Sua principal estratégia é comprar boas casas em ótimas localizações com preços baixos e depois revendê-las posteriormente à preços mais altos. Quanto maior a diferença entre a compra e a venda, maior o lucro da empresa e portanto maior sua receita.

Entretanto, as casas possuem muitos atributos que as tornam mais ou menos atrativas aos compradores e vendedores e a localização e o período do ano também podem influenciar os preços.

Portanto, como Data Scientist irei responder as seguinte perguntas:

* 1 - Quais casas o CEO da House Rocket deveria comprar e por qual preço de compra? * 

* 2 - Uma vez a casa em posse da empresa, qual o melhor momento para vendê-las e qual seria o preço da venda? *

* 3 - A House Rocket deveria fazer uma reforma para aumentar o preço da venda? Quais seriam as sugestões de mudanças? Qual o incremento no preço dado por cada opção de reforma? *

## Os Dados do Desafio
O conjunto de dados que representam o contexto está disponível na plataforma do Kaggle. https://www.kaggle.com/harlfoxem/housesalesprediction

Esse conjunto de dados contém casas vendidas entre Maio de 2014 e Maio de 2015. Você usará esses dados para desenvolver sua solução.

# Desenvolvimento e Entrega
O Case foi desenvolvido em um Jupyter Notebook, em linguagem Python.

Foi utilizado a metodologia Crisp-DM, com o primeiro ciclo priorizado para entender e aprender com os dados, á partir dá análise realizada apresentar os insights para a área desejada.

A entrega foi realizada em um dashboard com as principais insights dos dados e com as informações dos imóveis indicados para a compra no [Tableau]

Posteriormente, ficando aberto para um segundo ciclo e suas melhorias.

# Exploração dos dados

  * Descrição dos atributos do Dataset original

Atributos   | Descrição
------------|------------------
id	        |Identificação do imóvel
date	    |Data da venda do imóvel
price	    |Preço que o imóvel está sendo vendido pelo proprietário
bedrooms	|Número de quartos
bathrooms	|Número de banheiros (0.5 = banheiro em um quarto, mas sem chuveiro)
sqft_living	|Medida (em pés quadrado) do espaço interior dos imóveis
sqft_lot	|Medida (em pés quadrados) quadrada do espaço terrestre
floors	    |Número de andares do imóvel
waterfront	|Variável que indica a presença ou não de vista para água (0 = não e 1 = sim)
view	    |Um índice de 0 a 4 que indica a qualidade da vista da propriedade. Varia de 0 a 4, onde: 0 = baixa 4 = alta
condition	|1 = Fraco - 2 = Razoável- 3 = Média - 4 = Bom -  5 = Muito Bom - 
grade      |1-3 = Fica aquém dos padrões mínimos de construção - 4 = Construção geralmente mais antiga e de baixa qualidade. - 5 = Baixo custo de construção e mão de obra. - 6 =  A nota mais baixa atualmente atende ao código de construção.- 7 =  Grau médio de construção e design. - 8 = Um pouco acima da média em construção e design.- 9 = Melhor projeto arquitetônico com design e qualidade extra interior e exterior. - 10 = Casas com essa qualidade geralmente têm recursos de alta qualidade. - 11 Design personalizado - 13 Geralmente projetado e construído sob medida. 
sqft_above	|A metragem quadrada do espaço habitacional interior acima do nivel do solo
sqft_basement	|A metragem quadrada do espaço habitacional interior abaixo do nível do solo
yr_built	|Ano de construção de cada imóvel
yr_renovated	|Ano de reforma de cada imóvel
zipcode	    |CEP do imóvel
lat	        |Latitude
long	    |Longitude
sqft_livining15	|Medida (em pés quadrado) do espaço interno de habitação para os 15 vizinhos mais próximo
sqft_lot15	|Medida (em pés quadrado) dos lotes de terra dos 15 vizinhos mais próximo

  * Descrição das features criadas

