# Nicolas Rodriguez Diaz 112572
# Juandiego Alvarez Beltran 120688

# Metodos algebraicos

Los metodos algebraicos son utilizados para lograr obtener una respuesta del sistema en lazo cerrado que se desee y para lograr esto se modifica la funcion de transferencia con 2 metodos.

# Igualacion de modelo

Teniendo en cuenta que nuestro sistema $G(z)$ es un sistema que se encuentra el lazo abierto y que conocemos la respuesta que se desea de este sistema podemos implementar una funcion de trasnferencia en lazo cerrado $Go(z)$ de esta manera se asegurara el comportamiento del controlador $C(z)$

De esta manera asi queda nuestro controlador:
Teniendo en cuenta que nuentra funcion de transferencia en lazo cerrado es:$$ Go(z)= \frac{C(z)G(z)}{1+C(z)G(z)}$$
Para hallar nuestro controlador es necesario despejarlo de la ecuacion de $Go(z)$

 - De esta manera el denominadar de la ecuacion pasara a multiplicar a $Go(z)$ quedando de la siguiente manera:
						  $$(1+C(z)G(z))(Go(z))= C(z)G(z)$$
  - Realizando la multiplicacion de $Go(z)$con (1+C(z)G(z))
						  $$Go(z)+Go(z)C(z)G(z)=C(z)G(z)$$
  - Cambiando nuestra igualacion y dejando nuestro termino$Go(z)$
					  $$Go(z)=C(z)G(z)-Go(z)C(z)G(z)$$
  - De la ecuacion anterior sacamos factor comun C(z)
						   $$Go(z)=C(z)(G(z)-Go(z)G(z))$$
