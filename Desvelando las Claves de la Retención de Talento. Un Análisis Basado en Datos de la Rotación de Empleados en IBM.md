# Desvelando las Claves de la Retención de Talento: Un Análisis Basado en Datos de la Rotación de Empleados en IBM

Autor: Vicente Figueroa Lemus

## 1. Introducción

Uno de mis principales impulsos como Psicólogo especializado en People Analytics es el de explorar cómo los datos pueden iluminar y optimizar la compleja dinámica de las organizaciones, no por azar ni tampoco de manera desconocida: sino vislumbrando y poniendo luz en las realciones entre personas; buscando relaciones entre factores emocionales y sociales con sus efectos en el desempeño laboral, o en las distintas aristas que envuelven el trabajo (rotación, ausentismo, engagement, horas extras, reducción de costos, licencias, etcétera).

En particular, la gestión del talento y la retención de empleados se han convertido en focos centrales de mi interés profesional. En el competitivo entorno empresarial actual, la capacidad de atraer y, sobre todo, mantener a los empleados valiosos es más crítica que nunca. Los costos asociados a la rotación de personal son significativos y van mucho más allá de los gastos directos de Reclutamiento y Selección y Capacitación. Una alta rotación también implica la pérdida de un conocimiento organizacional, cultural y social valioso, la disminución de la moral del equipo y la interrupción de la cohesión y la productividad del trabajo. De hecho, se estima que el costo de reemplazar a un empleado puede ascender hasta el doble de su salario anual, lo que subraya la importancia de abordar la retención como una prioridad estratégica fundamental para cualquier organización. Identificar los factores que impulsan a los empleados a buscar oportunidades fuera de la empresa es el primer paso crucial para desarrollar e implementar estrategias de retención efectivas.

Para profundizar en estas dinámicas tomé la decisión de hacer un análisis indagatorio con Excel, Power BI y pandas (librería de Python), trabajando con el dataset público de Kaggle "IBM HR Analytics Employee Attrition & Performance". Este conjunto de datos es ampliamente utilizado en la comunidad de People Analytics y ofrece una rica fuente de información para investigar los factores que influyen en la decisión de un empleado de permanecer o abandonar una organización. El propósito fundamental de este artículo es presentar los hallazgos clave derivados de mi análisis exhaustivo de este dataset, con un enfoque específico en desentrañar los factores que tienen un impacto más significativo en la rotación de empleados. Para llevar a cabo este análisis, utilicé Excel como mi principal herramienta, aprovechando su capacidad para el análisis en profundidad y la visualización clara de los resultados. Los gráficos y tablas resultantes de este análisis se han compilado en un informe de visualización completo, accesible a través de un enlace en GitHub. Este proyecto representa una conexión directa con mis aspiraciones profesionales en el campo del Desarrollo Organizacional. Es de manera natural, por tanto, que busque realizar de manera autónoma la mayor cantidad de investigaciones en que, de manera autónoma y experimental pueda poner a pruebas mis atptidudes de análsiis de datos y a través de la experiencia, crecer y aprender. Los profesionales de DO confían en la capacidad de analizar datos para llevar a cabo evaluaciones exhaustivas de las organizaciones, identificar tendencias significativas y, en última instancia, formular recomendaciones basadas en evidencia sólida.

## 2. Comprendiendo el Dataset y el Enfoque Analítico

El dataset "IBM HR Analytics Employee Attrition & Performance" ofrece una visión detallada de diversos aspectos relacionados con los empleados, incluyendo datos demográficos como edad y género, factores intrínsecos al trabajo como el rol, el departamento y el nivel de satisfacción laboral, así como elementos relacionados con la experiencia del empleado como la antigüedad en la empresa, la distancia desde el hogar y la participación en programas de capacitación.El dataset consta de 35 columnas (variables) y más de 1500 filas. Esta riqueza de variables permite un análisis multifacético de los factores que pueden influir en la decisión de un empleado de abandonar la organización. Mi enfoque analítico se centró en la utilización de Excel para llevar a cabo un análisis exhaustivo de estos datos. El proceso comenzó con la limpieza y preparación del dataset, abordando cualquier inconsistencia o valor faltante para asegurar la integridad de los resultados.

