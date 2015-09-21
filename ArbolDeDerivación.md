###**An�lisis L�xico**

**Reemplazo de trigraphs y digraphs**
El reemplazo de los digraphs y trigraphs se realiza antes del linkeo, y el encargado es el preprocesador

**Tokenizaci�n**
int main (void9{
	int _[:>=<%-!.0,];
	int _[] = {-!.0,};
	printf("%d%d",sizeof_-sizeof_[0],sizeof(char)+0[_]);
}
**UT lexicamente correcto**
Es una unidad de traducci�n lexicamente correcto, debido a la utilzaci�n de digraphs y trigraphs, implimentando aritm�tica de arreglos (por medio de la conmutaci�n).

###**An�lisis Sint�ctico**

**Arbol De Derivaci�n**
unidad-de-traducci�n
unidad-de-traducci�n   declaraci�n-externa
declaraci�n-externa    definici�n-de-funci�n
declaraci�n	(DESARROLLO DEL PRINTF)	        
especificadores-de-declaraci�n declarador lista-de-declaraciones
especificador-de-tipo especificadores-de-declaraci�n declarador lista-de-declaraciones
INT declarador 
INT declarador-directo 
INT declarador-directo (lista-tipos-de-parametros)
INT identificador (lista-de-parametros, ...)
INT printf (declaraci�n-parametro,...)
INT printf (especificadores-de-declaraci�n declarador,...)
INT printf (clasificador-de-tipo especificadores-de-declaraciob declarador, ...)
INT printf (const especificador-de-tipo declarador,...)
INT printf (const char apuntador declarador-directo,..)
INT printf (const char * identificador,...)
INT printf (const char *,...)
definici�n-de-funci�n (DESARROLLO DEL MAIN)
especificadores-de-declaraci�n declarador lista-de-declaraciones
especificador-de-tipo especificadores-de-declaraci�n declarador lista-de-declaraciones
INT declarador
INT declarador-directo
INT declarador-directo (lista-tipo-de-parametros){
INT identificador (lista-de-parametros){
INT main (declaraci�n-par�metro){	
INT main (especificadores-de-declaraci�n){
INT main (especificador-de-tipo){
INT main (VOID){	
	unidad-de-traducci�n
	declaraci�n-externa
	declaraci�n
	especificadores-de-declaraci�n lista-declaradores-init;
	especificador-de-tipo declarador-init;
	INT declarador = inicializador;
	INT declarador-directo = {lista-de-inicializadores};
	INT declarador-directo [expresi�n-constante] = {inicializador};
	INT identificador [expresi�n-condicional] = {expresi�n-asignaci�n};
	INT a[expresi�n-l�gica-OR] = {expresi�n-condicional};
	INT a[expresi�n-l�gica-AND] = {expresi�n-l�gica-OR};
	INT a[expresi�n-OR-exclusivo] = {expresi�n-l�gica-AND};
	INT a[expresi�n-AND] = {expresi�n-l�gica-AND && expresi�n-OR-inclusivo};
	INT a[expresi�n-de-igualdad] = {expresi�n-l�gica-AND && expresi�n-l�gica-AND && expresi�n-OR-inclusivo};
	INT a[expresi�n-de-igualdad] = {expresi�n-OR-inclusivo && expresi�n-OR-inclusivo && expresi�n-OR-inclusivo};
	INT a[expresi�n-racional] = {expresi�n-OR-exclusivo && expresi�n-OR-exclusivo && expresi�n-OR-exclusivo};
	INT a[expresi�n-racional] = {expresi�n-AND && expresi�n-AND && expresi�n-AND};
	INT a[expresi�n-racional] = {expresi�n-de-igualdad && expresi�n-de-igualdad && expresi�n-de-igualdad};
	INT a[expresi�n-de-corrimiento] = {expresi�n-racional && expresi�n-racional && expresi�n-racional};
	INT a[expresi�n-aditiva] = {expresi�n-de-corrimiento && expresi�n-de-corrimiento && expresi�n-de-corrimiento};
	INT a[expresi�n-multiplicativa] = {expresi�n-aditiva && expresi�n-aditiva && expresi�n-aditiva};
	INT a[expresi�n-unaria] = {expresi�n-multiplicativa && expresi�n-multiplicativa && expresi�n-multiplicativa};
	INT a[expresi�n-posfija] = {expresi�n-unaria && expresi�n-unaria && expresi�n-posfija};
	INT a[expresi�n-primaria] = {operador-unario expresi�n-cast && operador-unario expresi�n-cast && expresi�n-primaria};
	INT a[constante] = {- expresi�n-cast && ! expresi�n-cast && constante};
	INT a[constante-entera] = {- expresi�n-cast && ! expresi�n-cast && constante-entera};
	INT a[] = {- expresi�n-cast && ! expresi�n-cast && 0};
	INT a[] = {- expresi�n-cast && ! 0.00};
	INT a[] = {-!.0};

**Unidad de Traducci�n sint�cticamente correcta**

###**An�lisis Sem�ntico**

**Funci�n del programa y an�lisis del resultado**
El programa posee dos declaraciones externas, el printf, y el main.
A su vez, utiliza una expresi�n y una asignaci�n.
Posee dos sentencias.

El programa, primero, reemplaza los digraphs y trigraphs, luego se inicializa un arreglo, donde sus posiciones posee el n�mero -!.0 (-1).
En esta inicializaci�n,luego del reemplazo de los digraphs y trigraphs, dentro de las llasves ({}), se realizan varios pasos, pirmero se reconoce un valor 0 float (0.0), el cual, luego de negarse este bit (!), se reemplaza por uno(1), a su vez, cuando se reemplaza por uno, se realiza un casteo, el cual transforma el tipo de dato num�rico a int (float->int), y por �ltimo, se niega logicamente el valor 1, quedadon como resultado y calor para asignar en el arreglo menos uno (-1).
Luego se realiza un printf, lo que genera una salida con formato por pantalla de dos numeros decimasles ("%d%d"), el primer n�mero decimal, se obtiene de la resta realizada entre el tipo de dato del arreglo (int), y el tipo de dato del elemnto almancenado en la primer posici�n del arreglo, (int, por ser -1), lo que devuelve por pantalla un cero. El segundo n�mero, es un cero (0), resultado de la suma entre el valor del tipo de dato de un char, el cual es uno (1) y el primer elemento del arreglo, el cual es, menos uno (-1), por consecuente, devuelve por pantalla un segundo cero.
 