# Autores:
* Juan Diego Alvarez Beltran 120688
* Nicolas Rodriguez Diaz 112572
* # INTRODUCCION CONTROL DIGITAL 
El control digital es un sistema de tiempo  discreto, solo puede tomar 2 posibles estados a diferencia del analogo que puede tomar cualquier valor a traves del tiempo.
> ### DIFERENCIAS DEL CONTROL DIGITAL Y EL ANALOGO
> 1. En cuanto a la exactitud tiene mayor exactitud el control analogo 
> 2. En cuanto a los errores de implementacion es mejor el control digital
> 3. En cuanto a la velocidad el control analogico es mas rapido, el control digital se debe procesar

###  Estructura de un controlador analogico
```mermaid
graph LR
entrada --> A((error)) ----> B[Controlador]
D --> salida
B --> D[planta]
D -- - -->  A
```
## Estructura de un controlador digital
```mermaid
graph LR
ENTRADA --> A((ERROR)) ----> B[CONVERSION A/D] ----> G[COMPUTADORADIGITAL]----> C[CONVERSION D/A]  ----> 
D[RETENCION]----> E[ACTUADOR]---->H[PLANTA]---->SALIDA
F[RELOJ] 
I[TRANSDUCTOR-SENSOR]
F---->B
F---->C
G---->F
H---->I
I---->A
___
```
## Conversion analogo digital 
1. Muestreo: Se realiza un muestreo cada cierto tiempo, es decir que no se convierte toda la señal y el intervalo de tiempo se realiza en segundos, por lo tanto se mide en Hz
- Al realizar una alta tasa del muestreo se puede obtener mas informacion de la señal, por ende si no se realiza una buena tasa de muestreo se perdera demasiada informacion y no sera fiel a la señal 
-  La tasa de muestreo debe ser periodica "tiempo fijo"
2. Cuantización: La senal analogica se conviertio en una serie de valores que corresponden a cada una de los valores tomados en la relizacion del muestreo
3. Codificación: Se asignan valores binarios a cada una de las muestras obtenidas y a estos les corresponde un valor unico, tambien se determinan la cantidad de bits que se utilizaran para evitar desperdiciar memoria 
## Ejercicios
💡
Señal : $0v-3v$
bits de represnetación = 2 bits 
$$ 2^{2}= 4 $$ posibles simbolos que pueden tomar valores
Rango analogico  $3-0 = 3v$
Representacion $$\frac {3}{4}=0.75v$$
| voltaje |representacion  |
|--|--|
|  0| 00 |
|  0.75v|  01|
|  1.5v|  10|
|  2.25v|  11|

## Ejemplo de realizacion de bits

📚Ejemplo 1

Señal : $0-7 v$
Bits de representación = 2 bits
$$2^{10}=1024$$ Cantidad de bits que realizaran la representación o cantidad de simbolos que puede tomar el muestreo 
Rango analogico : $7-0 =7$
representacion :$$\frac{7}{1023} = 0,006842619$$ Es la variacion del voltaje en el que se realizara cada muestreo $2^{10}-1=1023$

📚Ejemplo 2

Señal : $0-5 V$
Bits de representación = 2 bits
$$2^{4}=16 $$ Cantidad de bits que realizaran la representación o cantidad de simbolos que puede tomar el muestreo 
Rango analogico : $5-0 =5$
representacion : $$\frac{5}{15} = 0,3333333$$ Es la variacion del voltaje en el que se realizara cada muestreo $2^4-1=15$
| VOLTAJE | VALOR |
|---------|-------|
| 0       | 0000  |
| 0.3333  | 0001  |
| 0.6666  | 0010  |
| 0.9999  | 0011  |
| 1.3333  | 0100  |
| 1.6666  | 0101  |
| 1.9999  | 0110  |
| 2.3333  | 0111  |
| 2.6666  | 1000  |
| 2.9999  | 1001  |
| 3.3333  | 1010  |
| 3.6666  | 1011  |
| 3.9999  | 1100  |
| 4.3333  | 1101  |
| 4.6666  | 1110  |
| 5       | 1111  |
___
##	Conversion digital analogica
De igual manera se genera una correspondencia entre los valores digitales y analogicos 

### Metodos de conversión
Por lo general existen 2 tipos de conversión 

### Resistencias ponderadas

1. - Resistencias ponderadas que es facil de configurar pero es inexacto

![resistencias ponderadas](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQjv_TIK1X6lHw9v4E5HgTur2EU-5KTV4gp1w&s)
para calcular el voltaje de salida de las resistencias ponderadas se tiene la siguiente ecuación 

$$ Vo= -Rf(\frac{V1}{R}+\frac{V2}{2R}+\frac{V3}{4R}+...\frac{Vn}{R^N})$$

Donde los valores de las resistencias se deben tomar en orden de K para evitar posibles errores
La cantidad de bits o numeros de circuitos que se encuentren cerrado indicara el bit que se estara representando, es decir que si solo se encuentra el bit N° 2 cerrado se indicara el valor 0100 que se representara de la siguiente manera 
$$ Vo= -Rf(\frac{0}{R}+\frac{V2}{2R}+\frac{0}{4R}+...\frac{0}{R^N})$$

asi indicaremos que es el valor 0100 el que se esta representando en las resistencias ponderadas

### Red escalera R2R
2. - R2R que es mas complicado pero mas exacto

![ CADENA R2R](data:image/png;base64,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)
para calcular el valor del voltaje tenemos la siguiente ecucacion
$$ Vo= -(\frac{Rf}{R})(\frac{V1}{16}+\frac{V2}{8}+\frac{V3}{4}+\frac{V4}{2})$$

## Modelo matematico 

> Para ambos tipos de conversores se manejan los mismos componentes (muestreador, retenedor) estas realizan operaciones opuestas 
> hay que tener unas consideraciones que ocurren en el modelo ideal como que la entrada debe ser de igual magnitud que la salida 
> la conversion se demora en relizarse, pero para las consideraciones se debn tomar como si se hicieran de manera instantanea
>Estos sistemas utilizan un ZERO ORDER HOLD 
>
![zero order hold](https://electrositio.com/wp-content/uploads/2022/08/1660728239_144_Que-es-el-convertidor-analogico-digital-y-su-funcionamiento.jpg)


# Concluciones 
1. Para la conversion de las señales Analogicas a digitales como digitales analogicas es necesaria una buena implementacion de los componentes (amplificadores operacionales, valores de las resistencias).
2. En el metodo de las resistencias ponderadas es muy importante trabajar con resistencias de presicion debido a la gran variedad de resistencias que se manejan, a diferencia del r2r que solo maneja 2 valores de resistencias 
3. el metodo r2r tiende a ser mas presico y estable por lo nombrado anteriormente, solo el uso de dos valores de resistencia 
# Referencias
1. https://www.ecured.cu/Conversi%C3%B3n_Digital_Anal%C3%B3gica
2. [Qué Es El Convertidor Analógico-digital Y Su Funcionamiento - Electrositio](https://electrositio.com/que-es-el-convertidor-analogico-digital-y-su-funcionamiento/)
3. [Conversor digital-analógico | How it works, Application & Advantages (electricity-magnetism.org)](https://www.electricity-magnetism.org/es/conversor-digital-analogico/)