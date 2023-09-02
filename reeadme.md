# Ejercicio A: Triple de Pitágoras.

### El siguiente algoritmo se debe realizar utilizando Pseudocódigo, C++ y Python, es decir que se deben escribir en los tres lenguajes de programación, por lo que se  desea un excelente diseño para hacer su mejor propuesta de aplicaciones:

#### Un triángulo recto puede tener lados cuyas longitudes sean valores enteros. Un conjunto de tres valores enteros para los lados de un triángulo recto se conoce como triple de Pitágoras. Estos tres lados deben satisfacer la relación que establece que la suma de los cuadrados de dos lados es igual al cuadrado de la hipotenusa. Encuentre todos los triples de Pitágoras para lado1, lado2, y la hipotenusa, que no sean mayores de 500. Use un ciclo for triplemente anidado para probar todas las posibilidades. 
---
### Ya que tenemos la información empezamos el proceso de resaltar los puntos clave en el problema que nos ayudaran a resolverlo y en este caso son los siguientes: 
+ cateto 1
+ cateto 2
+ Hipotenusa
#### Tema: Triple de Pitágoras: en matemática se nos indica que la suma de ambos catetos elevados al cuadrado es igual al resultado de la hipotenusa al cudrado.

#### Generalizando la resolución del problema, necesitamos un algoritmo que nos pueda resolver  la ecuación de C^2 = a^2 + b^2 a través del triple de Pitágoras pero en este caso hasta 500, pero le sdos opciones extras las cuales son: 
  + Calcular un cateto en especifico de un triangulo unicamente con que el usuario ingrese la hipotenusa y el cateto que tenga.
  + Calcular la Hipotenusa de un triangulo solamente con que el usuario ingrese ambos catetos.
### se nos solicita que se implemente un ciclo for triplete anidado en los 3 tipos de programa, por lo que dependerá de del lenguaje del mismo.
----
### Codigo fuente en pseudocodigo(Pseint)

       Algoritmo Triple_de_Pitagoras
    Definir op Como Entero
    Definir cateto1, cateto2, hipotenusa Como Real
    Definir maximo Como Entero
    maximo <- 500
	
    Repetir
        // Mostrar menú
        Limpiar Pantalla
        Escribir "1. Calcular la hipotenusa"
        Escribir "2. Calcular un cateto"
        Escribir "3. Calcular triples de Pitágoras hasta 500"
        Escribir "4. Salir"
        Escribir "Ingrese la opción (1-4):"
        Leer op
		
        // Procesa la opcion elegida por el usuario.
        Segun op Hacer
            1:
                Escribir "Ingrese la longitud del primer cateto:"
                Leer cateto1
                Escribir "Ingrese la longitud del segundo cateto:"
                Leer cateto2
                hipotenusa <- raiz(cateto1^2 + cateto2^2)
                Escribir "La hipotenusa es: ", hipotenusa
            2:
                Escribir "Ingrese la longitud de un cateto:"
                Leer cateto1
                Escribir "Ingrese la longitud de la hipotenusa:"
                Leer hipotenusa
                cateto2 <- raiz(hipotenusa^2 - cateto1^2)
                Escribir "El otro cateto es: ", cateto2
            3:
                Escribir "Triples de Pitágoras menores o iguales a 500:"
                Para cateto1 <- 1 Hasta maximo Con Paso 1 Hacer
                    Para cateto2 <- cateto1 Hasta maximo Con Paso 1 Hacer
                        Para hipotenusa <- cateto2 Hasta maximo Con Paso 1 Hacer
                            Si cateto1^2 + cateto2^2 = hipotenusa^2 Entonces
                                Escribir "Cateto 1: ", cateto1, ", Cateto 2: ", cateto2, ", Hipotenusa: ", hipotenusa
                            Fin Si
                        Fin Para
                    Fin Para
                Fin Para
            4:
                Escribir "Fin del algoritmo"
            Otro:
                Escribir "Opción no válida"
        Fin Segun
		
        Escribir "Presione enter para continuar"
        Esperar Tecla
    Hasta Que op = 4
    Fin Algoritmo 
    
  #### para implentar la opción de menu fue necesario acudir al bucle "Segun" para poder ingresar las dos opciones añadidas anterior mente y en la tercera opción esta lo solcitidao el ciclo for triplemente anidado, creamos un algoritmo el cual no es necesario volver a ejecutar para poder ponerlo a prueba ya que con el ciclo "Repetir" y "limpiar pantalla" con tal solo un enter el limpia todos los datos visualizados con anterioridad para que el usuario pueda ingresar datos nuevos.
  ---

  ### Caputaras de pantalla del codigo fuente en Pseint:
