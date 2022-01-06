# Projeto de Insights: House Rocket
<img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/capa.jpg" alt="image">

# 1.O Problema
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

# 2.Desenvolvimento e Entrega
O Case foi desenvolvido em um Jupyter Notebook, em linguagem Python.

Foi utilizado a metodologia Crisp-DM, com o primeiro ciclo priorizado para entender e aprender com os dados, á partir dá análise realizada apresentar os insights para a área desejada.

A entrega foi realizada em um dashboard no Tableau com as principais insights dos dados e com as informações dos imóveis indicados para a compra para que a diretoria possa acompanhar os imóveis.

Posteriormente, ficando aberto para um segundo ciclo e suas melhorias.

# 3.Exploração dos dados

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
  
Atributos   | Descrição
------------|------------------
basement        |Se a casa possui porão
renovated	    |Se a casa foi reformada
sale_day	    |dia da venda
sale_month   |Mês da venda
sale_year    |Ano da Venda
sale_week_of_year  |Número da semana do ano, em que o imóvel foi vendido
sale_day_name      |Dia da semana em que o imóvel foi vendido
holyday_sale       |Se a venda ocorreu em algum feriado
holyday_week       | Se foi vendido em uma semana de feriado
season             |Estação do ano em que o imóvel foi vendido
price_median       |Mediana do preço conforme o CEP
Action             |Indicação se o imóvel deve ser comprado
sales_suggestion   |Sugestão de preço de venda
best_season_for_sale |Melhor temporada para venda
group              |Grupo em que o imóvel pertencer, conforme as suas condições
renovation_price   |Valor final de venda após reforma ou não do imóvel
suggested_reform   |Indicação se o imóvel deve ser reformado
expected_profit    |Lucro esperado do imóvel

## Premissas do negócio

* Os dados de venda são dos anos de 2014 e 2015.
* Imóveis com dados desproporcionais foram excluídos, entendendo que tiveram inputs manuais e com erros.
* Temos 21.436 imóveis disponíveis para venda.
* Para compra do imóvel, foi definido a seguite condição:
     *Imóveis que estejam com preço de venda á partir de 15% abaixo da mediana de cada zipcode e com condições acima de 1.
     *Foram encontrados 6.752 imóveis indicados para compra.

## Hipóteses do negócio

- **1.** O ZipCode pode influenciar no valor do imóvel ?
- **2.** Casas com vista privilegiada são 40% mais caras que na média ?
- **3.** Casas com vista para a água são 50% mais caras que na média ?
- **4.** O Preço dos imóveis ficaram mais caros no decorrer dos anos ?
- **5.** O dia da semana tende a influenciar na venda dos imóveis ?
- **6.** A estãção do ano tende a influenciar na venda do imóvel ?
- **7.** Imóveis vendidos no inverno são 30% mais baratos do que no verão, em média ?
- **8.** Imóveis vendidos em semana de feriados são mais caros que a média, se sim quantos % são mais caros ?
- **9.** Semana de feriado pode influenciar na venda de imóveis ?
- **10.** Imóves com mais andares são 30% mais caros ?
- **11.** Imóveis com porão são 30% mais caros ?
- **12.** Imóveis com data de contrução menos que 1970 são 30% mais baratos ?
- **13.** Imóveis com data de reforma maior que 1980 são 50% mais caros ?
- **14.** Imóveis com maior número de quarto são 40% mais caros ?
- **15.** Imóveis com maior número de banheiros são 40% mais caros ?
- **16.** A condição pode influenciar na venda de imóvel ?
- **17.** Casas em condições muito boas são 60% mais caras, na média ?
- **18.** Casa em condições fracas são 60% mais baratas, na média ?
- **19.** Casas que foram reformadas tendem a terem as melhores condições ?
- **20.** Casas com menor grau de construção, são 50% mais baratas, na média ?

### Principais Insights

<img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/H1.png" alt="image" width="2000">