*La manera en que lo hice fue la siguiente:*


```
import pandas as pd
df = pd.read_csv("HR_Data.csv")
df = df.drop_duplicates()
df["JobSatisfaction"] = df["JobSatisfaction"].clip(0, 4)  # Corrige valores fuera de rango
```


Posteriormente, realicé un análisis exploratorio de datos para identificar patrones iniciales y posibles relaciones entre las diferentes variables. Un aspecto central de mi análisis fue la identificación de correlaciones entre diversos atributos de los empleados (variables) y la rotación, buscando determinar qué factores mostraban una asociación más fuerte con la probabilidad de que un empleado dejara la empresa.

Para visualizar estos hallazgos clave de manera clara y accesible, utilicé las capacidades de gráficos y tablas dinámicas de Excel, así como también Power BI. El objetivo primordial de este enfoque analítico fue descubrir insights accionables que pudieran proporcionar a las organizaciones una comprensión más profunda de los factores que contribuyen a la rotación de empleados, permitiéndoles así desarrollar estrategias más efectivas para mitigar este fenómeno. El informe completo de visualización, que contiene los gráficos y tablas detallados generados durante este proceso, está disponible en mi repositorio de GitHub. 

## 3. Hallazgos Clave sobre la Rotación de Empleados

##### 3.1 El Impacto de la Satisfacción Laboral:

El análisis de los datos revela una relación clara entre los niveles de satisfacción laboral y las tasas de rotación de empleados. Los empleados que reportaron niveles más bajos de satisfacción con su trabajo mostraron una probabilidad significativamente mayor de dejar la empresa. Este hallazgo es natural y subraya el pensamiento de sentido común de brindar importancia fundamental a la satisfacción laboral como un factor que influye directamente en la decisión de un empleado de permanecer en una organización a largo plazo. Por otro lado, también busqué investigar de manera autónoma qué es lo que dice la literatura al respecto, en este sentido la investigación realizada por McKinsey (2023) también enfatiza la necesidad de que los empleados se sientan valorados en su entorno de trabajo, lo cual está intrínsecamente ligado a su nivel de satisfacción. Existe por lo tanto una fuerte correlación negativa entre la satisfacción laboral y la rotación de empleados. Cuando los empleados no se sienten satisfechos con diversos aspectos de su empleo, como sus responsabilidades, su entorno de trabajo, sus oportunidades de crecimiento o sus relaciones con subalternos, son más propensos a buscar oportunidades en otras organizaciones donde perciban una mayor realización y bienestar. Esta dinámica se alinea con la comprensión general de que la falta de satisfacción laboral es una de las razones más comunes por las que los empleados deciden abandonar sus puestos. En consecuencia, las organizaciones deberían priorizar la implementación de iniciativas concretas destinadas a mejorar dicho aspecto, parte importante de la vida del trabajador. Estas iniciativas podrían incluir la optimización del entorno de trabajo para fomentar la colaboración y el apoyo, la provisión de oportunidades claras y atractivas para el desarrollo profesional y el crecimiento dentro de la empresa.

*Tabla 1: Tasas de Rotación por Nivel de Satisfacción Laboral*

|                               |                     |                                   |                      |
| ----------------------------- | ------------------- | --------------------------------- | -------------------- |
| Nivel de Satisfacción Laboral | Número de Empleados | Número de Empleados que se Fueron | Tasa de Rotación (%) |
| 1                             | 284                 | 65                                | 22.8                 |
| 2                             | 270                 | 45                                | 16.6                 |
| 3                             | 446                 | 74                                | 16.5                 |
| 4                             | 470                 | 53                                | 11.3                 |

##### 3.2 El Rol del Equilibrio entre la Vida Laboral y Personal:

El análisis también reveló una conexión significativa entre la percepción de los empleados sobre el equilibrio entre su vida laboral y personal y sus tasas de rotación. Los empleados que indicaron tener dificultades para lograr un equilibrio saludable entre sus responsabilidades profesionales y personales mostraron una mayor propensión a dejar la empresa. Este hallazgo resalta la creciente importancia que los empleados otorgan a la posibilidad de integrar de manera efectiva sus vidas laborales y personales. En la misma línea, McKinsey también ha señalado que un desequilibrio significativo entre la vida laboral y personal es un factor determinante clave en las decisiones de rotación de empleados (2023). Es por ello que, en base a esta investigación se puede decir de manera conclusiva que el equilibrio entre vida laboral y personal (o mejor dicho, el **desequilibrio** entre la vida laboral y personal) constituye un factor de riesgo considerable para la rotación dentro de una empresa.

