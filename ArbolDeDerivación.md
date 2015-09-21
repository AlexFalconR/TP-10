###**Análisis Léxico**

**Reemplazo de trigraphs y digraphs**
El reemplazo de los digraphs y trigraphs se realiza antes del linkeo, y el encargado es el preprocesador

**Tokenización**
int main (void9{
	int _[:>=<%-!.0,];
	int _[] = {-!.0,};
	printf("%d%d",sizeof_-sizeof_[0],sizeof(char)+0[_]);
}
**UT lexicamente correcto**
Es una unidad de traducción lexicamente correcto, debido a la utilzación de digraphs y trigraphs, implimentando aritmética de arreglos (por medio de la conmutación).

###**Análisis Sintáctico**

**Arbol De Derivación**
unidad-de-traducción
unidad-de-traducción   declaración-externa
declaración-externa    definición-de-función
declaración	(DESARROLLO DEL PRINTF)	        
especificadores-de-declaración declarador lista-de-declaraciones
especificador-de-tipo especificadores-de-declaración declarador lista-de-declaraciones
INT declarador 
INT declarador-directo 
INT declarador-directo (lista-tipos-de-parametros)
INT identificador (lista-de-parametros, ...)
INT printf (declaración-parametro,...)
INT printf (especificadores-de-declaración declarador,...)
INT printf (clasificador-de-tipo especificadores-de-declaraciob declarador, ...)
INT printf (const especificador-de-tipo declarador,...)
INT printf (const char apuntador declarador-directo,..)
INT printf (const char * identificador,...)
INT printf (const char *,...)
definición-de-función (DESARROLLO DEL MAIN)
especificadores-de-declaración declarador lista-de-declaraciones
especificador-de-tipo especificadores-de-declaración declarador lista-de-declaraciones
INT declarador
INT declarador-directo
INT declarador-directo (lista-tipo-de-parametros){
INT identificador (lista-de-parametros){
INT main (declaración-parámetro){	
INT main (especificadores-de-declaración){
INT main (especificador-de-tipo){
INT main (VOID){	
	unidad-de-traducción
	declaración-externa
	declaración
	especificadores-de-declaración lista-declaradores-init;
	especificador-de-tipo declarador-init;
	INT declarador = inicializador;
	INT declarador-directo = {lista-de-inicializadores};
	INT declarador-directo [expresión-constante] = {inicializador};
	INT identificador [expresión-condicional] = {expresión-asignación};
	INT a[expresión-lógica-OR] = {expresión-condicional};
	INT a[expresión-lógica-AND] = {expresión-lógica-OR};
	INT a[expresión-OR-exclusivo] = {expresión-lógica-AND};
	INT a[expresión-AND] = {expresión-lógica-AND && expresión-OR-inclusivo};
	INT a[expresión-de-igualdad] = {expresión-lógica-AND && expresión-lógica-AND && expresión-OR-inclusivo};
	INT a[expresión-de-igualdad] = {expresión-OR-inclusivo && expresión-OR-inclusivo && expresión-OR-inclusivo};
	INT a[expresión-racional] = {expresión-OR-exclusivo && expresión-OR-exclusivo && expresión-OR-exclusivo};
	INT a[expresión-racional] = {expresión-AND && expresión-AND && expresión-AND};
	INT a[expresión-racional] = {expresión-de-igualdad && expresión-de-igualdad && expresión-de-igualdad};
	INT a[expresión-de-corrimiento] = {expresión-racional && expresión-racional && expresión-racional};
	INT a[expresión-aditiva] = {expresión-de-corrimiento && expresión-de-corrimiento && expresión-de-corrimiento};
	INT a[expresión-multiplicativa] = {expresión-aditiva && expresión-aditiva && expresión-aditiva};
	INT a[expresión-unaria] = {expresión-multiplicativa && expresión-multiplicativa && expresión-multiplicativa};
	INT a[expresión-posfija] = {expresión-unaria && expresión-unaria && expresión-posfija};
	INT a[expresión-primaria] = {operador-unario expresión-cast && operador-unario expresión-cast && expresión-primaria};
	INT a[constante] = {- expresión-cast && ! expresión-cast && constante};
	INT a[constante-entera] = {- expresión-cast && ! expresión-cast && constante-entera};
	INT a[] = {- expresión-cast && ! expresión-cast && 0};
	INT a[] = {- expresión-cast && ! 0.00};
	INT a[] = {-!.0};

**Unidad de Traducción sintácticamente correcta**

###**Análisis Semántico**

**Función del programa y análisis del resultado**
El programa posee dos declaraciones externas, el printf, y el main.
A su vez, utiliza una expresión y una asignación.
Posee dos sentencias.

El programa, primero, reemplaza los digraphs y trigraphs, luego se inicializa un arreglo, donde sus posiciones posee el número -!.0 (-1).
En esta inicialización,luego del reemplazo de los digraphs y trigraphs, dentro de las llasves ({}), se realizan varios pasos, pirmero se reconoce un valor 0 float (0.0), el cual, luego de negarse este bit (!), se reemplaza por uno(1), a su vez, cuando se reemplaza por uno, se realiza un casteo, el cual transforma el tipo de dato numérico a int (float->int), y por último, se niega logicamente el valor 1, quedadon como resultado y calor para asignar en el arreglo menos uno (-1).
Luego se realiza un printf, lo que genera una salida con formato por pantalla de dos numeros decimasles ("%d%d"), el primer número decimal, se obtiene de la resta realizada entre el tipo de dato del arreglo (int), y el tipo de dato del elemnto almancenado en la primer posición del arreglo, (int, por ser -1), lo que devuelve por pantalla un cero. El segundo número, es un cero (0), resultado de la suma entre el valor del tipo de dato de un char, el cual es uno (1) y el primer elemento del arreglo, el cual es, menos uno (-1), por consecuente, devuelve por pantalla un segundo cero.
 