- Despejamos C(z)  
						$$Cz=\frac{Go(z)}{G(z)(1-Go(z)}$$
## 💡Ejemplo
- Diseñar un controlador que cumpla con
- Estabilidad
- Comportamiento subamortiguado
- Mp< 5%

Conociendo nuestro sistema en lazo abierto$G(z)$ y conociendo la respuesta que deseamos $Go(z)$
		$$G(z)=\frac{0.004(z+1)}{z^2 -1.819z+0.8187}$$
		$$Go(z)=\frac{0.009z +0.008}{z^2 -1.801z+0.818}$$
		- Y ya habiendo conocido como se comportaba nuestro controlador $C(z)$
						$$Cz=\frac{Go(z)}{G(z)(1-Go(z))}$$
- Remplazamos $Go(z)$ y $G(z)$ en $C(z)$

$$C(z)=\frac{\frac{0.009z+0.008}{z^2 - 1.801z +0.818}}{\frac{0.004(z+1)}{z^2 - 1.819z +0.8187}*(1-\frac{0.009z+0.008}{z^2 -1.801z +0.818})}$$

Operando nuestro $C(z)$ queda de la siguiente manera.
$$C(z)= \frac{1.997z^2 + 0.233z - 1.529}{z^2 + 0.125z - 0.757}$$

- De esta manera podemor obtener la respuesta de nuestro controlador para que cumpla con la respuesta en lazo cerrado de como la deseamos 

# 📚Ejercicio
$$G(z)=\frac{0.01(z+1)}{z^2-2.01z+1}$$
$$Go(z)=\frac{0.009z}{z^2 - 1.801z + 0.818}$$

- Conociendo que nuestro controlador es $$Cz=\frac{Go(z)}{G(z)(1-Go(z))}$$

$$Cz=\frac{\frac{0.009z}{z^2 - 1.801z + 0.818}}{\frac{0.01(z+1)}{z^2 - 2.01z + 1}(1-\frac{0.009z+0.008}{z^2 -1.801z+0.818})}$$

- Multiplicamos en el denominador
 $Denominador=\frac{0.01(z+1)}{z^2 - 2.01z + 1}(\frac{1}{1}-\frac{0.009z+0.008}{z^2 -1.801z+0.818})$

- De esta manera nos queda
$$Cz=\frac{\frac{0.009z}{z^2 - 1.801z + 0.818}}{\frac{0.01(z+1)}{z^2 - 2.01z + 1}\frac{(z^2 -1.801z +0.818 - 0.009z -0.08)}{z^2 - 1.801z + 0.818}}$$

- de esta manera podremos simplificar las expresiones $z^2-1.801z+0.818$ del numerador y del denominador despues de aplicar la ley de extremos

- Quedandonos de esta manera 

$$C(z)= \frac{(0.009z +0.008)(z^2 -2.01z +1)}{0.01(z+1)(z^2-1.801z +0.818-0.009z-0.008)}$$

- Simplificando la expresion de nuestro controlador $C(z)$

$$C(z)= \frac{0.934z^3-1.004z^2-0.822z+0.973}{z^3-0.81z^2-z+0.81}$$
# Igualacion de coeficientes 

De igual manera para el metodo de igualacion de coeficientes sabemos que nuestra funcion de trasferencia en lazo abierto $G(z)$ ya se conoce, y que conocemos la ubicacion de los polos ya que conocemos la forma en la que queremos que nuestro sistema responda. Podemos representar estos polos por medio de un polinomio y asi asegurar que con la implementacion de nuestro controlador $C(z)$ nos asegure el comportamiento de la funcion de trasferencia.

## 💡Ejemplo

la funcion de trasferencia le aplicamos una accion proporcional
$$G(z)= \frac{0.0043}{z^2-1.819z+0.8187}$$

- Ubicacion de los polos:
	- $P1= 0.91+j0.23$
	- $P2=0.91-j0.23$
- Por lo que nuestro polinomio caracteristico sera:
$$(z-0.91+j0.23)(z-0.91-j0.23)$$ 
$$(z^2-0.91z-0.91z+0.82)$$
$$(z^2 -1.82z+0.82)$$ 
 - Recordando que nuestra funcion aplicando la accion proporcional y en lazo cerrado es $Go(z)=\frac{k*G(z)}{1+k*G(z)}$

$$Go(s)=\frac{k*\frac{0.0043}{z^2-1.819z+0.8187}}{1+k*\frac{0.0043}{z^2-1.819z+0.8187}}$$

$$Go(s)=\frac{k*0.0043}{z^2 -1.819z+0.8187+k*0.0043}$$

- ahora tenemos el polinomio en lazo cerrado y el plinomio deseado de esta manera igualamos los polinomios

- polinomio en lazo cerrado $Go(s)$

	$$z^2 -1.819z+0.8187+k*0.0043$$
- polinomio deseado 
$$z^2-1.819z+0.8187$$
- igualamos los polinomios 
$$z^2 -1.819z+0.8187+k*0.0043=z^2 -1.82z+0.82$$
- Se igualan coeficiente a coeficiente por lo que vemos que el segundo coeficiente de nuestro polinomio no es igual al polinomio de nuestro funcion de trasferencia
$$-1.819z=-1.82z$$
- De esta manera con la accion proporcional no se puede hallar nuestro polinomio caracteristico por lo que debemos recurrir a las funciones causales, y teniendo en cuenta que nuestras funciones son:
$$G(z)= \frac{N(z)}{D(z)}$$
$$Go(z)= \frac{No(z)}{Do(z)}$$
$$C(z)= \frac{B(z)}{A(z)}$$

recordando que nuestra funcion de transferencia en lazo cerrado es:

$$Go(z)= \frac{C(z)G(z)}{1+C(z)G(z)}$$

- Remplazando en $Go(z)$ nos queda de la siguiente manera  

$$ Go(z)=\frac{\frac{B(z)}{A(z)}\frac{N(z)}{D(z)}}{1+\frac{B(z)}{A(z)}\frac{N(z)}{D(z)}}$$

- 
- Operando nuestro denominador nos queda de la siguiente manera

$$\frac{1}{1}+\frac{B(z)}{A(z)}\frac{N(z)}{D(z)}$$

$$\frac{A(z)D(z)+ B(z)N(z)}{A(z)D(z)}$$

$$ Go(z)=\frac{\frac{B(z)}{A(z)}\frac{N(z)}{D(z)}}{\frac{A(z)D(z)+ B(z)N(z)}{A(z)D(z)}}$$

de esta manera podemos simplificar las expresiones $A(z)D(z)$ despues de aplicar la propiedades de extremos.
Quedandonos la siguiente expresion 
$$Go(z)= \frac{B(z)N(z)}{A(z)D(z)+ B(z)N(z)}$$

- Sabiendo que en nuestro denominador se encuentra la multiplicacion de $A(z)D(z)$ se agregara un polo a nuestra expresión 
- se utiliza un controlador con la siguiente funcion de trasferencia 
$$C(z)= \frac{Bo}{Ao+A1z}$$
$$G(z)= \frac{0.0043}{z^2-1.819z+0.8187}$$
Remplazamos en nuestra funcion de transferencia:
$$Go(z)= \frac{C(z)G(z)}{1+C(z)G(z)}$$

$$Go(z)= \frac{ \frac{Bo}{Ao+A1z}\frac{0.0043}{z^2-1.819z+0.8187}}{1+\frac{Bo}{Ao+A1z}\frac{0.0043}{z^2-1.819z+0.8187}}$$
$$Go(z)= \frac{0.0043Bo}{A1z^3+(A0-1.819A1)z^2+(0.8187A1 - 1.819A0)z+0.8187A0+0.0043Bo}$$
Teniendo en cuenta que tenemos un polo mas en nuestro nuevo polinomio deseado 

$P1(z-0.91+j0.23)$
$P2(z-0.91-j0.23)$
$P3(z-0.91)$
polinomio deseado 
$$z^3 -2.73z^2 +2.537z-0.8017$$

igualando nuestro polinomio con el denominador de nuestra funcion de trasferencia 

$$A1z^3+(A0-1.819A1)z^2+(0.8187A1 - 1.819A0)z+0.8187A0+0.0043Bo = z^3 -2.73z^2 +2.537z-0.8017$$

nuestro primer termino $z^3$ quedaria de la siguiente manera$A1= 1$
el segundo termino $A0-1.819A1=-2.73$
por lo que para la tercera ecucacion no satisfacen los valores de A0 y A1 por lo que es neceario utilizar un nuevo controlador 
$$C(z)= \frac{Bo+B1z}{Ao+A1z}$$
$$G(z)= \frac{0.0043}{z^2-1.819z+0.8187}$$

De igual manera Remplazamos en $Go(z)$

$$Go(z)= \frac{ \frac{Bo+B1z}{Ao+A1z}\frac{0.0043}{z^2-1.819z+0.8187}}{1+\frac{Bo+B1z}{Ao+A1z}\frac{0.0043}{z^2-1.819z+0.8187}}$$


$$Go(z)= \frac{0.0043(Bo+B1z)}{A1z^3+z^2(A0-1.819A1)+(0.8187A1-1.819A0+0.0043B1)z+0.8187A0+0.0043B0)}$$

