# juegotrivia
Un pequeño juego sobre preguntas de cultura general

import random

 

 

 

def manual(): #Muestra las reglas del juego

    print('-------------------------------------------------')

    print('''Manual de Búsqueda del tesoro

         

Este juego trata sobre encontrar un tesoro escondido en un mapa de 50 espacios, en cada juego el tesoro se escondera tras una casilla diferente,



En cada turno, el jugador deberá seleccionar una casilla, seguido de esto aparecera una pregunta, si es respondida correctamente, se cavara un hoyo en dicha casilla
          
Si el tesoro se encuentra en la casilla cavada, el jugador que lo cavo ganara

''')

   

    a = input('Ingresa cualquier caracter para volver: ')

    if a != '':

        print('-------------------------------------------------')

def creditos(): #Creditos del juego
            print(

        '''-------------------------------------------------

        Creado por:

        Alejandro Pérez Dávila & Sebastian Velasquez González

        2024


        'Es impresionante ver lo que se puede hacer con unas cuantas lineas de codigo, ha sido un largo camino, aveces puede parecer algo frustante pero con paciencia y esfuerzo se pueden lograr cosas muy geniales!

        Muchas gracias profe Jaime por ensenarnos y impulsarnos en el hermoso mundo de la programacion'

        -APD :3

        ''')

                 

                 

