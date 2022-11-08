<center><img style="text-align:center;" src="img/fgv.png" alt="drawing" width="400"/></center>
<center> <H1>        Fundação Getulio Vargas </H1> </center>
<center> <H1>        Escola de Matemática Aplicada</H1></center>
<center> <H1>        Curso de Ciência de Dados e Inteligência Artificial </H1></center>

<center> <H3>Álgebra Linear</H3></center>
<center> <H3>Professor: Yuri Saporito</H3></center>

### Colaboradores:

<a style="color: black; text-decoration: none; font-size:17px" href="https://github.com/adrian667">Adrian Castro</a>

<a style="color: black; text-decoration: none; font-size:17px" href="https://github.com/FabricioVenturim">Fabrício Dalvi Venturim</a>


# 1 - Teoria

## 1.1 - Mínimos Quadrados

O **método dos Mínimos Quadrados(MMQ)** também conhecido como Mínimos Quadrados Ordinários é um modo de otimização na matemática e estatística. Este método procura melhorar um conjunto de dados tentando minimizar a soma dos quadrados das diferenças entre o valor estimado e os dados observados tal que essas diferenças são chamadas de resíduos, vamos demonstrar esse problema.

Temos um conjunto de dados simples que consiste em $n$ pontos (que são pares ordenados) $(x_i, y_i)$, $i= 1,2,.....,n$ tal que $x_i$ é uma variável independe e $y_i$ é uma dependente.

A função modelo dada como $F(x,b)$ tal que os parâmetros ajustáveis são mantidos no vetor $b$, queremos encontrar os parâmetros que melhor se ajusta em nos dados.

O ajuste de um modelo é pelo seu resíduo, que é diferença entre o valor real da variável dependente e o valor predito pelo modelo:

$$ r_i = y_i - F(x_i,b) $$ 

Então, encontrar os valores ideais para os parâmetros, minimizando a soma S dos quadrados residuais :

$$ S = \sum\limits_{i-1}^{\mbox{}{n}}r^2_i$$

Um tipo de modelo de duas dimensões é o da reta da função afim:

$$ f(x) = b_0 + b_1x$$ 


$b_0$ sendo a intersecção em y e $b_1$ a inclinação.

## 1.2 - Regressão Linear

### 1.2.1 - Regressão Linear Simples

Em estatística ou econometria, a análise de regressão linear é usada para prever o valor de uma variável com base no valor de outra. A variável que deseja prever é chamada de **variável dependente**. A variável que é usada para prever o valor de outra variável é chamada de **variável independente**.

Em regressão simples, queremos estimar valores de determinada variável y. Para isso, consideramos os valores de outra variável x que acreditamos ter poder de explicação sobre y conforme a fórmulam:

$$ y = \alpha + \beta x + \epsilon$$

Tal que:

* $\alpha$ é o parâmetro do modelo chamado de constante (pois não depende de x).

* $\beta$ é o parâmetro do modelo chamado de coeficiente da variáve x.

* $\epsilon$ é o erro que representa a variação de y que não é explicada pelo modelo.

Em uma base de dados com $n$ valores observados de $y$ e $x$. Sabemos que usando base de dados $y$ e $x$ são vetores que representa uma lista de valores, um para cada observação de dados.

O método dos mínimos quadrados ajuda a encontrar as estimativas de $\alpha$ e $\beta$ . Como sabemos, serão somente estimativas desses parâmetros, pois o valor real dos parâmetros são desconhecidos.

 Logo, quando for fazer a estimativa iremos mudar a notação de algumas variáveis:

$$\alpha = a, \beta = b, \epsilon = e $$

Logo, quando estimamos um modelo a base de dados, estamos estimando :

$$y_i = a + bx_i + e_i$$  

Tal que $i$ indica uma das n observações da base de dados e $e$ vai ser chamado de resíduo ao invés de erro.

O método dos mínimos quadrados minimiza a soma dos quadrado dos resíduos, ou seja, minimiza:

$$\sum\limits_{t=0}^{\mbox{}{n}}e^2$$

A ideia dessa técnica é que, minimizando essa soma, encontraremos a e b que trarão menor diferença entre a previsão de $y$ e o $y$ realmente observado: 

Tomando $e_i = y_i - a -bx_i$, teremos 
$$ S(a,b) = \sum\limits_{t=0}^{\mbox{}{n}}(y_i - a -bx_i)^2$$

A minimização vai ser quando derivarmos S e relação a a e b, usando a regra da cadeia e depois igualando a zero. 

Assim chegaremos a: 

$$ b = (\sum \limits_{i=1}^{\mbox{}{n}}(x_i - x^*)(y_i - y^*))(\sum \limits_{i=1}^{\mbox{}{n}}(x_i - x^*)^2) $$ 


Tal que onde $y^*$ é a média amostral de y e $x^*$ é a média amostral de x. 

### 1.2.2 - Regressão Múltipla

A regressão múltipla apresenta um funcionamento parecido com o da regressão simples, porém, leva em consideração diversas variáveis explicativas x influenciando y ao mesmo tempo:

$$ y = b_0 + x_1b_1 + x_2b_2 + ... + x_kb_k + e$$
    
Ao usar uma base de dados com $k$ variáveis explicativas e $n$ observações, o modelo pode ser escrito de uma forma matricial, mas também pode ser resumida em fórmula como: 

$$ y = Xb + e $$ 

A técnica para mínimos quadrados continua sendo a mesma, logo tendo $e = y - Xb$ Temos:

$$S(b) = (y - Xb)^T (Y - Xb)$$ 

A minimização pode ser obtida ao derivar S e igualar a zero, logo teremos: 

$$b = (X^TX)^1X^Ty$$

## 1.3 - Exemplo simples

Abaixo, listamos apenas alguns dados de uma pesquisa americana sobre altura das pessoas, para que nossas contas não ﬁquem tão extensas.

| Altura  | Altura Mãe | Altura Pai|
|---------- | ----------  |---------- |
|152|155|165|
|162|155|160|
|165|170|173|
|170|163|183|
|173|168|183|
|183|165|183|


Quanto maior o número de dados, mais provável de o sistema ser impossível (podemos fazer a analogia geométrica de que por três pontos não colineares no espaço passa um único plano; se aumentarmos o número de pontos, mais difícil que haja um plano contendo todos eles).


\begin{equation*}
\begin{cases}
a\ +\ bx_{1} \ +\ cy_{1} \ =\ z_{1}\\
a+bx_{2} \ +\ cy_{2} \ =\ z_{2}\\
\vdots \\
a\ +\ bx_{k} \ +\ cy_{k} \ =\ z_{k}
\end{cases}\rightarrow \begin{bmatrix}
1 & x_{1} & y_{1}\\
1 & x_{2} & y_{2}\\
\vdots  & \vdots  & \vdots \\
1 & x_{k} & y_{k}
\end{bmatrix}\begin{bmatrix}
a\\
b\\
c
\end{bmatrix} =\begin{bmatrix}
z_{1}\\
z_{2}\\
\vdots \\
z_{k}
\end{bmatrix}
\end{equation*}

 Por isto, procuramos por uma solução de mínimos quadrados.


\begin{equation*}
A\vec{x} \ =\ \vec{b}\rightarrow \begin{bmatrix}
1 & 155 & 165\\
1 & 155 & 160\\
1 & 170 & 173\\
1 & 163 & 183\\
1 & 168 & 183\\
1 & 165 & 183
\end{bmatrix}\begin{bmatrix}
a\\
b\\
c
\end{bmatrix} =\begin{bmatrix}
152\\
162\\
165\\
170\\
173\\
183
\end{bmatrix}
\end{equation*}

