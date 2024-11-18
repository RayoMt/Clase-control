# Nicolas Rodriguez Diaz 112572
# Juan Diego Alvarez Beltran 120688


# Espacio de Estados a partir de una funcion de trasferencia

- Hay tantas formas de espacio de estados que ya se han estudiado algunas a profundidad como
1. Forma canonica controlable
2. Forma canonica observable 
3. Forma canonica diagonal

# Forma canocica controlable 
En la forma canonica controlable se puede construir el espacio de estados con los coeficientes de nuestra funcion de trasferencia.
- Teniendo la funcion de trasferencia
- $$G(z)=\frac{b_{0}z^{n}+b_{1}z^{n-1}+...+ b_{n-1}z+b_{n}}{z^{n}+a_{1}z^{n-1}+...+a_{n-1}z+a_{n}}$$

- Es posible obtener la forma canonica controlable de la siguiente manera
$$\begin{vmatrix}
x_{1}(k+1) \\x_{2}(k+1)
 \\...
 \\ x_{n-1}(k+1)
 \\ x_{n}(k+1)
\end{vmatrix}$$


- La cantidad de variables de estado sera dependiente del grado de la funcion de trasferencia 
- nuestra matriz $A$
$$\begin{bmatrix}
0& 1  &0  & ... & 0  \\
 0& 0 &1  &...  &0 \\
 0& 0 & 0 & 1 &0 \\
 -a_{n}&-a_{n-1}  & -a_{n-2} & ...  &-a_{1} \\
\end{bmatrix}$$
- se agrega un 0 en la primera posicion y se llena un estilo de matriz identidad hasta que 1 llegue al final 
- solo hay coeficientes en la ultima fila de la matriz, se gira el polinomio caracteristicos y cambia el signo de este.
- Se multiplica por la cantidad de variables de estado que especifique el grado del polinomio
$$\begin{vmatrix}
x_{1}(k) \\
 x_{2}(k)\\
 ...\\
 x_{n-1}(k)\\
x_{n}(k)
\end{vmatrix}$$
- matriz de entrada, solo va un 1 en la ultima fila de esta matriz que se multiplicara con nuestro polinomio de la matriz $A$
- esta sera nuetsra matriz $B$
$$\begin{vmatrix}
0 \\
 0\\
 ...\\
 0\\
1
\end{vmatrix} u(K)$$

Nos queda de la siguiente manera 
$$\begin{vmatrix}
x_{1}(k+1) \\x_{2}(k+1)
 \\...
 \\ x_{n-1}(k+1)
 \\ x_{n}(k+1)
\end{vmatrix} =
\begin{bmatrix}
0& 1  &0  & ... & 0  \\
 0& 0 &1  &...  &0 \\
 0& 0 & 0 & 1 &0 \\
 -a_{n}&-a_{n-1}  & -a_{n-2} & ...  &-a_{1} \\
\end{bmatrix}
\begin{vmatrix}
x_{1}(k) \\
 x_{2}(k)\\
 ...\\
 x_{n-1}(k)\\
x_{n}(k)
\end{vmatrix}+
\begin{vmatrix}
0 \\
 0\\
 ...\\
 0\\
1
\end{vmatrix} u(K)$$

de esta manera cumplimos con las ecuaciones de estado:
$$x(k+1)=Ax(k)+Bu(k)$$
para la ecuacion de estado de salida nos queda de la siguiente manera 
$$y(k)=
\begin{vmatrix}
b_{n} &b_{n-1}  &b_{n-2}&... &b_{1}  \\
\end{vmatrix}$$



- Esta sera nnuestra matriz $C$
-$$\begin{bmatrix}
x_{1}(k) \\
x_{2}(k) \\
 ...\\
 x_{n-1}(k)\\
x_{n}(k)
\end{bmatrix}$$

nuestra matriz $D$ sera igual a 0 por lo que es un sistema de una entrada y una salida, por lo que nuestra ecuacion en estado quedara de la siguiente manera
 $$y(k)=Cx(k)+Du(k)$$
  $$y(k)=Cx(k)+0u(k)$$
   $$y(k)=Cx(k)$$
- se gira el polinomio pero no se le cambia el signo
$$y(k)=
\begin{vmatrix}
b_{n} &b_{n-1}  &b_{n-2}&... &b_{1}  \\
\end{vmatrix}\begin{bmatrix}
x_{1}(k) \\
x_{2}(k) \\
 ...\\
 x_{n-1}(k)\\
x_{n}(k)
\end{bmatrix}$$

