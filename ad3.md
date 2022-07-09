# AD3

Esta es la **Actividad dirigida 3** que consiste en hacer un ejercicio de programación literaria aprovechando el código que hemos usado en programación con Python donde realizamos *web scraping*. 

## Instalar librerías

En estos casos no es necesario instalar aquellas librerías que vienen con *Python*, pero las `externas` sí deben ser **instaladas**.


```python
pip install requests bs4 pandas termcolor
```

    Requirement already satisfied: requests in c:\users\fanny\documents\python scripts\lib\site-packages (2.27.1)
    Requirement already satisfied: bs4 in c:\users\fanny\documents\python scripts\lib\site-packages (0.0.1)
    Requirement already satisfied: pandas in c:\users\fanny\documents\python scripts\lib\site-packages (1.4.2)
    Requirement already satisfied: termcolor in c:\users\fanny\documents\python scripts\lib\site-packages (1.1.0)
    Requirement already satisfied: charset-normalizer~=2.0.0 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (2.0.4)
    Requirement already satisfied: certifi>=2017.4.17 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (2021.10.8)
    Requirement already satisfied: idna<4,>=2.5 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (3.3)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in c:\users\fanny\documents\python scripts\lib\site-packages (from requests) (1.26.9)
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

A continuación agrego el código fuente para la actividad de **Programación literaria**.


```python
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

## Objetos/variables

Se declara la **variable** resultados para almacenar cada resultado de las `url`.

resultados = [] En esta celda se verán los resultados una vez se haya ejecutado el Web _Scrapping_. 

## Programación literaria
Voy a empezar la actividad de **programación literaria**, algo nuevo para mí. 

Para llevar a cabo esta actividad, emplearé la url principal del código dado por el profesor que es del diario [El País](https://resultados.elpais.com) de la cual obtendremos los datos. 

Como ocurre es los ejercicios de Web *Scrapping*, hay que hacer una petición. La estructura identificada para los títulos en HTML es h2.

La mencionada petición se hace con `req = requests.get(+URL)`. `If` es una condicional que `if (req.status_code != 200)`, que es el código de respuesta de estado satisfactorio o exitosa de la petición. Se pasa a extraer el texto HTML de la página web con  `BeautifulSoup(req.text, 'html.parser')`.

Entonces, cómo se hace el filtrado. Recurrimos a usar una de las funciones de `soup`, en este caso sería la función `findAll`. Así solo se guardará en `tags` (que es una variable) el texto de los titulares del sitio web. No obstante, si se desean almacenar de forma individual sería en resultados, se usa el bucle `for` (*se utiliza para repetir una o más instrucciones un determinado número de veces*). 

Con `resultados.append(h2.text)` se añaden todos los textos dentro de las etiquetas a la lista inicial resultados.


```python
req = requests.get("https://resultados.elpais.com")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup = BeautifulSoup(req.text, 'html.parser')
 
tags = soup.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)

