# Diseño de redes de atraso por analisis en frecuencia 

- Se busca que el controlador quede lo menos afectado con diferentes frecuencias, el analisis de frecuencia se realiza en tiempo continuo 
- Desde el diagrama de Bole se puede identificar el error de estado estacionario 

## 3 tipos de controladores por analisis de frecuencia 

- Adelanto de fase: Aumenta el ancho de banda del sistema y aunmenta la velocidad de respuesta del sistema pero afecta el ruido 
- Atraso de fase: Respuesta del sistema mas lenta y reduce la afectacion del ruido en el sistema 
- Atraso adelanto: Dentro de Atraso-Adelanto se encuentra el control PID que es un caso particular, donde el control PD reduce las oscilaciones del sistema (red de adelanto) y el control PI elimina la alta frecuencia (red de atraso).

# Margen de ganancia 
- Se mide en el diagrama de Bole
- El margen de ganancia es la ganancia que se requiere en lazo abierto para que el sistema en lazo cerrado sea inestable.
- Para medir el margen de ganancia es necesrio tener como referencia el margen de 180°
$$MG<0 =  negativo $$
$$MG>0  =  positivo $$
- El margen de ganancia No puede ser igual a 0
- El margen de ganancia debe ser lo mas grande posible 
# Margen de fase
- De igual manera el margen de fase en lazo abierto se calcula lo mas grande posible para logar que sea inestable en lazo cerrado 
- $$MP<-180 =  negativo $$
$$MG>-180  =  positivo $$
- Adb = ganancia unitaria 
- $Adb = 20 log A$
- el margen de fase debe ser lo mas grande posible
- si la fase no toca los -180° quiere decir que necesita una ganancia infinita

## Como conocer la respuesta de nuestro sistema en lazo cerrado 

- podemos conocer la respuesta de nuestro sistema en lazo cerrado conociendo los valores de la margen de fase y la margen de ganancia, pero para esto es necesario que se cumplan las siguientes condiciones:
- si mg y mp son positivos podemos concluir que nuestro sistema en lazo cerrado sera estable
- si mg y mp son 0 o negativo el sistema puede ser inestable en lazo cerrado
- ![diagrama de Bole](https://www.monografias.com/trabajos106/compensacion-utilizando-metodos-respuesta-frecuencia/img22.png)

El margen de fase tiene la siguiente relacion con el overshoot
$$margen fase=  \theta ^{-1}\frac{2\zeta }{(4\zeta ^{4}+1-2\zeta ^{2})^{1/2}}$$
$$\theta=100\zeta$$

# Procedimiento de diseño 
- Discretizar el modelo 
- trasformar $G(z)$ a $G(w)$
- Graficar los diagramas de Bode para la funcion $G(w)$

recordando  que $$W= \frac{2z-1}{Tz+1}$$ 
# 💡Ejemplo 
1. ev<10%
2. mp>60°
3. mg>12db
4. $$G(w)=\frac{1}{w(w+2)} $$
Para comenzar hay que corregir el error con la ganancia proporcional 

$$ev= \displaystyle \lim_{w \to 0}= \frac{1}{w\frac{kp}{w(w+2)}}$$

$$ev= \displaystyle \lim_{w \to 0}= \frac{(w+2)}{kp}$$
$$ev= \displaystyle \lim_{w \to 0}= \frac{(0+2)}{kp}$$
$$ev= \displaystyle \lim_{w \to 0}= \frac{2}{kp}$$
$$0.1<  \frac{2}{kp}$$
$$kp<  20$$

![diagrama de Bole](file:///C:/Users/nicol/OneDrive/Escritorio/TRABAJOS%20U/CONTROL%202/mark%20downs/correccion%20del%20error%20con%20kp.jpg)
- de esta manera logramos corregir el error con la accion proporcional 

# Red de atraso 

$$C(w)=\frac{1+aT1w}{1+T1w}<$$
$$0<a<1$$

- calcular el valor de kp
- medir margen de ganancia y fase teniendo en cuenta el kp
- calcular la frecuencia para cumplir con $Mp+6$ y este sera nuestro $G=0$, el Mp+6 es por que nuestra ganancia de fase no es igual al momento de aplicar nuestro kp 
- medir la atenuacion que cumpla con nuestro margen de fase
$$\alpha =-20loga$$
$$a= 10^{\frac{\alpha }{20}}$$
- Calculamos el valor de T1
$$\frac{1}{T1}=\frac{Wg}{10}$$ De esta manera estamos calculado 1 decada antes de la nueva frecuencia 
si $\alpha = 20db$
$$a= 10^-{\frac{20 }{20}}$$
$$a= 0.1$$
$Wg$ es la frecuecnua de ganancia que es necesaria para atenuar el diagrama de Bole
$$\frac{1}{T1}=\frac{Wg}{10}$$
Calculamos T1 en atraso de fase
$$\frac{1}{T1*a}= \frac{Wg}{10}$$
 $$T1= \frac{10}{0.10.908}=110.13$$
 ![Diagrama bole lazo cerrado](file:///C:/Users/nicol/OneDrive/Escritorio/TRABAJOS%20U/CONTROL%202/mark%20downs/cumpliendo%20el%20laxo%20cerrado%20y%20abierto%20.jpg)

# conclusiones 
- El diagrama de bole nos ayuda a identificar las soluciones para la estabilidad de los sistemas siguiendo su margen de fase y de ganancia 
- El diagrama de Bole ayuda con el diseño y ajuste de los controladores como el control PID y saber como el controlador respondera a diferentes frecuencias 
- La solucion por el diagrama de Bole ayuda a mejorar el comportamiento de los sistemas de control para asi asegurar que este sea estable y eficiente




# Referencias
1.extension://efaidnbmnnnibpcajpcglclefindmkaj/https://catedras.facet.unt.edu.ar/sist-control/wp-content/uploads/sites/77/2023/12/Diseno-de-Compensadores-bis-Fadel.pdf
2. https://www.monografias.com/trabajos106/compensacion-utilizando-metodos-respuesta-frecuencia/compensacion-utilizando-metodos-respuesta-frecuencia2

