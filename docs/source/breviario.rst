Breviario de Lenguaje C
=======================

-  `Breviario de Lenguaje C <#breviario-de-lenguaje-c>`__

   -  `Datos y Tipos de Datos <#datos-y-tipos-de-datos>`__

      -  `Valores y Objectos <#valores-y-objectos>`__
      -  `Variables y tipos. <#variables-y-tipos>`__

         -  `Declaración <#declaración>`__
         -  `Tipos comunes (simples) <#tipos-comunes-simples>`__

      -  `Constantes Literales <#constantes-literales>`__

   -  `Expresiones <#expresiones>`__
   -  `Operandos y operaciones <#operandos-y-operaciones>`__

      -  `Aritméticas: + - \* / % <#aritméticas------>`__
      -  `Operaciones booleanas: ! (negación) && (y lógico) \|\| (ó
         lógico) <#operaciones-booleanas--negación--y-lógico--ó-lógico>`__
      -  `Operaciones de comparación: == != < > <=
         >= <#operaciones-de-comparación------>`__
      -  `Operaciones de bit: & (y bitwise) \| (ó bitwise) ^ (xor
         bitwise) ~ (negación bitwise) << >>
         (desplazamientos) <#operaciones-de-bit--y-bitwise--ó-bitwise--xor-bitwise--negación-bitwise---desplazamientos>`__
      -  `Uso del paréntesis ( ) <#uso-del-paréntesis-->`__
      -  `Asignación = <#asignación->`__
      -  `Asignación combinada: += -= \*= /= %= &= \|=
         ^= <#asignación-combinada--------->`__
      -  `Operador , <#operador->`__
      -  `Operador ternario (1) ? (2) :
         (3) <#operador-ternario-1--2--3>`__

   -  `Sentencias <#sentencias>`__
   -  `Sentencias if y switch <#sentencias-if-y-switch>`__

      -  `Sintaxis if <#sintaxis-if>`__
      -  `Sintaxis switch <#sintaxis-switch>`__

   -  `Bucles (TBD) <#bucles-tbd>`__
   -  `Entrada y Salida de Datos <#entrada-y-salida-de-datos>`__

      -  `Canales de entrada/salida <#canales-de-entradasalida>`__
      -  `Salida con formato <#salida-con-formato>`__
      -  `Entrada con formato <#entrada-con-formato>`__

   -  `Punteros <#punteros>`__

      -  `Definición <#definición>`__
      -  `Sintaxis <#sintaxis>`__
      -  `Operaciones con punteros <#operaciones-con-punteros>`__

         -  `Operación indirección <#operación-indirección>`__
         -  `Operación dirección de <#operación-dirección-de>`__
         -  `Ejemplo <#ejemplo>`__

   -  `Funciones <#funciones>`__

      -  `Sintaxis básica <#sintaxis-básica>`__
      -  `Paso de parámetros por
         valor <#paso-de-parámetros-por-valor>`__
      -  `Paso de parámetros por
         referencia <#paso-de-parámetros-por-referencia>`__

   -  `Organización del código en C. <#organización-del-código-en-c>`__

      -  `Conceptos generales <#conceptos-generales>`__
      -  `Declaración y Definición <#declaración-y-definición>`__
      -  `Compilación y translation
         unit <#compilación-y-translation-unit>`__
      -  `Enlace del programa <#enlace-del-programa>`__
      -  `Uso de librerías <#uso-de-librerías>`__
      -  `Comandos <#comandos>`__
      -  `Librerías dinámicas <#librerías-dinámicas>`__

   -  `Arrays <#arrays>`__

      -  `Declaración de arrays muy
         grandes <#declaración-de-arrays-muy-grandes>`__
      -  `Arrays y punteros <#arrays-y-punteros>`__

   -  `Funciones y arrays <#funciones-y-arrays>`__
   -  `Arrays 2D y operador ``[ ]``. <#arrays-2d-y-operador-->`__
   -  `Punteros a arrays <#punteros-a-arrays>`__
   -  `Arrays de punteros y punteros a
      arrays <#arrays-de-punteros-y-punteros-a-arrays>`__
   -  `Funciones y arrays (2D o más) <#funciones-y-arrays-2d-o-más>`__
   -  `Memoria dinámica (arrays 1D) <#memoria-dinámica-arrays-1d>`__
   -  `Memoria dinámica (arrays 2D) <#memoria-dinámica-arrays-2d>`__

      -  `Equivalente a un array 2D <#equivalente-a-un-array-2d>`__
      -  `Alternativa a un array 2D como un vector de
         punteros <#alternativa-a-un-array-2d-como-un-vector-de-punteros>`__

   -  `struct (TBD) <#struct-tbd>`__

Datos y Tipos de Datos
----------------------

Valores y *Objectos*
~~~~~~~~~~~~~~~~~~~~

