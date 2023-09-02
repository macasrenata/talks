---
images: 'https://cdn.pixabay.com/photo/2020/05/20/03/50/gears-5193383_1280.png'
title: Análise de dados e Políticas Públicas
description: ' #python #comunidade #CienciadeDados'
---

#### Introdução

Utilizar análises de dados é muito importante para criar ou melhorar políticas públicas mais eficientes. Aqui vamos falar sobre como números e dados podem ser amigos das políticas públicas. Isso é importante porque queremos que representantes do estado democrático façam coisas que funcionem, certo?

Políticas públicas são basicamente os planos do governo para fazer a sociedade ficar melhor. Eles podem ser sobre saúde, educação, dinheiro, ou até mesmo coisas divertidas como cultura. Às vezes, todos nós ajudamos a pensar nelas!

A ideia é que essas políticas públicas sigam as regras que estão escritas na Constituição de 1988, que é como o manual das leis aqui no Brasil. Mas como saber o que fazer e onde investir nosso dinheiro? Aí é onde entram os dados.

Os dados são como pistas que nos ajudam a entender o que está acontecendo na sociedade. Eles nos mostram coisas como quanto dinheiro as pessoas ganham, se têm acesso a serviços como saúde e educação, e até mesmo se todo mundo está tendo as mesmas oportunidades.

Por exemplo, temos o Instituto Brasileiro de Geografia e Estatística - IBGE. Eles estão coletando informações sobre tudo, desde quantas pessoas vivem em uma cidade até quanto tempo leva para as pessoas irem ao trabalho.

A transparência é fundamental aqui. Precisamos ter certeza de que todos podem ver e entender esses dados, porque isso ajuda a manter as coisas justas. Existem até leis, como a Lei de Acesso à Informação, que garantem que você pode pedir essas informações ao governo. E também temos a Lei Geral de Proteção de Dados (LGPD), que protege suas informações pessoais.

Então, resumindo, dados são como dicas valiosas para criar políticas públicas melhores. E é importante que todos possam acessá-los e que nossos dados pessoais sejam protegidos. Afinal, estamos todos juntos nessa jornada para uma sociedade mais justa!




## Tutorial

Vamos realizar uma Análise de Dados simples utilizando Python, Pandas, Matplotlib, e o Google Colab! :) 


1. Vamos acessar o Google Colab:

- Nesse link aqui: https://colab.google/ 


2. Vamos clicar em "New Notebook”:

- Para isso precisamos ter uma conta no Google. 
- Vai abrir uma nova página no navegador com seu ‘Notebook’ aberto. 
- O legal é que nessa plataforma podemos simular um ambiente virtual para trabalhar com códigos, e podemos armazenar esses arquivos em diversos locais, na sua máquina, no github, no drive, etc…

![image](https://drive.google.com/file/d/1F3IUmcw22-dN-4L_PSsHUyV6gIJiDqd8/view) 



3. Vamos alterar o nome do arquivo: 

- Na parte superior do arquivo, basta clicar no nome do arquivo com extensão .ipynb e trocar para ‘aula1’. 
- Se quiser, podemos armazenar/salvar este arquivo no Drive, Github, etc…

4. Vamos configurar nosso projeto:

- No lado esquerdo do arquivo temos um opção para configurar o ‘arquivo’, vamos clicar nela, e vai aparecer o ícone de uma pasta, é o nosso projeto!
- No ‘Google Colab’ já temos um ambiente preparado para realizar análise de dados, porém pode utilizar outras tecnologias, como jupyter, anaconda, tudo depende do que vamos analisar. :) 
[image] ()



- Vamos copiar, ou arrastar o arquivo .csv para a pasta: ‘sample-data’ ou integrar com o Google Drive

- Montar o Google Drive no Colab, tem que criar uma célula(bloco de código) no notebook com o seguinte conteúdo:

```sh
from google.colab import drive
drive.mount('/content/drive')
```

- Ao fazer isso ira aparecer uma mensagem como esta:


```sh
Go to this URL in a browser: https://accounts.google.com/o/oauth2/auth?client_id=[um-valor-bem-longo]
Enter your authorization code:
```

- Acesse o URL acima, escolha uma conta Google, copie o token gerado e cole no Colab, aperte enter.
- Feito isso a célula atualiza e aparece a seguinte mensagem:

```sh
··········
Mounted at /content/drive
```

- Enviar o arquivo para Google Drive
- Com o drive montado, vá no seu Google Drive e faça upload do arquivo.

Exemplo: Datasets/imdb-reviews-pt-br.csv.

- Abrir Dataset no Colab: Com o arquivo no Google Drive, crie uma célula com os seguintes valores:

```sh
import pandas as pd

df = pd.read_csv('/content/drive/My Drive/Datasets/imdb-reviews-pt-br.csv')
df.head()
```

- Você já deve ser capaz de visualizar as primeiras linhas do seu dataset!!! :) 


5. Agora vamos acessar o site que disponibiliza dados abertos para fazermos a análise

- Vamos acessar o site do INEP no link abaixo:
https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/enem 