# Forma canonica observable 
- aunque ya sabemos la respuesta por la forma canonica controlable es bueno  conocer la forma matematica por que esta si varia y nos puede mostrar un camino mas sencillo
- teniendo esta ecuacion de diferencia 
$$G(z)=\frac{b_{0}z^{n}+b_{1}z^{n-1}+...+ b_{n-1}z+b_{n}}{z^{n}+a_{1}z^{n-1}+...+a_{n-1}z+a_{n}}$$
- Es posible obtener la forma canonica observable de la siguiente manera 
$$\begin{vmatrix}
x_{1}(k+1) \\x_{2}(k+1)
 \\...
 \\ x_{n-1}(k+1)
 \\ x_{n}(k+1)
\end{vmatrix}$$
- Cambia nuestra matriz $A$ ya que en esta matriz ya no ira en la ultima fila de la matriz, si no ir ubicada en la ultima columna, de igual manera el cambio de la ubicacion de nuestra matriz identidad 
- $$\begin{bmatrix}
0& 0  &0  & ... & -a_{n}& \\
 1& 0 &0  &...  & -a_{n-1}\\
 0& 1 & 0 & ... & -a_{n-2} \\
 0&0  & 1 & ...  &-a_{1} \\
\end{bmatrix}$$

$$\begin{vmatrix}
x_{1}(k) \\x_{2}(k)
 \\...
 \\ x_{n-1}(k)
 \\ x_{n}(k)
\end{vmatrix}$$
- De igual manera nuestra matriz $C$ ya no estara ubicada en nuetra ecuacion de salida si no que etsara ubicada en nuestra ecuacion de entrada
- $$\begin{vmatrix}
b_{n} \\b_{n-1}
 \\...
 \\ b_{2}
 \\ b_{1}
\end{vmatrix} u(k)$$ 
- Nuestra ecuacion de salida quedara de la siguiente manera ya que cambia, por el cambio de nuestra matriz $C$ va a ir una fila de 0 pero la ultima fila sera un 1
- $$y(k)=
\begin{vmatrix}
0 & 0 & ... & 0 & 1 \\
\end{vmatrix}
\begin{vmatrix}
x_{1}(k) \\x_{2}(k)
 \\...
 \\ x_{n-1}(k)
 \\ x_{n}(k)
\end{vmatrix}$$

# Forma canonica diagonal
- En la forma canonica diagonal no ocuparemos el polinomio caracteristico si no ocuparemos los polos del sistema pero estos deben ser diferentes todos
$$P_{1}=z_{1};P_{2}=z_{2};...;P_{n}=z_{n}$$
$$\begin{vmatrix}
x_{1}(k+1) \\x_{2}(k+1)
 \\...
 \\ x_{n-1}(k+1)
 \\ x_{n}(k+1)
\end{vmatrix}$$
igual que en las formas anteriores mantenemos la estructura
- La matriz $A$ cambiara ya que ubicaremos los polos de nuestro sistema en la diagonal de la matriz identidad.
 $$\begin{bmatrix}
P_{1}& 0  &0  & ... & 0 \\
 0& P_{2} &0  &...  & 0\\
 0& 0 & P_{3} & ... & 0 \\
 0&0  & 0 & ...  &P_{n} \\
\end{bmatrix}$$

$$\begin{vmatrix}
x_{1}(k) \\x_{2}(k)
 \\...
 \\ x_{n-1}(k)
 \\ x_{n}(k)
\end{vmatrix}$$
- en nuestra matriz de entrada rellenaremos todo con $1$

$$\begin{vmatrix}
1 \\1
 \\...
 \\ 1
 \\ 1
\end{vmatrix} u(K)$$

$$\begin{vmatrix}
x_{1}(k+1) \\x_{2}(k+1)
 \\...
 \\ x_{n-1}(k+1)
 \\ x_{n}(k+1)
\end{vmatrix}=
\begin{bmatrix}
P_{1}& 0  &0  & ... & 0 \\
 0& P_{2} &0  &...  & 0\\
 0& 0 & P_{3} & ... & 0 \\
 0&0  & 0 & ...  &P_{n} \\
\end{bmatrix}
\begin{vmatrix}
x_{1}(k) \\x_{2}(k)
 \\...
 \\ x_{n-1}(k)
 \\ x_{n}(k)
\end{vmatrix}+
\begin{vmatrix}
1 \\1
 \\...
 \\ 1
 \\ 1
\end{vmatrix} u(K)$$
- Nuestra matriz de salida se llenara con los coeficcientes de las fracciones parciales que se generaran al momento de separar nuestros polos
$$y(k)= 
\begin{vmatrix}
c_{1} &c_{2}  & ...  & c_{n-1} & c_{n} \\
\end{vmatrix}
\begin{vmatrix}
x_{1}(k) \\x_{2}(k)
 \\...
 \\ x_{n-1}(k)
 \\ x_{n}(k)
\end{vmatrix}$$

# Ejemplo canonica diagonal 💡


