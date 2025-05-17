# 52007
ANALIZADOR DE EXPRESIONES LOGICAS CON ANTLR Y JAVASCRIPT:

- Este proyecto permite analizar, interpretar y traducir expresiones lógicas escritas en notación proposicional a código JavaScript. Utiliza ANTLR4 para el análisis léxico y sintáctico, y     cuenta con funcionalidades como:

   1.DETECTAR ERRORES LEXICOS Y SINTACTICOS EN EXPRESIONES LOGICAS. 

   2.GENERAR EL ARBOL DE DERIVACION DE ESA EXPRESION.

   3.GENERA TABLA DONDE SE IDENTIFICA LOS LEXEMAS Y LOS TOKENS. 

   4.TRADUCE LA EXPRESION A SU EQUIVALENCIA EN JAVASCRIPT. 

REQUISITOS PARA QUE FUNCIONE DE MANERA CORRECTA: 
 1. Tener instalado Node.js (16 o superior)
    https://nodejs.org/es
 2. Tener instalado VS Code
    https://code.visualstudio.com/ 
 3. Tener instalado Java 11 o superior
    https://www.oracle.com/java/technologies/downloads/#java11
    (Seleccionar Segun su Sistema Operativo )  
 5. Tener Instalado Antlr como extensión de VS code

  ![Captura de pantalla 2025-05-17 151929](https://github.com/user-attachments/assets/53e2eb72-a32c-4f97-a1f9-df7a06c6a002)



Importante: Luego de instalar la extensión reinicia VS Code para que tome los cambios.

Instalacion del proyecto: Una vez ya instalados los requirimientos previos los siguiente es

1.Configurar las preferencias de generación de código de ANTLR: ve al menú
Archivo/Preferencias/Configuración ( CTL + ,) y busca las preferencias de ANTLR. Baja hasta
la sección Antlr4:Generation y edita settings.json. 


![Captura de pantalla 2025-05-17 152002](https://github.com/user-attachments/assets/e0d9c78f-1a5d-42d2-9f8e-0bc757dcbb86)

 
 
 Borrar todo lo que se encuentre y reemplazar por : 

{"antlr4.generation":{

"alternativeJar": "antlr-4.13.2-complete.jar",
 
 "mode": "external",
 
 "listeners": true,

 "visitors": true,
 
 "language": "JavaScript",

 "outputDir": "./generated"
 
 }}

  Importante: Guarda el archivo de configuración antes de continuar (CTRL+S)

  - Una vez instalado el ANTLR se debe clonar el proyecto desde el comando cmd ejecutando el siguiente comando

     git clone https://github.com/LIbanez04/52007.git

    - Una vez clonado cambiamos el directorio raiz del proyecto ejecutando el siguiente comando (CMD O POWERSHELL):

      cd antlr-analyzer
    - Despues ejecutamos el siguiente comando para abrirlo en VS code :

       . code


     ![Captura de pantalla (127)](https://github.com/user-attachments/assets/57a17d08-dcb9-4b00-ba83-42c7043c76fd)



      - Si la instalacion se realizo correctamente se deberian ver el proyecto en VS code.

FUNCIONAMIENTO DEL ANALIZADOR: 
1. Al presionar sobre el archivo Logic.g4 se podra observar la gramatica propuesta para el caso que estudia el analizador
2. La gramatica se divide en:

    . SINTAXIS (PARSER): En donde se define la combinacion de los tokens para generar cadenas validas

    . LEXICO (LEXER) : Aqui se define los elementos basicos del lenguaje como los operadores y parentesis

3. Para probar una entrada se necesita editar el archivo input.txt e ingresar una cadena o entrada (ej: p v q) y guardar los cambios (CTRL+S) 
4. Utilizando el Plugin ANTLR4 para construir el arbol de sintaxis para la cadena ingresada en el archivo input.txt se debe presionar F5.
5. Para ver el analizador funcionar concretamente nos vamos al directorio raiz del proyecto y abrimos el terminal

   ![Captura de pantalla (128)](https://github.com/user-attachments/assets/709944ef-eb4c-44af-8182-9c7957420993)



6. Una vez abierto el terminal debemos ejecutar el siguiente comando: npm start

   (Esto dara la instruccion de arranque al programa)

7. Una vez ejecutado el comando mostrara lo siguiente si entrada asignada en el input.txt es valida ( En este caso utilice la entrada ( p v q )

    a. Tabla de Tokens donde identificara cual es el Lexema y cual es el toquen asociado:


  ![Captura de pantalla 2025-05-17 152604](https://github.com/user-attachments/assets/5d06485c-3b35-4ed2-a536-01b54b34b203)


   
   b. Arbol de analisis sintactico:


  ![Captura de pantalla 2025-05-17 152649](https://github.com/user-attachments/assets/3a47afd9-0ef6-4d4e-8520-249ebde94d23)

   
  c . La traduccion de la entrada al Lenguaje de Programacion JAVASCRPT:


   ![Captura de pantalla 2025-05-17 152727](https://github.com/user-attachments/assets/4e5e4df9-18ae-4b28-bbc5-fbb3ba3821aa)


   d. El analisis respecto a la entrada, es decir determina si la entrada es valida o no y nos arrojara un "true" si la entrada es valida

   ![Captura de pantalla 2025-05-17 152756](https://github.com/user-attachments/assets/4789a6da-a4fd-4321-8d5a-44a655e321e0)

 
9. En caso de ser una entrada invalida(Lexica o sintacticamente) puesta previamente en el acrhivo input.txt.

   (En este caso utilice la cadena p # q) debiendo mostrar lo siguiente:

    a. Tipo de Error Detectado (LEXICO O SINTACTICO) 


      ![Captura de pantalla 2025-05-17 152854](https://github.com/user-attachments/assets/76a0ae67-b7ac-4a62-837e-cc7a6895612e)



     b. Linea donde se produce el error


      ![Captura de pantalla 2025-05-17 152924](https://github.com/user-attachments/assets/f85a5b24-0465-4d84-bc18-2c7a9e5bc0d1)


    c. El motivo del Error
  
      ![Captura de pantalla 2025-05-17 152950](https://github.com/user-attachments/assets/7c4a0892-c4cb-4cee-847a-c642fc75c6d3)


 



    
     
