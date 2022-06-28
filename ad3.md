# AD3

Esta es la actividad dirigida 3 que consiste en hacer un ejercicio de programación literaria aprovechando el código que hemos usado en programación con Python donde realizamos *web scraping*. 
A continuación pongo el código fuente.

## Instalar librerías

En estos casos no es necesario instalar aquellas librerías que vienen con *Python*, pero las `externas` sí deben ser ___instaladas.


```python
pip install requests bs4 pandas termcolor
```

    Requirement already satisfied: requests in c:\users\fanny\documents\python scripts\lib\site-packages (2.27.1)
    Requirement already satisfied: bs4 in c:\users\fanny\documents\python scripts\lib\site-packages (0.0.1)
    Requirement already satisfied: pandas in c:\users\fanny\documents\python scripts\lib\site-packages (1.4.2)
    Requirement already satisfied: termcolor in c:\users\fanny\documents\python scripts\lib\site-packages (1.1.0)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (1.26.9)
    Requirement already satisfied: charset-normalizer~=2.0.0 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (2.0.4)
    Requirement already satisfied: idna<4,>=2.5 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (3.3)
    Requirement already satisfied: certifi>=2017.4.17 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (2021.10.8)
    Requirement already satisfied: beautifulsoup4 in c:\users\fanny\documents\python scripts\lib\site-packages (from bs4) (4.11.1)
    Requirement already satisfied: python-dateutil>=2.8.1 in c:\users\fanny\documents\python scripts\lib\site-packages (from pandas) (2.8.2)
    Requirement already satisfied: pytz>=2020.1 in c:\users\fanny\documents\python scripts\lib\site-packages (from pandas) (2021.3)
    Requirement already satisfied: numpy>=1.18.5 in c:\users\fanny\documents\python scripts\lib\site-packages (from pandas) (1.21.5)
    Requirement already satisfied: six>=1.5 in c:\users\fanny\documents\python scripts\lib\site-packages (from python-dateutil>=2.8.1->pandas) (1.16.0)
    Requirement already satisfied: soupsieve>1.2 in c:\users\fanny\documents\python scripts\lib\site-packages (from beautifulsoup4->bs4) (2.3.1)
    Note: you may need to restart the kernel to use updated packages.
    

# Importar librerías


## Librerías y módulos

Aquí voy a importar las siguientes módulos y librerías

**Librerías externas**
- [requests](https://requests.readthedocs.io/en/latest/): Es una librería capaz de facilitar y abstraer el proceso de hacer solicitudes HTTP en Python en gran manera.
- [bs4](https://pypi.org/project/beautifulsoup4/): Beautiful Soup es una librería Python que permite extraer información de contenido en formato HTML o XML.
- [pandas](https://pypi.org/project/pandas/): Es una librería de Python especializada en el manejo y análisis de estructuras de datos.
- [termcolor](https://replit.com/talk/learn/How-to-Use-Termcolor-In-Python/24684): 

**Módulos internos del sistema** 
- [time](https://docs.python.org/es/3/library/time.html): El módulo time de la biblioteca estándar de Python proporciona un conjunto de funciones para trabajar con fechas y/o horas. 
- [csv](https://docs.python.org/es/3/library/csv.html): El módulo csv implementa clases para leer y escribir datos tabulares en formato CSV (valores separados por comas).
- [re](https://docs.python.org/es/3/library/re.html): Las funciones de este módulo permiten comprobar si una determinada cadena coincide con una expresión regular dada. 
- [os](https://docs.python.org/es/3.10/library/os.html):Este módulo permite a usted realizar operaciones dependiente del Sistema Operativo como crear una carpeta, listar contenidos de una carpeta, conocer acerca de un proceso y finalizar un proceso. 



```python
import requests
import time
import csv
import re
from bs4 import BeautifulSoup
import os
import pandas as pd
from termcolor import colored
```

## Código fuente de la actividad


```python
import requests
import time
import csv
import re
from bs4 import BeautifulSoup
import os
import pandas as pd
from termcolor import colored
 
resultados = []
 
req = requests.get("https://resultados.elpais.com")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup = BeautifulSoup(req.text, 'html.parser')
 
tags = soup.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req2 = requests.get("https://elpais.com/internacional")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup2 = BeautifulSoup(req2.text, 'html.parser')
 
tags = soup2.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req3 = requests.get("https://elpais.com/opinion")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup3 = BeautifulSoup(req3.text, 'html.parser')
 
tags = soup3.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req4 = requests.get("https://elpais.com/espana/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup4 = BeautifulSoup(req4.text, 'html.parser')
 
tags = soup4.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req5 = requests.get("https://elpais.com/economia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup5 = BeautifulSoup(req5.text, 'html.parser')
 
tags = soup5.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req6 = requests.get("https://elpais.com/sociedad/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup6 = BeautifulSoup(req6.text, 'html.parser')
 
tags = soup6.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req7 = requests.get("https://elpais.com/educacion/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup7 = BeautifulSoup(req7.text, 'html.parser')
 
tags = soup7.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req8 = requests.get("https://elpais.com/clima-y-medio-ambiente/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup8 = BeautifulSoup(req8.text, 'html.parser')
 
tags = soup8.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req9 = requests.get("https://elpais.com/ciencia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup9 = BeautifulSoup(req9.text, 'html.parser')
 
tags = soup9.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req10 = requests.get("https://elpais.com/cultura/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup10 = BeautifulSoup(req10.text, 'html.parser')
 
tags = soup10.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req11 = requests.get("https://elpais.com/babelia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup11 = BeautifulSoup(req11.text, 'html.parser')
 
tags = soup11.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req12 = requests.get("https://elpais.com/deportes/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup12 = BeautifulSoup(req12.text, 'html.parser')
 
tags = soup12.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req13 = requests.get("https://elpais.com/tecnologia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup13 = BeautifulSoup(req13.text, 'html.parser')
 
tags = soup13.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req14 = requests.get("https://elpais.com/tecnologia/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup14 = BeautifulSoup(req14.text, 'html.parser')
 
tags = soup14.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req15 = requests.get("https://elpais.com/gente/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup15 = BeautifulSoup(req15.text, 'html.parser')
 
tags = soup15.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req16 = requests.get("https://elpais.com/television/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup16 = BeautifulSoup(req16.text, 'html.parser')
 
tags = soup16.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
req17 = requests.get("https://elpais.com/eps/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup17 = BeautifulSoup(req17.text, 'html.parser')
 
tags = soup17.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
 
 
os.system("clear")
 
print(colored("A continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:", 'blue', attrs=['bold']))
print(colored("Feminismo", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "feminismo" in s]
print("\n".join(str_match))
 
print(colored("Igualdad", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "igualdad" in s]
print("\n".join(str_match))
 
print(colored("Mujeres", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "mujeres" in s]
print("\n".join(str_match))
 
print(colored("Mujer", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "mujer" in s]
print("\n".join(str_match))
 
print(colored("Brecha salarial", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "brecha salarial" in s]
print("\n".join(str_match))
 
print(colored("Machismo", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "machismo" in s]
print("\n".join(str_match))
 
print(colored("Violencia", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "violencia" in s]
print("\n".join(str_match))
 
print(colored("Maltrato", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "maltrato" in s]
print("\n".join(str_match))
 
print(colored("Homicidio", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "homicidio" in s]
print("\n".join(str_match))
 
print(colored("Género", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "género" in s]
print("\n".join(str_match))
 
print(colored("Asesinato", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "asesinato" in s]
print("\n".join(str_match))
 
print(colored("Sexo", 'green', attrs=['bold']))
 
str_match = [s for s in resultados if "sexo" in s]
print("\n".join(str_match))
```

    Colombia hace examen de conciencia
    Francisco de Roux: “Colombia conoció lo que significa la paz y no va a renunciar a ello”
    Gustavo Petro: “Si fracaso, las tinieblas arrasarán con todo”
    El jefe del Ejército colombiano renuncia para evitar caminar junto a Petro el día de la investidura
    Una testigo clave asegura que Trump sabía que la turba del 6 de enero estaba armada y aun así la instigó
    Ghislaine Maxwell, condenada a 20 años de cárcel por proporcionar menores a Epstein
    Murieron asfixiados y sin agua: la tragedia de los 51 migrantes en un tráiler en San Antonio
    La tragedia de los migrantes muertos en San Antonio, en imágenes
    López Obrador: “Es una tremenda desgracia”
    Al menos dos mexicanos hospitalizados 
    Tráfico de migrantes: un reguero de muertes en las fronteras sur y norte 
    La ruptura del diálogo entre Gobierno y el principal líder indígena ahonda la crisis en Ecuador 
    Un incendio provocado en medio de un motín en una cárcel de Colombia deja al menos 51 muertos
    Argentina limita el acceso a dólares para el pago de importaciones
    La protección del 30% de los mares de República Dominicana, el sueño del ministro asesinado
    Biden: “España es un aliado indispensable”
    La Justicia alemana condena a cinco años de cárcel a un exguardia de un campo nazi de 101 años
    Un ataque armado en un centro de vacunación infantil en México deja dos niños heridos
    Fina García-Marruz y la poesía del silencio
    La amenaza del ‘caso Assange’ 
    Temores frente a un “inevitable” Lula
    OTAN de izquierdas, OTAN de derechas
    La justicia en Colombia: por la verdad a la paz
    China anuncia una reducción de la cuarentena para los pasajeros internacionales
    Eliana Revollar, defensora del Pueblo de Perú: “En el Congreso está habiendo contrarreformas” 
    Una explosión de gas tóxico causa 12 muertos y 250 heridos en el puerto jordano de Áqaba
    “No tenemos otra opción que creer que podemos hacer lo necesario para que la humanidad sobreviva”
     Tras el ataque a un centro comercial en Ucrania: “Nadie entiende por qué Rusia ha hecho esto”
    Dos crímenes machistas sacuden Egipto y Jordania
    La erupción del Vesubio arrasó Pompeya en octubre y no en verano como se pensaba
    Robo de película en la feria de arte de Maastricht: a mazazos contra unas vitrinas con joyas
    De Margaret Atwood a Neil Young: la interrupción del embarazo en la cultura estadounidense
    Muere la actriz Mary Mara ahogada en un río
    Esto no se puede emitir: la historia de diez episodios que fueron demasiado lejos para la televisión
    Periodismo de investigación, una herramienta para la construcción de un mejor sistema democrático
    Enseñar el ombligo: de la obsesión de la moda por lucirlo al tabú por mostrarlo en la edad madura
    Mark Fleischman, dueño de Studio 54, planea terminar su vida con un suicidio asistido el 13 de julio
    La segunda vida de Fire Island, el primer pueblo gay de EE UU: sexo, PrEP, arte y fiestas en piscinas
    Victoria Beckham solo comió verduras y caramelos de menta en la boda de Sergio Ramos y Pilar Rubio
    Los efectos negativos del ‘delivery’: de la contaminación a la mala nutrición
    Viaje a las Lofoten, islas de montañas, frailecillos y leyendas de troles
    Nadal sufre a Cerúndolo en su vuelta a Londres
    La covid apea a Berrettini en Wimbledon
    El PSG comunica a Neymar que no le quiere
    Los circuitos estadounidense y europeo de golf refuerzan su alianza contra la liga saudí
    ¿El éxito en ventas es sinónimo de trascendencia?
    ¿Son necesarias las escuelas de arte?
    América Latina gira hacia una nueva izquierda
    Francia Márquez, Marta Lucía Ramírez y ‘las niñas’
    Nuevo balance de fuerzas en un mundo en conflicto
    Ramón Estévez lamenta llamarse Martin Sheen
    Forty-six migrants found dead inside abandoned trailer in Texas
    New York court strikes down law giving 800,000 noncitizens local voting rights
    Latin America looks to a new left 
    NATO summit opens to chart a blueprint in ‘a more dangerous world’
    Buzz Lightyear: To Lesbians and Beyond 
    Letras Americanas: la actualidad literaria de un continente vista por el escritor Emiliano Monge
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Toda la actualidad científica en el boletín de Materia
    Ideas: reportajes y entrevistas para entender el mundo
    Sturgeon anuncia un nuevo referéndum de independencia en Escocia para el 19 de octubre de 2023
    Un ataque ruso a un centro comercial lleno de civiles deja al menos 18 muertos
    Talíria Petrone, una diputada negra frente al dominio blanco del poder en Brasil
    Joseph Oughourlian, presidente de PRISA: “Es el momento de mirar hacia el futuro con ilusión y ambición”
    Muere Leonardo Del Vecchio, el hombre que le puso gafas al mundo
    La imparable subida de tasas de interés pone a prueba a la economía mexicana 
    California decidirá en noviembre si eleva el derecho al aborto a la Constitución local
    Cuando la homosexualidad te obliga a vivir huyendo
    El objetivo de vacunación mundial del 70% contra la covid-19 está obsoleto
    Canetti, Cortázar, Calvino, Sabato: las cartas de Mario Muchnik desvelan la trastienda de medio siglo de literatura
    Tres camiones españoles para empaquetar los museos de Ucrania
    Del ‘Paraíso perdido’ al ciclo ‘queer’: el director del festival Grec de Barcelona, Cesc Casadesús, recomienda sus espectáculos favoritos  
    Hallada en Canadá una cría de mamut en excepcional estado de conservación 
    ¿Dónde hay civilizaciones extraterrestres?
    Toreros, trenes voladores y ovaciones a Franco: las películas inéditas del ingeniero José Hernández Santorcuato
    El Barça vende el 10% de sus derechos televisivos durante 25 años al fondo Sixth Street por 200 millones
    Alcaraz resiste a base de martillazos
    Nakamura, el ajedrecista más rico
    La protección del 30% de los mares de República Dominicana, el sueño del ministro asesinado se hace realidad
    El inesperado musgo luminoso que puede salvar un barrio de Vigo
    La trampa mortal del trasvase Tajo-Segura: así se ahogan corzos y jabalíes en el canal 
    Lorena Jaume-Palasí: “Crear principios éticos universales para  la inteligencia artificial es una iniciativa cosmética”
    Inteligencia artificial ¿para qué?
    Acelerando la ciencia a 314.000 billones de operaciones por segundo
    Condena firme a la Televisión de Galicia por la persecución política de un periodista durante el mandato de Feijóo
    Podemos denuncia una “cacería judicial” tras desinflarse las tres últimas causas contra el partido
    La caída del chat europeo del crimen complica la vida a los narcos del Estrecho
    Qué ver en televisión para celebrar el Orgullo LGTBI+ 2022
    ‘First Class’: ¿Por qué estáis todas en barcos?’, por Paloma Rando
    ‘El manglar de la publicidad en abierto’, por Jimina Sabadú
    El mejor perro del mundo es un fox terrier llamado ‘Funfair Foxhouse’ y se ha coronado en Madrid
    Federico y Mary de Dinamarca sacan a su hijo mayor de su escuela por casos de acoso escolar y abusos sexuales
    Gracias, Locomía
    Volver a la escuela tras dos años de pandemia
    La discriminación contra las minorías sexuales limita el desarrollo de Latinoamérica
    Chanel, la vida después de Eurovisión: “No soy un títere”
    Así es el primer campo de golf de España convertido en una reserva natural
    América Latina gira hacia una nueva izquierda
    ‘Nuestro cerebro no es como un ordenador’, por Juan Arnau y Álex Gómez-Marín
    Orgullo y poderío de la diversidad sexual: el gran negocio de cuatro billones de dólares
    Tener casa en la playa se pone por las nubes: estos son los precios que se están pagando
    Viaje a la melancolía fotográfica de Javier Campano
    Cada testimonio es único: se acaba el tiempo de los supervivientes del Holocausto
    La razón por la que me quedo en Ucrania
    El objetivo de vacunación mundial del 70% contra la covid-19 está obsoleto
    Viaje a las Lofoten, islas de montañas, frailecillos y leyendas de troles
    El espectro de Riba de Santiuste y otras curiosas historias de castillos
    Ellos no bailaron solos: la mujer detrás de la loca historia de Locomía
    ¿Y si no fuese necesario dejar descansar las uñas entre manicuras?
    Eugenia Silva: “No he vivido situaciones extremas. Sabía qué quería y hasta dónde llegar”
    Las frustraciones de Wes Craven, el genio del terror que quería dirigir melodramas
    Ensalada de pepino, sandía y fresas
    De la Valentina al Lao Gan Ma: nuestras salsas de bote favoritas
    JP Morgan irrumpe en la última fase de la compra a El Corte Inglés de la Torre Titania
    Cata a ciegas: este es el mejor gazpacho del supermercado
    Ponte a prueba con nuestros crucigramas, sopas de letras, sudokus y juegos arcade
    Una científica de Cambridge desmonta en un sólo tuit el polémico discurso de Juan Manuel de Prada
    Ancelotti gana más que nadie
    Se buscan trabajadores de cuello verde. La economía sostenible pide un nuevo mercado laboral
    Turquía levanta el veto a las candidaturas de Suecia y Finlandia en Madrid
    Biden y Sánchez pactan ampliar en un 50% los destructores en la base de Rota
    El Rey llama a los mandatarios de la OTAN a mantener la unidad ante un mundo “más incierto y peligroso”
    La visión de Japón en la cumbre de la OTAN
    Comienza el espectáculo
    Putin teme a la UE más que a la OTAN
    Exiliados rusos
    Cambio en Colombia
    Claves de la cumbre de la OTAN en Madrid: Rusia, ampliación y terrorismo
     Tras el ataque al centro comercial de Kremenchuk: “Nadie puede entender por qué Rusia ha hecho esto contra un objetivo civil”
    Una testigo clave del 6 de enero asegura que Trump sabía que la turba estaba armada y aun así la instigó a que marchara hacia el Capitolio
    Jacinda Ardern defiende que el resultado de la cumbre de la OTAN no debe ser el rearme sino “la desescalada”
    El G-7 acuerda elevar la presión sobre Rusia y lanza advertencias a China
    La dependencia energética de Rusia baja el listón de los objetivos climáticos del G-7
    Sturgeon anuncia un nuevo referéndum de independencia en Escocia para el 19 de octubre de 2023
    Una explosión de gas tóxico causa 12 muertos y 250 heridos en el puerto jordano de Áqaba
    La Justicia alemana condena a cinco años de cárcel a un exguardia de un campo nazi de 101 años
    La ministra de Exteriores del Reino Unido: “La OTAN debe incrementar su presencia en Europa del Este y hacerla más permanente”
    El padre de una víctima en el atentado de Bataclan: “Yo he logrado seguir viviendo”
    El cierre de la fundición Ventanas marca un giro histórico en la política ambiental de Chile
    El Supremo de Nueva York revoca el derecho de voto en elecciones locales de 800.000 inmigrantes con papeles
    Hallada en Canadá una cría de mamut en excepcional estado de conservación 
    La pobreza y la inflación alimentan el nuevo estallido de Ecuador 
    Talíria Petrone, una diputada negra frente al dominio blanco del poder en Brasil
    Proteger la eutanasia
    La amenaza del ‘caso Assange’ 
    Jubilarse en el siglo XXI
    El Gobierno no tiene quien le quiera
    Simplemente fútbol
    La cita de la OTAN con la historia
    Esto sí es una crisis
    ¿Sabes para quién gobiernas?
    Los trajes del presidente Sánchez
    Comienza el espectáculo
    OTAN de izquierdas, OTAN de derechas
    48 horas de ataques a Gabriel 
    En Pamplona
    El Roto
    Peridis
    Flavita Banana
    Riki Blanco
    Sciammarella
    Planeta de Plástico, por Malagón
    Envía tu carta
    Tragedia en la frontera con Melilla
    Derechos vulnerados   
    Réquiem por la sierra de la Culebra  
    Opinar sin insultar
    Contra el conflicto de intereses, transparencia
    Entre los derechos de Esther López y los de los lectores
    El defensor del lector contesta
    PSOE y Podemos aprietan a sus socios para refrendar con más apoyos el nuevo decreto anticrisis
    Podemos denuncia una “cacería judicial” tras desinflarse las tres últimas causas contra el partido
    Ceuta y Melilla, la nueva vía de escape de Sudán
    Los trajes del presidente Sánchez
    Panegírico del voto
    Perder el sentido de la oportunidad
    La búsqueda de seguridad vence al cabreo
    Los errores se pagan
    La Fiscalía investigará la muerte de los migrantes que intentaron saltar la valla de Melilla
    Los 133 migrantes que lograron entrar en Melilla permanecen privados de libertad por “recomendación sanitaria”
    El Congreso declarará ilegal el franquismo y se investigarán sus crímenes hasta 1983 con la oposición de la derecha
    ¿Estamos preparados para los incendios que vienen?
    La ONU insta a España y Marruecos a investigar las muertes en la frontera de Melilla
    El paraguas de la OTAN extenderá su protección a Ceuta y Melilla
    El Gobierno no hace sitio a Feijóo ni a los ministros  de Unidas Podemos en los actos de la cumbre 
    Marruecos se apresura a enterrar a los migrantes que intentaron entrar en Melilla entre críticas por la falta de investigaciones
    PP, Más País y los nacionalistas piden que Sánchez comparezca en el Congreso para hablar del salto de Melilla 
    Miles de personas salen a la calle en Madrid para protestar contra la OTAN a pocos días del arranque de la cumbre  
    El presidente del INE dimite después de que el Gobierno cuestionase los datos del IPC y el PIB  
    Un paraíso en el que avistar más de 20 especies de cetáceos
    El secreto de Fuerteventura se hace viral: la ‘playa de las palomitas’
    Artesanía y cultura que conquista a las ‘influencers’
    Más allá de la capital. El triunfo de la vida rural madrileña
    Así lucha la tierra del cerezo para conseguir un nuevo florecimiento económico
    “Siempre me ha parecido que los que iban disfrazados eran los demás”
    “La herramienta más poderosa para salvar a la humanidad son las matemáticas”
    Lagarde promete llevar la política monetaria “tan lejos como sea preciso” para combatir la inflación 
    Escrivá propone un sistema de cotizaciones decreciente hasta 2025 para los autónomos que menos ganen 
    España empieza a enviar gas a Marruecos a través del gasoducto que cortó Argelia
    Abengoa, el ocaso del símbolo del desarrollo tecnológico en Andalucía
    Un reparto justo del sufrimiento
    La fina línea entre inflación y recesión
    Crisis energética y precios del carbono
    Una espiral maldita llamada inflación 
    Lecciones posteriores al Brexit para España
    La hiperinflación en Turquía le cuesta al BBVA 324 millones
    La dimisión del presidente del INE abre un nuevo frente al Gobierno
    El gasto medio de los hogares sigue por debajo de los niveles prepandemia
    Los supermercados ya aprecian comportamientos de “crisis de consumo” por la inflación
    El TJUE tumba el blindaje de Hacienda contra las indemnizaciones por violar el derecho de la UE
    La rehabilitación de viviendas choca con la barrera de la burocracia
    Joseph Oughourlian, presidente de PRISA: “Es el momento de mirar hacia el futuro con ilusión y ambición”
    El grupo IFA incrementa sus ventas un 3% en sus supermercados de España, Italia y Portugal
    Las recetas de Duro Felguera para recuperarse: conseguir inversores y más contratos
    Decathlon ganó un 12% más en 2021 en España tras superar los 2.000 millones de facturación
    El presidente del INE dimite después de que el Gobierno cuestionase los datos del IPC y el PIB  
    Tener casa en la playa se pone por las nubes: estos son los precios que se están pagando
    La cuesta abajo de Netflix despierta a los tiburones (pero por desgracia no está en venta)
    Una espiral maldita llamada inflación 
    LaLiga tiene un plan para conquistar América
    La fina línea entre inflación y recesión
    JP Morgan irrumpe en la última fase de la compra a El Corte Inglés de la Torre Titania
    El Gobierno prepara su rechazo a Abengoa mientras aprueba el rescate de Celsa
    Las cuotas de autónomos de 230 a 590 euros dependen del calendario de aplicación
    La matriz de Mediaset cotizará en la Bolsa de Madrid tras la opa
    Líos en la piscina comunitaria: normas y sentencias para un chapuzón seguro
    Parir en casa, educarlo por mi cuenta… ¿Qué puedo decidir sobre mi hijo y qué no?
    Saltarse un paso a nivel de camino a la oficina es accidente laboral
    Francisco Javier Blasco: “Llevamos años sin mejorar la eficacia de las políticas activas de empleo”
    ¿Es esta la edad dorada del emprendimiento universitario?
    Y después de la EBAU, ¿qué?
    Cancerberos del bienestar de la empresa
    Salud a golpe de clic con la cercanía del médico de cabecera
    Cómo garantizar la seguridad en un mundo de amenazas híbridas
    ¿Cuáles son los dilemas éticos del uso de la inteligencia artificial?
    Las aventuras de un par de calcetines que dan empleo a todo un pueblo
    Cultura financiera como punto de partida para volver a empezar
    Por qué digitalizar una pyme aporta más empleo
    Logística a bajas temperaturas, la revolución que vino del frío
    ‘Coopetir’: la actitud DFactory
    Así serán las ciudades de la (nueva) última milla
    Cinco errores habituales al digitalizar un negocio 
    PERTE Agroalimentario: ¿cómo acceder a los fondos europeos?
    Fondos soberanos: ¿Cómo funcionan las cajas fuertes de los estados más ricos?
    ¿Crisis de deuda mundial a la vista?
    El momento de la energía solar
    Las principales reformas (con subvención europea) para ahorrar energía en la vivienda
    Gloria Ramos, cuando el afán de superación acaba en la alfombra roja 
    La importancia de la cultura financiera para tener una buena jubilación
    Hotmart y su plataforma 360 para creadores de contenidos
    Una aplicación para presentar la declaración desde casa y conseguir los máximos beneficios
    Ghislaine Maxwell, condenada a 20 años de cárcel por proporcionar menores al depredador sexual Epstein
    Así serán las nuevas residencias: más parecidas a un hogar, atención personalizada y fin de las sujeciones
    China anuncia una reducción de la cuarentena para los pasajeros internacionales
    No se gobierna con el catecismo romano
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    El intento de suicidio de Juan y las somatizaciones de Carmen: ¿por qué los colegios necesitan un psicólogo educativo?
    El colectivo LGTBI llama a la resistencia ante las amenazas a sus derechos 
    El Congreso envía al Gobierno la propuesta sobre el cannabis medicinal con la oposición de la derecha
    El 98% de la población española respiró aire contaminado en 2021 pese a la reducción del tráfico por la pandemia
    Un juez de Ourense autoriza el cambio de sexo en el registro a un menor trans de ocho años
    Vox impide iluminar las Cortes de Castilla y León con los colores LGTBI durante el Orgullo por no ser un “colectivo vulnerable”
    Dos crímenes machistas sacuden Egipto y Jordania
    17 años de matrimonio igualitario: activistas LGTBI reflexionan sobre lo conseguido y lo que aún falta
    La protección del 30% de los mares de República Dominicana, el sueño del ministro asesinado se hace realidad
    La Comisión Europea destina a España las primeras 5.300 vacunas contra la viruela del mono 
    El PP espera que prospere su recurso contra la ley del aborto en el Constitucional
    El techo de cristal del grado medio de FP: candidatos demasiado preparados se quedan con los puestos
    La economía circular llega a la ciudad. Te contamos dónde se encuentra 
    Mitos, falsedades, bulos y realidades sobre el VIH 40 años después
    Educadores con VIH para minimizar el impacto tras el primer diagnóstico
    El tremendo peso de la obesidad en España
    Interactivo | Los 14 cambios en los aeropuertos españoles que no ves y que ya están ocurriendo
    Encontrar empleo pese a los obstáculos. Por dónde empezar la búsqueda
    La fórmula de Carboneros para evitar el éxodo rural: trabajar cuidando a los vecinos 
    Consejos y cuidados para el primer verano con un gatito o un perrito
    ¿Qué tienen en común perros y gatos cuando son cachorros?
    La guía definitiva para alimentarnos mejor (y cuidar nuestra salud y la del planeta)
    Más vida después del cáncer de próstata avanzado 
    Cáncer de ovario, el más rebelde de los tumores ginecológicos
    El metro como refugio. De los andenes de Madrid en 1936 a los de Kiev en 2022
    La salud mental de los refugiados: cómo abrirse para cerrar las heridas
    Yogures con menos azúcar, paso firme hacia la alimentación infantil del futuro
    ‘Gap year’ pre-universitario en el extranjero: todo lo hay que saber
    Así es la vida de los refugiados ucranianos en España
    El techo de cristal del grado medio de FP: candidatos demasiado preparados se quedan con los puestos
    Al campus desde la FP: el 13,2% de los estudiantes recién llegados a la universidad son titulados en ciclos superiores
    Primero de carrera: los bachilleres de la escuela pública son los que más materias aprueban 
    Universidad en reconstrucción 
    Volver a la escuela en América Latina tras dos años de pandemia
    El intento de suicidio de Juan y las somatizaciones de Carmen: ¿por qué los colegios necesitan un psicólogo educativo?
    El nuevo sistema para evaluar los conocimientos digitales de los profesores valdrá en toda España
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Solo un 3% de alumnos de Cataluña pidió hacer el examen de Selectividad en castellano
    Subirats reinterpreta la ley de Universidades: freno a la precariedad, facilidades para los alumnos extranjeros y ciencia abierta
    “Los profesores no van a cambiar de golpe su forma de trabajar el curso que viene por la nueva ley educativa”
    Sin currículos
    La escuela concertada ante las desigualdades: el debate pendiente
    La equidad frente a las políticas educativas de privatización en Andalucía
    No hay lunes al sol en la Universidad
    Ofrecer comedor gratis en todos los colegios públicos es “alcanzable y urgente”: costaría 1.664 millones al año, según la ONG Educo  
    Una fórmula para que la escuela pública compita mejor con la concertada
    La pérdida de alumnos por el descenso de la natalidad está afectando con más fuerza a la escuela pública que a la concertada
    El Ayuntamiento de Madrid guarda en un cajón una herramienta ya pagada para ver los datos de contaminación al detalle 
    La implantación del nuevo Bachillerato general fracasa pese a su demanda potencial: “Creímos que lo pedirían seis alumnos y lo han hecho 27”
    Toni Solano, director de instituto: “Veo mal a los niños, necesitan muchísima ayuda”
    Niños, Administraciones y redes sociales: prohibir su uso con una mano y enseñar a crear contenidos con la otra
    El Gobierno aprueba el decreto de bachillerato: los alumnos podrán terminar con un suspenso y desembocará en una nueva Selectividad
    La ley del silencio dentro y fuera del aula
    Las universitarias desertan del grado de Matemáticas ahora que tiene pleno empleo. ¿Por qué?
    Golpe a la temporalidad en las universidades: 25.000 profesores asociados serán indefinidos a tiempo parcial
    Antonio Abril: “Yo le decía a Castells: ‘Tienes que aguantar la presión, tienes que hacer la reforma universitaria”
    Los universitarios extranjeros podrán quedarse un año en España automáticamente al terminar la carrera
    La protección del 30% de los mares de República Dominicana, el sueño del ministro asesinado se hace realidad
    El 98% de la población española respiró aire contaminado en 2021 pese a la reducción del tráfico por la pandemia
    Así es el primer campo de golf de España convertido en una reserva natural
    Emergencia de los océanos: 142 países debaten cómo salvarlos en Lisboa
    A la caza de las megafugas invisibles de metano que calientan el planeta
    “No tenemos otra opción que creer que podemos hacer lo necesario para que la humanidad sobreviva” 
    La trampa mortal del trasvase Tajo-Segura: así se ahogan corzos y jabalíes en el canal 
    La inacción ante la pérdida de arena condena a las playas de Barcelona
    Sierra de la Culebra: un incendio gigantesco que no pone en peligro a los lobos, pero sí un modelo de convivencia ejemplar
    La indignación crece sobre las ascuas del incendio en la sierra de la Culebra
    Un caudal ecológico para recuperar L’Albufera
    Crisis energética y precios del carbono
    La lección del martín pescador para afrontar la crisis ecológica
    Estocolmo+50: mirar atrás para tomar impulso
    El verano ya no es lo que era 
    Ríos imposibles: las 171.000 barreras que rompen el curso de agua en España
    La UE abraza las renovables para romper la dependencia de Rusia
    La lucha en un pueblo de Teruel para salvar su última montaña
    ¿Qué aire respiran los niños de Madrid y Barcelona? En el 46% de los colegios se supera la contaminación permitida
    “No tenemos otra opción que creer que podemos hacer lo necesario para que la humanidad sobreviva” 
    ¿Dónde hay civilizaciones extraterrestres?
    Toreros, trenes voladores y ovaciones a Franco: las películas inéditas del ingeniero José Hernández Santorcuato
    Las personas que comparten el mismo olor tienen más probabilidades de forjar una amistad
    Así se puede ver la alineación de cinco planetas a simple vista, justo antes de cada amanecer
    Las vacunas contra el coronavirus salvaron 20 millones de vidas en su primer año
    Seis jóvenes científicos que han impulsado avances en la investigación matemática de vanguardia obtienen los Premios Vicent Caselles
    Así se puede ver la alineación de cinco planetas a simple vista, justo antes de cada amanecer 
    Fracciones egipcias
    El Congreso aprueba la reforma de la ley de la ciencia sin votos en contra
    Matemáticas para describir los remolinos, los taxis del océano
    Las incógnitas de la pastilla milagrosa contra un tipo de calvicie
    ¿Se puede dejar de roncar?
    El síndrome del hombre lobo y la realidad lógica de su fábula
    Muere Yves Coppens, uno de los descubridores del fósil más famoso del mundo 
    Ni patentes, ni firmar estudios: las científicas reciben mucho menos reconocimiento por su trabajo
    ¿Dónde hay civilizaciones extraterrestres?
    Matemáticas para describir los remolinos, los taxis del océano
    Reaparece la tesis de María Wonenburger, la pionera matemática española que permaneció décadas en el olvido
    Técnicas criptográficas que se fundamentan en lo impredecible
    Las matemáticas de los juegos malabares
    El problema del huerto
    Números McNugget
    La moneda de Frobenius
    El síndrome del hombre lobo y la realidad lógica de su fábula
    La locura como juego; más allá del Quijote y de las novelas de Pérez Galdós
    El andar del borracho, las huellas del azar y el juego de dados en algunos libros malditos
    El campo vibratorio y las fronteras de la ciencia desde un punto de vista científico
    Paul Auster fluctuando entre el pudin de pasas y la nube de mosquitos
    ¿Son mejores las hormonas bioidénticas?
    ¿Qué surgió antes, el ARN o el ADN?
    ¿Por qué se sabe que los núcleos de la Tierra rotan?
    ¿Qué son los mini reactores nucleares?
    Invitados indeseables por Navidad: el muérdago y otras plagas que evitar durante las fiestas
    Las ‘apps’ nutricionales o cómo comer bien no debería depender de uno mismo
    Malnutrición invisible: el impacto de la pobreza en la salud infantil
    El óxido de etileno, la sustancia cancerígena que ha obligado a retirar miles de alimentos en la UE
    Que no te líen con los ingredientes: aceites y grasas de mala calidad nutricional
    Fina García-Marruz y la poesía del silencio
    Robo de película en la feria de arte de Maastricht: a mazazos contra unas vitrinas con joyas
    Hannah Gadsby, la monologuista que rompió los moldes del género: “No hay una forma correcta de hacer comedia”
    Siempre nos quedará Ashbery
    Cualquier parecido con la realidad está calculado
    Aventuras en el desierto con la daga y el escorpión
    “¿Cómo lo haría Tony?”
    La erupción del Vesubio arrasó Pompeya en octubre y no en verano como se pensaba
    Muere la poeta cubana Fina García-Marruz a los 99 años
    Del ‘Paraíso perdido’ al ciclo ‘queer’: el director del festival Grec de Barcelona, Cesc Casadesús, recomienda sus espectáculos favoritos  
    De huerto en un pueblo de Ávila a una casa contemporánea
    Tres camiones españoles para empaquetar los museos de Ucrania
    Antonio Banderas y el legendario compositor Andrew Lloyd Webber se unen para producir teatro musical en español
    Canetti, Cortázar, Calvino, Sabato: las cartas de Mario Muchnik desvelan la trastienda de medio siglo de literatura
    Nabucco vuelve al Teatro Real 151 años después
    ‘Revista de Occidente’ y la asociación Atrapavientos, Premio Nacional al Fomento de la Lectura
    La loca historia de la peor película del rock jamás rodada
    Ethan Hawke se une al cortometraje wéstern que Almodóvar rodará en Almería
    Patricia Guerrero, el baile sin límite ni género: “¿Quién dice qué es el flamenco?”
    Viaje a la melancolía fotográfica de Javier Campano
    El último atardecer de Europa se ve solo desde este lugar. Un viaje hacia el infinito por el Camino de Fisterra-Muxía
    Un paseo fluvial con museos y otro lleno de piscinas termales. Las sorpresas de la Vía de la Plata
    Lorca, en la ciudad al margen
    El Pirineo oscense, para entrar a vivir
    Toda la lectura del verano, en el bolsillo
    Los diez mejores libros de la primera mitad de 2022
    Los otros Sherlock Holmes: los mejores detectives literarios
    Preestreno de verano de 'Nabucco' en el Teatro Real
    Disfruta de 'TINA', el musical de Tina Turner
    Te invitamos al evento 'Ecosistema ahora'
    'Los Chicos del Coro' en el Teatro La Latina
    Terciados y exigentes novillos
    Una de Miura sin opciones
    Manzanares salva la tarde de San Juan
    La fiesta de los toros, una emocionante y apasionada polémica desde el siglo XIII
    De Margaret Atwood a Neil Young: la interrupción del embarazo en la cultura norteamericana
    Viaje a la melancolía fotográfica de Javier Campano
    Cada testimonio es único: se acaba el tiempo de los supervivientes del Holocausto
    Un Houellebecq sentimental, la fiesta de la imaginación de Garriga Vela y otros libros de la semana
    Los cajones de sastre de Néstor Sanmiguel Diest
    CaixaForum València: un paisaje no es un edificio
    Moderat: “El tecno es mala hierba, nunca morirá”
    Poyo Rojo, la sensación argentina de la danza teatro 
    Las Huecas, teatro alternativo de verdad
    Trampantojo: Batallas culturales
    ‘Aniquilación’, de Michel Houellebecq: confusión en el campo de batalla
    Otros turismos (lejos y aquí cerca)
    Volver al cine
    Sin autor, da lo mismo
    Alex sin Ada
    ‘Horas muertas’, en un Dublín hipnótico
    ‘Prometeo’, trío de ases
    ‘La memoria del alambre’, ese algo misterioso que daba miedo
    ‘Tarradellas. Una cierta idea de Cataluña’: manual de resistencia
    Manuel Estrada: “Me agrada que una portada guste más después de leer el libro”
    Óscar Esquivias: “No hace falta ser creyente para leer la Biblia”
    Amelia Castilla: “Los ritos nos ayudan a hacer viable el trance de la muerte”
    Shuarma: “Me gusta de la poesía el silencio que encierra”
    Eva Orúe: “Haría cola por la firma de Margaret Atwood”
    Nadal sufre a Cerúndolo en su vuelta a Londres
    La covid apea a Berrettini y despeja el teórico trazado de Nadal en Wimbledon
    Badosa, en busca del clic que se le resiste
    El injusto veto a los rusos distorsiona este Wimbledon
    Patxo Unzueta, el magisterio desde el córner
    El doble regalo del deporte a Girona
    Aquel homenaje a Zico
    Mondelo pierde la demanda contra Xargay y Cruz, que denunciaron sus métodos abusivos
    El Barça vende el 10% de sus derechos televisivos durante 25 años al fondo Sixth Street por 200 millones
    Los circuitos estadounidense y europeo de golf refuerzan su alianza contra la liga saudí
    La autoridad antidopaje quiere infiltrar espías en los equipos durante el Tour de Francia
    El PSG comunica a Neymar que no lo quiere
    El equipo de Iniesta, último de la Liga japonesa, destituye a Lotina 
    Heurtel: “Salí por Atenas el día antes de un partido. Lo destruí todo”
    El calvario de Arón Canet: “Me entra ansiedad al pensar en el choque, casi pierdo la vida”
    Dana Reizniece-Ozola: “El ajedrez es muy útil para la política”
    Tour de Francia 2022: recorrido completo, etapas y fechas
    El viaje de Salma Paralluelo de las vallas a la Eurocopa
    Lanzado hacia los 18m, cada salto de Jordan Díaz es un récord, o casi
    Segunda oportunidad para Simeone
    La nueva gran atracción del fútbol español
    “Nunca acepto un no por respuesta”
    La mayor fábrica de baloncesto de Europa
    Crónica de dos ciudades moldeadas por la misma pasión 
    El Torneo de Candidatos de ajedrez de Madrid
    Alexia Putellas encabeza la lista de España para la Eurocopa femenina con Salma Paralluelo como sorpresa
    Proyecto Pelusa, el álbum de fans de Maradona más grande del mundo
    Alcaraz, entre tortilla, paseos y ajedrez 
    Segunda oportunidad para Simeone
    Nakamura, el ajedrecista más rico
    Patxo Unzueta, el magisterio desde el córner
    Ahora sí, esto es Wimbledon
    “Queremos que la programación sea el inglés del siglo XXI”
    Imágenes sexuales que destruyen y matan
    Tres cosas que hacemos mal con el teléfono móvil (y no sirven para nada)
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    ¿Sigue siendo imprescindible tener un antivirus? 
    Google News vuelve a España ocho años después de su cierre
    Mónica Ojeda, pedagoga: “Los adolescentes utilizan sus imágenes sexuales como moneda de cambio o como prueba de amor”
    Zuckerberg desvela cómo serán las gafas para entrar en el metaverso
    Por qué retuitear el vídeo sexual de Santi Millán también es delito: la desprotección de la intimidad en internet
    LaMDA, la máquina que “parecía un niño de siete años”: ¿puede un ordenador tener conciencia?
    La inteligencia artificial reconocerá el arte gracias a la ciencia ciudadana
    “Gano 1.500 euros al mes con los videojuegos”: así funciona el negocio de la compraventa de cuentas
    Cinco aplicaciones móviles, con aval científico, que salvan vidas o mejoran tu salud
    Cómo contarle tus ciclos menstruales a una app puede llevarte a la cárcel
    Bill Gates dice que las criptomonedas y los NFT están basados en encontrar a “alguien más tonto”
    En defensa de la procrastinación. Elogio del tiempo perdido (frente al que las redes te roban)
    Instagram, el mejor de los mundos posibles
    Del terrorismo youtuber al influencer rabioso: el odio inunda la red
    Cronodiversidad. ¿Por qué el tiempo cada vez va más rápido?
    Herramientas que ayudan a crecer a las empresas (más allá de los pagos)
    La solución definitiva para vender más (y mejor) en la web
    Cinco razones por las que este ‘smartphone’ es sencillamente tentador
    La cámara de este ‘smartphone’ es pura magia
    Un campus de programación para adquirir todas las habilidades ‘tech’
    Una catapulta para el talento de ‘kilómetro cero’
    “Queremos que la programación sea el inglés del siglo XXI”
    Imágenes sexuales que destruyen y matan
    Tres cosas que hacemos mal con el teléfono móvil (y no sirven para nada)
    Christopher Mims: “Amazon sabe cómo bajar el ritmo de trabajo para prevenir lesiones. Pero quizá dejaría de ganar dinero” 
    ¿Sigue siendo imprescindible tener un antivirus? 
    Google News vuelve a España ocho años después de su cierre
    Mónica Ojeda, pedagoga: “Los adolescentes utilizan sus imágenes sexuales como moneda de cambio o como prueba de amor”
    Zuckerberg desvela cómo serán las gafas para entrar en el metaverso
    Por qué retuitear el vídeo sexual de Santi Millán también es delito: la desprotección de la intimidad en internet
    LaMDA, la máquina que “parecía un niño de siete años”: ¿puede un ordenador tener conciencia?
    La inteligencia artificial reconocerá el arte gracias a la ciencia ciudadana
    “Gano 1.500 euros al mes con los videojuegos”: así funciona el negocio de la compraventa de cuentas
    Cinco aplicaciones móviles, con aval científico, que salvan vidas o mejoran tu salud
    Cómo contarle tus ciclos menstruales a una app puede llevarte a la cárcel
    Bill Gates dice que las criptomonedas y los NFT están basados en encontrar a “alguien más tonto”
    En defensa de la procrastinación. Elogio del tiempo perdido (frente al que las redes te roban)
    Instagram, el mejor de los mundos posibles
    Del terrorismo youtuber al influencer rabioso: el odio inunda la red
    Cronodiversidad. ¿Por qué el tiempo cada vez va más rápido?
    Herramientas que ayudan a crecer a las empresas (más allá de los pagos)
    La solución definitiva para vender más (y mejor) en la web
    Cinco razones por las que este ‘smartphone’ es sencillamente tentador
    La cámara de este ‘smartphone’ es pura magia
    Un campus de programación para adquirir todas las habilidades ‘tech’
    Una catapulta para el talento de ‘kilómetro cero’
    Caldereta junto a la playa o aperitivo con vistas al Guadiana: los Soletes de verano premian a los mejores chiringuitos, terrazas y heladerías de España 
    La reina Letizia, anfitriona de Jill Biden durante la semana de la cumbre de la OTAN de Madrid
    La segunda vida de Fire Island, el primer pueblo gay de Estados Unidos: sexo, PrEP, arte y fiestas en piscinas
    Victoria Beckham solo comió verduras, caramelos de menta y agua de coco en la boda de Sergio Ramos y Pilar Rubio
    Mark Fleischman, dueño de Studio 54, planea terminar su vida mediante eutanasia el 13 de julio en Suiza
    Federico y Mary de Dinamarca sacan a su hijo mayor de su escuela por casos de acoso escolar y abusos sexuales
    El mejor perro del mundo es un fox terrier llamado ‘Funfair Foxhouse’ y se ha coronado en Madrid
    La semana de la moda masculina de París apuesta por el cambio tranquilo
    Ramón Estévez lamenta llamarse Martin Sheen
    Piti Alonso: “Igual te organizo la alfombra roja de los Goya que la de la OTAN”
    Ana Rosa Quintana reaparece en un encuentro con sus compañeros de televisión
    Un libro y un documental revisitan la figura de George Michael: atracones de helado, culebrones, sexo y éxtasis
    Gracias, Locomía
    Eugenia Silva: “No he vivido situaciones extremas. Sabía qué quería y hasta dónde llegar”
    Ha Ha Ha! La colección de Gucci que Harry Styles y Alessandro Michele han creado a partir de los memes que intercambiaban
    Nicky y Simone Zimmermann: “Nos dijeron que no nos dedicáramos a la moda y que no trabajáramos en familia. No les hicimos caso y nos fue bien”
    Viktor & Rolf, 30 años de moda y rebelión: “No puedes estar siempre arriba”
    Desembarco de celebridades internacionales en Sevilla para el desfile de Dior
    De una pastelera de tartas en 3D a una creadora de café con huesos de dátil: estos son los próximos grandes talentos de la gastronomía global
    El publicista Miguel Olivares y la pasta del fin del mundo
    De La Tasquería a El Lince, un homenaje a la casquería más popular con sorpresas
    Al enemigo, ni ensaladilla: ¿qué comida es de izquierdas y cuál de derechas según las guerras culturales?
    Qué ver en televisión para celebrar el Orgullo LGTBI+ 2022
    La ilustradora española que se asoma a las ventanas de Nueva York en ‘Solo asesinatos en el edificio’
    24 series para este verano
    ‘First Class’: ¿Por qué estáis todas en barcos? ¿Tenéis todas un barco?
    El manglar de la publicidad en abierto 
    El espíritu de Balbín está por todas partes
    Los Romanoffs
    Muere la actriz Mary Mara (’Urgencias’ y ‘Ray Donovan’) ahogada en un río de Nueva York
    El manglar de la publicidad en abierto 
    ¿Merece la pena ver ‘La casa de papel: Corea’? Diferencias y semejanzas con la serie original
    Pepón Nieto denuncia que TVE vetó una de sus películas en ‘Cine de barrio’ y la corporación recula: se emitirá este sábado
    ‘La clave’ de Balbín, gloria y caída del programa que cambió la televisión española
    Un viaje en el tiempo con Kurt Vonnegut
    Muere José Luis Balbín, mítico presentador y creador del programa ‘La clave’
    El TSJ de Madrid declara nulo el despido del guionista de TVE que escribió el rótulo “Leonor se va de España, como su abuelo”
    ‘Legacy’: un Bosch sin placa y un poco perdido
    Los abonados a las plataformas y televisiones de pago superan el número de hogares españoles 
    ¿Qué ver hoy en TV? Martes 28 de junio de 2022
    Nueve capítulos para recordar ‘The Wire’ en su 20º aniversario
    Harry Palmer: el tercer vértice del mágico triángulo de espías británicos
    Las series de junio de 2022: ‘The Boys’ en Amazon Prime Video; ‘Peaky Blinders’ en Netflix y otras
    La fuerza acompaña a ‘Obi-Wan Kenobi’, una serie deslumbrante
    Lorena Jaume-Palasí: “Crear principios éticos universales para  la inteligencia artificial es una iniciativa cosmética”
    Hermanos Campana, los brasileños que crean diseños de poesía ancestral
    Así es el primer campo de golf de España convertido en una reserva natural
    Inteligencia Artificial al servicio de las finanzas
    Farrell y McNamara: “Los edificios no son tan solo infraestructuras, representan sistemas de valores”
    Chanel, la vida después de Eurovisión: “No soy un títere”
    La finca donde se resucita la tierra
    Acelerando la ciencia a 314.000 billones de operaciones por segundo
    Así fue nuestra experiencia de escribirnos con GPT-3, una máquina de inteligencia artificial
    La oficina, concentrada en 14 pulgadas
    El publicista Miguel Olivares y la pasta del fin del mundo
    El piloto de ‘airbuses’ que se eleva componiendo pop barroco
    Aprendizaje continuo para un mundo en cambio
    La conducción agradable y económica del Honda Civic e:HEV
    Por qué ya no soy futbolero
    Ubicación exacta de la utopía
    Una pequeña historia
    Historia para los nietos
    Harina enriquecida para acabar con el “hambre oculta”
    Lugares de esperanza para salvar los océanos
    Los guardianes del clima que llevan medio siglo leyendo las advertencias de los glaciares
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    Los ejecutivos voladores y la ética medioambiental
    Ibiza, entre la noche desenfrenada y el turismo tranquilo 
    Luz Casal: “Tengo el alma rockera. Nada ha doblegado mi rebeldía”
    Rashid Johnson: “Los pensadores y creadores negros estamos cansados de que nos nieguen un espacio autónomo”
    Sergio Hernández: “En el mundo, la gente ya no quiere verdades, quiere mentiras”
    Elvira Sastre: “No hay que perdonarlo todo”
    La trinidad del taco perfecto: “Buena tortilla, delicioso relleno y una salsa sabrosa”
    Bikôkô y Julio Peña, dos estrellas en ebullición  
    Cuando Chufy encontró a Rossy: dos amigas, una isla y una colección de moda
    La nueva edad de oro de la coctelería en Barcelona
    Riesgo, dolor y placer: cómo los humanos se aficionaron al picante 
    Ilusiones hipnóticas
    El poder del hormigón
    Maulévrier, Japón a la francesa
    ‘Fantasías en el Prado’, por Alberto García-Alix
    ¡‘Yee-haw’! Esto también es Brasil
    [1m[34mA continuación se muestran los titulares de las páginas principales del diario El País que contienen las siguientes palabras:[0m
    [1m[32mFeminismo[0m
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    [1m[32mIgualdad[0m
    La escuela concertada ante las desigualdades: el debate pendiente
    [1m[32mMujeres[0m
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    [1m[32mMujer[0m
    Ellos no bailaron solos: la mujer detrás de la loca historia de Locomía
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    [1m[32mBrecha salarial[0m
    
    [1m[32mMachismo[0m
    
    [1m[32mViolencia[0m
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    [1m[32mMaltrato[0m
    
    [1m[32mHomicidio[0m
    
    [1m[32mGénero[0m
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Hannah Gadsby, la monologuista que rompió los moldes del género: “No hay una forma correcta de hacer comedia”
    Patricia Guerrero, el baile sin límite ni género: “¿Quién dice qué es el flamenco?”
    [1m[32mAsesinato[0m
    La ilustradora española que se asoma a las ventanas de Nueva York en ‘Solo asesinatos en el edificio’
    [1m[32mSexo[0m
    La segunda vida de Fire Island, el primer pueblo gay de EE UU: sexo, PrEP, arte y fiestas en piscinas
    Un juez de Ourense autoriza el cambio de sexo en el registro a un menor trans de ocho años
    La segunda vida de Fire Island, el primer pueblo gay de Estados Unidos: sexo, PrEP, arte y fiestas en piscinas
    Un libro y un documental revisitan la figura de George Michael: atracones de helado, culebrones, sexo y éxtasis
    

# Objetos/variables

Se declara la **variable** resultados para almacenar cada resultado de las `URL`.

resultados = [] En esta celda se verán los resultados una vez se haya ejecutado el Web _Scrapping_. 

# Nota
Voy a empezar la actividad de **programación literaria**, algo nuevo para mí. 

Para llevar a cabo esta actividad seleccioné algunos de los **códigos** dados en el código principal, es decir tomaré algunas partes del código para ejecutar. 



Para empezar lo haré con la sección de **Educación**. Como ocurre es los ejercicios de Web *Scrapping*, hay que hacer una petición. 
La mencionada petición se hace con *req = requests.get(+URL)*. If es una condicional que *if (req.status_code != 200)*, que es el código de respuesta de estado satisfactorio o exitosa de la petición. Se pasa a extraer el texto HTML de la página web con  BeautifulSoup(req.text, 'html.parser').
Entonces, cómo se hace el filtrado. Recurrimos a usar una de las funciones de soup, la findAll. Así solo se guardará en tags (que es una variable) el texto de los titulares del sitio web. No obstante, si se desean almacenar de forma individual sería en resultados, se usa el bucle for (*se utiliza para repetir una o más instrucciones un determinado número de veces*). 



```python
req7 = requests.get("https://elpais.com/educacion/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup7 = BeautifulSoup(req7.text, 'html.parser')
 
tags = soup7.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    El techo de cristal del grado medio de FP: candidatos demasiado preparados se quedan con los puestos
    Al campus desde la FP: el 13,2% de los estudiantes recién llegados a la universidad son titulados en ciclos superiores
    Primero de carrera: los bachilleres de la escuela pública son los que más materias aprueban 
    Universidad en reconstrucción 
    Volver a la escuela en América Latina tras dos años de pandemia
    El intento de suicidio de Juan y las somatizaciones de Carmen: ¿por qué los colegios necesitan un psicólogo educativo?
    El nuevo sistema para evaluar los conocimientos digitales de los profesores valdrá en toda España
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Solo un 3% de alumnos de Cataluña pidió hacer el examen de Selectividad en castellano
    Subirats reinterpreta la ley de Universidades: freno a la precariedad, facilidades para los alumnos extranjeros y ciencia abierta
    “Los profesores no van a cambiar de golpe su forma de trabajar el curso que viene por la nueva ley educativa”
    Sin currículos
    La escuela concertada ante las desigualdades: el debate pendiente
    La equidad frente a las políticas educativas de privatización en Andalucía
    No hay lunes al sol en la Universidad
    Ofrecer comedor gratis en todos los colegios públicos es “alcanzable y urgente”: costaría 1.664 millones al año, según la ONG Educo  
    Una fórmula para que la escuela pública compita mejor con la concertada
    La pérdida de alumnos por el descenso de la natalidad está afectando con más fuerza a la escuela pública que a la concertada
    El Ayuntamiento de Madrid guarda en un cajón una herramienta ya pagada para ver los datos de contaminación al detalle 
    La implantación del nuevo Bachillerato general fracasa pese a su demanda potencial: “Creímos que lo pedirían seis alumnos y lo han hecho 27”
    Toni Solano, director de instituto: “Veo mal a los niños, necesitan muchísima ayuda”
    Niños, Administraciones y redes sociales: prohibir su uso con una mano y enseñar a crear contenidos con la otra
    El Gobierno aprueba el decreto de bachillerato: los alumnos podrán terminar con un suspenso y desembocará en una nueva Selectividad
    La ley del silencio dentro y fuera del aula
    Las universitarias desertan del grado de Matemáticas ahora que tiene pleno empleo. ¿Por qué?
    Golpe a la temporalidad en las universidades: 25.000 profesores asociados serán indefinidos a tiempo parcial
    Antonio Abril: “Yo le decía a Castells: ‘Tienes que aguantar la presión, tienes que hacer la reforma universitaria”
    Los universitarios extranjeros podrán quedarse un año en España automáticamente al terminar la carrera
    

# Otro código

En siguiente código se repite el **proceso** realizado en el anterior, lo único que cambia es la sección en este caso es [Deportes](https://elpais.com/deportes/): *Un req12 = requests.get* para hacer el web scrapping; *if (req.status_code != 200)* para comprobar la petición; *soup = BeautifulSoup(req.text, 'html.parser')* para comprobar que ha sido exitosa; y *tags = soup.findAll("h2")* para almacenar.


```python
req12 = requests.get("https://elpais.com/deportes/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup12 = BeautifulSoup(req12.text, 'html.parser')
 
tags = soup12.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    Nadal sufre a Cerúndolo en su vuelta a Londres
    La covid apea a Berrettini y despeja el teórico trazado de Nadal en Wimbledon
    Badosa, en busca del clic que se le resiste
    El injusto veto a los rusos distorsiona este Wimbledon
    Patxo Unzueta, el magisterio desde el córner
    El doble regalo del deporte a Girona
    Aquel homenaje a Zico
    Mondelo pierde la demanda contra Xargay y Cruz, que denunciaron sus métodos abusivos
    El Barça vende el 10% de sus derechos televisivos durante 25 años al fondo Sixth Street por 200 millones
    Los circuitos estadounidense y europeo de golf refuerzan su alianza contra la liga saudí
    La autoridad antidopaje quiere infiltrar espías en los equipos durante el Tour de Francia
    El PSG comunica a Neymar que no lo quiere
    El equipo de Iniesta, último de la Liga japonesa, destituye a Lotina 
    Heurtel: “Salí por Atenas el día antes de un partido. Lo destruí todo”
    El calvario de Arón Canet: “Me entra ansiedad al pensar en el choque, casi pierdo la vida”
    Dana Reizniece-Ozola: “El ajedrez es muy útil para la política”
    Tour de Francia 2022: recorrido completo, etapas y fechas
    El viaje de Salma Paralluelo de las vallas a la Eurocopa
    Lanzado hacia los 18m, cada salto de Jordan Díaz es un récord, o casi
    Segunda oportunidad para Simeone
    La nueva gran atracción del fútbol español
    “Nunca acepto un no por respuesta”
    La mayor fábrica de baloncesto de Europa
    Crónica de dos ciudades moldeadas por la misma pasión 
    El Torneo de Candidatos de ajedrez de Madrid
    Alexia Putellas encabeza la lista de España para la Eurocopa femenina con Salma Paralluelo como sorpresa
    Proyecto Pelusa, el álbum de fans de Maradona más grande del mundo
    Alcaraz, entre tortilla, paseos y ajedrez 
    Segunda oportunidad para Simeone
    Nakamura, el ajedrecista más rico
    Patxo Unzueta, el magisterio desde el córner
    Ahora sí, esto es Wimbledon
    

# Nota
He hecho la **descripción** de estos dos códigos, ya que la **solicitud se repite** en el resto de las secciones, que en total son 17. 

# Código de color
Ahora vez se muestran las **categorías** por las que se van a clasificar los titulares que se han imprimido. 
Primero, se verán por consola las **categorías** por las que se van a clasificar/segmentar los titulares extraídos; para filtrar los titulares por categoría se una un *bucle* for; y para finalizar, se verán todos los titulares de la **categoría en concreto**.


```python
print(colored("Igualdad", 'green', attrs=['bold']))

str_match = [s for s in resultados if "igualdad" in s]
print("\n".join(str_match))

print(colored("Mujeres", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujeres" in s]
print("\n".join(str_match))

print(colored("Mujer", 'green', attrs=['bold']))

str_match = [s for s in resultados if "mujer" in s]
print("\n".join(str_match))

print(colored("Brecha salarial", 'green', attrs=['bold']))

str_match = [s for s in resultados if "brecha salarial" in s]
print("\n".join(str_match))

print(colored("Machismo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "machismo" in s]
print("\n".join(str_match))

print(colored("Violencia", 'green', attrs=['bold']))

str_match = [s for s in resultados if "violencia" in s]
print("\n".join(str_match))

print(colored("Maltrato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "maltrato" in s]
print("\n".join(str_match))

print(colored("Homicidio", 'green', attrs=['bold']))

str_match = [s for s in resultados if "homicidio" in s]
print("\n".join(str_match))

print(colored("Género", 'green', attrs=['bold']))

str_match = [s for s in resultados if "género" in s]
print("\n".join(str_match))

print(colored("Asesinato", 'green', attrs=['bold']))

str_match = [s for s in resultados if "asesinato" in s]
print("\n".join(str_match))

print(colored("Sexo", 'green', attrs=['bold']))

str_match = [s for s in resultados if "sexo" in s]
print("\n".join(str_match))
```

    [1m[32mIgualdad[0m
    La escuela concertada ante las desigualdades: el debate pendiente
    La escuela concertada ante las desigualdades: el debate pendiente
    [1m[32mMujeres[0m
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    [1m[32mMujer[0m
    Ellos no bailaron solos: la mujer detrás de la loca historia de Locomía
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    Un aula de Vallecas se rebela contra los libros de texto que silencian a las mujeres
    [1m[32mBrecha salarial[0m
    
    [1m[32mMachismo[0m
    
    [1m[32mViolencia[0m
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    [1m[32mMaltrato[0m
    
    [1m[32mHomicidio[0m
    
    [1m[32mGénero[0m
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Hannah Gadsby, la monologuista que rompió los moldes del género: “No hay una forma correcta de hacer comedia”
    Patricia Guerrero, el baile sin límite ni género: “¿Quién dice qué es el flamenco?”
    [1m[32mAsesinato[0m
    La ilustradora española que se asoma a las ventanas de Nueva York en ‘Solo asesinatos en el edificio’
    [1m[32mSexo[0m
    La segunda vida de Fire Island, el primer pueblo gay de EE UU: sexo, PrEP, arte y fiestas en piscinas
    Un juez de Ourense autoriza el cambio de sexo en el registro a un menor trans de ocho años
    La segunda vida de Fire Island, el primer pueblo gay de Estados Unidos: sexo, PrEP, arte y fiestas en piscinas
    Un libro y un documental revisitan la figura de George Michael: atracones de helado, culebrones, sexo y éxtasis
    

# Comentarios

Tras haber realizado la actividad, quería hacer algunas anotaciones: 
1. Fue muy **interesante** tratar de descrifrar cada uno de los pasos de los diferentes códigos. 
2. Una **asignación** compleja, pero de la que se aprende algo nuevo. 
3. Al final el print(colored no me imprimió, pero logré hacer la explicación. 
4. Tengo que contarle que por **error borré la actividad** y me tocó hacerla de nuevo.