def iniciar_juego():

    preguntas = {

        "Como se le llamo a la primera computadora de la historia\n a)Eniac\n b)Java\n c)Maquina enigma\n d)Linux" : 'a',

        "Cual es el lugar mas frio de la tierra \n a)El desierto del sahara \n b)El polo sur\n c)El polo norte\n d)La antartida" : 'd',

        "En que continente esta Colombia?  \n a)America\n b)Asia\n c)Africa\n d)Oceania" : "a",

        "Cuando se independizo Colombia?  \n a)1810\n b)1600\n c)1900\n d)1902" : 'a',

        "Cuándo acabó la II Guerra Mundial?  \n a)1999\n b)1945\n c)1940\n d)1910" : 'b',

        "Que es Africa?  \n a)Un continente\n b)Un pais\n c)Todas las anteriores\n d)Ninguna de las anteriores" : 'a',

        "Quien pinto la ultima cena? \n a)Salvador Dali\n b)Pablo Piccaso\n c)Leonardo da Vinci\n d)Vincent Van Gogh" : 'c',

        "Con que se fabricaban los pergaminos?  \n a)Juncos\n b)Piel de animales\n c)Madera\n d)caña de azucar" : 'b',

        "Cual es el idioma mas hablado del mundo  \n a)Chino mandarin\n b)Ingles\n c)Espanol\n d)Portugues" : 'b',

        "Cual fue el primer metal usado por el hombre?  \n a)Hierro\n b)Tungsteno\n c)Cobre\n d)Obsidiana" : 'c',

        "Cual es el primer elemento de la tabla periodica  \n a)Hidrogeno\n b)Oxigeno\n c)Uranio\n d)Nitrogeno" : 'a',

        "Cual es el primer numero primo?  \n a)1\n b)0\n c)3\n d)2" : 'd',

        "Cual es el Unico mamifero que puede volar?  \n a)el ornitorrinco\n b)El pinguinos\n c)El murcielago\n d)El cocodrilo" : 'c',

        "Quien dijo 'solo se que nada se'  \n a)Platon\n b)Socrates\n c)Aristoteles\n d)Satre" : 'b',

        "La campana de Gauss está asociada a...  \n a)El estudio de sistemas politicos    \n b)El calculo de probabilidades\n c)La historia en la edad media\n d)Notaciones cartograficas" : 'b',

        "Cuáles son las notas musicales?  \n a)a b c d\n b) do re mi fa sol la si\n c)agua\n d) + - * /" : 'b',

        "En qué país se usó la primera bomba atómica en combate \n a)Estados Unidos\n b)China \n c)Japon\n d)Mexico" : 'c',

        "Dónde se encuentra la capa de ozono?  \n a)litosfera\n b)Atmosfera\n c)Espacio\n d)Corteza" : 'b',

        "Cual es la capital de Colombia  \n a)Cartagena \n b)Cauca\n c)Bogota\n d)Medellin" : 'c',

        "Cómo se llama el fundador de Facebook?  \n a)Elom Musk\n b)Mark Zuckerberg \n c)Stephen Hawking\n d)Will Smith" : 'b',

        "¿En qué año apareció en el mercado el videojuego Super Mario bros? \n a)1981\n b)2000\n c)1980\n d)1990" :  'c',

        "Cuántos corazones tienen los pulpos? \n a)1\n b)3\n c)no tienen\n d)2" : 'b',

        "Cuándo se extinguieron los mamuts?  \n a)ayer \n b)hace 4000 años\n c)hace 2 millones de años\n d)no se han extinguido": 'b',

        "Cual es el rio mas largo del mundo? \n a)el rio nilo \n b)el amazonas \n c) el rio sena \n d)ninguna de las anteriores" : 'b',

        '¿Quién es el autor de la frase "Pienso, luego existo"?\nA) Platón\nB) Galileo Galilei\nC) Descartes\nD) Sócrates' : 'c',

        '¿Cuál es el libro más vendido en el mundo después de la Biblia?\nA) El Señor de los Anillos\nB) Don Quijote de la Mancha\nC) El Principito\nD) Cien años de Soledad': 'b',

        '¿Quién pintó la obra "Guernica"?\nA) Paul Cézanne\nB) Pablo Picasso\nC) Diego Rivera\nD) Salvador Dalí' : 'b',

        '¿Cuál es la montaña más alta del continente americano?\nA) Monte Everest\nB) Aconcagua\nC) Pico Neblina\nD) Pico Bolívar' : 'b',

        '¿Cuáles son los nombres de los tres reyes magos?\nA) Gaspar, Nicolas y Nataniel\nB) Gaspar, Melchor y Baltazar\nC) Simon, Judas y Mateo\nD) Charles, George y Louis' : 'b',

        'El número romano MDCLXVI corresponde a:\nA) 1991\nB) 1000100\nC) 1551\nD) 1666' : 'd',

        'La sigla OTAN significa:\nA) Orden Territorial para Almacenes y Negocios\nB) Organización de Técnicos de Aeronáutica\nC) Organización del Tratado del Atlántico Norte\nD) Organización Tripartita de América del Norte' : 'c',

        '¿Cuál fue la primera novela que llamó la atención sobre los límites de la experimentación científica?\nA) Un mundo feliz de Aldous Huxley\nB) Frankenstein de Mary Shelley\nC) Yo, Robot de Isaac Asimov\nD) El hombre invisible de H.G. Wells' : 'b',

        '¿Qué película se basa en la vida de un matemático con esquizofrenia?\nA) El cisne negro\nB) El indomable Will Hunting\nC) La teoría de todo\nD) Una mente maravillosa' : 'd',

        '¿Cuál es el país más grande y el más pequeño del mundo?\nA) Rusia y Vaticano\nB) China y Nauru\nC) Canadá y Mónaco\nD) Estados Unidos y Malta' : 'a',

        '¿Cuánto tiempo tarda la luz del Sol en llegar a la Tierra?\nA) 12 minutos\nB) 1 día\nC) 12 horas\nD) 8 minutos' : 'd',

        'La sal común está formada por dos elementos, ¿cuáles son?\nA) Sodio y potasio\nB) Sodio y cloro\nC) Sodio y carbono\nD) Potasio y cloro' : 'b',

        '¿Cuántos decimales tiene el número pi π?\nA) Dos\nB) Cien\nC) Infinitos\nD) Mil' : 'c',

        '¿En qué periodo de la prehistoria fue descubierto el fuego?\nA) Neolítico\nB) Paleolítico\nC) Edad de los metales\nD) Edad de piedra' : 'b',

        '¿A qué compuesto corresponde la fórmula química H2O2?\nA) Agua hidrogenada\nB) Agua oxigenada\nC) Agua destilada\nD) Agua contaminada' : 'b',

        '¿Quién es considerado el padre de la ciencia y la filosofía?\nA) Tales de Mileto\nB) Aristóteles\nC) Demócrito\nD) Pitágoras' : 'a',

        '¿Cuáles son los dioses griegos correspondientes a los dioses romanos Júpiter y Plutón?\nA) Ares y Hermes\nB) Cronos y Apolo\nC) Zeus y Hades\nD) Dionisio y Démeter' : 'c',

        '¿Quién era primer ministro de Gran Bretaña cuando la reina Isabel II ascendió al trono?\nA) Margaret Thatcher\nB) Winston Churchill\nC) Neville Chamberlain\nD) William Shakespeare' : 'b',

        'Carlos Cruz-Diez fue:\nA) Artista cinético\nB) Compositor musical\nC) Artista cubista\nD) Escritor de ensayos' : 'a',

        '¿Cuál es la capital de Mongolia?\nA) Muharin Den\nB) Ulán Bator\nC) Pionyang\nD) Daca' : 'b',

        '¿Cuál es la persona más joven en ganar un premio Nobel?\nA) Greta Thunberg\nB) Shirley Temple\nC) Malala Yousafzai\nD) Ana Frank' : 'c',

        '¿Cuál es la categoría de los premios Nobel que ha recibido más galardones?\nA) Física\nB) Química\nC) Medicina\nD) Literatura' : 'a',

        '¿Cuál es la velocidad de la luz?\nA) 300 000 000 metros por segundo\nB) 150 000 000 metros por segundo\nC) 199 792 458 metros por segundo\nD) 299 792 458 metros por segundo' : 'd',

        '¿En qué orden se presentaron los modelos atómicos?\nA) Thomson, Dalton, Rutherford, Bohr\nB) Dalton, Thomson, Rutherford, cuántico\nC) Bohr, Rutherford, cuántico, Einstein\nD) Dalton, Einstein, cuántico, Sheldon Cooper' : 'b',

        '¿Cuáles son los tres predadores del reino animal reconocidos por: 1) habilidad de cazar en grupo, 2) camuflajearse para sorprender a su presa, 3) poseer sentidos refinados?\nA) Hiena; Oso polar; Lobo gris\nB) León; Tiburón blanco; Orca\nC) Tigre; Águila; Gato\nD) Tiburón blanco; Elefante; Escorpiónl' : 'a',

        '¿Cuál es la traducción correcta de la frase "There is a green carpet at the exit of the library"?\nA) Hay una verde carpeta en la salida de la librería\nB) Ahí es una verde carpeta en el éxito de la librería\nC) Hay una alfombra verde a la salida de la biblioteca\nD) Hay una alfombra verde a la salida de la librería' : 'c',

        '¿Cuánto tiempo tarda la luz del Sol en llegar a la Tierra?\nA) 12 minutos\nB) 1 día\nC) 12 horas\nD) 8 minutos' : 'd'

        }

       

    # Inicializa las variables y configura el juego

    global indice_turno

    global preguntas_por_casilla

    global respuestas_correctas

    global bob

    global tesoro

    global posible_ganador

    global jugadores

    global final

    global ya

    global preg

    indice_turno = 0

    jugadores = []

    posible_ganador = []

    ya = []

   

    bob = [[1, 2, 3, 4, 5, 6, 7, 8, 9, 10],

            [11, 12, 13, 14, 15, 16, 17, 18, 19, 20],

            [21, 22, 23, 24, 25, 26, 27, 28, 29, 30],

            [31, 32, 33, 34, 35, 36, 37, 38, 39, 40],

            [41, 42, 43, 44, 45, 46, 47, 48, 49, 50]]

 

    preguntas_lista = list(preguntas.keys())

    random.shuffle(preguntas_lista)

    preguntas_por_casilla = {}

    respuestas_correctas = {}

    for i in range(1, 51):  # Asumiendo que son 50 preguntas

        if i <= len(preguntas_lista):

            pregunta = preguntas_lista[i - 1]

            respuesta = preguntas[pregunta]

            preguntas_por_casilla[i] = pregunta

            respuestas_correctas[i] = respuesta

        else:

            preguntas_por_casilla[i] = "Pregunta no disponible"

            respuestas_correctas[i] = None

    tesoro = random.randint(1,50)

    final = False

    cant = int(input('inserte la cantidad de jugadores:'))

    for i in range(0,cant):

        jugadores.append(input('inserte el  nombre del jugador numero' + str(i+1) + ':'))

        posible_ganador.append(cant)

   