<img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/H5.png" alt="image" width="2000">

<img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/H14.png" alt="image" width="2000">

<img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/H15.png" alt="image" width="2000">

<img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/H16.png" alt="image" width="2000">

<img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/H17.png" alt="image" width="2000">

# 4.Questões do Negócio

**1 - Quais casas o CEO da House Rocket deveria comprar e por qual preço de compra?**

   * Os imóveis foram agrupado pelo CEP, e criado uma variável com mediana dos preços de venda de cada CEP.
   
   * Conforme em análise em hipóteses anteriores, foi verificado que a maioria dos imóveis que foram reformados estavam com nota acima de 3 nas condições, pensando em um possível custo de reforma nesses imóveis para melhorar suas condições e obtermos um lucro, foi direcionado para uma avaliação de compra das casas, os imóveis que estejam 15% abaixo da mediana de cada zipcode e com condições acima de 2.
    
   * Foi criado uma variável indicando se o imóveis deveria sr comprado conforme premissas assumidas nas análises.

**2 - Uma vez a casa em posse da empresa, qual o melhor momento para vendê-las e qual seria o preço da venda?**

   * Com as informações atuais em mãos foi criado uma feature denominada sales_suggestion com uma meta de ganho de 30% em relação aos imóveis adquiridos que estejam em condições acima de 3, e para os imóveis com condições abaixo de 2 foi sugerido um ganho de 20%.      
     
   * Para definir o melhor momento para a venda, com as datas e períodos que temos no dataframe. Foi assumido a premissa de definir a melhor temporada para venda conforme a estação do ano, comparando as medianas de vendas de cada estação do ano por zipcode, e qual a estação que teve a maior mediana para cada Zipcode, foi considerada como a melhor temporada para venda.

**3 - A House Rocket deveria fazer uma reforma para aumentar o preço da venda? Quais seriam as sugestões de mudanças? Qual o incremento no preço dado por cada opção de reforma?**

  * Para definir em como avaliar uma melhor visão para uma possível reforma, foi feita uma análise de correlação das variáveis do dataset com a variável preço.
  * Conseguimos dentificar que 5 variáveis possuem um forte correlação com o preço: sqft_living, grade,sqft_above , sqft_living15, bathrooms.
  * Com a variável que retorna a diferença em percentual do valor do imóvel em relação a mediana de cada CEP, criamos 10 grupos de casas.
  * Com os grupos criados, e com as variáveis que mais impactam no preço, foi verificado a mediana das características de cadas grupo e criado uma feature increment, para verificarmos o percentual de aumento de preço para cada subgrupo:
  
  <img src="https://github.com/leomacedo86/House_Rockets_Insight_Project/blob/main/Images/groups.png" alt="image" width="2000">
  
  * Com os grupos criados, conseguimos ver as medianas dos valores indicados para cada condição relacionada com o aumento de preços nas vendas. Para avaliar uma possível reforma no imóvel, foi criado uma condição para que em cada grupo possamos ver se ele tem variáveis iguais aos 3 grupos acimas, pois assim, pode-se avaliar a construção de novos cômodos, melhorias na casa, para que ela possa se enquadrar em um grupo acima e incrementarmos o valor da venda. Junto foi criado uma feature "suggested reform" que receberá sim ou não como reforma, e uma feature "renovation_price", que irá receber o novo valor indicado de venda conforme a reforma do grupo posterior.
  
  
# 4. Resultados Financeiros

Indicador   | Valores
------------|------------------
Casas selecionadas        |6.752 imóveis
Valor máximo investido	    |US$ US$2,418,274,205.00
Valor máximo esperado de vendas sem reformar os imóveis |US$3,143,756,466.50
Com as reformas indicadas esperamos um valor máximo de vendas|US$3,178,652,413.48
Incremento vendas com as reformas |US$34,895,946.98
Lucro esperado |US$760,378,208.48