No confundir *object* en C con los objetos de POO (por ejemplo de Java).
**NO** es lo mismo.

-  Un valor es un dato, la codificación binaria de un número (entero,
   coma flotante), una letra (o un texto, una cadena alfanumérica).

-  Un *objecto* según el estándar de C es “region of data storage in the
   execution environment, the contents of which can represent values”.
   Es decir, una zona de memoria donde el programa va a guardar un
   valor.

-  La manera más sencilla de usar *objectos* es el uso de variables,
   pero no la única.

-  Los *objectos* se pueden usar en el lado izquierdo de una asignación
   para modificar el valor que guardan. Se entiende cualquier forma de
   expresión cuyo resultado sea un objeto. Esto se denomina “*left
   value*”.

-  Cuando un *objecto* se sitúa en el lado derecho de una asignación se
   utiliza su valor, esto se denomina “*right value*”

Variables y tipos.
~~~~~~~~~~~~~~~~~~

-  Una variable es un *objecto* que tiene un identificador y un tipo. Es
   decir, **se declara**.

-  Un tipo implica un tamaño (no siempre fijado unívocamente en el
   estándar) y una codificación.

Declaración
^^^^^^^^^^^

Se escribe tipo e identificador. Ejemplos:

::

       int a;
       int b;
       int x, y;

Opcionalmente se puede inicializar cualquier declaración:

::

       int a = 3;
       int b;
       int x = -2, y = 2;

Tipos comunes (simples)
^^^^^^^^^^^^^^^^^^^^^^^

-  Enteros (con signo): char, short, int, long int, (long long int en
   C99).

-  Enteros (sin signo): unsigned char, unsigned short, unsigned int,
   unsigned long int, (unsigned long long int en C99).

-  Coma flotante: float, double

-  Alfanuméricos: char

Constantes Literales
~~~~~~~~~~~~~~~~~~~~

Las constantes literales se escriben tal cual mediante su valor. Aplican
las siguientes reglas:

-  Los números sin punto decimal positivos o negativos son constantes
   literales enteras (int). Ejemplos: ``3 -5 10 -324``

-  Números escritos con punto decimal son constantes literales en coma
   flotante (double). Ejemplos: ``3.14 -1.414``

-  Idem para números en notación científica, es indiferente escribir e ó
   E. Ejemplos: ``1e-5 3.14E5 1.1e-4 -1.414e+3``

-  Los caracteres (letras) individuales son constantes alfanuméricas
   simples (char). Se escriben con comilla simple y recta. Ejemplos:
   ``'a' '4' ';' ' ' '?'``

-  Algunos caracteres especiales se escriben mediante una secuencia
   especial que empieza por barra invertida (backslash). Ejemplo:
   ``'\n' '\t' '\''``

-  Las cadenas alfanuméricas se escriben con comillas doble recta.
   Ejemplos:
   ``"Hola Mundo" "Introduce un dato\n" "Entre \"comillas\" dobles"``.
   Es **obligatorio** cerrar la cadena alfanuméricoa en la misma línea
   de código fuente.

**Casos Especiales**

-  Se pueden poner sufijos para cambiar el tipo del literal, por
   ejemplo: ``3.14f`` es de tipo float, ``34U`` es unsigned int, ``12L``
   es long int.

-  Se pueden escribir constantes enteras en octal o hexadecimal
   prefijando el número con 0 ó 0x respectivamente. Ejemplos: ``010`` es
   8, ``0x10`` es 16.

-  Si se escriben dos cadenas alfanuméricas seguidas, sin nada más que
   espacio entre ellas se juntan en la misma constante. Esto es útil
   para escribir cadenas alfanuméricas largas. Por ejemplo:

::

   "Hola "
   "Mundo"

Es equivalente a ``"Hola Mundo"``

Expresiones
-----------

Operandos y operaciones
-----------------------

-  Operandos: constantes, variables, resultados de otras operaciones.

-  Operaciones: Atención al tipo de los operandos y del resultado.

Aritméticas: + - \* / %
~~~~~~~~~~~~~~~~~~~~~~~

-  Operandos numéricos, resultado numérico del mismo tipo.
-  Cuando tienen distinto tipo se “promociona” el de menor rango.
-  La división entera tiene dos operaciones: cociente y resto,
   respectivamente ``/`` y ``%``.

Ejemplos: El resultado de ``1 / 2`` es 0, ``1 % 2`` es 1, ``7 / 2`` es
3.

Operaciones booleanas: ! (negación) && (y lógico) \|\| (ó lógico)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Operandos numéricos, resultado int. Cualquier operando se convierte
   en verdadero si es distinto de cero y en falso si es cero. El
   resultado siempre es 1 (verdadero) o 0 (falso).

Ejemplos: El resultado de ``1 && 2`` es 1, ``0 || 0.4`` es 1, ``! 22``
es 0.