$$g(z)=\frac{z+1}{z^{2}+1.3z+0.4}=\frac{C_{1}}{z+0.5}+\frac{C_{2}}{z+0.8}$$
$$z+1=C_{1}(z+0.8)+c_{2}(z+0.5)$$
$$z+1=z(C_{1}+C_{2})+C_{1}*0..8+C_{2}*0.5$$
$$1=C_{1}+C_{2}$$
$$1=0.8C_{1}+0.5C_{2}$$ 2 ecuaciones y 2 incognitas
- Solucion de las ecuaciones
$$c_{1}=1-c_{2}$$
$$1=0.8(1-C_{2})+0.5C_{2}$$
$$c_{2}=-\frac{2}{3}$$
$$c_{1}=1-(-\frac{2}{3})=\frac{5}{3}$$

- Representado en las matrices, y ubicando los polos en la diagonal correspondiente 
$$\begin{vmatrix}
x_{1}(k+1) \\ x_{2}(k+1)
\end{vmatrix}=
\begin{vmatrix}
-0.5 & 0 \\
 0& -0.8 \\
\end{vmatrix}
\begin{vmatrix}
x_{1}(k) \\ x_{2}(k)
\end{vmatrix}+
\begin{vmatrix}
1\\ 1
\end{vmatrix} u(k)$$
$$y= \begin{vmatrix}
\frac{5}{3} & -\frac{2}{3}  \\
\end{vmatrix}
\begin{vmatrix}
x_{1}(k) \\ x_{2}(k)
\end{vmatrix}
$$
# Ejemplo 2 forma canonica y observable 💡

$$G(z)=\frac{z+1}{z^{2}+1.3z+0.4}$$
### forma canonica controlable
- forma canonica controlable a partir de la funcion de trasferencia, recordando cambiar de signo y girar nuestro polinomio caracteristico 

$$\begin{vmatrix}
x_{1}(k+1) \\ x_{2}(k+1)
\end{vmatrix}= 
\begin{vmatrix}
0 & 1 \\
 -0.4&-1.3  \\
\end{vmatrix}
\begin{vmatrix}
x_{1}(k) \\ x_{2}(k)
\end{vmatrix}+
\begin{vmatrix}
0 \\ 1
\end{vmatrix}u(k)$$
- Matriz de salida recordando que la matriz de salida es con los coeficientes de los zeros de nuetro sistema
- $$y=\begin{bmatrix}
1 & 1 \\
\end{bmatrix}\begin{vmatrix}
x_{1}(k) \\ x_{2}(k)
\end{vmatrix}$$

### forma canonica observable



- Utilizando la misma funcion de trasferencia, recordando que en la forma canonica observable los coeficientes de nuestros polinomios caracteristico ahora se hubicaran en la ultima columna
$$\begin{vmatrix}
x_{1}(k+1) \\ x_{2}(k+1)
\end{vmatrix}= 
\begin{vmatrix}
0 & -0.4 \\
 1 &-1.3  \\
\end{vmatrix}
\begin{vmatrix}
x_{1}(k) \\ x_{2}(k)
\end{vmatrix}+
\begin{vmatrix}
1 \\ 1
\end{vmatrix}u(k)$$
- Ecuacion de salida
- $$y=
\begin{vmatrix}
0 & 1 
\end{vmatrix}
\begin{vmatrix}
x_{1}(k) \\ x_{2}(k)
\end{vmatrix}
$$

# Espacio de estados a funcion de trasferencia

$$X(k+1)=AX(k)+Bu(k)$$
$$Y(k)=CX(k)+Du(k)$$
- Se aplica trasformada z termino a termino
$$zX(z)= AX(z)+Bu(z)$$
$$Y(z)= CX(z)+Du(z)$$
- Despejando $\frac{Y(z)}{U(z)}$ Para hallar las entradas del sistema
$$zX(z)-AX(z)=Bu(z)$$
Sacamos la inversa multiplicada a ambos lados quedandonos de la siguiente manera 
$$X(z)=(zI-A)^{-1}BU(z)$$
conociendo nuestro x(z) remplazamos en la funcion 
$$Y(z)= CX(z)+Du(z)$$
quedndo de la sigueinte manera
$$Y(z)= C(zI-A)^{-1}BU(z)+Du(z)$$
factorisamos $u(z))$

$$Y(z)= (C((zI-A)^{-1}B)+D)u(z)$$
de aca ya podemos despejar para dejar en terminos de $\frac{Y(z)}{U(z)}$

$$\frac{Y(z)}{U(z)}= (C((zI-A)^{-1}B)+D)$$
# Concluciones

- Si se trabaja con funcion de trasferencia solo se puede hallar 1 sistema que nos asegure el comportamiento 
- El trabajar con las formas de espacio de estados no ayuda a simplificar el analisis del sistema ya que son formas estudiadas y probadas pero no cumplen en todos los sistemas
- Podemos representar el mismo sistema pero con diferentes matrices dependiendo la forma de espacio de estados que utilicemos
