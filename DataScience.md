# Data Science

Esos son los aputes básicos sobre que es Data Science, que roles existen, cómo es el flujo de trabajo, etc.

Las notas fueron tomadas desde un ciclo de charlas dictadas por Diego Vallarino, este ciclo se llamo "Coffe & Data Science".

## En que usa el tiempo el científico de datos

El input son los DATOS

**1. Trabajo puro de tratamientos de datos (70%)**

- ETL (extract, transform and load)
- Database (familiarizarse con los datos, dibujarlos, primeros KPIs)

**2. Trabajo de análisis (30%)**

- Análisis (relación entre variables, tendencias, modelos)
- visualización (jugar con visualizaciones para presentar a otras personas)

El output son los INSIGHTS

## ¿Qué perfiles existen en Data Science?

**1. Data Scientist**

- Sabe de matematicas, programación y comunicación
- Generalmente utiliza SQL, Python y R

**2. Data Engineer**

- Sabe de programación, matematicas y big data
- Utiliza Hadoop, NoSQL y Python
- Se encarga de que las fuentes de datos sean confiables
- Se encarga de que la extracción de datos pueda ser reproducible o programable
- Limpia los datos
- Reduce el riesgo de errores en los datos

**3. Data Analysts**

- Sabe de estadistica, comunicación y conocimiento del negocio
- Utiliza Excel, Tableau y SQL
- Se enfoca en hacer análisis que estan muy ligados al negocio
- Tiene la capacidad de hacer queries básicas en bases de datos

Entre ellos se complementan, el Engineer se encarga de que los datos sean confiables y crea procesos para tenerlos disponibles. El Scientist limpia los datos, los procesa y los cura. El Analysts entiende el negocio para explotar los datos.

En el mercado hay personas de diferentes carreras trabajando con datos, principalmente de ingenieria y economia, pero también de biología, quimica, comunicación, etc.

Es importante saber trabajar con datos, pero también entender como se comportan las personas a traves de los datos, por eso los economistas son perfiles muy interesantes.

**¿Qué tiene que saber un gerente de area de datos?**

- Crear equipos de data scientist que se complementen
- Coordinar y seleccionar a los mejores talentos
- Definir los objetivos y prioridades del equipo
- Conocer las tecnologías disponibles
- Entender cual es el problema a resolver, para poner a las personas correctas. Esto es importante ya que se pueden tener roles muy diferentes, desde ingenieros hasta sociologos

**¿Qué hay que estudiar para trabajar en cada perfil?**

**1. Data Scientist**

- Matematicas
- Computer Science

**2. Data Engineer**

- Computer Science
- Ingenieria

**3. Data Analysts**

- Economia
- Finanzas
- Matematicas
- Entender el negocio

**4. Head of Data**

- MBA
- Finance

## ¿Cuál es el objetivo de un Data Science?

Transformar los datos en insights que generen impactos en el problema que se quiere resolver. Por ejemplo: ganar más dinero, ahorrar costos, incrementar productividad, etc.

## ¿Cuales son las industrias que usan más los datos?

Hay casos en todas las industrias, pero la clave es elegir empresas que manejen una gran cantidad de datos, pueden ir desde:

- Finanzas
- Turismo
- Retail
- E-comerce
- Apuestas
- Salud

Generalmente se buscan hacer predicciones.

## ¿Un framework como Data Scientist?

Lo primero es entender en que estado esta en la empresa en cuanto a como utiliza los datos.

1. Reporteria operacional, la clásica reporteria contable o financiera donde hay información básica
2. Reportería KPIs, no solo se saben las ventas, sino que ventas por territorio o empleado por ejemplo
3. Exploración y visualización de datos. No solamente se indentifica lo que pasó sino que tambien se empiezan a visualizar y comparar diferentes KPIs
4. Segmentación, es cuando se empieza a trabajar con la segmentación inteligente. Por ejemplo una persona que formo una familia y tiene un buen salario es propensa a comprar un auto. Se segmenta por comportamientos, no por edad por ejemplo
5. Modelos predictivos, todo lo que vimos hasta la 4 son comportamientos pasados o que sicedieron, siempre se mira hacia atrás. A partir de acá podemos empezar a entender modelos predictivos, osea no solo entender quien me compró sino quien me va a comprar
6. Analytics cognitivos / Machine learning, esto son modelos dinámicos, la diferencia con el 5 es que los modelos de la 5 son estaticos. En machine learning los modelos son dinámicos, es decir a medidas que se usan el modelo aprende o "se entrena". A medida que tiene mas datos el algoritmo va ajustando los parametros automaticamente para llegar a mejores resultados

