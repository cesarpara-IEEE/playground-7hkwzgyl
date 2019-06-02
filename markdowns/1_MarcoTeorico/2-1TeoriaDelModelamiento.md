
### 2.1. Teoría de modelamiento de un sistema 

El objetivo de modelar un sistema, de caracterizar matemáticamente consiste en llegar a describirlo en la forma más completa, exacta y sencilla posible, para posteriormente analizarlo y poder realizar diseños de controladores de tal manera que su funcionamiento se adecue a los requerimientos de diseño. El modelo matemático se basa en una o varias ecuaciones que representan el comportamiento del sistema, pero no representan un único modelo, pues se pueden lograr representaciones diferentes del mismo sistema que no contradicen una a la otra. Sin embargo, es útil encontrar el modelo que proporcione información de interés para cada problema en particular.

Realizar un modelo físico comprende dos aspectos importantes: hallar las características dinámicas del sistema con base en la teoría matemática, desarrollos experimentales y la información que se tenga de la planta; para posteriormente realizar aproximaciones bajo criterios válidos que simplifiquen el resultado obtenido.

Las consideraciones y aproximaciones se realizan con base en las simulaciones iterativas de las respuestas que el modelo presenta con respecto a las que debería tener el sistema real. De la escogencia de estas se obtiene un modelo del sistema sobre el cual se realizará un controlador que tendrá éxito según la exactitud del modelo especificado.

En este orden de ideas se puede decir que para el modelamiento de un sistema térmico, que es el problema a tratar, deben tenerse en cuenta diferentes parámetros físicos y experimentales del sistema que permitan obtener una representación aproximada de la planta a partir de la relación entre entrada y salida, teniendo en cuenta los fenómenos no lineales y estableciendo las consecuencias que esto trae en su respectivo modelamiento.


#### *2.1.1  Modelamiento a partir de variables internas de un sistema térmico*

Como un método adicional al análisis de sistemas a partir de las entradas y salidas del mismo es posible establecer un modelo que tenga en cuenta las características físicas y en específico térmicas, propias de la planta. Sin embargo estos métodos no son estrictamente independientes y es útil hacer un acercamiento entre estos para obtener una aproximación más acertada del comportamiento real del sistema. Para lograrlo se deben tener en cuenta tres aspectos:

A partir de las variables a controlar, se debe tener en cuenta cuales son las entradas, salidas y variables internas del proceso. De la misma forma se deben tener en cuenta cuales son las constantes y parámetros que intervienen.

En segunda instancia se describen las relaciones matemáticas que involucran todos los parámetros físicos involucrados, para que finalmente se determinen ecuaciones que enlazan estas relaciones, formando así un modelo que puede ser comparado y ajustado con respecto a otros métodos de modelado, como el de relación entradas, salidas del sistema.

En los Sistemas térmicos, las variables involucradas son: la temperatura $`T(°C)`$ y el flujo de calor por unidad de tiempo que es la potencia transferida al sistema, $`f=\frac{dQ}{dt}(w)`$ y la energía definida como $`Q=\int fdt(w_s)`$. Por otro lado se deben tener en cuenta el calor específico
$`c \frac{w_s}{kg °C}`$ definido como la cantidad de calor necesario para aumentar la temperatura de una masa unitaria un grado centígrado, además la relación entre el flujo de calor $`f`$ el gradiente de temperaturas que resulta ser una variable llamada resistencia térmica $`R=\frac{\Delta T}{f}\frac{°C}{w}`$.

Normalmente la temperatura no es homogénea en un cuerpo y por lo contrario presenta gradientes de temperatura que dan lugar a ecuaciones diferenciales con derivadas parciales y parámetros distribuidos. Por este motivo se hacen simplificaciones a modelos donde el cuerpo se divide en pequeñas regiones que se consideran como homogéneas, e isotérmicas simplemente suponiendo homogeneidad en todo el sistema debido a condiciones particulares.

En termodinámica se definen algunas propiedades físicas que relacionan la temperatura y el flujo de calor, una de estas es la transferencia de calor que se puede dar por conducción, convección y radiación, En la práctica el intercambio de calor puede mezclar los tres modos, la transferencia por convección se presenta entre partículas adyacentes impartiendo energía entre un nivel más alto a un nivel más bajo, se puede definir la conducción como la proporcionalidad del flujo de calor por unidad de área a la conductividad térmica y un gradiente de temperatura, donde la conductividad es una característica física propia de los materiales.

La convección, más relacionada con la transferencia que se da dentro del horno para este proyecto, implica el intercambio de energía entre un fluido compacto y una superficie, similar a la que se genera naturalmente a través del aire caliente que sube desde la superficie, o la generada por medio de un ventilador. La convección se define como la cantidad de calor movida que depende de cuánto calor puede transportar el medio $`Q=hA(T_in-T)`$ donde A es el área de la superficie normal a la dirección de flujo y h es el coeficiente de transferencia de calor $`\frac{w}{m^2°C}`$ propio de cada fluido. Para el aire $`5<h<30`$

El calentamiento de un horno suele modelarse teniendo en cuenta la aproximación mencionada de suponer una temperatura homogénea dentro del mismo. En un punto se genera una potencia calorífica $`P`$ dada en vatios $`(W)`$, de la que una parte se emplea para calentar un cuerpo $`P_c`$ y el resto fluye hacia el exterior $`P_{ext}`$ Dados que la construcción física del horno contempla una resistencia y una capacidad térmica $`R, C`$, se tiene que por convección se transmitirá calor del punto que genera potencia hacia todo el interior del horno. Este punto que genera potencia es una fuente de flujo de calor $`f`$ equivalente aproximadamente a la potencia disipada por el resistor, en otras palabras $`f=P=V*I`$ donde $`V, I`$ es el voltaje y la corriente proveniente de la red eléctrica sobre el resistor que genera el flujo de calor.

Se denominará por consecuencia con las variables térmicas a $`P_{ext}`$ y $`P_c`$ como flujos de calor $`f_{ext}`$ y $`f_c`$ respectivamente.

De esta forma se tiene la siguiente ecuación diferencial dada en derivadas ordinarias y como una representación lineal del modelo:

$`C\frac{dT}{dt}=f_c=P-f_{ext}=p-\frac{T-T_{ext}}{R}`$

Donde $`T_{ext}`$ es  la temperatura exterior o la temperatura ambiente.

Por último en diagrama de bloques se tiene:
