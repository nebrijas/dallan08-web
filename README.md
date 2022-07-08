# Repositorio de trabajo del módulo PERIODISMO DE DATOS II

#Actividades-Indice 


- [Actividad_dirigida_1](ad1.md)
- [Actividad_dirigida_2](ad2.md)
- [Actividad_dirigida_3](ad3.md)
- [Actividad_dirigida_4](ad4.md)


## Último ejercicio de programación literaria

#### ¿Qué hemos hecho durante este módulo de Periodismo de Datos II: Herramientas digitales para la visualización y presentación de datos? 

Sin duda alguna con este módulo he conocido y practicado la base de la **visualización de datos**, un mundo que si bien es interesante, requiere de mucha práctica para ejecutarlo con mayor agilidad. En los próximos puntos explicaré lo que he hecho en las actividades dirigidas, las cuales han sido cuatro:

1. **La actividad dirigida 1:** Me encantó porque trató sobre destacar los aspectos que me habían llamado la atención de un reportaje de visualización de datos. El objetivo era practicar con Markdown. Fue como la introducción a Markdown, un código que era completamente nuevo para mí. Con Markdown pude agregar formatos como encabezados, negritas, cursivas, listas, a el texto del reportaje que había seleccionado del diario [El Mundo](https://www.elmundo.es/ciencia-y-salud/medio-ambiente/2021/12/30/61bcd569fc6c83a2308b459a.html), titulado **"Del cuerno de rinoceronte al guacamayo: Así opera en España el mercado negro de animales protegidos que sobrevive a la pandemia"**. 
De la sintaxis de Markdowm aprendí a colocar un texto en negrita, en cursiva, a colocar a la ves cursiva y negrita. Aunque de la sintaxis lo primero que aprendí fue a colocar los títulos con los **hashtag #** (como le llamamos en Panamá) o almohadillas. A medida que se van sumando más #, el título va tomando un tamaño inferior. 
- Por ejemplo, para un titulo de primer nivel, es decir el más grande sería un # (*hashtag*), pero solo al principio de la frase o la palabra que desee resaltar. No obstante, me quedó claro que el # debe ir precedido de un espacio, porque de lo contrarrio no se marcara el tamaño deseado. Emplear un solo hashtag es lo que se conoce como **h1**, si ya va incrementando el número de #, sería **h2, h3, h4**.
- Hoy día sé como hacer una lista ordenada, que es con números (1., 2., 3., y así sucesivamente) para enlistar los elementos que queremos resaltar; pero también sé cómo se hace una lista desordenada, pues se emplea el guion (-) antes de lo que queremos que salga en una lista, pero no tendrá un orden per se.  
- En el caso de las **negritas** se deben colocar **dos asteriscos al inicio y al final del enunciado** que se quiere resaltar. 
- Mientras que para el caso de las **cursivas** solo se agrega un **asterico, tanto al inicio o al final del texto** que se desee resaltar en cursiva. 
- Si quisiera utilizar los dos la **cursiva y negrita a la vez**, debo combinar la sintaxis, envolviendo la palabra entre tres asteriscos o tres guiones bajos.
- Para lograr una cita en el texto se debe utilizar el carácter mayor que **>** al inicio del bloque de texto.
    
Este es solo un resumen de lo que aprendí de la sintaxis de Markdown, algo que me ha parecido super intersante y es hasta divertido emplearlas en los textos. Solo hay que precticar más para poder recordarlas bien. 

2. **La actividad dirigida 2**: ¡Un gran reto para mí! Aprendí a emplear Git Bash, que es una aplicación de terminal que se emplea como interfaz con un sistema operativo a través de comandos escritos.
Al ingresar a la terminal de Git Bash el primer paso fue clonar (**Git clone**) https://github.com/nebrijas/dallan08-web. Fue aquí donde pude modificar el repositorio; también tuve que configurar el **name, con git config name** y el **e-mail, con git config e-mail**; generamos un toquen. Todo el proceso para el uso por primera vez de Git Bash. 
Para usar Gitb Bash hay que tener presente algunos comandos, a continuación detalles algunos de los que empleamos en este módulo:
- El comando **Git clone** es para descargarte el código fuente existente desde un repositorio remoto.
- El comando **pwd** funciona para imprimir el directorio de trabajo actual.
- Con el comando de **ls** se enumerar el contenido del directorio actual.
- El comando de **git status** proporciona la información necesaria sobre la rama actual.
- Con el comando **git add** se incluyen los cambios del o de los archivos en tu siguiente commit.
- **Git commit** considero que es el comando más usado. Se emplea cuando ya queremos guardar los cambios de una tarea.
- El comando **Git push** es el paso con el que le das enviar tus cambios al servidor remoto. Es decir, este comando envía tus commits al repositorio remoto.
- El comando **git pull** se usa para recibir actualizaciones del repositorio remoto. 

Pero, esto no es todo, ya que en esta actividad también se convirtió el contenido que teníamos en GitHub a página web. Ese primer contenido en GitHub fue una de las primeras cosas que vimos en la asignatura antes de llegar a Jupyter. 

3. **La actividad dirigida 3**: Inauguramos esta actividad con un ejercicio de **Programación literaria** (primera vez con este tema). El código fue facilitado por el profesor, la temática era sobre las secciones del diario **El País**. Hicimos un **web scrapping**. 
Teníamos que ir describiendo las acciones que realizamos con el código. En algunos se repetía el proceso, pero igual se practicó para ir afianzando los conocimientos. 
Como mencioné anteriormente teníamos que hacer un ejercicio de **Programación literaria**, es decir, ir explicando todo lo que ibamos ejecutando con el código, parte por parte, utilizando la sintaxis de Markdown. Hemos aprendido a usar Jupyter (toda una odisea instalar este programa). Durante esta actividad de **programación literaria** pudimos ir describiendo en una celda del cuaderno de Jupyter teníamos el código y en la siguiente cela podíamos cambiar a lenguaje Markdown para explicar lo que significaba el código y lo que habíamos hecho. Al final para guardar o para que tomará el formato Markdown se lograba con **Ctrl + enter**, lo mismo se hacía para ejecutar el código. 

4. **La actividad dirigida 4**: ¡Una actividad muy interesante! En esta ocasión también hicimos un ejercicio de **Programación literaria**, pero aprendimos algo más, **obtener datos de tablas y a convertir esos datos en gráficas**, las cuales son importantes para trabajar reportajes de datos, con ese elemento gráfico podemos mostrar la información de una forma más concreta y atractiva a los lectores. Esta actividad también la trabajamos en un cuaderno de **Jupyter**. Al igual que la actividad anterior se iba explicando con la sintaxis de Markdown lo que se ejecutaba con el código (que estaba en la celda de code). Además, íbamos viendo los resultados del **código** que ejecutábamos, algo que me sorprendió. 
Para esta actividad nos conectamos a la [API](https://api.covid19api.com/), también se hizo la instalación e importación de Pandas para poder realizar la actividad. Luego empezamos a definir la **Variable/Objeto** para poder llamar a la lista de la API y para saber si funciona la llamada invocamos a la *url*.
También usamos la función **función pd.read_json**, a la cual se le añade una **variable** (df) y con ella podemos ver un estracto con las filas del inicio y las del final.
Aplicando varias funciones vimos primeros los datos de los **Casos de Covid-19 de España y Panamá**, e incluso hicimos una comparación entre amos. Luego hicimos una comparación entre los países de Centroamérica. De los países centroamericanos obtuvimos tablas y gráficos. Después concatenamos `(pd.concat)` todos los países (Panamá, Costa Rica, Nicaragua, Guatemala y El Salvador) en una una sola tabla y procedimos a plotear para verlo en una sola gráfica. 