`Data + Analytics + Technology = Soluciones`

### Data

- Bases de datos propias
- Bases de datos diferenciadas
- Bases de datos alternativas

### Analytics

- Descriptiva, ¿que pasó?
- Diagnostico, ¿porque pasó?
- Predictiva, ¿qué es lo que va a pasar?
- Prescriptiva, ¿qué es lo que debería hacer? Por ej un algoritmo que toma la desición si dar un crédito o no a un cliente

### Technology

- Python
- R
- Data Studio

`Value = 4D + 3E`

## Cómo diseñar y seleccionar la data

Lo primero es entender cual es el problema a resolver, entender la necesidad de negocio. Entender la industria es fundamental.

### Tipos de problemas comunes

Comercial:

- Segmentación
- Originación
- Retención
- Pricing

Caracteristicas:

- Behavioral Science
- Estructura de incentivos
- Creación de valor

### Design

El diseño de las soluciones para estos problemas es la primera D, el Design.

### Data

Son todos los datos que tenemos para analizar el problema o generar predicciones. Sacamos datos desde doferentes fuentes. Tener muchos datos no significa que tenemos mejores soluciones, a veces los datos generan mucho ruido que nos hace pasar mucho tiempo limpiando y terminamos con pocas variables para los modelos.

**Esta bueno tener data pero hay que tener la data correcta y que genere valor para el problema que se quiere solucionar. Esta es la segunda D.**

### Develop

Es quizas la parte más conocida o entretenido, el desarrollo de los algoritmos. Se utiliza data analytics junto a machine learning. Es la tercera D.

#### Descriptivos

Hay algoritmos del tipo descriptivo, como por ejemplo:

- Procesamiento de carteras de cliente
- Text analytics
- Análisis de sentimientos

#### Predictivos

Hay algoritmos del tipo predictivo, como por ejemplo:

- Scoring de riesgo
- Score de churn
- Score recomendation

-----------------------------------

## 1. ¿Cómo visualizamos?

Se pueden utilizar las siguientes herramientas:

- Tableau, para análitica descriptiva, desarrollo de dashboards, etc
- Power BI, parecido a Tableau, mejor integrada a Excel, para análitica descriptiva
- Python y sus librerías para visualizar datos

## 2. ¿Cómo modelamos?

Como se pueden usar algoritmos para modelar. Hay dos grandes grupos de algoritmos de machine learning:

### No supervisado

En estos algoritmos no se tienen las variables de respuesta a partir de un input, no sabemos como se va a comportar la persona con determinado input, a diferencia del supervisado.

#### Clustering

Uno de los principales modelos de este tipo de algoritmos es la `Clustering` o clasterisación. Se trata de poder segmentar en función de patrones comunes. Por ejemplo, lograr algutinar en una función patrones de compra.

Por ej:

- Todas estas personas van a entrenar demañana
- Todas estas personas van a la facultad

Dependiendo de la cantidad de variables algutinadas que tenemos intentamos segmentar para predecir comportamientos.

Es importante tener variables historicas pero tambien un pequeño a futuro. Eso hace que tengamos un cluster con una lógica de propensión.

- kMeans, kmedoids, Fruzzy C-Means
- Hierachical
- Gaussian mixture
- Neural networks
- Hidden markov model

### Supervisado

Generalmente se usan para predecir a traves de modelos, dónde hay input data y output data. Son los mas comunes.

Por ej:

- Si una persona quiere comprar
- Si una persona va a pagar
- Si una persona quiere ir a x lugar

Para predecir esto se tiene una enorme cantidad de datas con variables como por ejemplo: personas de tal edad, tal sexo, que compraron x cosa, que viajaron a x lugar.

*Existen dos grandes tipos:*

#### A. Clasificación

El objetivo es poder predecir el comportamiento de una variable Dicotomica(si o no) o Categórica(hugo, paco, luís).

- Support Vector Machines
- Discriminant Analytics
- Naive Bayes
- Neareset Neighbor

#### B. Regresión

El objetivo es poder predecir el comportamiento de una variable Continua. El precio de un producto.

- Linear regression GLM
- SVR, GPR
- Ensemble methods
- Decision trees
- Neural networks

### ¿Cómo elegir cual usar?

Dependiendo del problema que queramos resolver es el tipo de algoritmos o el conjunto de algoritmos a utilizar.

Si en google ponemos "Machine Learning Algorithm Cheat Sheet" seguro salen gráficos que nos ayudan en la elección de estos algoritmos.

Por ejemplo Microsoft Azure tiene uno muy bueno.

Se puede usar:

- Algoritmos en la nube (Azuro, AWS, Google)
- Python