```

    Elon Musk retira la oferta de compra por Twitter
    Kirchner acusa al ministro de Economía saliente de “desestabilización institucional”
    Asesinado a tiros el ex primer ministro japonés Shinzo Abe
    Vídeo | El momento del atentado
    
    Shinzo Abe, un primer ministro carismático que marcó el rumbo del país
    El detenido: desempleado y antiguo miembro de las fuerzas armadas
    Detenido en Brasil el presunto autor intelectual del asesinato de Dom Philips y Bruno Pereira en la Amazonia
    Biden reacciona a las críticas sobre su inacción con un decreto para proteger el aborto
    El misterio de la carta del soldado alemán
    Las voces de los niños de la guerra en Colombia: “Los colegios se volvieron salas fúnebres”
    Trump y Biden miden ya sus fuerzas para las presidenciales de 2024
    Cuatro agentes de la Patrulla Fronteriza enfrentarán procesos disciplinarios tras el maltrato a inmigrantes haitianos en Texas
    Nadie frena la novena reelección de un eterno sindicalista argentino
    Detenida la esposa del empresario italiano Raphael Tunesi como autora intelectual de su asesinato
    La sobrexplotación amenaza a las especies silvestres de las que dependen miles de millones de personas en el mundo
    Rosaly Lopes, la persona que más volcanes ha descubierto: “Puede haber vida en Titán” 
    Un Djokovic de récord se medirá con Kyrgios en la final de Wimbledon
    El Partido Conservador explora cómo acelerar la salida de Johnson
    La UE confía en que la relación con Londres mejore
    Un mandato rocambolesco plagado de escándalos
    Vídeo | Del Brexit al ‘partygate’, los escándalos que han acabado con la dimisión
    El bombazo que volvió a poner a Peña Nieto bajo los reflectores de la política en México
    La Fiscalía mexicana reabre el caso por el asesinato del excandidato Colosio
    El Papa asegura que el camino que ha seguido la Iglesia contra la pederastia “es irreversible”
    Lanzaderas de misiles, drones turcos y cañones de artillería: Ucrania reclama más armas para recuperar terreno 
    Hallada en España la cara del homínido más antiguo de Europa
    Vivir sin agua en un paraíso
    Chile necesita construir grandes mayorías
    ¿Habrá nueva Constitución?
    La juventud en el país de Mickey Mouse
    Guerra con aceite de oliva
    Stephen King adora ‘Stranger Things’ y viceversa
    Rubén Blades: “Yo siempre he sido parte del público”
    El cine de propaganda nunca muere: ahora se suman chinos y rusos
    ‘Thor’, los traumas y las risas de los dioses dirigidos por un niño
    Francia considera que el autor de una obra es el artista que la concibe y no el que la ejecuta
    ¿Quién es quién en la familia real de Mónaco? Un repaso a los Grimaldi
    Los hombres también se ponen bótox: este es su perfil y sus razones
    Elon Musk, sobre sus 10 hijos: “Estoy haciendo todo lo posible para ayudar con la crisis de despoblación” 
    El pionero que desnudó y fotografió a otros hombres cuando estaba prohibido
    Demi Moore posa con su nueva colección de biquinis diseñados por ella misma
    Cielo e infierno de Rafael Nadal, entre dos mundos
    Checo Pérez vive su momento más dulce tras una década en la Fórmula 1
    Pogacar no se cansa de arrasar a sus rivales en el Tour de Francia
    EL PAÍS América gana el Premio de la Asociación Mundial de Editores al mejor sitio de noticias de Latinoamérica
    Vender a una niña por comida: “Hubo pretendientes e intenté escoger al más joven”
    Francisco de Roux: “Si no se acaba con el narco, Colombia no tendrá paz”
    La economía mundial se desinfla: así es la crisis que viene
    Japan’s ex-PM Shinzo Abe dies in hospital after being shot by gunman
    An ex-Marine processes war trauma, uncovers memories of abuse at a Catholic school in Spain
    US basketball star Brittney Griner pleads guilty to drug charges in Russia
    Nicole Kidman makes a surprise appearance on the Balenciaga runway
    Elon Musk secretly fathered twins with an executive at his company
    Letras Americanas: la actualidad literaria de un continente vista por el escritor Emiliano Monge
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Toda la actualidad científica en el boletín de Materia
    Ideas: reportajes y entrevistas para entender el mundo
    El agente que mató a George Floyd, condenado a otros 21 años de cárcel por violar sus derechos civiles
    Haití, sin presidente y sin Estado un año después del asesinato de Jovenel Moïse
    Petro nombra a Alejandro Gaviria en Educación y ahonda en su perfil de moderado
    Inflación, energía, reservas y tipo de cambio: los desafíos que lastran a la economía Argentina en el segundo semestre
    Los argentinos se lanzan a las tiendas ante una nueva crisis del peso: “Si ves algo, compra”
    Uniper, la mayor gasista alemana, pide el rescate asfixiada por los recortes del gas ruso
    Marcos López Hoyos, inmunólogo: “Deberíamos usar mascarillas en interiores y comer en terrazas”
    La falta de presupuesto ahoga a los refugios para mujeres víctimas de violencia en México
    ¿Existe brecha generacional en el colectivo LGTBI? De la lucha por los derechos al debate identitario
    Alivio para el arte conceptual: la justicia francesa considera que el autor de una obra es el artista que la concibe y no el que la ejecuta
    ‘Mali Twist’: Y el rock también llegó a Malí
    Muere el actor James Caan, célebre por encarnar a Sonny Corleone en ‘El padrino’, a los 82 años
    Hallada en Atapuerca la cara del humano más antiguo de Europa
    Rosaly Lopes, la persona que más volcanes ha descubierto: “Puede haber vida en Titán” 
    Antonio Guillamón: “La identidad de género no se elige, como prueba el fracaso de las terapias de conversión”
    ¿Por qué me gusta el fútbol? 
    ‘El Pedro Ferrándiz más humano’, por Juan Antonio Corbalán
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    La sobrexplotación amenaza a las especies silvestres de las que dependen miles de millones de personas en el mundo
    ‘Mi familia de ardillas’, por Jacinto Antón
    Adiós al Aquarama del zoo de Barcelona, el hogar de la orca ‘Ulises’
    El misterio de la carta del soldado alemán
    ‘Por qué los proyectos ‘cripto’ son tan difíciles de entender’, por Jordi Pérez Colomé
    Jorge Stolfi: “Soy catedrático de informática. Como mis colegas, sé que la tecnología de bitcoin es basura”
    Las discrepancias entre PP y PSOE enturbian el homenaje a Miguel Ángel Blanco 
    Los partidos de derecha en Barcelona se ponen en marcha para destronar a Ada Colau
    Pablo Iglesias, sobre los audios de Villarejo: “Toda esta ‘basura’ ha alimentado el relato mediático sobre Podemos durante años”
    ‘Encerrado con el diablo’: Dennis Lehane busca en el fondo del alma
    ‘Sanfermines: maltrato animal en riguroso directo’, por Eva Güimil
    ‘La noche más larga’ y ‘La lista final’: palomitas sin sabor para el verano
    El espectáculo (teatral) debe continuar en la alta costura de París
    Por qué es importante conocer tu personalidad erótica para tener una vida sexual más satisfactoria
    Elon Musk tuvo gemelos en secreto con una ejecutiva de una de sus empresas
    El Panamá indígena busca empoderar a sus mujeres
    Volver a la escuela tras dos años de pandemia
    ¿Dónde está exactamente el origen del mal?
    El hombre que persigue la gaita más antigua del mundo
    La tiranía de la vida eficiente: ¿alguien es capaz de no hacer nada? 
    Carlos Nobre: “La Amazonia  ya muestra síntomas  de muerte”
    Manual para sobrevivir al calentón del euríbor
    La carrera por las oposiciones ha empezado: en juego hay 45.000 trabajos para toda la vida
    Ayn Rand, ‘rednecks’ e inclusividad forzada: el mundo virtual como escenario político
    Hay un río de oro negro bajo A Coruña
    Un continente donde los sueños tienen menos de 30 años
    Toca devolver lo prestado: la crisis de deuda asfixia el desarrollo en África
    Vídeo | Qué hacer si te pierden la maleta cuando viajas en avión: los pasos a seguir
    Así fue mi cara a cara con una orca salvaje en el Mar de Cortés
    Nicole Kidman aparece como modelo sorpresa en el chocante desfile de Balenciaga
    El ‘influencer’ más varguardista del momento crea parodias de la moda desde una de las islas más pobres del mundo
    A-ha: cómo tres tipos que no se soportan sobrevivieron a la canción pop más grande de los ochenta 
    Una granja llena de armas y dos denuncias por secuestro: ¿cómo ha llegado Ezra Miller hasta aquí?
    Aló Comidista: “¿Tomar gazpacho es un pecado nutricional?”
    ¿Cuál es la mejor marca de tónica?
    Las oficinas del futuro: espacios híbridos con tecnología integrada para rendir más (y mejor)
    Abre la primera casa sin cocina para los enfermos que no pueden parar de comer: así es el síndrome de Prader Willi
    Ponte a prueba con nuestros crucigramas, sopas de letras, sudokus y juegos arcade
    Las cámaras captan lo que ha hecho Nadal al irse de Wimbledon: dice mucho de cómo es
    Jovic y cinco más, fuera
    Carmona, la transformación de un territorio con abejas y renovables
    

## Continuamos con el scraping de las secciones del diario

En siguiente código se repite el **proceso** realizado en el anterior, lo único que cambia es la sección en este caso es [Internacional](https://elpais.com/internacional): `Un req12 = requests.get` para hacer el web scrapping; *if (req.status_code != 200)* para comprobar la petición; `soup = BeautifulSoup(req.text, 'html.parser')` para comprobar que ha sido exitosa; y *tags = soup.findAll("h2")* para almacenar.



```python
req2 = requests.get("https://elpais.com/internacional")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup2 = BeautifulSoup(req2.text, 'html.parser')
 