Vamos a explicar esto último con los hallazgos de la investigación. Los empleados que sienten que sus demandas laborales invaden de manera excesiva su tiempo personal y familiar son más propensos a experimentar agotamiento y estrés, lo que a su vez puede llevarlos a: 1) buscar oportunidades de empleo que ofrezcan un mejor balance entre su vida personal y laboral 2) tener peor rendimiento dentro de la empresa 3) perder el sentido de su trabajo 4) sentirse frustrados, agobiados, deprimidos y ansiosos.

##### 3.3 La Influencia del Departamento y el Rol del Trabajo:

Un aspecto tremendamente interesante era el de investigar las diferentes tasas de rotación entre diferentes departamentos y roles de trabajo. Estas sospechas interesantes luego se convirtieron en hallazgos valiosos en el sentido de que se entraron variaciones significativas en la tasa de rotación dependiendo tanto del Departamento al que pertenecía el trabajador, como a su Rol de Trabajo y su salario mensual. Por ejemplo, se observó que ciertos departamentos, como Ventas e Investigación y Desarrollo, y roles específicos, como Representante de Ventas y Técnico de Laboratorio, tendían a exhibir tasas de rotación más elevadas en comparación con otros segmentos de la organización. Este hallazgo subraya que la rotación de empleados no es un fenómeno uniforme que afecte a toda la empresa por igual, sino que puede concentrarse en áreas o roles particulares.

En este sentido, comprender qué áreas específicas del negocio están experimentando una mayor pérdida de empleados es crucial para enfocar los esfuerzos de retención de manera efectiva, dirigiendo los recursos y las intervenciones donde es más necesario y su impacto sea mayor. Las razones detrás de estas diferencias en las tasas de rotación podrían estar relacionadas con desafíos o factores estresantes específicos inherentes a ciertos roles o departamentos. Por ejemplo, los roles de ventas a menudo implican altas presiones y objetivos exigentes, lo que podría contribuir a una mayor rotación. De manera similar, ciertos departamentos podrían tener culturas laborales o dinámicas de equipo que influyen en la satisfacción y, por ende, en la retención de sus empleados. En consecuencia, se recomienda que las empresas desarrollen iniciativas de retención personalizadas y adaptadas a los departamentos y roles de trabajo que muestran tasas de rotación más altas. Este enfoque específico puede resultar más efectivo que la implementación de estrategias genéricas de retención a nivel organizacional.

El punto más importante en relación a este apartado es el de no tratar las estrategias de onboarding, vida del colaborador y retención de manera uniforme, simplista y reduccionista. Es importante buscar los datos más interesantes, hacer las correlaciones más apropiadas y en base a estas sacar las conclusiones que sean más pertinentes y agudas. Si se detecta un departamento con una tasa de rotación significativamente más alta que las demás entonces investigar. Es decir, hacer entrevistas, preguntas, análisis de cultura, de clima, de compensaciones, de tareas, etc. y en base a esto diseñar estrategias personalizadas para paliar las carencias existentes. Ser agudo y estratégico.

*Tabla 2: Tasas de Rotación por Departamento*

|                            |                     |                                   |                      |
| -------------------------- | ------------------- | --------------------------------- | -------------------- |
| Departamento               | Número de Empleados | Número de Empleados que se Fueron | Tasa de Rotación (%) |
| Investigación y Desarrollo | 961                 | 133                               | 13.8                 |
| Ventas                     | 446                 | 92                                | 20.6                 |
| Recursos Humanos           | 63                  | 12                                | 19.0                 |

##### 3.4 El Impacto de la Antigüedad y la Experiencia:

El análisis de la relación entre la antigüedad del empleado (los años totales de trabajo dentro de la empresa) y la rotación reveló patrones interesantes. Se observó que las tasas de rotación tienden a ser más altas entre los empleados que tienen una menor antigüedad en la organización o que se encuentran en etapas iniciales de sus carreras profesionales. De hecho, la rotación durante el primer año de empleo es particularmente elevada. Este hallazgo sugiere que los empleados que son relativamente nuevos en la empresa pueden ser más propensos a abandonar si sus expectativas iniciales no se cumplen o si no perciben un camino claro hacia el crecimiento y el desarrollo profesional dentro de la organización. En la misma línea, McKinsey & Company (2023) también ha destacado que las oportunidades de desarrollo profesional tienen un impacto significativo en la retención de los empleados. En consecuencia, las organizaciones deberían prestar especial atención a la creación de programas de incorporación que ayuden (de verdad) a los nuevos empleados a integrarse a la cultura de la empresa, comprender sus roles y responsabilidades, y establecer expectativas realistas sobre su futuro dentro de la empresa. En la misma línea e incluso aún más sensible: es crucial proporcionar vías claras y accesibles para el desarrollo profesional, incluyendo oportunidades de capacitación, mentoría y avance dentro de la empresa. 

Al invertir en el crecimiento de sus empleados, las organizaciones pueden mejorar significativamente la retención, especialmente entre aquellos que se encuentran al comienzo de sus carreras.

##### 3.5 Otros Factores Contribuyentes:

Por último, mencionar otros factores de suma importancia que no fueron mencionados en ninguno de los apartados anteriores. Por ejemplo, se encontró una correlación entre un ingreso mensual promedio más bajo y tasas de rotación más altas. Esto subraya la importancia de una compensación competitiva como un factor clave para retener el talento. Los empleados que sienten que no están siendo compensados de manera justa por su trabajo son más propensos a buscar oportunidades en otras organizaciones que ofrezcan mejores beneficios, especialmente salariales.

Otros factores, como la distancia desde el hogar, la frecuencia de los viajes de negocios y los tiempos dedicados a la capacitación también mostraron influencia en las tasas de rotación. Estos hallazgos sugieren que la decisión de un empleado de irse de una empresa suele estar influenciada por múltiples factores, todos relacionados al trabajo ya sea de manera intrínseca como extrínseca. Es por ello que, para abordarlos de manera efectiva, las empresas deben adoptar una estrategia y visión holística de la experiencia del empleado, considerado una larga variedad de factores determinantes. En este sentido, un enfoque integral para la retención de empleados debería incluir estrategias que aborden la satisfacción laboral, el equilibrio entre la vida laboral y personal, las oportunidades de desarrollo profesional, las compensaciones, etc.
## 4. Conectando los Hallazgos con el Desarrollo Organizacional

Los hallazgos derivados de este análisis de la rotación de empleados en IBM poseen una conexión y relevancia directa para el campo del Desarrollo Organizacional. La comprensión detallada del "quién, cuándo y por qué" de la rotación de empleados proporciona una base sólida para informar las intervenciones de DO diseñadas para fortalecer la retención de talento y promover una salud organizacional más robusta. Estos hallazgos pueden ser utilizados estratégicamente para desarrollar iniciativas específicas destinadas a aumentar el compromiso de los empleados, abordando directamente los factores que se han identificado como impulsores de la rotación. Además, la información obtenida de este análisis puede guiar el diseño y el perfeccionamiento de programas de incorporación y capacitación más efectivos, asegurando que los nuevos empleados se integren exitosamente a la organización y estén involucrados y con un sentido claro desde el inicio. Es relevante mencionar la posibilidad de mejora en los procesos de gestión del desempeño y la implementación de sistemas de retroalimentación más constructivos y regulares, los cuales pueden beneficiarse de estos 'insights', contribuyendo a un mayor sentido de reconocimiento y desarrollo entre los empleados.

Fomentar un entorno de trabajo que se perciba de manera positiva y de apoyo es otro objetivo clave del DO que se alinea directamente con la reducción de la rotación, ya que los empleados que se sienten valorados y respaldados son menos propensos a buscar empleo en otro lugar.