Calculamos


\begin{equation*}
A^{T} A=\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 1\\
155 & 155 & 170 & 163 & 168 & 165\\
165 & 160 & 173 & 183 & 183 & 183
\end{bmatrix}\begin{bmatrix}
1 & 155 & 165\\
1 & 155 & 160\\
1 & 170 & 173\\
1 & 163 & 183\\
1 & 168 & 183\\
1 & 165 & 183
\end{bmatrix} =\begin{bmatrix}
6 & 976 & 1047\\
976 & 158968 & 170553\\
1047 & 170553 & 183221
\end{bmatrix}
\end{equation*}

e


\begin{equation*}
A^{T}\vec{b} =\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 1\\
155 & 155 & 170 & 163 & 168 & 165\\
165 & 160 & 173 & 183 & 183 & 183
\end{bmatrix}\begin{bmatrix}
152\\
162\\
165\\
170\\
173\\
183
\end{bmatrix} =\begin{bmatrix}
1005\\
163689\\
175803
\end{bmatrix}
\end{equation*}

Por escalonamento,


\begin{equation*}
\begin{bmatrix}
6 & 976 & 1047 & 1005\\
976 & 158968 & 170553 & 163689\\
1047 & 170553 & 183221 & 175803
\end{bmatrix}\rightarrow \begin{bmatrix}
1 & 0 & 0 & 14.781\\
0 & 1 & 0 & 0.099\\
0 & 0 & 1 & 0783
\end{bmatrix}
\end{equation*}

A equação de melhor ajuste procurada é, portanto, aproximadamente,


\begin{equation*}
z\ \simeq \ 14.781\ +\ 0.099x\ +\ 0.783y
\end{equation*}

<center><img style="text-align:center;" src="img/geo.png" alt="drawing" width="400"/></center>

# 2 - Aplicação

## 2.1 - Contexto e Objetivos

Um sistema de compartilhamento de bicicletas é um serviço no qual as bicicletas são disponibilizadas para uso compartilhado para indivíduos a curto prazo por um preço ou gratuitamente. Muitos sistemas de compartilhamento de bicicletas permitem que as pessoas peguem uma bicicleta emprestada de um "dock" que geralmente é controlado por computador, no qual o usuário insere as informações de pagamento e o sistema o desbloqueia. Esta bicicleta pode então ser devolvida a outra doca pertencente ao mesmo sistema.

Com base em várias pesquisas meteorológicas e estilos das pessoas, Queremos entender os fatores dos quais depende a demanda por essas bicicletas compartilhadas. Especificamente, queremos entender os fatores que afetam a demanda por essas bicicletas compartilhadas no mercado americano. 

**Objetivo do negócio:**

Somos obrigados a modelar a demanda por bicicletas compartilhadas com as variáveis ​​independentes disponíveis. Ele será usado para entender exatamente como as demandas variam com diferentes recursos. Esse modelo será útil para manipular a estratégia de negócios de acordo com os níveis de demanda e atender às expectativas do cliente. Além disso, o modelo será uma boa maneira de a administração entender a dinâmica da demanda de um novo mercado.

link: https://business-science.github.io/timetk/reference/bike_sharing_daily.html

## 2.2 - Importação e Limpeza dos dados


```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline

from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split
import statsmodels.api as sm
```


```python
bike = pd.DataFrame(pd.read_csv("day.csv"))
```


```python
bike
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>instant</th>
      <th>dteday</th>
      <th>season</th>
      <th>yr</th>
      <th>mnth</th>
      <th>holiday</th>
      <th>weekday</th>
      <th>workingday</th>
      <th>weathersit</th>
      <th>temp</th>
      <th>atemp</th>
      <th>hum</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>cnt</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>01-01-2018</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>14.110847</td>
      <td>18.18125</td>
      <td>80.5833</td>
      <td>10.749882</td>
      <td>331</td>
      <td>654</td>
      <td>985</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>02-01-2018</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>14.902598</td>
      <td>17.68695</td>
      <td>69.6087</td>
      <td>16.652113</td>
      <td>131</td>
      <td>670</td>
      <td>801</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>03-01-2018</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>8.050924</td>
      <td>9.47025</td>
      <td>43.7273</td>
      <td>16.636703</td>
      <td>120</td>
      <td>1229</td>
      <td>1349</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>04-01-2018</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
      <td>1</td>
      <td>8.200000</td>
      <td>10.60610</td>
      <td>59.0435</td>
      <td>10.739832</td>
      <td>108</td>
      <td>1454</td>
      <td>1562</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>05-01-2018</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>5</td>
      <td>1</td>
      <td>1</td>
      <td>9.305237</td>
      <td>11.46350</td>
      <td>43.6957</td>
      <td>12.522300</td>
      <td>82</td>
      <td>1518</td>
      <td>1600</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>725</th>
      <td>726</td>
      <td>27-12-2019</td>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>5</td>
      <td>1</td>
      <td>2</td>
      <td>10.420847</td>
      <td>11.33210</td>
      <td>65.2917</td>
      <td>23.458911</td>
      <td>247</td>
      <td>1867</td>
      <td>2114</td>
    </tr>
    <tr>
      <th>726</th>
      <td>727</td>
      <td>28-12-2019</td>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
      <td>10.386653</td>
      <td>12.75230</td>
      <td>59.0000</td>
      <td>10.416557</td>
      <td>644</td>
      <td>2451</td>
      <td>3095</td>
    </tr>
    <tr>
      <th>727</th>
      <td>728</td>
      <td>29-12-2019</td>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
      <td>10.386653</td>
      <td>12.12000</td>
      <td>75.2917</td>
      <td>8.333661</td>
      <td>159</td>
      <td>1182</td>
      <td>1341</td>
    </tr>
    <tr>
      <th>728</th>
      <td>729</td>
      <td>30-12-2019</td>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>10.489153</td>
      <td>11.58500</td>
      <td>48.3333</td>
      <td>23.500518</td>
      <td>364</td>
      <td>1432</td>
      <td>1796</td>
    </tr>
    <tr>
      <th>729</th>
      <td>730</td>
      <td>31-12-2019</td>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>8.849153</td>
      <td>11.17435</td>
      <td>57.7500</td>
      <td>10.374682</td>
      <td>439</td>
      <td>2290</td>
      <td>2729</td>
    </tr>
  </tbody>
</table>
<p>730 rows × 16 columns</p>
</div>



### Verificar as informações do dataframe 


```python
bike.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 730 entries, 0 to 729
    Data columns (total 16 columns):
     #   Column      Non-Null Count  Dtype  
    ---  ------      --------------  -----  
     0   instant     730 non-null    int64  
     1   dteday      730 non-null    object 
     2   season      730 non-null    int64  
     3   yr          730 non-null    int64  
     4   mnth        730 non-null    int64  
     5   holiday     730 non-null    int64  
     6   weekday     730 non-null    int64  
     7   workingday  730 non-null    int64  
     8   weathersit  730 non-null    int64  
     9   temp        730 non-null    float64
     10  atemp       730 non-null    float64
     11  hum         730 non-null    float64
     12  windspeed   730 non-null    float64
     13  casual      730 non-null    int64  
     14  registered  730 non-null    int64  
     15  cnt         730 non-null    int64  
    dtypes: float64(4), int64(11), object(1)
    memory usage: 91.4+ KB
    

