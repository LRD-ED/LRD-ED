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



Proyecto de Depuración Java
1. Instalación y Ejecución
Clonar: git clone

Compilar: mvn clean compile

Ejecutar: Abrir Main.java y pulsar F5 en VS Code (o usar el comando mvn exec:java -Dexec.mainClass="com.miempresa.app.Main").

2. Errores y Soluciones
Error 1: División por Cero
Fallo: ArithmeticException al dividir entre 0 en Calculadora.java.

Depuración: Localizado con Breakpoints viendo que la variable b era 0 en el panel de Variables.

Solución: Se añadió un if (b == 0) para evitar el cálculo y devolver 0.

Error 2: Puntero Nulo
Fallo: NullPointerException en Utils.java al usar .length() en un texto null.

Depuración: Identificado rastreando el flujo en el Call Stack (Pila de llamadas).

Solución: Se añadió un if (texto == null) para validar la variable antes de medirla.

3. Dependencias
Maven: Gestiona la estructura del proyecto y la compilación.

Java JDK 17: Versión del lenguaje utilizada.

Swing (JOptionPane): Librería nativa usada para mostrar la ventana emergente de "Hola Mundo".

Resultado Esperado
Al ejecutar la versión corregida, la aplicación ya no se cierra; procesa los datos y muestra una ventana con el mensaje "Hola Mundo".


------------------------------------------------------------------TAREA 12.1-------------------------------------------------------------------------------------

Este proyecto consiste en la automatización de dos procesos clave en el sistema de gestión de recursos humanos OrangeHRM. El objetivo principal fue validar que el sistema permite crear un empleado y, posteriormente, asignarle múltiples componentes salariales de forma correcta.

Para que este robot funcione, se han utilizado las siguientes "piezas":

Java: El lenguaje de programación (el cerebro).

Selenium WebDriver: La herramienta que mueve el ratón y escribe en el navegador.

TestNG: El marco que organiza las pruebas y nos dice si han pasado o han fallado.

Maven: El encargado de descargar todas las librerías necesarias automáticamente.

Proceso de Ejecución 
1. Creación del Empleado (Precondición)
Primero, el robot entra al sistema con las credenciales de administrador. Navega al módulo PIM, rellena los datos básicos de un nuevo empleado (Nombre y Apellido) y guarda los cambios. Este paso es fundamental porque sin un empleado, no podemos asignar salarios.

2. Asignación de Múltiples Salarios
Una vez creado el empleado, el robot:

Lo busca en la lista general para entrar a su perfil.

Accede a la pestaña Salary.

Añade un "Salario Base" de $30,000.

Añade un "Bono Anual" de $5,000.

Verifica que ambos registros queden guardados en la tabla del empleado.

Durante el desarrollo, nos encontramos con varios obstáculos técnicos que logramos solucionar:

El problema de los botones "fantasma": OrangeHRM tiene muchos botones de "Guardar" que se llaman igual. Para solucionarlo, creamos una ruta específica (XPath) que le dice al robot: "Dale al botón de guardar que está SOLO dentro de la caja de salarios".

Listas desplegables rebeldes: Seleccionar la moneda a veces fallaba porque la lista tardaba en cargar. Lo solucionamos usando comandos de teclado (flecha abajo y Enter), lo cual es mucho más fiable que intentar hacer clic en el texto.

Sincronización: El robot es más rápido que la página web. Añadimos esperas inteligentes para que el robot aguante unos segundos hasta que los mensajes de éxito desaparezcan antes de intentar hacer la siguiente acción.


--------------------------------------------ACT 12.2----------------------------------------------------------------------------------------------------

# Proyecto de Automatización de Pruebas: Módulos Admin, PIM y Leave (OrangeHRM)

Este proyecto contiene el diseño, la documentación y la automatización de la suite de pruebas funcionales para la plataforma **OrangeHRM** (Demo Open Source), abarcando los módulos críticos de **Administración (Admin)**, **Gestión de Personal (PIM)** y **Control de Ausencias (Leave)**.

El objetivo principal es asegurar la estabilidad de los flujos de trabajo mediante la creación de scripts robustos e inmunes a fallos dinámicos de la interfaz.

---

## 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Java 11 / 17
* **Framework de Pruebas:** JUnit 5 / TestNG (IntelliJ IDEA)
* **Automatización del Navegador:** Selenium WebDriver (Chrome Driver)
* **Patrón de Sincronización:** Explicit Waits (`WebDriverWait`) para el manejo seguro de componentes asíncronos y listas flotantes.

---

## 📋 Cobertura de la Suite de Pruebas (Test Cases)

El proyecto cuenta con un total de **10 Casos de Prueba (TC)** completamente automatizados, diseñados bajo una estricta separación de acciones y condiciones de verificación:

| TestID | Módulo | Nombre del Caso de Prueba | Descripción / Acción Clave |
| :--- | :--- | :--- | :--- |
| **TC01** | Auth | Login Exitoso | Validación del acceso al panel principal (`Dashboard`). |
| **TC02** | Admin | Creación de Job Title | Alta de un nuevo puesto de trabajo y verificación en la tabla. |
| **TC03** | Admin | Creación de Nacionalidad | Registro dinámico inmune a duplicados utilizando sufijos aleatorios. |
| **TC04** | Admin | Edición de Información General | Activación del *toggle* de edición y actualización del número de registro empresarial. |
| **TC05** | PIM | Creación de Empleado con Credenciales | Alta completa en el sistema expandiendo el formulario de seguridad (Usuario/Password). |
| **TC06** | PIM | Búsqueda de Informes de Empleado | Manejo de selectores dinámicos y autocompletado (`Type for hints...`). |
| **TC07** | PIM | Búsqueda y Eliminación de Empleado | Flujo completo de borrado interactuando con modales de confirmación (`Yes, Delete`). |
| **TC08** | Leave | Consulta de Asignaciones de Empleado | Control avanzado de menús desplegables basados en contenedores `div` flotantes. |
| **TC09** | Leave | Generación de Informe de Ausencias | Filtrado por tipología de baja y renderizado del contenedor de resultados (`Generate`). |
| **TC10** | Leave | Asignación Exitosa de Ausencia | Flujo corregido contra duplicados de fecha (limpieza por emulación de teclado) y control de saldos. |

---

## 🚀 Estrategias de Robustez Implementadas (Anti-Fallos)

Durante el desarrollo se identificaron comportamientos dinámicos complejos en OrangeHRM que hacían que las pruebas convencionales fallaran. Se aplicaron las siguientes soluciones técnicas:
1. **Borrado Agresivo de Calendarios:** Ante el bloqueo del método `.clear()` nativo de Selenium en los campos de fecha, se implementó una simulación humana mediante comandos de teclado (`CONTROL + A` + `BACK_SPACE`) para evitar la duplicación de cadenas de texto.
2. **Captura de Listbox Flotantes:** Las sugerencias de nombres y desplegables no usan elementos HTML `<select>` estándar. Se controlaron mediante esperas explícitas de visibilidad sobre contenedores con `role='listbox'` y clics directos sobre sus nodos hijos indexados o por texto.
3. **Mapeo Riguroso (Normas de Uso):** El diseño de la suite de pruebas se ciñe estrictamente a la separación de **StepAction** (*Pulsar*, *Escribir*, *Seleccionar*) y **StepCondition** (*Comprobar que...*), garantizando una documentación 1:1 con el código de Selenium.

