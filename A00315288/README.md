### Examen 1
**Universidad ICESI**  
**Curso:** Sistemas Operativos  
**Docente:** Daniel Barragán C.  
**Tema:** Comandos de Linux, Virtualización  
**Correo:** daniel.barragan at correo.icesi.edu.co  
**Estudiante:** Julián David González Jiménez  
**Código:** A00315288  

### Objetivos
* Conocer y emplear comandos de Linux para la realización de tareas administrativas
* Virtualizar un sistema operativo
* Conocer y emplear capacidades de CentOS7 para la vitualización

### Prerrequisitos
* Virtualbox o WMWare
* Máquina virtual con sistema operativo CentOS7

### Descripción
El primer parcial del curso sistemas operativos trata sobre el manejo de los comandos de Linux, virtualización y el uso de las características de CentOS7

### Actividades
1. Incluir nombre, código (5%)
2. Ortografía y redacción cuando sea necesario (5%)
3. Resuelva los siguienes retos de la página https://cmdchallenge.com y presente la solución a cada uno de ellos a través de un ejemplo práctico en CentOS7. Presente capturas de pantalla relevantes como evidencias de lo realizado (20%)

  * sum_all_numbers  
  Cree un archivo de texto y coloque números en forma de lista, al ejecutar el comando cat archivo | jq -s add, se suman todos los números que hay en esa lista.
  
  
  ![][2] 
  
  ![][1]
  
  * replace_spaces_in_filenames  
  Cree un directorio y al ejercutar el comando ls | tr "lo que quiero cambiar" "lo que va a aparecer"; no solo es para espacios en blanco, puede ser para cualquiere caracter. 
  
   ![][4] 
  
  ![][3]
  
  * reverse_readme  
  Se crea un archivo de texto con palabras en forma de lista, al ejecutar el comando cat archivo | tac, se reordena la lista, colocando las palabras en orden contrario. 
  
  ![][6] 
  
  ![][5]
  
  * remove_duplicated_lines  
  Cree un archivo de texto con una lista de palabras que se repiten, al usar el comando cat archivo | awk '!x[$0]++', se eliminan las palabras que se repiten en el archivo. 
  
  ![][8] 
  
  ![][7]
  
  * disp_table  
  Se crea un archivo de tipo csv en donde se intenta crear una tabla con el formato por comas, que separan cada columna, al ejecutar el comando cat archivo | column -s , -t, se reacomoda el archivo y queda en formato tabla. 
  
  ![][10] 
  
  ![][9]
  
4. Realice un script que cumpla las condiciones que se describen a continuación. Presente capturas de pantalla relevantes como evidencias del funcionamiento (30%)
  * El usuario gutenberg debe existir en el sistema operativo  
  Para crear un usuario se usa el comando adduser. Se puede observar en la captura que estoy dentro del usuario gutenberg. 
  
  ![][11] 
  
  * El script se debe ejecutar cada 5 minutos, consulte el manual de crontab  
  Se tiene que modificar el archivo crontab por medio del comando crontab -e, ahi se debe escribir, por medio del formato que crontab maneja, el tiempo cuando se debe ejecutar, el comando que se espera que se ejecute y la ruta del archivo a ejecutar. 
  
  ![][12]
   
  * EL script debe descargar un libro del proyecto https://www.gutenberg.org/ en el directorio /home/gutenberg/mybooks  
  Se crea un archivo .sh, que básicamente lo que hace es crear un número aleatorio, despúes por medio del comando wget descarga un archivo .txt de una página web, y y lo guarda en la carpeta mybooks.
  
   ![][13]
   
   ![][14] 
   
  * Si ya existe un libro en el directorio mybooks, debe ser reemplazado  
  Se puede observar que estamos en la carpeta mybooks, imprimo las primeras diez lineas del libro y aparecen, es decir que el archvo punto .sh funciona, despúes aparece un mensaje que dice que tiene un correo nuevo, esto indica que se volvió
   a ejecutar el archivo .sh, y por último muestro otra vez las primeras 10 líneas del archivo y se ve que es otro libro totalmente diferente al anterior.
   
   ![][15] 
  
5. Describa el funcionamiento del código fuente rickroll.c del repositorio de github https://github.com/jvns/kernel-module-fun. Muestre el funcionamiento al compilar el código y cargarlo como un módulo del kernel a través de un video que deberá cargar en Youtube e incluir el enlace en el informe (30%). Se recomienda emplear el sistema operativo Ubuntu con interfaz gráfica para esta prueba.

Funcionamento del código fuente rickroll.c: El código basicamente lo que hace es que cuando uno abra cualquier mp3, se abra siempre la misma canción llamada: Rick Astley - Never Gonna Give You Up, en vez de abrir la canción originalmente abierta. 

Como hace esto:
Las primeras lineas importan los modulos necesarios para ejecutar todo el el resto del código. A continuación se inicializan las variables que se van a utilizar, también se definen dos modificaciones a un registro del sistema operativo llamado: DISABLE_WRITE_PROTECTION y ENABLE_WRITE_PROTECTION. Despúes de esto si viene la parte de la ejecución del algoritmo, con el metodo rickroll_init. La primera parte de este método verifica que la ruta sea valida, despúes se obtiene la tabla de llamadas al sistema y verifica que si se halla almacenado bien la tabla. Por último se deshabilita la protección contra escritura en la tabla, se llama al metodo que es el encargado de abrir el archivo. Se modifica el puntero que abre archivos en la tabla de llamados al sistema, para que apunte siempre al método rickroll_open. Este método con la extención del archivo que se intenta abrir, si no es .mp3, llama a la función original_sys_open, pasandole el archivo que se esta intentando abrir, esto para que como esta archivo no es mp3, se pueda abrir con normalidad. Si el archivo si es mp3 se llama a original_sys_open pero esta vez como parametro le pasa la ruta de la canción ya dicha, así siempre se va a abrir esta canción en vez de otro archivo mp3. Al final esta el metodo rickroll_cleanup, para dejar la tabla de llamadas al sistema como antes de realizar los cambios. 

6. El informe debe ser entregado en formato pdf a través del moodle y el informe en formato README.md debe ser subido a un repositorio de github. El repositorio de github debe ser un fork de https://github.com/ICESI-Training/so-exam1 y para la entrega deberá hacer un Pull Request (PR) respetando la estructura definida. El código fuente y la url de github deben incluirse en el informe (10%)  

### Referencias
* https://cmdchallenge.com  
* https://www.gutenberg.org  
* https://github.com/jvns/kernel-module-fun/blob/master/rickroll.c
* https://www.youtube.com/watch?v=efEZZZf_nTc

[1]: acentos.png
[2]: aoage.png
[3]: bcentos.png
[4]: bpage.png
[5]: ccentos.png
[6]: cpage.png
[7]: dcentos.png
[8]: dpage.png
[9]: ecentos.png
[10]: epage.png
[11]: lsgutenberg.png
[12]: contrab-e.png
[13]: sh.png
[14]: lsmybooks.png
[15]: verificacion.png