def ciclo_de_turnos(jugadores): #Una funcion que permite la organizacion del ciclo de jugadores, sin importar su cantidad

    global jugador_actual

    indice_turno = 0

    while True:

        jugador_actual = jugadores[indice_turno % len(jugadores)]

        print(f"Turno de {jugador_actual}")

        indice_turno += 1

       

       

def mostrar_tablero(): #Muestra el tablero

   

    print("mapa actual:")

    for fila in bob:

        print(fila)

 

def elegir_casilla(): # Permitir a los jugadores elegir una casilla del tablero

   

    casilla_seleccionada = int(input("Elige una casilla: "))

    return casilla_seleccionada

 

 

def reemplazar_casilla(casilla_seleccionada): #Para reemplazar la casilla elegida por una x

    for i in range(len(bob)):  # Recorrer las filas

        for j in range(len(bob[i])):  # Recorrer las columnas

            if bob[i][j] == casilla_seleccionada:  # Encontrar el número seleccionado

                bob[i][j] = 'x'  # Reemplazar con un x, simbolizando que se cavo un hoyo

                return

def turnos_y_preguntas(casilla_seleccionada, jugador_actual): # Seleccionar una pregunta aleatoria y mostrarla al jugador

   

    if casilla_seleccionada in ya:

        print('Esa casilla ya fue cavada, intenta de nuevo')

        print(f'''Turno de {jugador_actual}

             

             

              ''')

        casilla_seleccionada = elegir_casilla()

        turnos_y_preguntas(casilla_seleccionada,jugador_actual)

    else:

        pregunta = preguntas_por_casilla[casilla_seleccionada]

        respuesta_correcta = respuestas_correctas[casilla_seleccionada]

        print(f"Pregunta: {pregunta}")

        # Verificar si el jugador ha respondido correctamente

        respuesta = input("Ingrese su respuesta: ")

        if respuesta == respuesta_correcta and casilla_seleccionada == tesoro:

            ganador(jugador_actual)

        elif respuesta == respuesta_correcta:

            print("La respuesta es correcta!, pero el tesoro no estaba alli")

            reemplazar_casilla(casilla_seleccionada)

            ya.append(casilla_seleccionada)

        else:

            print(f"Incorrecto, {jugador_actual} ha fallado al cavar el hoyo")

               

           

       

 

