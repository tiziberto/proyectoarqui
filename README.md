# Proyecto Integrador Arquitecturas en Computadoras 1

Este proyecto te permite acceder a diferentes secuencias de luces utilizando un menu que accederemos con una contraseña.

## Índice
1. [Especificaciones Técnicas](#especificaciones-técnicas)
2. [Contraseña para el Menú Principal](#contraseña-para-el-menú-principal)
3. [Menú](#menú)
4. [Instrucciones de Uso](#instrucciones-de-uso)
5. [Fallas conocidas](#fallas-conocidas)

## Especificaciones Técnicas
Utilizamos la placa DE0-Nano FPGA Altera Cyclone IV. La placa está compuesta de 8 leds, dos botones (boton 0 y boton 1), y 4 dipswitches ([3][2][1][0]). El boton 0, fue destinado a resetear el sistema.
Usted ingresará al sistema con una contraseña. Tiene 3 intentos para ingresar, en caso de que se fallen todos los intentos, se encenderán los 8 leds, indicando que es no es posible continuar en el sistema. 

## Contraseña para el Menú Principal
Para acceder al menú principal, utiliza la siguiente contraseña: `4 switches para arriba (1111)`

## Menú
El menú te permite acceder a las siguientes secuencias:

### 1. Auto Fantástico
La secuencia del "Auto Fantástico" realiza un barrido de las luces para un lado y luego para el otro.

### 2. Carrera
Carrera entre 2 luces, con ventaja de una luz por ser mas lenta.

### 3. Tetris
La secuencia representa el famoso videojuego “tetris”, bloques cayendo de arriba hacia abajo y llenándose el tablero de a poco hasta llegar al punto de altura máxima y perdiendo.

### 4. Policía
Luces policiales con diferentes combinaciones.

## Instrucciones de Uso
1. Ingresa la contraseña proporcionada a través de los dipswitches para acceder al menú principal. En este caso la contraseña es 1111, es decir, todos los switches levantados. Para confirmar la contraseña, deberá pulsarse el boton 1.
2. En caso de que la contraseña se confirme, se encenderá por un momento el último led de la derecha es decir el led [7] y se ingresará al menu. 
El menú consta de 4 leds que se mueven iterativamente de derecha a izquierda hasta el cuarto led, es decir el led [3], arrancando desde el led [0].
Cada luz encendida, indica una secuencia distinta de luces. 
Led [0] encendido: Auto Fantastico. 
Led [1] encendido: La Carrera.
Led [2] encendido: Tetris.
Led [3] encendido: Auto de policia.
3. Para ingresar a cada secuencia, se pulsara el boton [1] en el momento de que luz de la secuencia deseada esté encendido.
4. Una vez ingresado a la secuencia, si se quiere volver al menu en cualquier momento, deberá bajarse el dipswitch[0] y se pulsará el boton [1]
5. Finalmente, una vez en la secuencia, podemos cambiar la velocidad en la que se ejecutan estas. Para ello, deberá subirse el dipswitch[0] y 
si se quiere subir la velocidad, deberá bajarse el dipswitch[1] y deberá pulsarse el boton 1. Por el contrario, si se quiere disminuir la velocidad,
deberá subirse el dipswitch[1] y deberá pulsarse el boton 1, tantas veces como quiera aumentarse o disminuirse la velocidad.

## Fallas Conocidas
1. La secuencia: luces de la policia no funciona correctamente. Posible falla: Un branch que apunte a un lugar incorrecto o una operacion que no se este haciendo correctamente. 
2. En la secuencia del auto fantastico, durante la vuelta un led se queda apagado de mas. Posible solucion: Modificar delays.