tags = soup2.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    Un magnicidio inusual que hace sentir a los japoneses vulnerables 
    Ucrania rinde homenaje a Boris Johnson
    Muere a los 79 años el expresidente de Angola Eduardo Dos Santos en Barcelona
    Un magnicidio inusual que hace sentir a los japoneses vulnerables 
    Populistas occidentales por el desagüe de la historia
    Boris Johnson dimite
    La ultraderecha mundial y el control de los cuerpos
    Las otras fronteras de Rusia: entre el miedo (al imperio) y los intereses nacionales
    El Partido Conservador explora cómo acelerar la salida de Boris Johnson de Downing Street
    Boris Johnson: un mandato rocambolesco plagado de escándalos
    Shinzo Abe no es el primero: historia reciente de los magnicidios
    El detenido por la muerte de Abe: desempleado y antiguo miembro de las fuerzas armadas
    Los principales líderes internacionales condenan el asesinato a tiros de Shinzo Abe
    Shinzo Abe, un primer ministro carismático que marcó el rumbo de la política en Japón
    La UE confía en que la relación con Londres mejore tras la salida de Boris Johnson
    ¿Quiénes son los favoritos para suceder a Boris Johnson?
    Boris Johnson: el final de la escapada del mago del Brexit
    Populistas occidentales por el desagüe de la historia
    Trump y Biden miden ya sus fuerzas para las elecciones de 2024
    Detenido en Brasil el presunto autor intelectual del asesinato de Dom Philips y Bruno Pereira en la Amazonia
    Nadie frena la novena reelección de un eterno sindicalista argentino
    “Hay una parte de la verdad de Colombia que solo se puede conocer fuera de Colombia”
    Trump y Biden miden ya sus fuerzas para las elecciones de 2024
    El agente que mató a George Floyd, condenado a otros 21 años de cárcel por violar sus derechos civiles
    