Operaciones de comparación: == != < > <= >=
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Operandos cualquier tipo (el mismo), resultado int (booleano).
-  Tienen más prioridad que las booleanas, pero mejor usar paréntesis
-  Cuidado con omitir operandos. Ejemplo: ``1 < x < 10`` es siempre 1
   (verdadero). Lo correcto es: ``1 < x && x < 10``.

Operaciones de bit: & (y bitwise) \| (ó bitwise) ^ (xor bitwise) ~ (negación bitwise) << >> (desplazamientos)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Operandos enteros, resultado entero.
-  Aplica a cada bit la operación correspondiente.

Ejemplos:

-  ``1 << 3`` es 8, ``12 | 11`` es 15, ``12 & 11`` es 8.
-  ``x & (1 << 3)`` El resultado es el valor de x con un 0 en el tercer
   bit empezando por la derecha.
-  ``x | (1 << 3)`` El resultado es el valor de x con un 1 en el tercer
   bit empezando por la derecha.
-  ``~ x + 1`` El resultado es el valor de -x (si x es un entero con
   signo).

Uso del paréntesis ( )
~~~~~~~~~~~~~~~~~~~~~~

-  Sirven para priorizar unas operaciones sobre otras.

-  Incluso cuando no sean necesarios contribuyen a hacer más claras las
   operaciones al hacer *explícito* el orden de las operaciones.

Asignación =
~~~~~~~~~~~~

La asignación es una operación que tiene:

-  Un efecto, cambiar el valor del *objecto* a la izquierda del ``=``
   (el *left value*).
-  Un resultado, el propio valor que se asigna. Normalmente este
   resultado no se usa, **se descarta**.

Ejemplo: ``x = 3`` efecto: la variable x modifica su valor a 3 perdiendo
el valor anterior, resultado: 3 (el mismo valor asignado).

Asignación combinada: += -= \*= /= %= &= \|= ^=
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La asignación combinada es una operación aritmética o de bit seguida de
una asignación.

Ejemplo: ``x += 3`` es lo mismo que ``x = x + 3``

Operador ,
~~~~~~~~~~

-  Esta operación evalua las expresiones a cada lado, su resultado es el
   resultado de la derecha.

Ejemplo: ``3,4`` es 4, por tanto cuidado con usar , en vez de . para
escribir números en coma flotante.

Operador ternario (1) ? (2) : (3)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Evalua el primer operador y toma como resultado la expresión (2) si
   (1) es verdadero o el resultado de la expresión (3) en caso
   contrario.

Ejemplo: ``a < b ? a : b`` es el valor mínimo de a y b.

Sentencias
----------

En un programa en C existen:

1. Declaraciones
2. Sentencias

Las declaraciones definen nuevos identificadores: variables, funciones,
tipos de datos… No son código que se ejecute, salvo quizás alguna
inicialización.

Mientras que las sentencias sí se ejecutan, son las ordenes que el
ordenador realiza según el programa que se ha escrito. Todas las
sentencias en los programas de C deben estar escritas dentro de una
función.

Una sentencia puede ser:

1. Una expresión terminada con un punto y coma.
2. Se incluyen como expresiones las llamadas a función (el paréntesis de
   llamada a una función se considera un operador).
3. Una sentencia compuesta delimitada por una apertura y un cierre de
   llaves (sin punto y coma final).
4. Una sentencia condicional (if, switch).
5. Una sentencia repetitiva o bucle (for, while, do … while).

Sentencias if y switch
----------------------

Sintaxis if
~~~~~~~~~~~

::

   if (cond) sentencia1 
   [ else sentencia2 ]

-  Cuando se anidan el ``else`` se asocia al ``if`` más cercano que sea
   posible.

Sintaxis switch
~~~~~~~~~~~~~~~

::

   switch ( entero ) 
   {
       case CTE_LITERAL1 : 
           break;
       case CTE_LITERAL2 : 
           break;
       default:
           break;
   }

-  Se producen dos *saltos* el primero hasta la etiqueta que coincide y
   el segundo del ``break`` hasta la siguiente sentencia.

-  Las sentencias ``break`` son opcionales. Las etiquetas no son
   ejecutables en ningún caso.

Bucles (TBD)
------------

TODO: Pendiente de escribir

Entrada y Salida de Datos
-------------------------

Canales de entrada/salida
~~~~~~~~~~~~~~~~~~~~~~~~~

Cuando se arranca un programa en la terminal se crean tres *canales*
estándares: entrada, salida y errores. Por defecto:

-  El canal de entrada estándar toma la información del teclado (y la
   lleva al programa).
-  Lo que se escribe en los canales estándares de salida y errores se
   muestra en la terminal en forma de texto.

*Nota*: Al usar el teclado la información que el usuario escribe *sólo*
se *envía* al canal de entrada cuando se pulsa *enter*. Pero, además, la
propia pulsación de *enter* es un salto de línea y se envía como tal al
canal de entrada.