igualamos nuestro polinomio caracteristico con el polinomio deseado 

$$z^3 -2.73z^2 +2.537z-0.8017 = A1z^3+z^2(A0-1.819A1)+(0.8187A1-1.819A0+0.0043B1)z+0.8187A0+0.0043B0) $$

De esta manera tenemos 4 incognitas y asi mimso tenemos 4 ecucaciones en el polinomio en lazo cerrado $$A1z^3+z^2(A0-1.819A1)+(0.8187A1-1.819A0+0.0043B1)z+0.8187A0+0.0043B0)$$

$z^3=A1=1$
$z^2=A0-1.819A1=-2.73$
$z=0.8187A1-1.819A0+0.0043B1=+2.537$
$z^0=0.8187A0+0.0043B0=0.8017$

$A1=1$
$B0=-12.99$
$A0=-0.911$
$B1=14.23$

Al momento de resolver encontramos los coeficientes del controlador $$C(z)= \frac{Bo+B1z}{Ao+A1z}$$

$$C(z)= \frac{-12.99+14.23z}{-0.911+z}$$

# Concluciones 

- Con los metodos algebraicos es posible encontrar la respuesta de cualquier sistema en lazo cerrado pero no siempre son impementables estas soluciones 
- Ya que en el metodo algebraico igualacion de los coeficientes  nos concentramos en los polinomios cartacteristicos y deseados (denomidador) no tenemos control sobre los zeros de nuestras funciones 
- Para la igualacion de modelo es necesario tener informacion sobre nuestro sistema, para lograr moldear la funcion de trasferencia en lazo cerrado.
