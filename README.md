# Diseño de redes de atraso por análisis de frecuencia
## Introduccion
El diseño de redes de atraso por analis de frecuencia se basa en ajustar la respuesta de un sistema mediante la modificación de su comportamiento en el dominio de la frecuencia. Este se utiliza para reducir la ganancia del sistema en frecuencias altas, lo que ayuda a mejorar la estabilidad y a reducir la sensibilidad al ruido, sin afectar las frecuencias bajas.

En el contexto del análisis de frecuencia, el diseño se apoya en el uso de diagramas de Bode, que son representaciones gráficas de la respuesta en frecuencia de un sistema. A través de estos diagramas, es posible medir y ajustar los márgenes de estabilidad del sistema, como el margen de ganancia y el margen de fase, que indican cuánta ganancia o fase se puede agregar al sistema antes de que se vuelva inestable.
## Ventajas del diseño por diagrama de bode
Estos gráficos permiten visualizar el error en estado estacionario y el análisis de frecuencia. Además, facilitan la medición directa de los márgenes de estabilidad de una manera muy similar a los diseños en el dominio del tiempo cuando las funciones se realizan a una frecuencia angular (w).
## Controladores por análisis en frecuencia
El compensador de adelanto de fase es el que incrementa la velocidad de respuesta del sistema y los márgenes de estabilidad, el compensador de atraso de fase es el que reduce la ganancia en frecuencias altas sin afectar las bajas, reduciendo el ancho de banda y mejorando la resistencia al ruido y el compensador atraso-adelanto, combina las ventajas de ambos compensadores, mejorando márgenes de estabilidad, ancho de banda y reduciendo el error en estado estacionario.
## Control PID
Este tipo de controlador es un caso especial de compensación atraso-adelanto. La parte PD afecta las altas frecuencias y mejora el ángulo de adelanto de fase, lo que incrementa la estabilidad del sistema. Por otro lado, la parte PI actúa como una red de atraso. Aunque es posible sintonizar un PID mediante análisis en frecuencia, la sintonización generalmente se realiza en el dominio del tiempo debido a su facilidad de análisis.
## Margen de ganancia
El margen de ganancia (MG) es el cambio en la ganancia de lazo abierto requerido para que un sistema en lazo cerrado sea inestable. Se mide en decibelios (dB) y se toma como referencia la fase de 180°. Si MG es positivo, el sistema es estable; si es negativo, el sistema puede volverse inestable.
## Margen de fase
El margen de fase (MP) es el cambio en la fase de lazo abierto necesario para que un sistema en lazo cerrado se vuelva inestable. Este se mide en grados y se toma como referencia cuando la ganancia es unitaria (0 dB). Un MP mayor a -180° indica estabilidad, mientras que un MP menor a -180° puede indicar inestabilidad.
## Imagen de ejemplo
![Figura de ejemplo en clase](images/plantilla/Captura2.PNG)
Un sistema con MG y MP positivos es estable, pero si alguno de estos márgenes es cero o negativo, el sistema puede volverse inestable. Además, se recomienda que estos márgenes sean lo más grandes posible para garantizar estabilidad.
## Respuesta temporal en sistemas continuos y su relación entre margen de fase y maximo sobreimpulso
Para sistemas de segundo orden, el margen de fase está directamente relacionado con el porcentaje del maximo sobreimpluso (%overshoot). Generalmente, este sobrepaso se aproxima con base en el margen de fase disponible. El margen de fase y el porcentaje de sobrepaso están relacionados, de modo que un mayor margen de fase reduce el overshoot en la respuesta del sistema. 
## Procedimiento de diseño
Para diseñar un controlador utilizando análisis en frecuencia se deben seguir lo siguientes pasos: Primero, se discretiza la planta analógica para obtener su equivalente digital G(z), luego se transforma a G(w) y se grafican los diagramas de Bode. A partir de estos gráficos, se diseña la compensación necesaria y se recupera la función C(z) para implementarla en el controlador digital.
## Ejemplo
Se presenta un ejemplo práctico de cómo corregir el error de estado estacionario utilizando un compensador.