#### Explicando as variáveis:

* **instant**: index do DataBase (type: int).

* **dteday**: Dia (type: Data).

* **season**: Estação do ano, sendo 1, 2, 3 e 4 index para, respectivamente, inverno, primavera, verão e outono. (type: int)

* **yr**: Ano, sendo 1 o ano de 2018 e 2 para o ano de 2019. (type: int)
 
* **mnth**: O mês do ano. (type: int).

* **holiday**: 1 para feriados e 0 para dias comuns. (type: int).

* **weekday**: index para os dias da semana, começando no domingo com o index 0. (type: int)

* **workingday**: se o dia não for fim de semana nem feriado for 1, caso contrário será 0.

* **weathersit**:  (type: int)

 - 1: Claro, Poucas nuvens, Parcialmente nublado.
 
 - 2: Névoa + Nublado, Névoa + Nuvens quebradas, Névoa + Poucas nuvens, Névoa

 - 3: Neve fraca, Chuva fraca + Trovoada + Nuvens dispersas, Chuva fraca + Nuvens dispersas

 - 4: Chuva Pesada + Paletes de Gelo + Trovoada + Névoa, Neve + Neblina  

* **temp**: Temperatura normalizada em Celsius. Os valores são derivados via (t-t_min)/(t_max-t_min), t_min=-8, t_max=+39 (somente em escala horária). (type: int).

* **atemp**: Temperatura de sensação normalizada em Celsius. Os valores são derivados via (t-t_min)/(t_max-t_min), t_min=-16, t_max=+50 (somente em escala horária). (type: int).

* **hum**: Umidade normalizada. Os valores são divididos em 100 (máx.). (type: int).

* **windspeed**: velocidade do vento normalizada. Os valores são divididos em 67 (máx.). (type: int).

* **casual**: contagem de usuários casuais. (type: int).

* **registered**: contagem de usuários registrados. (type: int).

* **cnt**: contagem do total de bicicletas alugadas, incluindo casuais e registradas. (type: int).


```python
bike.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>instant</th>
      <th>season</th>
      <th>yr</th>
      <th>mnth</th>
      <th>holiday</th>
      <th>weekday</th>
      <th>workingday</th>
      <th>weathersit</th>
      <th>temp</th>
      <th>atemp</th>
      <th>hum</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>cnt</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
      <td>730.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>365.500000</td>
      <td>2.498630</td>
      <td>0.500000</td>
      <td>6.526027</td>
      <td>0.028767</td>
      <td>2.995890</td>
      <td>0.715068</td>
      <td>1.394521</td>
      <td>20.319259</td>
      <td>23.726322</td>
      <td>62.765175</td>
      <td>12.763620</td>
      <td>849.249315</td>
      <td>3658.757534</td>
      <td>4508.006849</td>
    </tr>
    <tr>
      <th>std</th>
      <td>210.877136</td>
      <td>1.110184</td>
      <td>0.500343</td>
      <td>3.450215</td>
      <td>0.167266</td>
      <td>2.000339</td>
      <td>0.451691</td>
      <td>0.544807</td>
      <td>7.506729</td>
      <td>8.150308</td>
      <td>14.237589</td>
      <td>5.195841</td>
      <td>686.479875</td>
      <td>1559.758728</td>
      <td>1936.011647</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>2.424346</td>
      <td>3.953480</td>
      <td>0.000000</td>
      <td>1.500244</td>
      <td>2.000000</td>
      <td>20.000000</td>
      <td>22.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>183.250000</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>4.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>13.811885</td>
      <td>16.889713</td>
      <td>52.000000</td>
      <td>9.041650</td>
      <td>316.250000</td>
      <td>2502.250000</td>
      <td>3169.750000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>365.500000</td>
      <td>3.000000</td>
      <td>0.500000</td>
      <td>7.000000</td>
      <td>0.000000</td>
      <td>3.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>20.465826</td>
      <td>24.368225</td>
      <td>62.625000</td>
      <td>12.125325</td>
      <td>717.000000</td>
      <td>3664.500000</td>
      <td>4548.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>547.750000</td>
      <td>3.000000</td>
      <td>1.000000</td>
      <td>10.000000</td>
      <td>0.000000</td>
      <td>5.000000</td>
      <td>1.000000</td>
      <td>2.000000</td>
      <td>26.880615</td>
      <td>30.445775</td>
      <td>72.989575</td>
      <td>15.625589</td>
      <td>1096.500000</td>
      <td>4783.250000</td>
      <td>5966.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>730.000000</td>
      <td>4.000000</td>
      <td>1.000000</td>
      <td>12.000000</td>
      <td>1.000000</td>
      <td>6.000000</td>
      <td>1.000000</td>
      <td>3.000000</td>
      <td>35.328347</td>
      <td>42.044800</td>
      <td>97.250000</td>
      <td>34.000021</td>
      <td>3410.000000</td>
      <td>6946.000000</td>
      <td>8714.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
#Quantidade de valores nulos

na = bike[bike.isna()].count()
print(na)
```

    instant       0
    dteday        0
    season        0
    yr            0
    mnth          0
    holiday       0
    weekday       0
    workingday    0
    weathersit    0
    temp          0
    atemp         0
    hum           0
    windspeed     0
    casual        0
    registered    0
    cnt           0
    dtype: int64
    

#### Análise das informações encontradas:

* Há 730 instâncias e 16 variáveis
* Não há valores NaN no nosso banco de dados
* 11 variáveis int, 4 float e 1 data, sendo que 'mnth', 'weekday', 'season' e 'weathersit' são variáveis categóricas.

#### Como essa variáveis são categóricas, vamos mudar o seu tipo:


```python
bike['yr'] = bike['yr'].astype('category')
bike['season'] = bike['season'].astype('category')
bike['weathersit'] = bike['weathersit'].astype('category')
bike['mnth'] = bike['mnth'].astype('category')
bike['weekday'] = bike['weekday'].astype('category')
```


```python
bike.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 730 entries, 0 to 729
    Data columns (total 16 columns):
     #   Column      Non-Null Count  Dtype   
    ---  ------      --------------  -----   
     0   instant     730 non-null    int64   
     1   dteday      730 non-null    object  
     2   season      730 non-null    category
     3   yr          730 non-null    category
     4   mnth        730 non-null    category
     5   holiday     730 non-null    int64   
     6   weekday     730 non-null    category
     7   workingday  730 non-null    int64   
     8   weathersit  730 non-null    category
     9   temp        730 non-null    float64 
     10  atemp       730 non-null    float64 
     11  hum         730 non-null    float64 
     12  windspeed   730 non-null    float64 
     13  casual      730 non-null    int64   
     14  registered  730 non-null    int64   
     15  cnt         730 non-null    int64   
    dtypes: category(5), float64(4), int64(6), object(1)
    memory usage: 67.6+ KB
    

#### Vamos excluir as seguintes variáveis:

* **instant** : É apenas um valor de índice.

* **dteday** : Já temos essa variáveis separada em outras variáveis.

* **casual & registered** : ambas as colunas contêm a contagem de bicicletas reservadas por diferentes categorias de clientes. Como nosso objetivo é encontrar a contagem total de bicicletas e não por categoria específica, vamos ignorar essas duas colunas.


```python
bike_new = bike[['season', 'yr', 'mnth', 'holiday', 'weekday',
       'workingday', 'weathersit', 'temp', 'atemp', 'hum', 'windspeed',
       'cnt']]
