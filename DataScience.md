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