Salida con formato
~~~~~~~~~~~~~~~~~~

Para escribir en el canal de salida se usa ``printf``. Para llamar a
``printf`` hay que pasar como argumento una cadena alfanumérica (con
``"``) donde se indica el texto a escribir.

Para escribir datos de variables o expresiones se utilizan argumentos
adicionales, por cada argumento se debe colocar en la cadena de formato
un *especificador de conversión* que determinan cómo se debe convertir
el dato pasado como argumento al texto que se va a escribir en la
terminal. La conversión se indica con un tipo de dato asociado.

Los siguientes son los *especificadores de conversión* más habituales:

============= =====================================
Especificador Tipo de Conversión
============= =====================================
%d            Número entero en base 10
%f            Números en coma flotante (cualquiera)
%c            Letra
%s            Cadena alfanumérica (texto)
============= =====================================

Algunas extensión a estos especificadores de conversión básicos son:

-  Indicar la *anchura*: se escribe un número entre el ``%`` y la letra.
   Sirve para hacer columnas en la salida.

-  Indicar las cifras decimales en los números en coma flotante: se
   escribe un punto y el número de cifras. Por ejemplo: ``%.3f`` son
   tres cifras decimales.

-  Escribir un ``+`` delante de los números positivos: se escribe un
   ``+`` justo después del ``%``. Por ejemplo: ``%+d``.

-  Para escribir el símbolo de tanto por ciento sin confusión respesto
   de un especificador de conversión se escriben dos: ``%%``.

-  Hay muchas más: rellenar los números con ceros a la izquierda,
   conversiones a notación científica, a hexadecimal u octal…

*Nota*: No es habitual usarlo, pero el retorno de ``printf`` es el
número de caracteres escrito en el canal.

Entrada con formato
~~~~~~~~~~~~~~~~~~~

Para leer del canal de entrada estándar se usa ``scanf``. Para llamar a
``scanf`` hay que pasar como argumento una cadena alfanumérica (con
``"``) donde se indica el contenido esperado a la entrada. Este
argumento se denomina cadena de *formato*.

Al leer, se va comprobando si lo que se encuentra se corresponde con lo
esperado y si *no* es así, la lectura se interrumpe.

En la cadena de formato se puede encontrar:

1. Especificadores de conversión. Para los especificadores de conversión
   se intenta convertir los caracteres de la entrada al tipo indicado
   hasta que ya no sea posible. Por ejemplo: si el especificador de
   conversión es %d se intentan leer los caracteres para calcular un
   número en base 10, cuando algún carácter no pueda formar parte del
   número se interrumpe la lectura.
2. Blancos (**espacio, tabulador, salto de línea**). Cualquier blanco en
   el formato tiene el mismo efecto: se corresponde con cualquier número
   de blancos en el canal de entrada. El efecto que se logra es *saltar*
   u omitir los blancos al leer el texto en el canal de entrada. Se
   suele utilizar un simple espacio (y no tabulares o saltos de línea).
   Se insiste desde el punto de vista de lectura todos los blancos son
   equivalentes.
3. Otros caracteres. Cualquier otro carácter tiene que corresponder
   exactamente con lo que se encuentra en el canal de entrada.

Al leer el canal, ``scanf`` procesa los caracteres que encuentra, los
transforma en el *tipo de dato* especificado y guarda el valor hallado
en *la variable apuntada por la dirección de memoria que se pasa como
argumento*. Por esta razón la coincidencia debe ser **exacta**.

Los siguientes son los *especificadores de conversión* más habituales:

============= =========================== ==================
Especificador Tipo de Conversión          Tipo del argumento
============= =========================== ==================
%d            Número entero en base 10    int\*
%f            Números en coma flotante    float\*
%lf           Números en coma flotante    double\*
%c            Letra                       char\*
%s            Cadena alfanumérica (texto) char\* (array)
============= =========================== ==================

Al leer con los especificadores: %d, %f, %lf, %s se saltan los blancos
que se puedan encontrar inicialmente. No así con %c, si hubiese un
blanco ese es el valor que se lee y guarda en la variable.

Para los datos numéricos la lectura se interrumpe cuando el siguiente
carácter no pueda formar parte de la representación del número (un
espacio, una coma, una letra…). Para %s la lectura se interrumpe al
llegar a un espacio en blanco, el efecto, equivale aproximadamente a
leer palabras pero los signos de puntuación sí se agregan a la cadena
leída.

Además de estos especificadores es muy útil el especificador corchete
que sirve para leer cadenas alfanuméricas **mientras** los caracteres
leídos estén entre los dados entre los corchetes (``%[]``) o **hasta**
que se encuentre uno que estén entre los corchetes (``%[^]``).

Hay dos extensiones a estos especificadores:

1. La anchura: un número que se indica detrás del ``%`` y que indica el
   número máximo de caracteres leídos. Esto sirve para leer columnas de
   ancho fijo. Por ejemplo: ``"%3d%3d`` separaría el texto ``123456`` en
   el canal de entrada en dos números: 123 y 456. La anchura debe ser
   considerada **obligatoria** en la lectura de cadenas para no
   desbordar el tamaño de la cadena.
2. Modificadores de longitud. Por ejemplo: ``%Ld`` sirve para guardar el
   valor leído en una variable de tipo ``long``.

El retorno de ``scanf`` es el número de datos leídos correctamente y,
por tanto, almacenados en las correspondientes variables.

Cuando no es posible leer un número (se encuentra una letra o cualquier
otro carácter que no se corresponde con el número esperado) la lectura
se interrumpe y este dato no se cuenta como leido. Por ejemplo, si la
entrada es:

::

   -34 a 4.3

y se intenta leer con:

::

   int num; char letra; double x;
   int res;

   res = scanf("%d%c%lf", &a, &letra, &x);

La variable ``res`` tomará el valor 2 porque se leerán los valores para
num (-34), para letra (el espacio), pero no se podrá leer el valor de x
(porque hay una ‘a’) y, por tanto, no cuenta como leida. De las 3
variables se han leido 2 y ese es el retorno del ``scanf``.

Si se hiciese: ``res = scanf("%d %c%lf", &a, &letra, &x);`` el retorno
sí sería 3 (se salta el espacio) y la variable ``x`` tomaría el valor
esperado.

También puede ser ``EOF`` si se intenta leer más allá del final del
canal de entrada.

Punteros
--------

Definición
~~~~~~~~~~

Un puntero es:

-  Un tipo de dato que se corresponde con una dirección de memoria. En
   sistemas operativos de 64 bits son un enteros sin signo de 8 bytes.
   Una dirección de memoria es el número que permite encontrar un dato
   concreto en la memoria del ordenador.
-  Una variable de este tipo.
-  Y son una *referencia* a una variable (objeto en la terminología C)

Además:

-  La frase: “puntero apunta a variable” significa que la dirección de
   memoria que está guardada en el puntero es la dirección de la
   variable.
-  La frase: “p es un puntero a entero” significa que en la dirección de
   memoria guardada en p se supone que hay un variable de tipo entero.

Sintaxis
~~~~~~~~

-  Se coloca un asterisco delante del identificador de la variable.
-  El siguiente código declara un puntero, ``p`` que *apunta* a un
   entero, ``int``:

::

   int *p;

Operaciones con punteros
~~~~~~~~~~~~~~~~~~~~~~~~

Operación indirección
^^^^^^^^^^^^^^^^^^^^^

-  Su símbolo es el asterisco (*)
-  Es una operación aplicable sólo a punteros
-  Es una operación unaria (un único operando) por la izquierda (el
   símbolo de la operación se coloca a la izquierda del operando)
-  Obtiene la variable a la que apunta el puntero
-  El tipo del resultado coincide con el tipo al que apunta el puntero

Operación dirección de
^^^^^^^^^^^^^^^^^^^^^^

-  Su símbolo es el carácter (&) *et* ó *ampersand*
-  Es una operación aplicable sólo a variables (objetos)
-  Es una operación unaria (un único operando) por la izquierda (el
   símbolo de la operación se coloca a la izquierda del operando)
-  Obtiene la dirección de memoria de una variable
-  El tipo del resultado es un puntero que apunta al tipo de la variable

Ejemplo
^^^^^^^

::

   int num = 6;
   int *p; /* Declaración de un puntero a entero */

   p = &num; /* p apunta num */

   num = 2 * *p; /* Se multiplica 2 por 6 */

   printf("num = %d\n", num); /* Muestra 12 */

   *p = 7; /* Se fija a 7 el valor de la variable apuntada por p */

   printf("num = %d\n", num); /* Muestra 7 */

Una forma de verlo:

Por **definición** las operaciones & y \* son inversas, es decir:
``*&num`` es identicamente igual a ``num``.

Funciones
---------

Sintaxis básica
~~~~~~~~~~~~~~~

::

   tipo_retorno id_funcion(Tipo1 par1, Tipo2 par2) {
       /* Implementación */
       return expresion;
   }

Importante: tipo_retorno NO puede ser un array (con ``[ ]``).

Paso de parámetros por valor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

El paso de todos los parámetros es por valor, *siempre*.

Es equivalente a hacer: ``par = expresion_arg``, donde el lado derecho
de la asignación es, precisamente, el argumento que se pasa a la función
en la llamada.

Paso de parámetros por referencia
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

El paso de un puntero a una función *también* es **por valor**, pero
como los punteros son referencias, entonces, el paso de un puntero
implica:

-  Que se puede acceder (leer o modificar) la dirección de memoria
   apuntada por el puntero (normalmente una variable).

-  Y, entonces, la variable apuntada por el puntero es un parámetro
   *indirecto*, se dice que la variable (como tal) se pasa por
   *referencia* dado que se podrá utilizar o modificar su valor.

-  En la práctica sirve para tener parámetros:

1. De salida. Es decir, aquellos donde se fija el valor de la variable
   con un resultado calculado internamente en la función.

2. De entrada / salida. Es decir, aquellos donde se utiliza el valor de
   la variable para hacer los calculos dentro de la función y,
   posteriormente, se modifica con un resultado de la función.

Organización del código en C.
-----------------------------

Conceptos generales
~~~~~~~~~~~~~~~~~~~

Por costumbre se entiende que:

-  Los archivos .h se incluyen y contienen las cabeceras o declaraciones
   de funciones.
-  Los archivos .c se compilan y contienen la implementación de las
   mismas

Declaración y Definición
~~~~~~~~~~~~~~~~~~~~~~~~

-  La declaración de una función es su cabecera
-  La definición de una función es su implementación
-  La definición de una variable es lo que solemos llamar declaración
   por no ser demasiado estrictos
-  La declaración de una variables, sintácticamente, es su definición
   precedida por ``extern``

Compilación y translation unit
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Un archivo .c que se compila de forma individual una vez que ha
   pasado por el preprocesador se dice que una *translation unit*. Se
   distigue de propio archivo .c porque en la *translation unit* se
   encuentra todo el código fuente de los archivos de cabeceras que se
   hayan incluido.
-  Para que la compilación tenga éxito:

   1. Se debe encontrar la declaración de todas las variables y
      funciones usadas
   2. Pero *NO* hace falta que estén sus definiciones
   3. No pasa nada porque se repitan declaraciones, pero sólo puede
      haber una definición de cada cosa.

Enlace del programa
~~~~~~~~~~~~~~~~~~~

-  Una vez compiladas todas las *translation unit*\ s se procede a
   enlazar todo para producir el programa. Es decir, para producir un
   programa (el código objeto ejecutable) se **juntan** todos los
   códigos objetos, *.o (*.obj) de las compilaciones previas.
-  Para producir el programa se debe cumplir:

   1. Que se encuentre una definición y sólo una para cada variable y
      función declaradas.
   2. Que se encuentre una función y sólo una con el nombre ``main``
   3. Si no es así se producirán errores de *link*

Uso de librerías
~~~~~~~~~~~~~~~~

-  En esencia, una librería en C es **juntar** archivos \*.o procedentes
   de compilaciones de archivos de C relacionados.
-  De hecho, suele ser un archivo *comprimido* o un *tar* de estos
   archivos.
-  Se usan en el momento de enlazar para proporcionar las definciones de
   las funciones en la librería.
-  Para poder usar las funciones de la librería en otros archivos de C
   hace falta tener sus declaraciones. Normalmente estas se encuentran
   en archivos .h que también se suministran junto con la propia
   librería.
-  Por costumbre se suelen colocar en una carpeta llamada *include*

Comandos
~~~~~~~~

Para compilar archivos:

.. code:: bash

   gcc -ansi -pedantic -Wall -Wextra -c *.c

La opción ``-c`` indica que el archivo sólo se compila no se enlaza.

Para enlazar:

.. code:: bash

   gcc -ansi -pedantic -Wall -Wextra *.o main.c -o programa.out

Se escriben como argumentos del comando los archivos objeto generados
previamente (o los .c si no se habían compilado).

Para crear una librería *estática*:

.. code:: bash

   ar rcs libnombre.a *.o

El comando ``ar`` crea un *archivo*, donde se guardan archivos ``*.o``.
Simplemente una agrupación de los archivos objeto.

Para utilizar una librería:

.. code:: bash

   gcc -ansi -pedantic -Wall -Wextra -L. -lnombre main.c -o programa.out

El enlace de librería se hace a través de dos opciones:

-  ``-L`` seguido por la(s) ruta(s) donde se deben buscar las librería,
   por ejemplo, la carpeta de trabajo ``.``
-  ``-l`` (ele minúscula) seguido del nombre de la librería. Se puede
   omitir el prefijo ``lib`` y la extensión ``*.a``

Librerías dinámicas
~~~~~~~~~~~~~~~~~~~

Una librería dinámica (o *shared object*) es una librería que se carga
en tiempo de ejecución. Por contraste con una librería estática:

-  Un ejecutable que enlaza una librería estática extrae de la librería
   el código objeto necesario y lo incorpora en si mismo.
-  Un ejecutable que enlaza una librería dinámica sólo toma una
   referencia a la librería y a las funciones que se encuentren en ella.
   En el momento de arrancar tiene que *cargar* la librería y encontrar
   la referencia a las funciones que le hagan falta.
-  Esto último implica que se debe encontrar en la ruta donde se buscan
   librerías,
-  O debe añadirse a la variable de entorno ``LD_LIBRARY_PATH``.

Arrays
------

Pendiente

Declaración de arrays muy grandes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Declarar variables locales en ``main`` es una buena práctica, no
obstante, es posible declarar variables *globales* si su declaración se
escribe fuera del ``main`` (y de cualquier otra función). La declaración
de variables globales se considera una mala práctica porque se puede
acceder (leer su valor o modificarlo) desde cualquier punto del código
fuente.

Sin embargo, la declaración de variables globales puede estar
justificada (o ser necesaria) en algunos casos. Uno de ellos es la
declaración de variables tipo array de gran tamaño. Como las variables
locales se colocan en una zona de memoria de tamaño limitado llamada
stack declarar estas variables grandes puede ser un problema incluso
para compilar el programa.

Por ejemplo:

::

   #define MUCHO 100000

   double arrayGrande[MUCHO][MUCHO]; /* Se admite porque es muy grande */

   int main() {
       double arrayCuidado[MUCHO][MUCHO]; /* Puede dar problemas */
       return 0;
   }

Arrays y punteros
~~~~~~~~~~~~~~~~~

-  Cualquier array es *convertible* en un puntero que apunta al primer
   elemento del array.

-  La aritmética de punteros equivale a *moverse* en un array. Es decir,
   se cumple que:

``a[b]`` es exactamente lo mismo que ``*(a+(b))``. (**Literal en el
estándar de C**)

Siendo a un array y b una expresión cuyo resultado es un entero.

-  Alternativamente, sumar ``a + (b)`` tiene como resultado un puntero
   que cuya dirección de memoria está ``b`` veces desplazada respecto de
   ``a`` en *unidades* del tipo al que apunta el puntero.

Funciones y arrays
------------------

En C, los parámetros de tipo array como tal realmente **NO** existen. En
su lugar, sea cuál sea la sintaxis utilizada, C va a usar un puntero
para pasar el array.

Se podría decir que todos los arrays en C se pasan por referencia.

Es decir, las declaraciones de funciones:

::

   void func1(int array[], int tam);
   void func2(int array[20], int tam);
   void func3(int *array, int tam);

Son **equivalentes**. Cuando se hace una llamada en la forma:

::

   int mi_array[10];
   funcX(mi_array, 10);

Da igual la forma de declara la funcion (func1, func2, o func3) el paso
del parámetro **siempre** consiste en pasar la dirección de memoria del
primer elemento de ``mi_array`` y, por eso, es necesario pasar un
argumento adicional (el 10) para indicar el tamaño del array.

Arrays 2D y operador ``[ ]``.
-----------------------------

Si ejecutamos el siguiente fragmento de código fuente:

::

   int array[][2] = { 11, 22 }, { 33, 44 }, { 55, 66 };
   printf("%d", array[1][1]);

obtenemos 44. Porque:

-  El primer corchete salta una fila y el segundo salta un elemento. El
   primer corchete nos lleva a la fila { 33, 44 } y el segundo al 44.

-  En los arrays 2D (y superiores) los elementos siguen estando
   contiguos en memoria, la manera en que el operador indexación
   funciona es *saltando* filas al aplicar el primer corchete y
   *saltando* elementos al aplicar el segundo corchete.

Punteros a arrays
-----------------

Recordamos:

::

   int array[] = { 11, 22, 33 };
   printf("%d", *(array+1));

Muestra 22 porque:

1. ``array`` se convierte en un puntero a ``int``.
2. la aritmetica de punteros desplaza en memoria el puntero tantos
   ``int`` como indique el otro sumando (en este caso 1).

Vamos a considerar el siguiente código fuente:

::

   int array[][2] = { 11, 22 }, { 33, 44 }, { 55, 66 };
   printf("%d", (array+1)[0]);

1. El ``array`` se convierte en un puntero a una *fila* compuesta de dos
   número enteros.
2. Al sumar 1 se desplaza una fila en memoria, es decir, se desplaza 2
   enteros porque esa fila está formada por 2 enteros. Y el puntero
   apunta a la fila (al primer elemento de la fila, el 33).
3. Al hacer [0] obtenemos 33, el primer elemento de esa fila.

Arrays de punteros y punteros a arrays
--------------------------------------

Consideremos estas dos declaraciones:

::

   int* array_p[5]; /* 1 */
   int (*p_array)[5]; /* 2 */

La declaración (1) es **1 array de 5 punteros a enteros**. Los elementos
del array son punteros **NO** enteros.

La declaración (2) es **1 puntero a un array de 5 enteros**. **NO hay
ningún array**, solo hay un puntero y lo importante de ese puntero es
que, al sumar +1 al puntero, se saltan 5 enteros en memoria. Este es el
tipo al que se transforman las arrays 2D en C.

Cuando el array de la declaración (1) se convierte implicítamente en un
puntero se transforma en ``int**``. Veamos:

::

   int array_int[5]; /* array_int -> int* */
   int* array_punteros[5]; /* array_punteros -> int** */

El array ``array_int`` se convierte en la dirección de memoria al primer
elemento como los elementos son ``int``, su dirección es ``int*``.

El array ``array_punteros`` se convierte en la dirección de memoria al
primer elemento como los elementos son ``int*``, su dirección es
``int**``.

Funciones y arrays (2D o más)
-----------------------------

Un array estático bidimensional se convierte en un puntero a una fila,
por tanto, para utilizarlo como parámetro de una función existen las
siguientes opciones:

Declaración como array (la más sencilla):

::

   void una_funcion(int array[][5], int n_filas);

Importante: *NO* se puede quitar el 5 (o el número que corresponda)
porque el compilador debe saber cuanto ocupa una fila, su tamaño.

Declaración como puntero (la *real*):

::

   void una_funcion(int (*array)[5], int n_filas);

Es decir, el parámetro es el *puntero a la primera fila*. Igual que en
cualquier otro array, es el puntero al primer elemento del array.

Memoria dinámica (arrays 1D)
----------------------------

Frente a la memoria estática, aquella cuyo tamaño se conoce en tiempo de
compilación, la memoria dinámica se gestiona durante la ejecución del
programa mediante dos operaciones:

1) Reserva de memoria: el programa indica al sistema operativo que va a
   utilizar una cantidad de bytes para su uso.
2) Liberación de memoria: el programa indica al SO que ya no va a
   utilizar los bytes que había reservado.

