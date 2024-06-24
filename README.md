# Análisis de Criptomonedas

## Eleccion de las monedas:

Entendiendo que las monedas mas valoradas son las que tienen mayor capitalizacion de mercado, el primer criterio para la elección sera la capitalizacion de mercado. Por otro lado, como se haran comparaciones entre las monedas, es importante distinguir las monedas estables de las que tienen mayor variacion. Por ello, se eligen 5 monedas de la categoria Layer-1 (Dogecoin no es del tipo layer_1) y 5 monedas del tipo StableCoin.

Las 4 primeras monedas de Layer-1 son elegidas por capitalizacion de mercado, la quinta; Dogecoin es elegida dado que mediante sucesivos Tweets, Elon Musk la recomendaba y la des recomendaba de manera frecuente. Es por ello que el driver para su movimiento de precio es en esos casos distinto a las otras monedas que generalmente su variacion de precio esta relacionada al Bitcoin. Para estudiar estas relaciones, se elige Doge por fuera del criterio de la capitalizacion de mercado.

Por el lado de las stable-coin, las 3 primeras elegidas (Tether, Usd-coin, Dai) estan en orden de capitalización de mercado, pero tambien es importante destacar que tanto Tether como Usd-coin estan respaldadas en dolares. En tanto que Dai es una moneda que no tiene respaldo en dolares fisicos, sino que su precio esta controlado por distintos algoritmos que emiten o queman monedas para mantener el precio. Por ultimo, las otras dos monedas restantes son respaldadas en oro. Esta diversidad en fundamentos, alienta la búsqueda de información valiosa desde los datos.

En la siguiente lista se pueden ver las monedas elegidas para el analisis.

CoinList = 'bitcoin', 'ethereum', 'binancecoin', 'solana', 'dogecoin', 'tether', 'usd-coin', 'dai', pax-gold', 'tether-gold'

### Funciones utilizadas:
**date_price_market_caps_volume(coin):**

Esta funcion utiliza el get de coingecko para tomar el precio, market_cap, total_volumes. Se cambian Nans por el valor al siguiente muestra. 
Luego se realizan algunas transformaciones, se agregan columnas de caracteristicas normalizadas como precio , marketcap, y volumen, todas ellas respecto al maximo y se expresan en %. Estos dataframes tendran una granularidad diaria.
Se corroboró que solo algunas monedas tienen valores Nan, y las que lo tienen, lo tienen en 'market_cap' 
Con esta funcion se generan 10 DataFrames.

**dicc_nomb(df, coin):**

Funcion utilizada para cambiar los nombres que tienen por defecto los DataFrames. Se le agrega al final del nombre de cada campo el nombre de la moneda para poder realizar luego un merge.

**OHLC(coin):**
Esta funcion genera un dataframe con los datos de: precio de apertura, precio de cierre, maximo minimo del intevalo de tiempo. El intervalo de tiempo es 4 dias. Ademas se crean otras dos columnas, variacion entre apertura y cierre respecto a la apertura, y variacion entre max y min respecto a la media del intervalo en %.
Se ha comprobado que no requiere que se realicen eliminacion de nulos o Nans.
En la funcion, se agregan dos columnas, una para Variacion respecto apertura / cierre y otra para la variacion respecto al max / min del intervalo.





#### **Conclusion 1**

De las 10055 monedas, solo bitcoin tiene el 48.2 % del total del marketcap, y entre las primeras 5 monedas está el 80 % del total.

#### **Conclusion 2**

En el top 5 de arriba, solo figura una sola moneda del tipo "stablecoin": tether, que se encuentra en el puesto 3. En el puesto 6 figura la segunda, usd-coin.

#### **Conclusion 3**

En la gráfica del precio normalizado (monedas Layer-1) puede verse que hay alguna correlacion en la variacion, generalmente atadas a la variacion del precio del bitcoin.

#### **Conclusion 4**

Las monedas DogeCoin y Solana tienen menor correlacion respecto a las otras tres que se mueven de manera parecida.

#### **Conclusion 5**:

Se observa mayor variacion en las monedas USDT, USDC, y DAI al comienzo de vida de cada moneda.
Ademas se ve inestabilidad respecto al dolar de las monedas PAXG y XAUT, como era de esperarse ya que estan respaldadas en ORO.

#### **Conclusion 6**

Este grafico muestra la variacion de monedas en circulacion de las monedas respaldadas en dolar. Esta variacion es menor en DAI (por sus fundamentos como se comento antes), y es casi nula en las monedas respaldadas en oro.

#### **Conclusion 7**

Puede verse la variacion en escalon de la moneda XAUT a diferencia de la monenda PAXG. A que se debe esta variacion podria estudiarse en un futuro.

#### **Conclusion 8**

Del conjunto de monedas con "precio variable", la que tiene **menor** variacion de precio en el intervalo de tiempo dado de 4 dias, es bitcoin, seguida por ethereum.