#### Repetimos el ejercicio en otras secciones
En esta ocasión continuamos con la sección [Opinión](https://elpais.com/opinion)

Al igual que en la anterior sección se convoca los datos de la `url`. Para completar la petición empleamis `request` para completar la petición. Además, `raise`, que es una función que se usa para indicar que se ha ocurrido un error o hay una excepción.


```python
req3 = requests.get("https://elpais.com/opinion")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup3 = BeautifulSoup(req3.text, 'html.parser')
 
tags = soup3.findAll("h2")
 
for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    El legado de Boris Johnson
    Chile necesita construir grandes mayorías
    La juventud en el país de Mickey Mouse
    Disonancias en la izquierda
    ‘Mi casa, mi árbol’
    Ten cuidado
    Emprendedor de ‘fake news’
    Esto es una fotografía
    Guerra con aceite de oliva
    Castración
    Carlos Ríos, un nutricionista en el ojo del huracán 
    Vendaval inflacionista
    Deriva reaccionaria en Estados Unidos
    El Roto
    Peridis
    Flavita Banana
    Riki Blanco
    Sciammarella
    Planeta de Plástico, por Malagón
    Envía tu carta
    Lo raro es vivir
    Defender lo público
    Los excesos de Telmo Martín
    En la calle circulan rumores
    Opinar sin insultar
    Contra el conflicto de intereses, transparencia
    El defensor del lector contesta
    

#### Continuamos con otras secciones 

Se repite el mismo proceso, empezando por invocar las `url` de las secciones: España, Economía, Sociedad, Educación, Clima y Medio Ambiente, Ciencia, Cultura, Babelia, Deportes, Tecnología. 

Los códigos tienen solicitudes similares a los anteriores, lo que va a cambiar son los titulares, ya que son secciones diferentes. 
Emplearemos: `requests.get`, `if req.status_code != 200`, `raise Exception`. La variable `soup = BeautifulSoup(req.text,'html.parser')`. También la estructura identificada para el llamado de datos es h2.

Además, se deben modifican los nombres de las variables. Por ejemplo `req4`, para la sección [España](https://elpais.com/espana/); `req5` para [Economia](https://elpais.com/economia/); `req6` para [Sociedad](https://elpais.com/sociedad/) y así sucesivamente con las otras secciones.


```python
 
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
```

    Yolanda Díaz presenta Sumar como movimiento ciudadano que busca “un nuevo contrato social”
    El Gobierno y la Generalitat  se comprometen a retomar el diálogo y “superar la judicialización”
    El juez cita como imputados a tres exjefes de ETA por el asesinato de Miguel Ángel Blanco
    Ante la crisis, ¿gestionas o lideras?
    El almirante Cervera y el honor de España
    El Gran Retroceso
    Santa Bárbara y la cultura de la defensa
    ¿Es posible disentir de esta retórica belicista?
    Interior estudia incentivos a los guardias civiles de zonas rurales para evitar el cierre de cuarteles
    Marlaska elogia a Marruecos y su trabajo de “contención” de la inmigración tras la muerte de 23 subsaharianos en Melilla 
    El Defensor del Pueblo abre una investigación sobre el incendio en la sierra de la Culebra
    Feijóo considera “discutible” dedicar dinero público a becas para familias de rentas altas como hace Ayuso
    Un juez archiva la causa contra el exmagistrado del Constitucional Fernando Valdés por supuesto maltrato 
    La Audiencia Provincial de Palma decide continuar con el juicio a Cursach tras desestimar buena parte de las peticiones de las defensas
    Segunda ola calor del verano: al menos cuatro días con máximas de hasta 46° y noches tórridas a más de 25°
    La Audiencia justifica la salida del magistrado Delgado del juicio a Camps “para alejar cualquier sospecha de falta de imparcialidad”
    Pablo Iglesias, sobre los audios de Villarejo: “Toda esta ‘basura’ ha alimentado el relato mediático sobre Podemos durante años”
    El frente catalán del nuevo proyecto de Yolanda Díaz
    Defensa se abre a revisar los sueldos de los 120.000 militares españoles 
    Un paraíso en el que avistar más de 20 especies de cetáceos
    El secreto de Fuerteventura se hace viral: la ‘playa de las palomitas’
    Un vino para triunfar entre los mileniales
    Artesanía y cultura que conquista a las ‘influencers’
    Más allá de la capital. El triunfo de la vida rural madrileña
    Elon Musk retira la oferta de compra por Twitter
    El BCE cifra en 70.000 millones las pérdidas de la gran banca ante una crisis climática
    Las constructoras acusan a la CNMC de “falta de rigor” por la macromulta de 204 millones
    Ya se puede pedir el cheque ‘antinflación’ de 200 euros: ¿quién tiene derecho? ¿Dónde solicitarlo?
    Bancos centrales, entre líneas
    Estado autonómico: Sobre las reformas pendientes
    Carlos Jiménez Villarejo: un hombre contra la desesperanza
    IPC: de la negación al riesgo de sobrerreacción
    A Unilever se le indigesta el helado 
    Francisco González pide volver a declarar como imputado en el ‘caso Villarejo’
    Uniper, la mayor gasista alemana, pide el rescate asfixiada por los recortes del gas ruso
    Volkswagen presiona a Tesla con la construcción de su primera planta de baterías
    Las principales cajas de ahorros y bancos minoristas del mundo ponen el foco en los avances en finanzas sostenibles
    Estas son las mayores multas a empresas españolas por repartirse los contratos y manipular precios
    Los datos de empleo de junio en EE UU alejan el temor de la recesión y animan a la Fed a subir tipos
    El número de usuarios falsos en Twitter pone en peligro la compra de Musk
    Caso Laso: ¿Me pueden echar tras sufrir un infarto?
    Patricia Ayuela (Línea Directa Aseguradora): “No gestiono la compañía mirando a la Bolsa”
    Iberdrola desarrollará 16 proyectos renovables en el Reino Unido tras “garantizar su rentabilidad”
    Repsol triplica el margen de beneficio de sus refinerías en España entre abril y junio
    La carrera por las oposiciones ha empezado: en juego hay 45.000 trabajos para toda la vida
    Los jueces se ponen de parte de las víctimas de ‘phishing’ bancario
    Texas es la nueva China para  Elon Musk
    IPC: de la negación al riesgo de sobrerreacción
    A Unilever se le indigesta el helado 
    Siemens pagará la opa sobre Gamesa con un préstamo de 4.000 millones
    Telefónica segrega sus filialesen Argentina que pasan a un holdingde nueva creación
    
    Así será el nuevo DiverXO: en un bosque en La Finca y una sala de 1.900 metros para 40 comensales
    El criptoinvierno fuerza el cierre de 2gether y deja a la deriva a 100.000 afectados
    No se puede desheredar a un familiar con el que no se tiene relación, según el Supremo
    Líos en la piscina comunitaria: normas y sentencias para un chapuzón seguro
    Parir en casa, educarlo por mi cuenta… ¿Qué puedo decidir sobre mi hijo y qué no?
    Música que transforma vidas y esboza futuros
    El futuro probable de una sociedad insostenible
    Francisco Javier Blasco: “Llevamos años sin mejorar la eficacia de las políticas activas de empleo”
    La hora del bienestar corporativo
    Cancerberos del bienestar de la empresa
    Cómo garantizar la seguridad en un mundo de amenazas híbridas
    ¿Cuáles son los dilemas éticos del uso de la inteligencia artificial?
    Las aventuras de un par de calcetines que dan empleo a todo un pueblo
    Cultura financiera como punto de partida para volver a empezar
    ¿Puede convertirse España en una de las potencias logísticas del futuro?
    Por qué digitalizar una pyme aporta más empleo
    ‘Coopetir’: la actitud DFactory
    Así serán las ciudades de la (nueva) última milla
    Cinco errores habituales al digitalizar un negocio 
    PERTE Agroalimentario: ¿cómo acceder a los fondos europeos?
    Fondos soberanos: ¿Cómo funcionan las cajas fuertes de los estados más ricos?
    ¿Crisis de deuda mundial a la vista?
    El método Muñoz para triunfar en cada reto que se propone
    Gloria Ramos, cuando el afán de superación acaba en la alfombra roja 
    Ocho ‘startups’ innovadoras con nombre propio
    Hotmart y su plataforma 360 para creadores de contenidos
    El responsable LGTBI del PSOE celebra que Sánchez apartase a Calvo por su oposición a la ‘ley trans’
    Biden reacciona a las críticas sobre su inacción con un decreto para proteger el aborto
    El Papa asegura que el camino que ha seguido la Iglesia contra la pederastia “es irreversible”
    El control del cuerpo de las mujeres
    No se gobierna con el catecismo romano
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    La sobrexplotación amenaza a las especies silvestres de las que dependen miles de millones de personas en el mundo
    Los ricos esperan menos para operarse, también en los hospitales públicos
    El 60% de los universitarios no se ve preparado para un mercado laboral que no encuentra los perfiles necesarios  
    El Constitucional declara por primera vez que toda discriminación de las personas trans es ilegal
    La ministra de Ciencia e Innovación: “El gran peligro es el negacionismo climático”
    Las emisiones de efecto invernadero volvieron a crecer en 2021 en España aunque sin sobrepasar los niveles previos a la pandemia
    ¿Existe brecha generacional en el colectivo LGTBI? De la lucha por los derechos al debate identitario
    Marcos López Hoyos, inmunólogo: “Deberíamos usar mascarillas en interiores y comer en terrazas”
    ¿Hay que obligar a los niños a hacer deberes en verano? Los expertos recomiendan actividades que no se parezcan a las tareas escolares
    La emergencia climática llama a la puerta del mundo
    Empresas, expertos, políticos y científicos reclaman compromiso ante la emergencia climática: “Lo fundamental es cumplir”
    Se buscan profesionales en economía circular
    La economía circular llega a la ciudad. Te contamos dónde se encuentra 
    ¿Por qué hablar de VIH en el Orgullo y no en los sanfermines?
    Mitos, falsedades, bulos y realidades sobre el VIH 40 años después
    Qué son las evidencias científicas y por qué están revolucionando la educación
    Munic, el joven redimido por el trap
    El tremendo peso de la obesidad en España
    Interactivo | Los 14 cambios en los aeropuertos españoles que no ves y que ya están ocurriendo
    Encontrar empleo pese a los obstáculos. Por dónde empezar la búsqueda
    La fórmula de Carboneros para evitar el éxodo rural: trabajar cuidando a los vecinos 
    Consejos y cuidados para el primer verano con un gatito o un perrito
    ¿Qué tienen en común perros y gatos cuando son cachorros?
    La guía definitiva para alimentarnos mejor (y cuidar nuestra salud y la del planeta)
    El metro como refugio. De los andenes de Madrid en 1936 a los de Kiev en 2022
    La salud mental de los refugiados: cómo abrirse para cerrar las heridas
    Yogures con menos azúcar, paso firme hacia la alimentación infantil del futuro
    Conectada con el mercado laboral y tecnológica: así es la universidad del presente
    Así es la formación más abierta y flexible, a prueba de crisis
    El 60% de los universitarios no se ve preparado para un mercado laboral que no encuentra los perfiles necesarios  
    ¿Cómo se cierra un colegio público?
    Los sindicatos educativos catalanes convocan huelga el 7 de septiembre, primer día de curso en los institutos, y el 28
    ¿Hay que obligar a los niños a hacer deberes en verano? Los expertos recomiendan actividades que no se parezcan a las tareas escolares
    El caso de Georgia, en EE UU: becar sin importar la renta agranda la desigualdad
    Madrid, el paraíso de la educación privada: en la capital son minoría los alumnos de la pública
    Trabajar en el ‘big data’: “Nunca he tenido que echar currículum, las ofertas me han llegado solas”
    El Gobierno lanza una ofensiva contra las becas para rentas altas de Ayuso que Feijóo respalda
    José Manuel Bar, secretario de Estado de Educación: “Los docentes de secundaria deben empezar a estudiar pedagogía en su carrera”
    Ayuso se apunta ahora el tanto de la bajada de tasas universitarias, pese a que las llevó a los tribunales para no reducirlas
    Notas de Selectividad 2022 por comunidades: los aprobados rozan el 96%
    Sin currículos
    La escuela concertada ante las desigualdades: el debate pendiente
    La equidad frente a las políticas educativas de privatización en Andalucía
    No hay lunes al sol en la Universidad
    El nuevo sistema para evaluar los conocimientos digitales de los profesores valdrá en toda España
    Ofrecer comedor gratis en todos los colegios públicos es “alcanzable y urgente”: costaría 1.664 millones al año, según la ONG Educo  
    Una fórmula para que la escuela pública compita mejor con la concertada
    La pérdida de alumnos por el descenso de la natalidad está afectando con más fuerza a la escuela pública que a la concertada
    El caso de Georgia, en EE UU: becar sin importar la renta agranda la desigualdad
    El techo de cristal del grado medio de FP: candidatos demasiado preparados se quedan con los puestos
    La implantación del nuevo Bachillerato general fracasa pese a su demanda potencial: “Creímos que lo pedirían seis alumnos y lo han hecho 27”
    Toni Solano, director de instituto: “Veo mal a los niños, necesitan muchísima ayuda”
    Niños, Administraciones y redes sociales: prohibir su uso con una mano y enseñar a crear contenidos con la otra
    Una historia en la que caben Alaska, García Lorca, Suárez y Popper: la Universidad Internacional Menéndez Pelayo cumple 90 años 
    Subirats reinterpreta la ley de Universidades: freno a la precariedad, facilidades para los alumnos extranjeros y ciencia abierta
    Las universitarias desertan del grado de Matemáticas ahora que tiene pleno empleo. ¿Por qué?
    Golpe a la temporalidad en las universidades: 25.000 profesores asociados serán indefinidos a tiempo parcial
    “No hay pensamiento sin tiempo para pensar”
    “En el hospital, la enseñanza es una medicina más”
    Un alegato por la paz y la cultura
    La sobrexplotación amenaza a las especies silvestres de las que dependen miles de millones de personas en el mundo
    Segunda ola calor del verano: al menos cuatro días con máximas de hasta 46° y noches tórridas a más de 25°
    La emergencia climática llama a la puerta del mundo
    Las emisiones de efecto invernadero volvieron a crecer en 2021 en España aunque sin sobrepasar los niveles previos a la pandemia
    Jornada del foro Ecosistema Ahora, organizado por EL PAÍS, en imágenes
    La oceanógrafa y buceadora Gádor Muntaner: “Lo que más miedo me da es nadar en un mar sin tiburones”
    Los rinocerontes regresan a Mozambique 40 años después de su desaparición
    Carlos Nobre: “La Amazonia  ya muestra síntomas  de muerte”
    El Parlamento Europeo respalda el sello verde de la UE al gas y energía nuclear
    Un alud letal y una histórica sequía: el cambio climático castiga al norte de Italia
    Un año de espera por la bicicleta: el estallido de la demanda coincide con la escasez de suministro
    Un plan de retirada  
    Crisis energética y precios del carbono
    La lección del martín pescador para afrontar la crisis ecológica
    Estocolmo+50: mirar atrás para tomar impulso
    Ríos imposibles: las 171.000 barreras que rompen el curso de agua en España
    La UE abraza las renovables para romper la dependencia de Rusia
    La lucha en un pueblo de Teruel para salvar su última montaña
    ¿Qué aire respiran los niños de Madrid y Barcelona? En el 46% de los colegios se supera la contaminación permitida
    “No hay pensamiento sin tiempo para pensar”
    “En el hospital, la enseñanza es una medicina más”
    Un alegato por la paz y la cultura
    Hallada en Atapuerca la cara del humano más antiguo de Europa
    El humano más antiguo de Europa: prehistoria que hace historia
    Rosaly Lopes, la persona que más volcanes ha descubierto: “Puede haber vida en Titán” 
    Una cena conflictiva
    ‘Meraxes gigas’: descubierta en la Patagonia argentina una nueva especie de dinosaurio carnívoro gigante
    La cola vestigial, el apéndice oculto del hombre que venció a Napoleón en Waterloo
    La agenda de la NASA para volver a la Luna (y quedarse)
    El sector biotecnológico supera las cifras de 2020 y capta 180 millones de euros de inversión privada
    “La identidad de género no se elige, como prueba el fracaso de las terapias de conversión”
    Un novedoso estudio sobre estrés adolescente propone un nuevo método para afrontarlo: optimizarlo en lugar de evitarlo
    Las mentes humanas detrás de las mentes artificiales
    El cerebro está más caliente de lo que se pensaba 
    Cangrejos ermitaños: el arte de seleccionar la mejor concha
    Las temperaturas extremas también matan en América Latina
    Vuelve el LHC, el mayor experimento sobre la Tierra 
    La matemática Maryna Viazovska gana la medalla Fields tras descubrir la mejor forma de apilar naranjas en 24 dimensiones
    ¿Dónde hay civilizaciones extraterrestres?
    Las mentes humanas detrás de las mentes artificiales
    Matemáticas para describir los remolinos, los taxis del océano
    Reaparece la tesis de María Wonenburger, la pionera matemática española que permaneció décadas en el olvido
    Técnicas criptográficas que se fundamentan en lo impredecible
    Alrededor de la mesa
    Fracciones egipcias
    El problema del huerto
    La cola vestigial, el apéndice oculto del hombre que venció a Napoleón en Waterloo
    Molinos y gigantes, adelantos tecnológicos y el síndrome bicicleta
    El síndrome del hombre lobo y la realidad lógica de su fábula
    La locura como juego; más allá del Quijote y de las novelas de Pérez Galdós
    El andar del borracho, las huellas del azar y el juego de dados en algunos libros malditos
    ¿Son mejores las hormonas bioidénticas?
    ¿Qué surgió antes, el ARN o el ADN?
    ¿Por qué se sabe que los núcleos de la Tierra rotan?
    ¿Qué son los mini reactores nucleares?
    Invitados indeseables por Navidad: el muérdago y otras plagas que evitar durante las fiestas
    Las ‘apps’ nutricionales o cómo comer bien no debería depender de uno mismo
    Malnutrición invisible: el impacto de la pobreza en la salud infantil
    El óxido de etileno, la sustancia cancerígena que ha obligado a retirar miles de alimentos en la UE
    Que no te líen con los ingredientes: aceites y grasas de mala calidad nutricional
    ¿Cómo es un festival intergeneracional en 2022?
    Apoteosis de The Killers en Mad Cool ante 70.000 personas
    Lo que debemos a Patxo Unzueta
    La huida
    Un siglo de canciones, 1.500 artistas
    Peter Brook, el gran árbol del teatro
    El cine de propaganda nunca ha desaparecido: ahora se lanzan a él chinos y rusos
    Alivio para el arte conceptual: la justicia francesa considera que el autor de una obra es el artista que la concibe y no el que la ejecuta
    ‘Thor: Love and Thunder’, cuarta aventura individual del superhéroe de Marvel, y otros estrenos de este fin de semana
    #Brahms125 aporta pasión y consuelo en las cálidas noches granadinas
    La Comunidad de Madrid retira una obra de Paco Bezerra prevista por los Teatros del Canal alegando razones económicas
    Estopa, Creu de Sant Jordi desde la periferia de la periferia
    ‘Mali Twist’: Y el rock también llegó a Malí
    Muere el actor James Caan, célebre por encarnar a Sonny Corleone en ‘El padrino’, a los 82 años
    Rubén Blades: “Yo siempre he sido parte del público”
    La oceanógrafa y buceadora Gádor Muntaner: “Lo que más miedo me da es nadar en un mar sin tiburones”
    Rosalía en Almería, con R de reinona y A de apoteósico
    Metallica triunfa a base de oficio en un Mad Cool repleto
    Queen se aferra a su corona en el concierto del WiZink
    Cuándo un gallego te dice que sí, aunque esté pensando que no. La retranca gallega y otros misterios que descubrir en el Camino Inglés
    El último atardecer de Europa se ve solo desde este lugar. Un viaje hacia el infinito por el Camino de Fisterra-Muxía
    Lorca, en la ciudad al margen
    El Pirineo oscense, para entrar a vivir
    Toda la lectura del verano, en el bolsillo
    Longsellers: los libros más vendidos a lo largo de la historia
    Libros para descubrir el mundo recomendados por Benjamín Prado
    Encuentro virtual con la cantante Carla Morrison
    Ciclo MET VERANO con Cine Yelmo
    'KLIMT. La experiencia inmersiva'
    'Padre no hay más que uno 3'
    Más allá del frenesí de los Sanfermines
    El palco, una ignominia
    El segundo encierro de San Fermín 2022, en imágenes
    Un toro rezagado alarga el segundo encierro de San Fermín a tres minutos y 10 segundos
    ‘Agua y jabón’: más que un libro, una constelación de genialidades
    Ayn Rand, ‘rednecks’ e inclusividad forzada: el mundo virtual como escenario político
    Hay un río de oro negro bajo A Coruña
    Max Aub, el escritor español que mejor contó la experiencia de la guerra y los refugiados 
    La Bienal del Whitney habla mucho y dice poco
    Los primeros poemas de Severo Sarduy, una joya inédita
    Libros para el verano: 80 novedades recomendadas para estas vacaciones
    Rigoberta Bandini, Jordi Évole, Rosa Montero, Juan Diego Botto, Albert Serra y otros nombres de la cultura proponen sus lecturas estivales
    ‘The Murder of Crows’: por qué el arte sonoro es más poderoso que el visual
    El regreso de Perrate: fiesta, linaje y ocho gozosos minutos de bulerías
    Raíces y alas del flamenco: seis discos entre tradición y evolución
    Cabeza acéfala
    Lo que siento (no se olviden de Ucrania) 
    El desafío de Frida Kahlo
    Otros turismos (lejos y aquí cerca)
    ‘Horas muertas’, en un Dublín hipnótico
    ‘Prometeo’, trío de ases
    ‘La memoria del alambre’, ese algo misterioso que daba miedo
    ‘Tarradellas. Una cierta idea de Cataluña’: manual de resistencia
    Antoni Muntadas: “Supe que me dedicaría al arte cuando dejé de pintar”
    Manuel Estrada: “Me agrada que una portada guste más después de leer el libro”
    Óscar Esquivias: “No hace falta ser creyente para leer la Biblia”
    Amelia Castilla: “Los ritos nos ayudan a hacer viable el trance de la muerte”
    Shuarma: “Me gusta de la poesía el silencio que encierra”
    España debuta con cabeza en la Eurocopa
    Rumbo a Kyrgios, un Djokovic de récord
    Pogacar no se cansa de arrasar a sus rivales en el Tour de Francia
    La Superliga, una oportunidad única para la Unión Europea
    ¿Por qué me gusta el fútbol? 
    Rafael no concibe abandonar
    El Pedro Ferrándiz más humano
    Cielo e infierno de Nadal, entre dos mundos
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    Mapi León: “Se demostró que el fútbol femenino solo había que saber venderlo”
    Así tuvo que cambiar Nadal su saque para aguantar el dolor en Wimbledon
    Lim envía a su mano derecha a desbloquear el nuevo Mestalla
    Joseph Blatter y Michel Platini, absueltos de los cargos de corrupción por un tribunal suizo
    Anand remonta y gana tras una obra de arte de Jaime Santos
    Nadal se retira de Wimbledon: “Así no puedo ganar”
    El deporte se complica para las mujeres trans
    Dos glorias activas frente a dos jóvenes pujantes en el XXXV Magistral Ciudad de León
    Muere Pedro Ferrándiz, leyenda del banquillo del Real Madrid de baloncesto
    Pogacar impone su ley y ya es líder del Tour de Francia
    España desarbola a Corea y se clasifica para octavos
    “Si no tenemos en quién mirarnos es muy difícil saber qué queremos ser”
    “Nunca acepto un no por respuesta”
    La nadadora que dejó de competir para hacer campeones de básquet
    Crónica de dos ciudades moldeadas por la misma pasión 
    Muere Pedro Ferrándiz, leyenda del banquillo del Real Madrid de baloncesto
    Nadal se retira de Wimbledon: “Así no puedo ganar”
    Pogacar impone su ley y ya es líder del Tour de Francia
    La UEFA se blinda contra la Superliga 
    La baloncestista Brittney Griner se declara culpable de posesión de drogas en Rusia
    Nadal quiere jugar contra Kyrgios
    Las jugadoras de Inglaterra piden a Nike cambiar el color del pantalón por la regla
    El Barcelona espera una respuesta del Bayern por Lewandowski mientras presenta a Christensen
    “¿Quieres cobrar tu salario en streaming?” Por qué los proyectos cripto son tan difíciles de entender
    El misterio de la carta del soldado alemán
    El porqué de los desafíos criptográficos: conocerte a ti mismo, conocer a tu enemigo
    Con el relax del verano se acentúan los peligros cibernéticos: así puede protegerse durante las vacaciones
    Meta presenta un traductor capaz de operar en tiempo real con 200 idiomas
    “Soy catedrático de informática. Como mis colegas, sé que la tecnología de bitcoin es basura”
    El sector biotecnológico supera las cifras de 2020 y capta 180 millones de euros de inversión privada
    Las mentes humanas detrás de las mentes artificiales
    El juego de la técnica
    Daniel Innerarity: “Los algoritmos son conservadores y nuestra libertad depende de que nos dejen ser imprevisibles”
    Regina Barzilay: “Tenemos que aprender a vivir en un mundo en el que la tecnología toma decisiones que no podemos supervisar”
    Herramientas y trucos para recordar la ubicación del coche gracias al móvil
    Las tres amigas que quieren revolucionar los materiales de construcción con fibras de hongos
    El Constitucional afianza el derecho al olvido en internet
    Dall-E Mini, el popular generador automático de imágenes que hace dibujos sexistas y racistas 
    En defensa de la procrastinación. Elogio del tiempo perdido (frente al que las redes te roban)
    Instagram, el mejor de los mundos posibles
    Del terrorismo youtuber al influencer rabioso: el odio inunda la red
    Cronodiversidad. ¿Por qué el tiempo cada vez va más rápido?
    El impacto de la tecnología en la hostelería: de la comanda digital al pago con código QR
    Herramientas que ayudan a crecer a las empresas (más allá de los pagos)
    Cinco razones por las que este ‘smartphone’ es sencillamente tentador
    La cámara de este ‘smartphone’ es pura magia
    Por qué los nuevos coches ya no los diseñarán las personas
    Una catapulta para el talento de ‘kilómetro cero’
    

#### Código de la última sección del diario

Esta es la última sección del **código general** facilitado para esta actividad. Se repiten los mismos pasos o proceso de las secciones anteriores, pero se cambia el nombre de la variable colocando, en este caso que es para la [EPS](https://elpais.com/eps/) `req17`.


```python
req17 = requests.get("https://elpais.com/eps/")
# Si el estatus code no es 200 no se puede leer la página
if (req.status_code != 200):
 raise Exception("No se puede hacer Web Scraping en"+ URL)
soup17 = BeautifulSoup(req17.text, 'html.parser')

tags = soup17.findAll("h2")

for h2 in tags:
    print(h2.text)
    resultados.append(h2.text)
```

    Pietro Beccari: “El desfile de Sevilla es uno de los mejores, si no el mejor, que ha hecho Maria Grazia Chiuri en Dior”
    El golazo literario de Roberto Santiago con ‘Los futbolísimos’
    ¿Dónde está exactamente el origen del mal?
    El hombre que persigue la gaita más antigua del mundo
    La uva más denostada de  Castilla-La Mancha resurge de sus cenizas
    La rebelión de las cocineras de España: “Hay mujeres, falta reconocimiento”
    En busca de la huella de Camarón de la Isla, leyenda viva del flamenco
    Oliviero Toscani: “El fascismo resulta muy cómodo porque no te exige razonar”
    La importancia del respeto para sentirnos bien
    República Dominicana, donde la vida fluye por el río infinito
    El placer de lo rancio y otros gustos y aromas que recuerdan la niñez
    España entra en la ruta del lujo mundial: fiestas, palacios y joyas valoradas en millones de euros
    Así es el barrio de Pekín donde hay “robotaxi” y la compra llega en vehículo sin conductor
    El nuevo Volkswagen Amarok crece y tiene hasta 302 CV
    La palabra médico
    El cuerpo
    Cuento de Catherine del Biombo 5
    Vende menos comer que correr
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
    La casa de Nina Urgell Cloquell, un piso en el que las paredes hablan
    Garbanzos verdes y puchero
    Bikôkô y Julio Peña, dos estrellas en ebullición  
    Cuando Chufy encontró a Rossy: dos amigas, una isla y una colección de moda
    Retrato Robot 
    Ilusiones hipnóticas
    El poder del hormigón
    Maulévrier, Japón a la francesa
    ‘Fantasías en el Prado’, por Alberto García-Alix
    

## Clear

Ahora es momento de emplear el **os.system(clear)**, para que se limpie la pantalla después de hacer el **Web Scrapping**.

## Código de color

Ahora se muestran las **categorías** por las que se van a clasificar los titulares que se han imprimido. 
Primero, se verán por consola las **categorías** por las que se van a clasificar/segmentar los titulares extraídos; para filtrar los titulares por categoría se una un *bucle* `for`; y para finalizar, se verán todos los titulares de la **categoría en concreto**.


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
    El caso de Georgia, en EE UU: becar sin importar la renta agranda la desigualdad
    La escuela concertada ante las desigualdades: el debate pendiente
    El caso de Georgia, en EE UU: becar sin importar la renta agranda la desigualdad
    El caso de Georgia, en EE UU: becar sin importar la renta agranda la desigualdad
    La escuela concertada ante las desigualdades: el debate pendiente
    El caso de Georgia, en EE UU: becar sin importar la renta agranda la desigualdad
    [1m[32mMujeres[0m
    La falta de presupuesto ahoga a los refugios para mujeres víctimas de violencia en México
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    El Panamá indígena busca empoderar a sus mujeres
    El control del cuerpo de las mujeres
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    El deporte se complica para las mujeres trans
    La rebelión de las cocineras de España: “Hay mujeres, falta reconocimiento”
    La rebelión de las cocineras de España: “Hay mujeres, falta reconocimiento”
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    El deporte se complica para las mujeres trans
    [1m[32mMujer[0m
    La falta de presupuesto ahoga a los refugios para mujeres víctimas de violencia en México
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    El Panamá indígena busca empoderar a sus mujeres
    El control del cuerpo de las mujeres
    Un día muy triste para todas las mujeres
    El Supremo de Estados Unidos destruye un derecho fundamental de las mujeres
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    El deporte se complica para las mujeres trans
    Juana Martín, primera mujer española “y gitana” en la alta costura de París, tras su desfile: “Me he dejado la piel”
    La rebelión de las cocineras de España: “Hay mujeres, falta reconocimiento”
    Las actrices de ‘Intimidad’: “Si una mujer no es complaciente en esta profesión, llegan las amenazas”
    La rebelión de las cocineras de España: “Hay mujeres, falta reconocimiento”
    La lesión de Alexia Putellas: las roturas del ligamento cruzado anterior son tres veces más frecuentes en mujeres 
    El deporte se complica para las mujeres trans
    [1m[32mBrecha salarial[0m
    
    [1m[32mMachismo[0m
    
    [1m[32mViolencia[0m
    La falta de presupuesto ahoga a los refugios para mujeres víctimas de violencia en México
    Epidemia de violencia: claves del negocio de las armas en Estados Unidos
    [1m[32mMaltrato[0m
    Cuatro agentes de la Patrulla Fronteriza enfrentarán procesos disciplinarios tras el maltrato a inmigrantes haitianos en Texas
    ‘Sanfermines: maltrato animal en riguroso directo’, por Eva Güimil
    Un juez archiva la causa contra el exmagistrado del Constitucional Fernando Valdés por supuesto maltrato 
    Sanfermines: maltrato animal en riguroso directo
    [1m[32mHomicidio[0m
    
    [1m[32mGénero[0m
    Americanas: Reportajes y noticias sobre feminismo e historias con enfoque de género de la región
    Antonio Guillamón: “La identidad de género no se elige, como prueba el fracaso de las terapias de conversión”
    “La identidad de género no se elige, como prueba el fracaso de las terapias de conversión”
    [1m[32mAsesinato[0m
    Detenido en Brasil el presunto autor intelectual del asesinato de Dom Philips y Bruno Pereira en la Amazonia
    Detenida la esposa del empresario italiano Raphael Tunesi como autora intelectual de su asesinato
    La Fiscalía mexicana reabre el caso por el asesinato del excandidato Colosio
    Haití, sin presidente y sin Estado un año después del asesinato de Jovenel Moïse
    Los principales líderes internacionales condenan el asesinato a tiros de Shinzo Abe
    Detenido en Brasil el presunto autor intelectual del asesinato de Dom Philips y Bruno Pereira en la Amazonia
    El juez cita como imputados a tres exjefes de ETA por el asesinato de Miguel Ángel Blanco
    [1m[32mSexo[0m
    
    

# Comentarios generales de la actividad

Tras haber realizado la actividad, quería hacer algunas anotaciones: 
1. Fue muy **interesante** tratar de descrifrar cada uno de los pasos de los diferentes códigos. 
2. Una **asignación** compleja, pero de la que se aprende algo nuevo. 
3. Al final el print(colored no me imprimió, pero logré hacer la explicación. 
4. Tengo que contarle que por **error borré la actividad** y me tocó hacerla de nuevo.