def ganador(jugador_actual): #Si un jugador gana, se muestra su nombre y se reinicia la funcion main

    global final

    print(f'felicidades {jugador_actual} has ganado!!!')

   

    print(''''volviendo al menu principal...

         

         

          ''')

    final = True

 

 

 

 

 

 

 

def main(): #Main

    global indice_turno

    while True:

       

        print(('''Bienvenido a Búsqueda del Tesoro!

   

        1 | Iniciar Juego

        ------------------

        2 | Manual

        ------------------

        3 | Créditos

        ------------------

        4 | Salir

        ------------------

   

        '''))

        opcion = input('elige una opcion:')

       

        if opcion == '1':

            iniciar_juego()

            while final == False:

                mostrar_tablero()

                jugador_actual = jugadores[indice_turno % len(jugadores)]

                print(

                   

                    f'''Turno de {jugador_actual}

                     

                     

                      ''')

                casilla_seleccionada = elegir_casilla()

                turnos_y_preguntas(casilla_seleccionada,jugador_actual)

               

                indice_turno = indice_turno + 1

           

       

        elif opcion== '2':

            manual()

        elif opcion== '3':

            creditos()

        elif opcion=='4':

            raise SystemExit

        else:

            print('opcion incorrecta, intenta de nuevo')

           

main()