Ambas operaciones se realizan mediante funciones de la librería estándar
de C y la memoria usada se gestiona mediante punteros.

Como parámetros y argumentos de estas operaciones se utiliza un tipo de
puntero especial llamado genérico, es un tipo de puntero del que se
desconce a qué apunta. Representa una dirección de memoria pura, se
conoce la dirección, pero no se supone nada sobre el contenido de esa
dirección. Se declaran como ``void*``.

Para reservar memoria se puede hacer:

::

   void* dyn_m = malloc(5*sizeof(int));
   void* dyn_c = calloc(5, sizeof(int));

En ambos casos se reserva una zona de memoria para su uso posterior. Con
malloc se indica el número de bytes. Con calloc se supone que se reserva
una zona de memoria para colocar un número de elementos de tamaño dado,
en el ejemplo 5 elementos de tamaño int.

Normalmente el puntero ``void*`` se convierte en un puntero que apunte a
lo que deseamos guardar en esa zona de memoria. Por ejemplo:

::

   int* dyn_m = (int*)malloc(5*sizeof(int));
   int* dyn_c = (int*)calloc(5, sizeof(int));

Donde la operación (int\ *) también llamada cast se puede omitir (o da
un aviso) según la versión del compilador. Ambos punteros se puede
manejar como equivalentes a un array de 5 enteros. Se dice que
son*\ arrays dinámicos*.