bike_new
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>season</th>
      <th>yr</th>
      <th>mnth</th>
      <th>holiday</th>
      <th>weekday</th>
      <th>workingday</th>
      <th>weathersit</th>
      <th>temp</th>
      <th>atemp</th>
      <th>hum</th>
      <th>windspeed</th>
      <th>cnt</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>14.110847</td>
      <td>18.18125</td>
      <td>80.5833</td>
      <td>10.749882</td>
      <td>985</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>14.902598</td>
      <td>17.68695</td>
      <td>69.6087</td>
      <td>16.652113</td>
      <td>801</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>3</td>
      <td>1</td>
      <td>1</td>
      <td>8.050924</td>
      <td>9.47025</td>
      <td>43.7273</td>
      <td>16.636703</td>
      <td>1349</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>4</td>
      <td>1</td>
      <td>1</td>
      <td>8.200000</td>
      <td>10.60610</td>
      <td>59.0435</td>
      <td>10.739832</td>
      <td>1562</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>5</td>
      <td>1</td>
      <td>1</td>
      <td>9.305237</td>
      <td>11.46350</td>
      <td>43.6957</td>
      <td>12.522300</td>
      <td>1600</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>725</th>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>5</td>
      <td>1</td>
      <td>2</td>
      <td>10.420847</td>
      <td>11.33210</td>
      <td>65.2917</td>
      <td>23.458911</td>
      <td>2114</td>
    </tr>
    <tr>
      <th>726</th>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>6</td>
      <td>0</td>
      <td>2</td>
      <td>10.386653</td>
      <td>12.75230</td>
      <td>59.0000</td>
      <td>10.416557</td>
      <td>3095</td>
    </tr>
    <tr>
      <th>727</th>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
      <td>10.386653</td>
      <td>12.12000</td>
      <td>75.2917</td>
      <td>8.333661</td>
      <td>1341</td>
    </tr>
    <tr>
      <th>728</th>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>10.489153</td>
      <td>11.58500</td>
      <td>48.3333</td>
      <td>23.500518</td>
      <td>1796</td>
    </tr>
    <tr>
      <th>729</th>
      <td>1</td>
      <td>1</td>
      <td>12</td>
      <td>0</td>
      <td>2</td>
      <td>1</td>
      <td>2</td>
      <td>8.849153</td>
      <td>11.17435</td>
      <td>57.7500</td>
      <td>10.374682</td>
      <td>2729</td>
    </tr>
  </tbody>
</table>
<p>730 rows × 12 columns</p>
</div>



### Criando variáveis ficticías 

As variáveis categorias não podem ser utilizadas em forma de texto, uma vez que os algoritmos compreendem apenas valores numéricos. Também não podemos simplesmente atribuir um valor numérico para cada categoria, uma vez que esse processo, conhecido como ponderação arbitrária, pode criar uma ordenação e pesos para as categorias que não refletem a realidade.

O processo correto de transformação das variáveis categóricas é feito a partir da criação de novas colunas a partir das categorias. Cada uma delas se torna uma nova coluna e o valor na linha correspondente será 1, caso tenha a presença da característica. Do contrário, será 0. Esse processo é conhecido como codificação **"one-hot"**.

| Variável   | 
|---------- |
| Característica 1 | 
| Característica 2  |   
| Característica 3  |   

| Característica 1   | Característica 2 | Característica 3|
|---------- | ----------  |---------- |
|**1** | 0 | 0| 
| 0  |  **1** | 0| 
| 0  |  0 | **1**| 


```python
bike_new = pd.get_dummies(bike_new)
bike_new.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 730 entries, 0 to 729
    Data columns (total 35 columns):
     #   Column        Non-Null Count  Dtype  
    ---  ------        --------------  -----  
     0   holiday       730 non-null    int64  
     1   workingday    730 non-null    int64  
     2   temp          730 non-null    float64
     3   atemp         730 non-null    float64
     4   hum           730 non-null    float64
     5   windspeed     730 non-null    float64
     6   cnt           730 non-null    int64  
     7   season_1      730 non-null    uint8  
     8   season_2      730 non-null    uint8  
     9   season_3      730 non-null    uint8  
     10  season_4      730 non-null    uint8  
     11  yr_0          730 non-null    uint8  
     12  yr_1          730 non-null    uint8  
     13  mnth_1        730 non-null    uint8  
     14  mnth_2        730 non-null    uint8  
     15  mnth_3        730 non-null    uint8  
     16  mnth_4        730 non-null    uint8  
     17  mnth_5        730 non-null    uint8  
     18  mnth_6        730 non-null    uint8  
     19  mnth_7        730 non-null    uint8  
     20  mnth_8        730 non-null    uint8  
     21  mnth_9        730 non-null    uint8  
     22  mnth_10       730 non-null    uint8  
     23  mnth_11       730 non-null    uint8  
     24  mnth_12       730 non-null    uint8  
     25  weekday_0     730 non-null    uint8  
     26  weekday_1     730 non-null    uint8  
     27  weekday_2     730 non-null    uint8  
     28  weekday_3     730 non-null    uint8  
     29  weekday_4     730 non-null    uint8  
     30  weekday_5     730 non-null    uint8  
     31  weekday_6     730 non-null    uint8  
     32  weathersit_1  730 non-null    uint8  
     33  weathersit_2  730 non-null    uint8  
     34  weathersit_3  730 non-null    uint8  
    dtypes: float64(4), int64(3), uint8(28)
    memory usage: 60.0 KB
    


```python
bike_new
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>holiday</th>
      <th>workingday</th>
      <th>temp</th>
      <th>atemp</th>
      <th>hum</th>
      <th>windspeed</th>
      <th>cnt</th>
      <th>season_1</th>
      <th>season_2</th>
      <th>season_3</th>
      <th>...</th>
      <th>weekday_0</th>
      <th>weekday_1</th>
      <th>weekday_2</th>
      <th>weekday_3</th>
      <th>weekday_4</th>
      <th>weekday_5</th>
      <th>weekday_6</th>
      <th>weathersit_1</th>
      <th>weathersit_2</th>
      <th>weathersit_3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>1</td>
      <td>14.110847</td>
      <td>18.18125</td>
      <td>80.5833</td>
      <td>10.749882</td>
      <td>985</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>1</td>
      <td>14.902598</td>
      <td>17.68695</td>
      <td>69.6087</td>
      <td>16.652113</td>
      <td>801</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>1</td>
      <td>8.050924</td>
      <td>9.47025</td>
      <td>43.7273</td>
      <td>16.636703</td>
      <td>1349</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>1</td>
      <td>8.200000</td>
      <td>10.60610</td>
      <td>59.0435</td>
      <td>10.739832</td>
      <td>1562</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>1</td>
      <td>9.305237</td>
      <td>11.46350</td>
      <td>43.6957</td>
      <td>12.522300</td>
      <td>1600</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>725</th>
      <td>0</td>
      <td>1</td>
      <td>10.420847</td>
      <td>11.33210</td>
      <td>65.2917</td>
      <td>23.458911</td>
      <td>2114</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>726</th>
      <td>0</td>
      <td>0</td>
      <td>10.386653</td>
      <td>12.75230</td>
      <td>59.0000</td>
      <td>10.416557</td>
      <td>3095</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>727</th>
      <td>0</td>
      <td>0</td>
      <td>10.386653</td>
      <td>12.12000</td>
      <td>75.2917</td>
      <td>8.333661</td>
      <td>1341</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>728</th>
      <td>0</td>
      <td>1</td>
      <td>10.489153</td>
      <td>11.58500</td>
      <td>48.3333</td>
      <td>23.500518</td>
      <td>1796</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>729</th>
      <td>0</td>
      <td>1</td>
      <td>8.849153</td>
      <td>11.17435</td>
      <td>57.7500</td>
      <td>10.374682</td>
      <td>2729</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>730 rows × 35 columns</p>