En esencia, este análisis subraya el papel fundamental de la toma de decisiones basada en datos para lograr un desarrollo organizacional más efectivo. Las habilidades en el análisis de datos se han convertido en una competencia central para los profesionales de DO, otorgándoles la capacidad de diagnosticar con precisión los problemas organizacionales y de medir el impacto real de las intervenciones implementadas. Esto es debido a que al comprender a fondo los datos que subyacen a la rotación de los empleados, los profesionales de DO pueden desarrollar soluciones más específicas y efectivas, lo que a su vez conduce a una mejora tanto en la retención de talento como en el rendimiento general de la empresa.

## 5. Conclusión
#### Un Compromiso con la Gestión del Talento Basada en Datos

En resumen, el análisis realizado ha revelado varios factores clave que influyen significativamente en la decisión de un empleado de abandonar una organización. Entre estos, la satisfacción laboral y el equilibrio entre la vida laboral y personal emergen como impulsores críticos, con una fuerte correlación negativa con las tasas de rotación. Además, se observaron variaciones importantes en la rotación entre diferentes departamentos y roles de trabajo, lo que sugiere la necesidad de estrategias de retención más específicas y personalizadas. Por otro lado, la antigüedad y la experiencia del empleado también juegan un papel importante, con tasas de rotación potencialmente más altas entre los empleados más nuevos y entre aquellos que no perciben oportunidades de crecimiento dentro de la empresa.

Finalmente, otros factores como la compensación, la distancia desde el hogar y los viajes de negocios también mostraron un efecto en la decisión de dejar una organización. Este análisis subraya el valor intrínseco de utilizar el análisis de datos para obtener una comprensión profunda de desafíos organizacionales complejos como la rotación de empleados. Como Analista de People debo ser honesto y decir que cada investigación y proyecto significan una oportunidad de aprender algo nuevo, de crecer, actuar de manera autónoma y formarme como profesional. Dejar el trabajo apostillado y crecer por cuenta propia.

*Tabla 3: Principales Factores Determinantes de la Rotación de Empleados (Resumen)*

|                                  |                                                                            |                                                                                                                                                       |
| -------------------------------- | -------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Factor Determinante              | Insight Clave                                                              | Posible Intervención de DO                                                                                                                            |
| Satisfacción Laboral             | Menor satisfacción se asocia con mayor rotación.                           | Implementar encuestas de satisfacción, abordar áreas de mejora, mejorar el entorno laboral y las oportunidades de crecimiento.                        |
| Equilibrio Vida Laboral/Personal | Desequilibrio se asocia con mayor rotación.                                | Promover políticas de trabajo flexible, asegurar cargas de trabajo manejables, fomentar una cultura que respete el tiempo personal.                   |
| Departamento/Rol del Trabajo     | Tasas de rotación varían significativamente entre departamentos y roles.   | Desarrollar iniciativas de retención personalizadas para departamentos y roles con altas tasas de rotación, abordando sus necesidades específicas.    |
| Antigüedad/Experiencia           | Mayor rotación al inicio de la carrera o sin oportunidades de crecimiento. | Enfocarse en programas de incorporación efectivos, proporcionar vías claras de desarrollo profesional y oportunidades de avance dentro de la empresa. |
| Compensación                     | Ingresos más bajos pueden correlacionarse con mayor rotación.              | Revisar y comparar la compensación con los estándares del mercado, asegurar una remuneración justa y competitiva para retener el talento valioso.     |

Anexo:

https://www.mckinsey.com/capabilities/people-and-organizational-performance/how-we-help-clients?source=post_page-----78989e52c31b---------------------------------------

https://www.mckinsey.com/featured-insights/mckinsey-explainers/what-is-talent-management?source=post_page-----78989e52c31b---------------------------------------

https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/five-fifty-the-data-talent-link?source=post_page-----78989e52c31b---------------------------------------

https://www.mckinsey.com/capabilities/quantumblack/our-insights/using-people-analytics-to-drive-business-performance-a-case-study?source=post_page-----78989e52c31b---------------------------------------#/

https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset?source=post_page-----78989e52c31b---------------------------------------

https://github.com/vifigueroalemus/IBM-HR-Analytics-Employee-Attrition-Case-Study/blob/main/IBM%20HR%20Analytics%20Project.%20Visualizations.pdf