- ![Captura](https://drive.google.com/file/d/1Vxqf2t9Lrxxw8Oao6fX6xmnKAUcLVALv/view?usp=sharing)

-![captura](https://drive.google.com/file/d/1D9vELjkoAMutjuEjZ2VNwbjVOvIZpen-/view?usp=sharing)


.


---
### Codigo fuente en C++   
    #include <iostream>
    #include <cmath>
    using namespace std;
    int main() {
    // Declarar variables
	int op;
     double cateto1, cateto2, hipotenusa;
     int maximo = 500;

    do {
        // Mostrar menú.
        system("cls");
        cout << "1. Calcular la hipotenusa" << endl;
        cout << "2. Calcular un cateto" << endl;
        cout << "3. Calcular triples de Pitágoras hasta 500" << endl;
        cout << "4. Salir" << endl;
        cout << "Ingrese la opcion (1-4): ";
        cin >> op;

        // Procesa la opcion elegida por el usuario.
        switch (op) {
            case 1:
                cout << "Ingrese la longitud del primer cateto: ";
                cin >> cateto1;
                cout << "Ingrese la longitud del segundo cateto: ";
                cin >> cateto2;
                hipotenusa = sqrt(cateto1 * cateto1 + cateto2 * cateto2);
                cout << "La hipotenusa es: " << hipotenusa << endl;
                break;
            case 2:
                cout << "Ingrese la longitud de un cateto: ";
                cin >> cateto1;
                cout << "Ingrese la longitud de la hipotenusa: ";
                cin >> hipotenusa;
                cateto2 = sqrt(hipotenusa * hipotenusa - cateto1 * cateto1);
                cout << "El otro cateto es: " << cateto2 << endl;
                break;
            case 3:
                cout << "Triples de Pitágoras menores o iguales a 500:" << endl;
                for (cateto1 = 1; cateto1 <= maximo; cateto1++) {
                    for (cateto2 = cateto1; cateto2 <= maximo; cateto2++) {
                        for (hipotenusa = cateto2; hipotenusa <= maximo; hipotenusa++) {
                            if (cateto1 * cateto1 + cateto2 * cateto2 == hipotenusa * hipotenusa) {
                                cout << "Cateto 1: " << cateto1 << ", Cateto 2: " << cateto2 << ", Hipotenusa: " << hipotenusa << endl;
                            }
                        }
                    }
                }
                break;
            case 4:
                cout << "Fin del programa" << endl;
                break;
            default:
                cout << "Opcion no valida" << endl;
        }

        cout << "Presione enter para continuar";
        cin.ignore();
        cin.get();
    } while (op != 4);

    return 0;
    }
  
#### En c++ insertamos el ciclo for anidado dentro de  un ciclo swith y el ciclo switch se encuentra  dentro de un ciclo do while, tiene las mismas funciones y como el lenguaje de programación lo requeria se acudio a la libreria #include <cmath> para realizar las ecuaciones.
---

 ### Caputaras de pantalla del código fuente en C++:
- ![Captura](https://drive.google.com/file/d/1ji0dwQSaB5OWYXuFfZhvlCeqMH8dhfN2/view?usp=sharing)
- ![Captura 2](https://drive.google.com/file/d/14rgJ62r8aurCiIaWkLdXOYUATMZcj-Xy/view?usp=sharing)
- ---
### Codigo fuente en Phyton
    import os
    # Declarar variables
    cateto1 = 0.0
    cateto2 = 0.0
    hipotenusa = 0.0
    maximo = 500

    while True:
        os.system('clear' if os.name == 'posix' else 'cls')
        print("1. Calcular la hipotenusa")
        print("2. Calcular un cateto")
        print("3. Calcular triples de Pitágoras hasta 500")
        print("4. Salir")
        op = int(input("Ingrese la opción (1-4): "))

    if op == 1:
        cateto1 = float(input("Ingrese la longitud del primer cateto: "))
        cateto2 = float(input("Ingrese la longitud del segundo cateto: "))
        hipotenusa = (cateto1*2 + cateto22)*0.5
        print("La hipotenusa es:", hipotenusa)
    elif op == 2:
        cateto1 = float(input("Ingrese la longitud de un cateto: "))
        hipotenusa = float(input("Ingrese la longitud de la hipotenusa: "))
        cateto2 = (hipotenusa*2 - cateto12)*0.5
        print("El otro cateto es:", cateto2)
    elif op == 3:
        print("Triples de Pitágoras menores o iguales a 500:")
        for cateto1 in range(1, maximo + 1):
            for cateto2 in range(cateto1, maximo + 1):
                for hipotenusa in range(cateto2, maximo + 1):
                    if cateto1*2 + cateto22 == hipotenusa*2:
                        print("Cateto 1:", cateto1, ", Cateto 2:", cateto2, ", Hipotenusa:", hipotenusa)
    elif op == 4:
        print("Fin del programa")
        break
    else:
        print("Opción no válida")

    input("Presione enter para continuar")

#### en Python es mucho mas practico crear algoritmos debido a que el lenguaje de programación es mucho mas corto, en este caso utilizamos un bucle "while" para poder elaborar nuestro menú y dentro de el nuestro ciclo for triplemente anidado.
---
 ### Capturas de pantalla del código fuente en Python:
- ![captura](https://drive.google.com/file/d/1UJzVpxJgQVjGD0zz6gk_2dtF_fCSqfec/view?usp=sharing)
- ![Captura 2](https://drive.google.com/file/d/1TtUt6ECH-33B8pwSnqkbrob9w0q_r3gi/view?usp=sharing)

Como  podemos darnos cuenta en los tres lenguajes de programación fue necesario declarar variables,  el uso de un ciclo while, switch y segun, para la elaboración del menú.

#### En los tres lenguajes se trato de demostrar el funcionamiento de los mismos con capturas de pantalla y demostrando que no contaban con ningún error.**

----
---
# Ejercicio B: Juego del ahorcado
 - C++
 - Python
 - Pseint
---
Este código es un programa simple que implementa el juego del ahorcado. El objetivo del juego es adivinar una palabra oculta letra por letra antes de quedarse sin intentos. 

Se incluyen las bibliotecas `<iostream>` y `<string>` para utilizar las funciones de entrada/salida y trabajar con cadenas de texto. Se define la función `main()`, que es la función principal del programa y es el punto de entrada.
    
Se declara una variable llamada `palabraSecreta` que contiene la palabra que el jugador debe adivinar. En este caso, la palabra es "hola mundo".
    
Se declara una variable llamada `palabraAdivinada` que se inicializa con una cadena de guiones bajos (`_`) y tiene la misma longitud que la `palabraSecreta`. Esta variable almacenará la palabra a medida que el jugador adivina las letras.
    
Se declara una variable llamada `intentos` inicializada en 6. Esta variable rastreará cuántos intentos le quedan al jugador antes de perder el juego.
    
Se imprime un mensaje de bienvenida al juego del ahorcado.
Comienza un bucle "while" que se ejecutará mientras el jugador tenga intentos restantes (es decir, `intentos > 0`).
    
Se imprime una representación gráfica del ahorcado y se muestra la palabra a adivinar con guiones bajos para las letras aún no adivinadas. Se solicita al jugador que ingrese una letra. Se declara una variable `letraAdivinada` inicializada en `false` que se utilizará para verificar si la letra ingresada por el jugador está en la palabra secreta.
    
Se utiliza un bucle "for" para recorrer cada letra de la`palabraSecreta` y verificar si coincide con la letra ingresada por el jugador. Si hay una coincidencia, se actualiza la variable `palabraAdivinada` para mostrar la letra adivinada y se establece `letraAdivinada` en `true`.
    
  Si la letra no fue adivinada (`letraAdivinada` sigue siendo `false`), se reduce el número de `intentos` en 1 y se muestra un mensaje de "Letra incorrecta".
    
Se verifica si el jugador ha adivinado la palabra completa. Si `palabraAdivinada` es igual a `palabraSecreta`, significa que el jugador ha adivinado la palabra y se muestra un mensaje de felicitación. Luego, el bucle se rompe usando `break`.
    
Si el bucle termina y `intentos` es igual a 0, se muestra un mensaje indicando que el jugador se quedó sin intentos y se revela la `palabraSecreta`.
    
Finalmente, el programa regresa 0 para indicar una finalización exitosa.

### Código Fuente en  C++:

        #include <iostream>
    #include <string>
    using namespace std;
    
    int main() {
        string palabraSecreta = "hola mundo";
        string palabraAdivinada(palabraSecreta.length(), '_');
        
        int intentos = 6;
        
        cout << "Bienvenido al juego del ahorcado!" << endl;
        
        while (intentos > 0) {
            cout << "   _" << endl;
            cout << "  |       |" << endl;
            cout << "  |       " << (intentos < 6 ? "O" : "") << endl;
            cout << "  |      " << (intentos < 4 ? "/" : " ") << (intentos < 5 ? "|" : "") << (intentos < 3 ? "\\" : "") << endl;
            cout << "  |      " << (intentos < 2 ? "/" : " ") << " " << (intentos < 1 ? "\\" : "") << endl;
            cout << "  |" << endl;
            cout << "|" << endl;
            
            cout << "Palabra a adivinar: " << palabraAdivinada << endl;
            cout << "Intentos restantes: " << intentos << endl;
            
            char letra;
            cout << "Ingresa una letra: ";
            cin >> letra;
            
            bool letraAdivinada = false;
            for (int i = 0; i < palabraSecreta.length(); i++) {
                if (palabraSecreta[i] == letra) {
                    palabraAdivinada[i] = letra;
                    letraAdivinada = true;
                }
            }
            
            if (!letraAdivinada) {
                intentos--;
                cout << "Letra incorrecta." << endl;
            }
            
            if (palabraAdivinada == palabraSecreta) {
                cout << "¡Felicidades, has adivinado la palabra!" << endl;
                break;
            }
        }
        
        if (intentos == 0) {
            cout << "¡Oh no! Se te acabaron los intentos. La palabra era: " << palabraSecreta << endl;
        }
        
        return 0;
    }
En en siguiente enlace se podrá visualizar la ejecución del código fuente en youtube: [enter link description here](https://youtu.be/HPCTV55ephM)

----
### Python

Este es un código de Python que implementa el juego del ahorcado. El objetivo del juego es adivinar una palabra oculta letra por letra antes de quedarse sin intentos. 

Se importa el módulo random, que se utilizará para elegir una palabra al azar de una lista.

Se define una lista llamada palabras que contiene las palabras que el jugador puede adivinar. En este caso, las palabras son "Python", "programación" y "computadora". Se utiliza random.choice(palabras) para elegir una palabra al azar de la lista palabras y se almacena en la variable palabraSecreta. Esta será la palabra que el jugador debe adivinar.

Se crea una lista llamada palabraAdivinada que inicialmente contiene guiones bajos (_) y tiene la misma longitud que la palabraSecreta. Esta lista se utilizará para rastrear las letras adivinadas y las que faltan por adivinar. Se inicializa la variable intentos en 6. Esta variable rastreará cuántos intentos le quedan al jugador antes de perder el juego.
Se imprime un mensaje de bienvenida al juego del ahorcado.

Comienza un bucle "while" que se ejecutará mientras el jugador tenga intentos restantes (es decir, intentos > 0).

En cada iteración del bucle, se imprime una representación gráfica del ahorcado y se muestra la palabra a adivinar con guiones bajos para las letras aún no adivinadas. Se solicita al jugador que ingrese una letra.

Se declara una variable letraAdivinada inicializada en False, que se utilizará para verificar si la letra ingresada por el jugador concuerda con una letra de la palabraSecreta.

Se utiliza un bucle "for" para recorrer cada letra de la palabraSecreta y verificar si coincide con la letra ingresada por el jugador. Si hay una coincidencia, se actualiza la lista palabraAdivinada para mostrar la letra adivinada y se establece letraAdivinada en True.

Si la letra no fue adivinada (letraAdivinada sigue siendo False), se reduce el número de intentos en 1 y se muestra un mensaje de "Letra incorrecta".

Se verifica si el jugador ha adivinado la palabra completa. Si "".join(palabraAdivinada) es igual a palabraSecreta, significa que el jugador ha adivinado la palabra y se muestra un mensaje de felicitación. Luego, el bucle se rompe usando break.

Si el bucle termina y intentos es igual a 0, se muestra un mensaje indicando que el jugador se quedó sin intentos y se revela la palabraSecreta.

### Codigo fuente Python:

        import random
    
    # Lista de palabras a adivinar
    palabras = ["python", "programacion", "computadora"]
    
    # Elegir una palabra al azar
    palabraSecreta = random.choice(palabras)
    
    palabraAdivinada = ['_' for _ in palabraSecreta]
    intentos = 6
    
    print("Bienvenido al juego del ahorcado!")
    
    while intentos > 0:
        print("   _")
        print("  |       |")
        print("  |       " + ("O" if intentos < 6 else ""))
        print("  |      " + ("/" if intentos < 4 else " ") + ("|" if intentos < 5 else "") + ("\\" if intentos < 3 else ""))
        print("  |      " + ("/" if intentos < 2 else " ") + " " + ("\\" if intentos < 1 else ""))
        print("  |")
        print("|")
    
        print("Palabra a adivinar:", "".join(palabraAdivinada))
        print("Intentos restantes:", intentos)
    
        letra = input("Ingresa una letra: ")
    
        letraAdivinada = False
        for i in range(len(palabraSecreta)):
            if palabraSecreta[i] == letra:
                palabraAdivinada[i] = letra
                letraAdivinada = True
    
        if not letraAdivinada:
            intentos -= 1
            print("Letra incorrecta.")
    
        if "".join(palabraAdivinada) == palabraSecreta:
            print("¡Felicidades, has adivinado la palabra!")
            break
    
    if intentos == 0:
        print("¡Oh no! Se te acabaron los intentos. La palabra era:", palabraSecreta)

En en siguiente enlace se podrá visualizar la ejecución del código fuente en youtube: [enter link description here](https://youtu.be/FsEQPuH-e1c)

---
### Codigo fuente Pseint:

El juego permite al jugador elegir entre dos niveles de dificultad (básico y medio) y adivinar una palabra oculta letra por letra antes de quedarse sin oportunidades.

El código comienza definiendo variables y listas para rastrear palabras, aciertos, turnos, fallos, oportunidades, y más. Se muestra un menú al jugador donde puede elegir entre los niveles básico y medio, o salir del juego. En el nivel básico (caso 1), se elige una palabra al azar de una lista predefinida de palabras y se inicializan variables para rastrear letras incorrectas y las oportunidades restantes. 

El jugador tiene que adivinar la palabra ingresando letras. El juego muestra las letras adivinadas y las letras en blanco para las que aún no se han adivinado. Si el jugador se queda sin oportunidades, pierde. Si adivina la palabra, gana.
   
En el nivel medio (caso 2), se repite el proceso, pero con una lista diferente de palabras y un conjunto diferente de oportunidades. El jugador sigue adivinando letras para encontrar la palabra oculta. En ambos casos, el juego muestra una representación gráfica del ahorcado y sigue registrando aciertos, fallos e intentos hasta que el jugador adivine la palabra o se quede sin oportunidades. Si el jugador adivina la palabra, muestra un mensaje de felicitación y, de lo contrario, muestra un mensaje de derrota junto con la palabra oculta.
    
En el caso de que el jugador elija salir (caso 3), el juego termina. Si el jugador ingresa una opción no válida, se muestra un mensaje de error. Al final de cada juego, el código espera a que el jugador presione cualquier tecla antes de continuar.

       Algoritmo JuegoAhorcado
        	definir palabr, palabra, casillas como cadena
        	definir aciertos, turnos, fallos, p_tb, oportunidades, OP como entero
        	definir letra, chr como caracter
        	definir encontrando como logico
        	
        	Escribir "      Menú"
        	Escribir "   1. Nivel Básico"
        	Escribir "   2. Nivel Medio"
        	escribir "   3. Salir "
        	escribir "   Ingrese su opción (1-3)"
        	leer OP
        	Segun OP hacer
        		1:
        			p_tb<-20
        			oportunidades<-8
        			dimension palabra[p_tb]
        			
        			palabra[1]<-"duda"
        			palabra[2]<-"ojo"
        			palabra[3]<-"anima"
        			palabra[4]<-"duro"
        			palabra[5]<-"pua"
        			palabra[6]<-"ahoga"
        			palabra[7]<-"dije"
        			palabra[8]<-"vos"
        			palabra[9]<-"acero"
        			palabra[10]<-"echo"
        			palabra[11]<-"uso"
        			palabra[12]<-"apoye"
        			palabra[13]<-"cuña"
        			palabra[14]<-"rie"
        			palabra[15]<-"almas"
        			palabra[16]<-"gota"
        			palabra[17]<-"via"
        			palabra[18]<-"amigo"
        			palabra[19]<-"copo"
        			palabra[20]<-"feo"
        			
        			a_<-' '
        			h_<-' '
        			o_<-' '
        			r_<-' '
        			c_<-' '
        			ax<-' '
        			d_<-' '
        			ox<-' '
        			
        			turnos<-0
        			aciertos<-0
        			
        			palabr<-palabra[azar(p_tb)+1]
        			n<-Longitud(palabr)
        			Dimension casillas(n)
        			Para x<-1 Hasta n Con Paso 1 Hacer
        				casillas[x]<-"_"
        			Fin Para
        			Repetir
        				Escribir ""
        				escribir "Oportuniddes restantes: ", oportunidades-turnos
        				Para x<-1 Hasta n Con Paso 1 Hacer
        					Escribir Sin Saltar " ", casillas[x]
        				Fin Para
        				escribir " "
        				Escribir Sin Saltar "Escriba la letra: "
        				leer letra
        				encontrando<-Falso
        				Para x<-1 Hasta n Con Paso 1 Hacer
        					chr<-Subcadena(palabr, x,x)
        					Si Mayusculas(letra)=Mayusculas(chr) Entonces
        						encontrando<-Verdadero
        						si casillas[x]="_" Entonces
        							casillas[x]<-chr
        							aciertos<-aciertos+1
        							
        						FinSi
        					Fin Si
        				FinPara
        				si no encontrando Entonces
        					turnos<-turnos+1
        					Escribir "Letra no encontrada."
        					Segun turnos hacer
        						1:
        							a_<-'A'
        						2:
        							h_<-'H'
        						3:
        							o_<-'O'
        						4 :
        							r_<-'R'
        						5:
        							c_<-'C'
        						6:
        							ax<-'A'
        						7:
        							d_<-'D'
        						8:
        							Ox<-'O'
        							
        							
        					FinSegun	
        				FinSi
        				Escribir "",a_
        				Escribir "",h_
        				Escribir "",o_
        				Escribir "",r_
        				Escribir "",c_
        				Escribir "",ax
        				Escribir "",d_
        				Escribir "",ox
        				
        				
        			Hasta Que turnos>=oportunidades o aciertos>=n;
        			si aciertos=n Entonces
        				
        				Escribir "Felicidades, has ganado"
        			sino
        				Escribir "Has perdido."
        			FinSi
        			Escribir "La palabra secreta es: ", palabr;
        			escribir "Aciertos: ",aciertos,"  Fallos: ",turnos
        			escribir "PRESIONE CUALQUIER TECLA PARA CONTINUAR";
        			esperar Tecla;
        			
        			
        		2:
        			p_tb<-20
        			oportunidades<-8
        			dimension palabra[p_tb]
        			
        			palabra[1]<-"fabricado"
        			palabra[2]<-"camiseta"
        			palabra[3]<-"ninguno"
        			palabra[4]<-"zapato"
        			palabra[5]<-"habaneros"
        			palabra[6]<-"cabellera"
        			palabra[7]<-"celular"
        			palabra[8]<-"cobija"
        			palabra[9]<-"habilidad"
        			palabra[10]<-"eliminar"
        			palabra[11]<-"galleta"
        			palabra[12]<-"alarma"
        			palabra[13]<-"vacilados"
        			palabra[14]<-"bolsillo"
        			palabra[15]<-"archivo"
        			palabra[16]<-"espejo"
        			palabra[17]<-"compilado"
        			palabra[18]<-"celebrar"
        			palabra[19]<-"rebotar"
        			palabra[20]<-"adorno"
        			
        			// Resto del código para jugar el nivel medio sigue igual
        			a_<-' '
        			h_<-' '
        			o_<-' '
        			r_<-' '
        			c_<-' '
        			ax<-' '
        			d_<-' '
        			ox<-' '
        			
        			turnos<-0
        			aciertos<-0
        			//fallos<-0
        			
        			palabr<-palabra[azar(p_tb)+1]
        			n<-Longitud(palabr)
        			Dimension casillas(n)
        			Para x<-1 Hasta n Con Paso 1 Hacer
        				casillas[x]<-"_"
        			Fin Para
        			Repetir
        				Escribir ""
        				or=oportunidades-turnos
        				escribir "Oportuniddes restantes: ", or
        				Para x<-1 Hasta n Con Paso 1 Hacer
        					Escribir Sin Saltar " ", casillas[x]
        				Fin Para
        				escribir " "
        				Escribir Sin Saltar "Escriba la letra: "
        				leer letra
        				encontrando<-Falso
        				Para x<-1 Hasta n Con Paso 1 Hacer
        					chr<-Subcadena(palabr, x, x)
        					Si Mayusculas(letra)=Mayusculas(chr) Entonces
        						encontrando<-Verdadero
        						si casillas[x]='_' Entonces
        							casillas[x]<-nose
        							aciertos<-aciertos+1
        							
        						FinSi
        					Fin Si
        				FinPara
        				si no encontrando Entonces
        					turnos<-turnos+1
        					Escribir "Letra no encontrada."
        					Segun turnos hacer
        						1:
        							a_<-'A'
        						2:
        							h_<-'H'
        						3:
        							o_<-'O'
        						4 :
        							r_<-'R'
        						5:
        							c_<-'C'
        						6:
        							ax<-'A'
        						7:
        							d_<-'D'
        						8:
        							Ox<-'O'
        							
        							
        					FinSegun	
        				FinSi
        				Escribir "",a_
        				Escribir "",h_
        				Escribir "",o_
        				Escribir "",r_
        				Escribir "",c_
        				Escribir "",ax
        				Escribir "",d_
        				Escribir "",ox
        				
        				
        				
        			Hasta Que turnos>=oportunidades o aciertos>=n;
        			si aciertos=n Entonces
        				
        				Escribir "Felicidades, has ganado"
        			sino
        				Escribir "Has perdido."
        			FinSi
        			Escribir "La palabra secreta es: ", palabr;
        			escribir "Aciertos: ",aciertos,"  Fallos: ",fallos, "  Intentos: ",intentos
        			
        		3:
        			escribir "Usted ha salido del juego"
        			
        		de otro modo:
        			escribir "Opción no válida"
        	FinSegun
        	
        	escribir "PRESIONE CUALQUIER TECLA PARA CONTINUAR"
        	esperar Tecla
        FinAlgoritmo

En en siguiente enlace se podrá visualizar la ejecución del código fuente en YouTube: [enter link description here](https://youtu.be/ZBZ0HXF7rPc)

----
Integrantes del grupo y aportes: 

 - Dalila Zacarias-------------------50% 
 - Cristian Gomez------------------50%