</div>



## 3 - Verificando Correlações

### 3.1 - Variáveis numéricas 

Vamos fazer um gráfico de pares de todas as variáveis numéricas.


```python
# Cria um novo dataframe apenas com variáveis numéricas:

bike_num = bike_new[[ 'temp', 'atemp', 'hum', 'windspeed','cnt']]

sns.pairplot(bike_num, diag_kind='kde')
plt.show()
```


    
![png](output_83_0.png)
    


O Par-Plot acima indica que existe uma RELAÇÃO LINEAR entre 'temp', 'atemp' e 'cnt'

### 3.2 - Variáveis Categóricas

Construir boxplot de todas as variáveis categóricas (antes de criar dummies) contra a variável alvo 'cnt'.

Para ver como cada variável preditora se compara à variável de destino.


```python
plt.figure(figsize=(25, 10))
plt.subplot(2,3,1)
sns.boxplot(x = 'season', y = 'cnt', data = bike)
plt.subplot(2,3,2)
sns.boxplot(x = 'mnth', y = 'cnt', data = bike)
plt.subplot(2,3,3)
sns.boxplot(x = 'weathersit', y = 'cnt', data = bike)
plt.subplot(2,3,4)
sns.boxplot(x = 'holiday', y = 'cnt', data = bike)
plt.subplot(2,3,5)
sns.boxplot(x = 'weekday', y = 'cnt', data = bike)
plt.subplot(2,3,6)
sns.boxplot(x = 'workingday', y = 'cnt', data = bike)
plt.show()
```


    
![png](output_87_0.png)
    


**mnth**: Quase 10% das reservas de bicicletas aconteceram nos meses 5,6,7,8 e 9, com uma média de mais de 4.000 reservas por mês. Isso indica que mnth tem alguma tendência para reservas e pode ser um bom preditor para a variável dependente.

**weathersit**: Quase 67% das reservas de bicicletas estavam acontecendo durante o "weathersit1", com uma média de cerca de 5.000 reservas (para o período de 2 anos). Isto foi seguido por weathersit2 com 30% da reserva total. Isso indica que o clima mostra alguma tendência em relação às reservas de bicicletas pode ser um bom preditor para a variável dependente.

**holiday**: Quase 97,6% das reservas de bicicletas ocorreram quando não é feriado, o que significa que esses dados são claramente tendenciosos. **Isso indica que o feriado NÃO PODE ser um bom preditor para a variável dependente**.

**weekday**: a variável dia da semana apresenta tendência muito próxima (entre 13,5%-14,8% do total de reservas em todos os dias da semana) tendo suas medianas independentes entre 4.000 a 5.000 reservas. Esta variável pode ter alguma ou nenhuma influência sobre o preditor.

**workingday**: Quase 69% das reservas de bicicletas ocorreram em 'dia útil' com uma mediana de cerca de 5.000 reservas (para o período de 2 anos). Isso indica que a jornada de trabalho pode ser um bom preditor para a variável dependente.

### 3.3 -  Matriz de correlação

Vamos verificar os coeficientes de correlação para ver quais variáveis são altamente correlacionadas.


```python
plt.figure(figsize = (25,20))
sns.heatmap(bike_new.corr(), annot = True, cmap="RdBu")
plt.show()
```


    
![png](output_91_0.png)
    


O mapa de calor mostra claramente quais variáveis são multicolineares por natureza e quais têm alta colinearidade com a variável alvo.



```python
bike_new.drop(["holiday"], axis=1, inplace = True)
```