Generalmente se ponen a competir a 3 o 4 algoritmos para ver cual performa mejor y da mejores predicciones.

Para eso se suele separar la data en **70% para entrenamiento** y **30% para las pruebas de performance**.

Los algoritmos o metodos de machine leargning más utilizados en el 2018-2019 son:

- Regresion 56%
- Decision Trees / Rules 48%
- Clustering 47%
- Visualization 46%
- Random Forests 45%
- Statics Descriptive 39%
- K-Nearest Neighbours 33%
- Time series 32%
- Ensemble methods 30%
- Text mining 28%
- PCA 28%
- Boosting 27%
- Neural Networks 25%

### Delivery

Corresponde a la cuarta D. Por ejemplo corresponde a cuando aparece una publicidad en Twitter recomendando algo a partir de las busquedas del usuario, sus comportamientos, etc.

### 4D x 3E

- Design
- Data
- Develop
- Delivery

- Easy to implement
- Easy to use
- Easy to revenue

## Economía de la Información, del Comportamiento, y Data Science

Por ejemplo sirve para responder preguntas como: ¿cuanto cobrar el pop en el cine?, ¿qué tiene que ver 3 premios nobel con el precio de la cerveza artesanal?

Esta parte se trata de ver como mezclar la economia con la big data.

### Asimetría de la información

Se da ca cuando una de las partes, en un contrato, tiene mas/menos información sobre un bien.

### Selección adversa

El proceso por el cual dada una asimetría de información, la selección no es correcta.

### Riesgo moral

Aquellas situaciones en las que un individuo tiene información asimetrica acerca de las consecuencias de sus propias acciones.

-----------------------------------

Con el análisis de datos, podemos tomar la desición con más información, disminuyendo la asimetría de información reduciendo el riesgo a caer en una selección adversa.

### Behavioral economics

Es la rama de la economía que estudia como las personas toman desiciones, utilizando la psicología y la neurociencia.

El concepto de behavioral economics es muy importante para analizar mejor los datos y entender que sesgos tienen las personas y poder influir en ellos.

Hay dos grandes enfoques en el Behavioral economics:

1. Entender los sesgos
2. Crear incentivos para mover a las personas a dónde queremos

#### Curva de utilidad y preferencias

Los conjuntos de puntos en el espacio de combinaciones de bienes para los que la satisfacción del consumidor es idéntica.

No todos los productos son lo mismo, por ej 3 cafe pueden diferir en: experiencia de consumo, precio, etc.

#### Bienes inferiores y bienes superiores

El inferior es aquel cuya demanda aumenta a medida que la renta decrece.

El superior es aquel que cuando aumenta su precio aumenta su demanda, ya que se considera un bien exclusivo.

Se puede convertir un bien inferior en uno superior a traves de los datos.

#### Disposición a pagar 

Cantidad máxima que pagaría un cliente por un producto.

#### Costo de oportunidad

Es el costo de la alternativa a la que renunciamos cuando tomamos una determinada desición, incluyendo los beneficios que podríamos haber obtenido de haber escogido la opción alternativa.

#### Irracionalidad

Las personas en el corto plazo toman desiciones no racionales.

### Caso Netflix

Netflix es una empresa basada en datos que toman una cantidad de información para mantener a las personas mirando series.

Se dice que las maratones de series generar dopamina. Llegaron a esa conclusión analizando los datos, dandose cuenta que la gente prefiere ver las series de corrido, preferiblemente los fines de semana.

Netflix mirando como la gente mira la series, decide como lanzar las series. Generalmente lanzan las series los viernes, para que las personas las miren en forma de maratón.

Esto es un comportamiento irracional de los usuarios, que por la generación de dopamina, mantiene a las personas enchufadas todo el fin de semana mirando una serie.

¿Qué hay detrás de la dopamina? Irracionalidad, incentivos y hábitos.

### Hook canvas

Es un canvas que demuestra como se puede pasar desde lo emocional a los hábitos. Se puede buscar en google y verlo visualmente.

1. Disparador (extrenos: llamada, mail, publicidad, tweet, etc) (internos: hábitos, emociones, aburrimiento, etc)
2. Acción que genera recompensa (scroll, buscar en google, ver videos)
3. Recompenza (de tribu, de cazador, de yo)
4. Inversión (de tiempo, de dinero, de recuerdos)

Esta rueda termina generando un hábito o un vicio. Con los datos se pueden armar este tipo de ruedas.

Este canvas se puede aplicar para diferentes comportamientos para entender un poco como funciona el mecanismo. Por ejemplo: para entender a los juagdores de fornaite, a las personas que miran maratones de series, a los compradores compulsivos, etc.