- Ao clicar no link será realizado o download do arquivo .zip(compactado) com todos os dados 
- Descompactar o arquivo .zip e verificar quais são as pastas e tipos de arquivo que contém 
- Para o tutorial vamos selecionar a de microdados do Enem



6. Agora vamos programar! Se vc não sabe nada de python, não tem problema, é só copiar e colar o bloco de código abaixo:

> Mas é fundamental estudar Python ou outra linguagem de programação se você pretende avançar na carreira na área de Ciência de Dados. :) '

- criar uma variavel para armazenar os dados que vão ser importados com o panda:

https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html 

```sh
microdados = pd.read_csv(‘caminho-do-arquivo’), sep=";", enconding='ISO-8859-1' 
```

- Depois de copiar o código e colar no Google Colab, clique na tecla run dentro do bloco de código e veja a mágica acontecer!
- Ao rodar o comando teremos o data Frame que é a estrutura de dados do pandas que é encapsulado e lido por ele, ou seja, uma tabela com linhas e colunas :) 
[image] ()


7. A partir daqui iniciamos a análise:

- Nesse momento é hora de realizar os questionamentos
- O que queremos analisar? 
- Quais as perguntas que os dados, e índices podem apontar respostas, ou hipóteses? 
- Como esse resultado pode impactar nas decisões tanto no público como no privado?


- Para continuar, vamos fazer uma breve análise exploratória a partir da seguinte questão: 

- Como organizar as colunas para ter insights? 
- Vamos digitar o código abaixo para verificar os dados

```sh
microdados.columns.values
```
[image] ()


- Esse comando irá retornar um array com um vetor e com o nome de todas as colunas


- Como hoje vamos analisar somente um conjunto de dados, vamos selecionar apenas algumas colunas para isso, ou seja, vamos  criar um data frame para esta análise. - Vamos digitar o seguinte código:

O método que vamos utilizar é o filter (para filtrar as colunas que queremos analisar)

```sh
microdadoSelecionado = microdados.filter(items=colunaSelecionadas)

microdadoSelecionado.head()
```
[image] ()


- Vamos analisar a distribuição de alunos por município

https://pandas.pydata.org/docs/getting_started/intro_tutorials/06_calculate_statistics.html 

https://pandas.pydata.org/docs/reference/index.html 

Ou seja, quantas linhas tem para cada município:

- Com o nome da variável da coluna e o método da biblioteca do Pandas, também podemos ordenar os dados e procurar o município que queremos, por exemplo:

```sh
colunaSelecionada = microdadoSelecionado['NO_MUNICIPIO_PROVA']

colunaSelecionada
```
[image] ()


e


```sh
colunaSelecionada.value_counts()
```
[image] ()


- Agora vamos fazer para a faixa etária:

```sh
colunaSelecionadaIdade = microdadoSelecionado['TP_FAIXA_ETARIA']

colunaSelecionadaIdade.value_counts()
```
[image] ()



8. E agora para visualizar os dados vamos utilizar a biblioteca matplotlib 

https://matplotlib.org/stable/api/ 

- Importamos ela lá no início do projeto, lembra? Aqui está como importamos:

```sh
import matplotlib
```
[image] ()




- E podemos rodar esse comando:

```sh
colunaSelecionadaIdade.hist()
```
[image] ()


- E se quisermos aumentar a distribuição de dados para melhor utilização, podemos usar o parâmetro ‘bins’:

```sh
colunaSelecionadaIdade.hist(bins=30)
```
[image] ()


- Agora vamos fazer a análise de gênero:

```sh
colunaGenero = microdadoSelecionado['TP_SEXO']
colunaGenero.hist()
```
[image] ()


`spoiler!`
> Opa, mas o Enem não cadastra por gênero, temos apenas a opção de masculino e feminino, será que esses dados não podem auxiliar a uma política pública para que tenha mais opções de gênero?


#### Conclusão:

Agora, é hora de se aprofundar na Análise de Dados. Vamos explorar mais, fazer perguntas diferentes e experimentar tecnologias novas. Lembrem-se, o que vimos foi um tutorial básico para mostrar como usar dados públicos em análises simples ou complexas.

O uso de dados é essencial para políticas públicas eficazes. Ajuda as organizações governamentais e não-governamentais a tomar decisões informadas, alinhadas com as necessidades reais da sociedade, e também a avaliar o desempenho das políticas após a implementação. Vamos continuar explorando a análise de dados para atender melhor às necessidades da sociedade!









#### Fonte:

Cursos gratuitos Do Governo Federal para a area de Ciência de Dados: https://www.gov.br/governodigital/pt-br/capacita/ciencia-de-dados 

Pesquisa sobre Ciência de Dados e Educação: https://www.institutounibanco.org.br/iniciativas/centro-de-pesquisa-transdisciplinar-em-educacao-cpte/ciencia-de-dados-na-educacao/ 


2022 - Ciência de dados em políticas públicas: uma experiência de formação	Escola Nacional de Administração Publica (Brasil); De Toni, Jackson (Organizador); Dorneles, Rachel (Organizadora) - https://repositorio.enap.gov.br/handle/1/7472 