```python
bike_new
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>workingday</th>
      <th>temp</th>
      <th>atemp</th>
      <th>hum</th>
      <th>windspeed</th>
      <th>cnt</th>
      <th>season_1</th>
      <th>season_2</th>
      <th>season_3</th>
      <th>season_4</th>
      <th>...</th>
      <th>weekday_0</th>
      <th>weekday_1</th>
      <th>weekday_2</th>
      <th>weekday_3</th>
      <th>weekday_4</th>
      <th>weekday_5</th>
      <th>weekday_6</th>
      <th>weathersit_1</th>
      <th>weathersit_2</th>
      <th>weathersit_3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>14.110847</td>
      <td>18.18125</td>
      <td>80.5833</td>
      <td>10.749882</td>
      <td>985</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>14.902598</td>
      <td>17.68695</td>
      <td>69.6087</td>
      <td>16.652113</td>
      <td>801</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>8.050924</td>
      <td>9.47025</td>
      <td>43.7273</td>
      <td>16.636703</td>
      <td>1349</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>8.200000</td>
      <td>10.60610</td>
      <td>59.0435</td>
      <td>10.739832</td>
      <td>1562</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>9.305237</td>
      <td>11.46350</td>
      <td>43.6957</td>
      <td>12.522300</td>
      <td>1600</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>725</th>
      <td>1</td>
      <td>10.420847</td>
      <td>11.33210</td>
      <td>65.2917</td>
      <td>23.458911</td>
      <td>2114</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>726</th>
      <td>0</td>
      <td>10.386653</td>
      <td>12.75230</td>
      <td>59.0000</td>
      <td>10.416557</td>
      <td>3095</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>727</th>
      <td>0</td>
      <td>10.386653</td>
      <td>12.12000</td>
      <td>75.2917</td>
      <td>8.333661</td>
      <td>1341</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>728</th>
      <td>1</td>
      <td>10.489153</td>
      <td>11.58500</td>
      <td>48.3333</td>
      <td>23.500518</td>
      <td>1796</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>729</th>
      <td>1</td>
      <td>8.849153</td>
      <td>11.17435</td>
      <td>57.7500</td>
      <td>10.374682</td>
      <td>2729</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>730 rows × 34 columns</p>
</div>



## 4 - Construindo um modelo linear

### 4.1 - Separando os dados de treinamento e os dados de teste

Vamos separar 95% dos nossos dados aleatóriamente para fazer o modelo e os outros 5% para fazer testes no final.


```python
# np.random.seed(0)
df_train, df_test = train_test_split(bike_new, train_size = 0.95, test_size = 0.05)
```

### 4.2 - Separando as variáveis independentes e a dependente

Antes será realizada a separação entre a variável dependente e as variáveis independentes.


```python
#Variável dependente
y = df_train["cnt"].copy()
#Variáveis independentes
X = df_train.drop('cnt', axis=1)
```

### 4.3 - Rodando o modelo


```python
modelo1 = (sm.OLS(y,sm.add_constant(X)).fit())
modelo1.summary(title='Sumário do modelo')
```




<table class="simpletable">
<caption>Sumário do modelo</caption>
<tr>
  <th>Dep. Variable:</th>           <td>cnt</td>       <th>  R-squared:         </th> <td>   0.840</td> 
</tr>
<tr>
  <th>Model:</th>                   <td>OLS</td>       <th>  Adj. R-squared:    </th> <td>   0.834</td> 
</tr>
<tr>
  <th>Method:</th>             <td>Least Squares</td>  <th>  F-statistic:       </th> <td>   129.6</td> 
</tr>
<tr>
  <th>Date:</th>             <td>Tue, 08 Nov 2022</td> <th>  Prob (F-statistic):</th> <td>3.36e-244</td>
</tr>
<tr>
  <th>Time:</th>                 <td>15:56:06</td>     <th>  Log-Likelihood:    </th> <td> -5587.9</td> 
</tr>
<tr>
  <th>No. Observations:</th>      <td>   693</td>      <th>  AIC:               </th> <td>1.123e+04</td>
</tr>
<tr>
  <th>Df Residuals:</th>          <td>   665</td>      <th>  BIC:               </th> <td>1.136e+04</td>
</tr>
<tr>
  <th>Df Model:</th>              <td>    27</td>      <th>                     </th>     <td> </td>    
</tr>
<tr>
  <th>Covariance Type:</th>      <td>nonrobust</td>    <th>                     </th>     <td> </td>    
</tr>
</table>
<table class="simpletable">
<tr>
        <td></td>          <th>coef</th>     <th>std err</th>      <th>t</th>      <th>P>|t|</th>  <th>[0.025</th>    <th>0.975]</th>  
</tr>
<tr>
  <th>const</th>        <td> 1283.0008</td> <td>  118.093</td> <td>   10.864</td> <td> 0.000</td> <td> 1051.121</td> <td> 1514.881</td>
</tr>
<tr>
  <th>workingday</th>   <td>  269.9648</td> <td>   51.169</td> <td>    5.276</td> <td> 0.000</td> <td>  169.493</td> <td>  370.436</td>
</tr>
<tr>
  <th>temp</th>         <td>   62.9904</td> <td>   35.072</td> <td>    1.796</td> <td> 0.073</td> <td>   -5.874</td> <td>  131.855</td>
</tr>
<tr>
  <th>atemp</th>        <td>   39.9079</td> <td>   30.011</td> <td>    1.330</td> <td> 0.184</td> <td>  -19.019</td> <td>   98.835</td>
</tr>
<tr>
  <th>hum</th>          <td>  -14.8461</td> <td>    3.041</td> <td>   -4.883</td> <td> 0.000</td> <td>  -20.817</td> <td>   -8.876</td>
</tr>
<tr>
  <th>windspeed</th>    <td>  -41.8600</td> <td>    6.464</td> <td>   -6.476</td> <td> 0.000</td> <td>  -54.552</td> <td>  -29.168</td>
</tr>
<tr>
  <th>season_1</th>     <td> -503.6074</td> <td>  123.139</td> <td>   -4.090</td> <td> 0.000</td> <td> -745.396</td> <td> -261.819</td>
</tr>
<tr>
  <th>season_2</th>     <td>  362.2782</td> <td>  124.109</td> <td>    2.919</td> <td> 0.004</td> <td>  118.586</td> <td>  605.970</td>
</tr>
<tr>
  <th>season_3</th>     <td>  333.0997</td> <td>  131.285</td> <td>    2.537</td> <td> 0.011</td> <td>   75.316</td> <td>  590.883</td>
</tr>
<tr>
  <th>season_4</th>     <td> 1091.2304</td> <td>  127.962</td> <td>    8.528</td> <td> 0.000</td> <td>  839.971</td> <td> 1342.489</td>
</tr>
<tr>
  <th>yr_0</th>         <td> -376.1716</td> <td>   66.749</td> <td>   -5.636</td> <td> 0.000</td> <td> -507.235</td> <td> -245.108</td>
</tr>
<tr>
  <th>yr_1</th>         <td> 1659.1725</td> <td>   66.056</td> <td>   25.118</td> <td> 0.000</td> <td> 1529.468</td> <td> 1788.877</td>
</tr>
<tr>
  <th>mnth_1</th>       <td> -270.3882</td> <td>  182.223</td> <td>   -1.484</td> <td> 0.138</td> <td> -628.191</td> <td>   87.414</td>
</tr>
<tr>
  <th>mnth_2</th>       <td>  -87.5059</td> <td>  171.466</td> <td>   -0.510</td> <td> 0.610</td> <td> -424.185</td> <td>  249.173</td>
</tr>
<tr>
  <th>mnth_3</th>       <td>  314.0708</td> <td>  130.047</td> <td>    2.415</td> <td> 0.016</td> <td>   58.718</td> <td>  569.423</td>
</tr>
<tr>
  <th>mnth_4</th>       <td>  231.8143</td> <td>  158.468</td> <td>    1.463</td> <td> 0.144</td> <td>  -79.344</td> <td>  542.972</td>
</tr>
<tr>
  <th>mnth_5</th>       <td>  506.6890</td> <td>  165.842</td> <td>    3.055</td> <td> 0.002</td> <td>  181.052</td> <td>  832.326</td>
</tr>
<tr>
  <th>mnth_6</th>       <td>  301.3691</td> <td>  158.470</td> <td>    1.902</td> <td> 0.058</td> <td>   -9.793</td> <td>  612.532</td>
</tr>
<tr>
  <th>mnth_7</th>       <td> -142.4901</td> <td>  187.586</td> <td>   -0.760</td> <td> 0.448</td> <td> -510.823</td> <td>  225.843</td>
</tr>
<tr>
  <th>mnth_8</th>       <td>  205.8053</td> <td>  179.931</td> <td>    1.144</td> <td> 0.253</td> <td> -147.495</td> <td>  559.106</td>
</tr>
<tr>
  <th>mnth_9</th>       <td>  745.3960</td> <td>  140.844</td> <td>    5.292</td> <td> 0.000</td> <td>  468.844</td> <td> 1021.948</td>
</tr>
<tr>
  <th>mnth_10</th>      <td>  254.6614</td> <td>  160.113</td> <td>    1.591</td> <td> 0.112</td> <td>  -59.726</td> <td>  569.048</td>
</tr>
<tr>
  <th>mnth_11</th>      <td> -415.5061</td> <td>  170.783</td> <td>   -2.433</td> <td> 0.015</td> <td> -750.845</td> <td>  -80.167</td>
</tr>
<tr>
  <th>mnth_12</th>      <td> -360.9148</td> <td>  148.356</td> <td>   -2.433</td> <td> 0.015</td> <td> -652.218</td> <td>  -69.611</td>
</tr>
<tr>
  <th>weekday_0</th>    <td>  524.3115</td> <td>   73.068</td> <td>    7.176</td> <td> 0.000</td> <td>  380.839</td> <td>  667.784</td>
</tr>
<tr>
  <th>weekday_1</th>    <td>  -19.6029</td> <td>   71.720</td> <td>   -0.273</td> <td> 0.785</td> <td> -160.428</td> <td>  121.222</td>
</tr>
<tr>
  <th>weekday_2</th>    <td> -103.2312</td> <td>   71.577</td> <td>   -1.442</td> <td> 0.150</td> <td> -243.775</td> <td>   37.313</td>
</tr>
<tr>
  <th>weekday_3</th>    <td>    5.7978</td> <td>   71.248</td> <td>    0.081</td> <td> 0.935</td> <td> -134.101</td> <td>  145.696</td>
</tr>
<tr>
  <th>weekday_4</th>    <td>  197.7012</td> <td>   72.107</td> <td>    2.742</td> <td> 0.006</td> <td>   56.116</td> <td>  339.287</td>
</tr>
<tr>
  <th>weekday_5</th>    <td>  189.2998</td> <td>   71.792</td> <td>    2.637</td> <td> 0.009</td> <td>   48.334</td> <td>  330.266</td>
</tr>
<tr>
  <th>weekday_6</th>    <td>  488.7246</td> <td>   72.744</td> <td>    6.718</td> <td> 0.000</td> <td>  345.889</td> <td>  631.560</td>
</tr>
<tr>
  <th>weathersit_1</th> <td> 1227.6004</td> <td>   73.007</td> <td>   16.815</td> <td> 0.000</td> <td> 1084.248</td> <td> 1370.953</td>
</tr>
<tr>
  <th>weathersit_2</th> <td>  770.6161</td> <td>   76.166</td> <td>   10.118</td> <td> 0.000</td> <td>  621.061</td> <td>  920.171</td>
</tr>
<tr>
  <th>weathersit_3</th> <td> -715.2157</td> <td>  151.930</td> <td>   -4.708</td> <td> 0.000</td> <td>-1013.536</td> <td> -416.895</td>
</tr>
</table>
<table class="simpletable">
<tr>
  <th>Omnibus:</th>       <td>122.217</td> <th>  Durbin-Watson:     </th> <td>   1.996</td>
</tr>
<tr>
  <th>Prob(Omnibus):</th> <td> 0.000</td>  <th>  Jarque-Bera (JB):  </th> <td> 312.737</td>
</tr>
<tr>
  <th>Skew:</th>          <td>-0.908</td>  <th>  Prob(JB):          </th> <td>1.23e-68</td>
</tr>
<tr>
  <th>Kurtosis:</th>      <td> 5.745</td>  <th>  Cond. No.          </th> <td>4.86e+16</td>
</tr>
</table><br/><br/>Notes:<br/>[1] Standard Errors assume that the covariance matrix of the errors is correctly specified.<br/>[2] The smallest eigenvalue is 1.56e-27. This might indicate that there are<br/>strong multicollinearity problems or that the design matrix is singular.



### 4.4 - Analisando a tabela

### 4.4.1 - Primeira parte

### 𝑅² e 𝑅² ajustado — Coeficiente de determinação


* O que é $R^2$?

O coeficiente de determinação é uma proporção que ajuda a entender o quanto as variáveis explicativas explicam a variação da média da quantidade de pessoas que alugam bicicletas.

O 𝑅² varia entre 0 e 1, então quanto maior o 𝑅² melhor é o modelo de regressão, pois teria uma maior a capacidade de explicação.

Uma limitação dessa medida é que com a inserção de regressores ao modelo o 𝑅² tende a aumentar.

* Fórmula do 𝑅²


\begin{gather*}
\sum _{t=1}^{T}{}( y_{t} \ -\ \overline{y})^{2} =\sum _{t=1}^{T}{}(\hat{y}_{t} \ -\ \overline{y})^{2} \ +\ \sum _{t=1}^{T}{}( y_{t} \ -\ \overline{y})^{2}\\
SST\ =\ SSR\ +\ SSE\\
R^{2} \ =\ \frac{SSR}{SST} \ ou\ 1\ -\ \frac{SSE}{SST}\\
\\
\end{gather*}

SST = Soma dos quadrados totais (sum of squares total).

SSR = Soma dos quadrados da regressão (sum of squares due to regression).

SSE = Soma dos quadrados dos resíduos (sum of squares error).

* O que é $R^2$ ajustado?

Diferente do 𝑅², o 𝑅² ajustado não sofre a limitação de nunca decair. Caso seja inserido um modelo de regressão uma variável que não seja importante o 𝑅² ajustado irá diminuir.

Uma característica do 𝑅² ajustado é que ele pode ser negativo e por isso ele não pode ser interpretado como uma proporção. Além disso essa medida serve para fazer a comparação entre modelos diferentes.

* Fórmula do 𝑅² ajustado


\begin{gather*}
1\ -\ \ \frac{SSR/( T-K)}{SST/( T-1)} \ \\
ou\\
1\ -\ \left(\frac{T-K}{T-1}\right)\left( 1-R^{2}\right)\\
ou\\
1\ -\ \left( 1-R^{2}\right)\left(\frac{T-1}{T-K}\right)\\
\end{gather*}

T = Número de observações.

K = Número de parâmetros.

### F-statistic e Prob(F-statistic)

Teste de significância conjunta dos parâmetros do modelo.

Hipóteses do teste:


\begin{align*}
H_{0} :& \ \beta _{1} \ =\ \beta _{2} \ =\ ...=\beta _{k} =0\\
H_{1} :& \ não\ H_{0} \
( Pelo\ menos\ uma\ das\ inclinações\ é\ diferente\ de\ zero)\\
\end{align*}

Testa se os coeficientes são conjuntamente nulos e para esse teste deve-se rejeitar a hipótese nula e para rejeitar a hipótese nula precisamos que o valor da estatística gerado no modelo esteja fora da região de aceitação da hipótese nula. Esse teste é conhecido como o teste F.

A regra de rejeição é que


\begin{gather*}
F\  >\ F_{K\ -\ 1;\ \ T-K;\ 1-\alpha }\\
\end{gather*}


O valor foi de 133.0 (cada vez que rodar será diferente) e observando a tabela da distribuição F de Snedecor a 5% [aqui](https://edisciplinas.usp.br/pluginfile.php/3333945/mod_resource/content/1/Distribuicao%20F%205%25.pdf) , veremos que esse valor fica muito acima dos valores limites seja qual for o grau de liberdade (os graus de liberdade são definidos como 𝑛−𝑘).

Conclusão rejeitamos a hipótse nula e os parâmetros/coeficientes são conjuntamente significativos.

O Prob(F-statistic) diz a mesma coisa que o F-statistic : probabilidade da hipótese nula ser verdadeira.

### 4.4.2 - Segunda Parte

Nessa segunda parte constam os parâmetros, o erro padrão de cada coeficiente, a estatística t, seus respectivos p-valores e os intervalos de confiança.

### Coeficientes ou parâmetros


A constante é a média da variável dependente, quando todos os valores das outras variáveis forem zero. Os parâmetros das variáveis independentes medem o impacto na variação média da variável dependente.

### Erro padrão

Erro padrão é uma estimativa do desvio padrão do coeficiente, uma medida da quantidade de variação no coeficiente ao longo de seus pontos de dados.

### Teste de significância individual dos parâmetros


Esse resultado faz parte do teste de hipótese do parâmetro. Nesse teste de hipótese testamos se o parâmetro é estatisticamente igual a um determinado valor, ou seja,


\begin{gather*}
H_{0} :\ \beta _{j} \ =\ \beta _{j}^{0} =0\\
H_{1} :\ \beta _{j} \ \neq \beta _{j}^{0} \neq 0\\
\end{gather*}

O ideal para esse teste é que rejeitemos a hipótese nula.

### P-valor


É uma estatística que relata os resultados de um teste de hipótese, essa estatística satisfaz 0≤𝑝(𝑥)≤1. É conhecido como nível de significância exato ou observado ou probabilidade exata de cometer um erro de Tipo I (rejeitar a hipótese nula quando ela é verdadeira).

Quanto maior o valor dessa estatística, maior a evidência a favor da hipótese alternativa do teste. Aqui o teste é da significância individual dos parâmetros.

## 5 - Análise dos resultados

### 5.1 - Variáveis mais influentes


```python
parametros = modelo1.params 
print(parametros.sort_values(ascending=False))
```

    yr_1            1659.172461
    const           1283.000828
    weathersit_1    1227.600421
    season_4        1091.230374
    weathersit_2     770.616132
    mnth_9           745.396046
    weekday_0        524.311463
    mnth_5           506.689045
    weekday_6        488.724602
    season_2         362.278187
    season_3         333.099655
    mnth_3           314.070795
    mnth_6           301.369102
    workingday       269.964763
    mnth_10          254.661361
    mnth_4           231.814285
    mnth_8           205.805336
    weekday_4        197.701218
    weekday_5        189.299800
    temp              62.990427
    atemp             39.907937
    weekday_3          5.797827
    hum              -14.846082
    weekday_1        -19.602879
    windspeed        -41.860015
    mnth_2           -87.505924
    weekday_2       -103.231203
    mnth_7          -142.490072
    mnth_1          -270.388246
    mnth_12         -360.914850
    yr_0            -376.171633
    mnth_11         -415.506051
    season_1        -503.607388
    weathersit_3    -715.215726
    dtype: float64
    

Temos que as variáveis que mais influenciam a quantidade de bicicletas alugadas:
* **Year**: Houve uma grande diferença do número de bicicletas alugadas do primeiro ano para o segundo ano.
* **weathersit**: A forma como o dia está influencia bastante na quantidade de bicicletas alugadas.
* **Season**: A estão do ano também influencia muito, sendo o verão o coeficiente positivo e no inverno negativo.


```python
colors = {0:"blue", 1:"green"}

