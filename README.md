Para poder ejecutar correctamente el proyecto, es necesario contar con un entorno de desarrollo previamente configurado.

Requisitos necesarios

Java Development Kit (JDK 23)

Apache Maven

Visual Studio Code

Extensiones de VSCode:

Java Extension Pack

Language Support for Java by Red Hat

Debugger for Java

Además, deben estar configuradas correctamente las variables de entorno:

JAVA_HOME

MAVEN_HOME

Instalación del proyecto

Clonar el repositorio desde GitHub:

git clone <URL_DEL_REPOSITORIO>


Acceder al directorio del proyecto:

cd proyecto-hola-mundo


Abrir el proyecto con Visual Studio Code:

code .

3. Instrucciones de Ejecución

Una vez instalado el proyecto, se debe utilizar Maven para compilar y ejecutar la aplicación.

Abrir la terminal integrada de Visual Studio Code.

Compilar el proyecto con el siguiente comando:

mvn compile


Ejecutar la aplicación indicando la clase principal:

mvn exec:java -Dexec.mainClass="com.ejemplo.holamundo.App"


Si la ejecución es correcta, aparecerá una ventana emergente con el mensaje “Hola Mundo”.

4. Posibles Problemas y Soluciones
Problema 1: Maven no se reconoce como comando

Descripción:
Al ejecutar mvn compile, el sistema indica que el comando no existe.

Solución:
Verificar que Apache Maven esté correctamente instalado y que la variable de entorno MAVEN_HOME esté configurada y añadida al PATH.

Problema 2: Error relacionado con JAVA_HOME

Descripción:
Durante la compilación aparece un error indicando que Java no está configurado correctamente.

Solución:
Comprobar que el JDK 23 esté instalado y que la variable de entorno JAVA_HOME apunte a la ruta correcta del JDK.

Problema 3: No aparece la ventana emergente

Descripción:
La aplicación se ejecuta, pero no se muestra la ventana.

Solución:
Verificar que el código Java utiliza correctamente la clase JOptionPane y que la clase principal especificada en Maven sea:

com.ejemplo.holamundo.App

5. Información Adicional sobre las Dependencias Utilizadas

El proyecto utiliza Apache Maven como herramienta de gestión del proyecto.

No se han añadido dependencias externas.

Se emplean únicamente librerías estándar de Java SE, concretamente:

javax.swing.JFrame

javax.swing.JOptionPane

Maven se encarga de la compilación, organización del proyecto y ejecución de la aplicación mediante su estructura y plugins por defecto.

Grabación de pantalla 2026-01-23 003950.gif