Para liberar memoria se hace:

::

   free(dyn_m);
   free(dyn_c);

Las funciones ``malloc``, ``calloc`` y ``free`` están declaradas en el
archivo de cabeceras: *stdlib.h*.

Memoria dinámica (arrays 2D)
----------------------------

Equivalente a un array 2D
~~~~~~~~~~~~~~~~~~~~~~~~~

El equivalente a una array 2D estática es una variable dinámica donde se
impone que tenga el número de filas y columnas correspondientes.

Si queremos el equivalente a ``int array2d[7][5]``, hacemos (en 2
pasos):

::

   void *p = malloc(35*sizeof(int)); 
   /* También: void *p = calloc(7, sizeof(int[5])); */
   int (*array)[5] = p;
   array[2][3] = 33;
   /* [...] */ 
   free(array);

Alternativa a un array 2D como un vector de punteros
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Alternativamente se puede generar una matriz dinámica como un vector de
punteros. Este alternativa tiene como ventaja que no es necesario fijar
el tamaño de la fila. Y tiene como inconveniente que exige un mayor
número de variables dinámicas: un vector de punteros y una variable
dinámica por cada fila.

Para la misma matriz, ``int array2d[7][5]``, se hace:

::

   int i;
   int **array = calloc(7, sizeof(int*));  /* Vector de 7 punteros */
   for (i = 0; i < 7; ++i ) {
     array[i] = calloc(5, sizeof(int)); /* Vector de 5 int */
   }

   array[2][3] = 33; /* array[2] es el puntero a la segunda fila */

   for (i = 0; i < 7; ++i ) {
     free(array[i]); /* Se Libera las filas */
   }
   free(array); /* Se libera el vector de punteros */

struct (TBD)
------------

TODO: Pendiente de escribir