sns.scatterplot(x = "dteday", y = "cnt", data =  bike, hue="yr")
# Adicionando legendas as barras
plt.xlabel("Dias")
plt.ylabel("Quantidade de bicicletas alugadas")
plt.title("Quantidade de bicicletas alugadas por dia")

# Criando a legenda e exibindo o gráfico
L=plt.legend()
L.get_texts()[0].set_text(2018)
L.get_texts()[1].set_text(2019)
plt.show()
plt.show()
```


    
![png](output_142_0.png)
    


### 5.2 - Equação da Reta


```python
def equacao(parametros):
    equacao = "cnt = "
    for param, coef in zip(parametros.index, parametros):
        if param == "const":
            equacao += f"({coef}) + "
        elif param == "weathersit_3":
            equacao += f"{param} * ({coef})"
        else:
            equacao += f"{param} * ({coef}) + "
    return equacao

print(equacao(parametros))
```

    cnt = (1283.0008275841926) + workingday * (269.96476310385447) + temp * (62.99042700061759) + atemp * (39.90793693807034) + hum * (-14.846081677272966) + windspeed * (-41.86001491773811) + season_1 * (-503.60738797290736) + season_2 * (362.27818674944444) + season_3 * (333.0996550827772) + season_4 * (1091.2303737248783) + yr_0 * (-376.1716333745937) + yr_1 * (1659.1724609587852) + mnth_1 * (-270.3882461407232) + mnth_2 * (-87.50592362783769) + mnth_3 * (314.07079461537296) + mnth_4 * (231.81428467414233) + mnth_5 * (506.6890454237204) + mnth_6 * (301.3691021599381) + mnth_7 * (-142.49007168961063) + mnth_8 * (205.80533584732933) + mnth_9 * (745.3960456669554) + mnth_10 * (254.66136123507928) + mnth_11 * (-415.5060510144063) + mnth_12 * (-360.91484956576835) + weekday_0 * (524.3114627146174) + weekday_1 * (-19.602879295147527) + weekday_2 * (-103.2312028477437) + weekday_3 * (5.797827474312738) + weekday_4 * (197.7012178554164) + weekday_5 * (189.29979991704616) + weekday_6 * (488.7246017656925) + weathersit_1 * (1227.6004213915203) + weathersit_2 * (770.6161323410106) + weathersit_3 * (-715.2157261483375)
    


```python
df_test.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>workingday</th>
      <th>temp</th>
      <th>atemp</th>
      <th>hum</th>
      <th>windspeed</th>
      <th>cnt</th>
      <th>season_1</th>
      <th>season_2</th>
      <th>season_3</th>
      <th>season_4</th>
      <th>...</th>
      <th>weekday_0</th>
      <th>weekday_1</th>
      <th>weekday_2</th>
      <th>weekday_3</th>
      <th>weekday_4</th>
      <th>weekday_5</th>
      <th>weekday_6</th>
      <th>weathersit_1</th>
      <th>weathersit_2</th>
      <th>weathersit_3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>329</th>
      <td>1</td>
      <td>15.409153</td>
      <td>19.25435</td>
      <td>68.1667</td>
      <td>4.584194</td>
      <td>3068</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>163</th>
      <td>1</td>
      <td>26.035000</td>
      <td>30.08270</td>
      <td>49.4583</td>
      <td>20.458450</td>
      <td>5020</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>234</th>
      <td>1</td>
      <td>26.274153</td>
      <td>30.30335</td>
      <td>45.5417</td>
      <td>9.833121</td>
      <td>5895</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>122</th>
      <td>1</td>
      <td>25.283347</td>
      <td>29.10395</td>
      <td>69.7083</td>
      <td>22.958689</td>
      <td>4451</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>308</th>
      <td>1</td>
      <td>13.393347</td>
      <td>16.19270</td>
      <td>51.9167</td>
      <td>12.667154</td>
      <td>3926</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>...</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 34 columns</p>
</div>




```python
def cnt(parametros, df_dados):
    df_dados_independentes = df_dados.drop('cnt', axis=1)
    dados_depedente = list(df_dados["cnt"])
    previsto = []
    for coluna, valores in df_dados_independentes.iterrows():
        valores_new = [0] + list(valores)
        cnt = 0
        for coef, valor in zip(parametros,valores_new):
#             print(coef, valor)
            if cnt == 0:
                cnt += coef
            else:
                cnt += (coef * valor)
        cnt = "{:0.0f}".format(cnt)
        previsto.append(int(cnt))

    df_cnt = pd.DataFrame({"Previsto": previsto, "Original": dados_depedente})
    return df_cnt
df = cnt(parametros, df_test)     
```


```python
df.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Previsto</th>
      <th>Original</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3596</td>
      <td>3068</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4324</td>
      <td>5020</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4918</td>
      <td>5895</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3772</td>
      <td>4451</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3249</td>
      <td>3926</td>
    </tr>
    <tr>
      <th>5</th>
      <td>842</td>
      <td>1162</td>
    </tr>
    <tr>
      <th>6</th>
      <td>7091</td>
      <td>7767</td>
    </tr>
    <tr>
      <th>7</th>
      <td>3389</td>
      <td>1951</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1559</td>
      <td>1011</td>
    </tr>
    <tr>
      <th>9</th>
      <td>4987</td>
      <td>4833</td>
    </tr>
  </tbody>
</table>
</div>



### 5.3 - Visualização

Vamos agora plotar um gráfico com as previsões e as quantidades reais


```python
previsto_list = list(df["Previsto"])
original_list = list(df["Original"])

# Definindo a largura das barras
barWidth = 0.25

# Aumentando o gráfico
plt.figure(figsize=(10,5))

# Definindo a posição das barras
r1 = np.arange(len(previsto_list))
r2 = [x + barWidth for x in r1]

# Criando as barras
plt.bar(r1, previsto_list, color = "#6A5ACD", width=barWidth, label="Previsto")
plt.bar(r2, original_list, color = "#6495ED", width=barWidth, label="Original")

# Adicionando legendas as barras
plt.xlabel("Dias aleatórios")
plt.ylabel("Quantidade de bicicletas alugadas")
plt.title("Previsão da quantidade de bicicletas alugadas")

# Criando a legenda e exibindo o gráfico
plt.legend()
plt.show()
```


    
![png](output_150_0.png)
    

