# ProyFinalPromptEngineering
Proyecto Final Curso Prompt Engineering 2023-2 Profesor Juan Carlos Correa

### Objetivo

Describir el trabajo realizado a lo largo del curso con las herramientas GitHub y ChatGpt.

### Proyecto Personal

El Proyecto que estoy desarrollando actualmente tiene que ver con el tema de Graph Machine Learning
en este momento se tienen dos objetivos concretos: 

1. Dictar en el semestre 2024-2 Un curso de [Graph machine Learning](https://distill.pub/2021/gnn-intro/) de manera conjunta con profsores de la Universidad Nacional
2. Escribir un libro de [Ciencia de Redes](https://github.com/jamelende/LibroCienciaDeRedes) donde uno de sus capítulos (Capítulo 8) es  sobre Graph Machine Learning.

### Actividades a lo largo del curso (GitHub)

Las actividades que se desarrollaron en el curso como apoyo al desarrollo del proyecto fueron las siguientes:

1. Creación de una [Página Web](http://profesores.is.escuelaing.edu.co/~amelendez/GraphMachineLearning/P%C3%A1ginaWebGraphMachineLearning2023-2.html) que contiene el estado del arte al igual que  diferentes recursos y enlaces del tema de Graph Machine Learning.
2. Desarrollo completo de un ejemplo de detección de comunidades en la [Red Karate](https://networkrepository.com/soc-karate.php), usando Graph machine Learning, en particular el método de node embedding llamado [node2Vec](https://towardsdatascience.com/node2vec-explained-db86a319e9ab).
Este ejemplo se encuentra como un repositorio de GitHUb, el enlace es: [GML](https://github.com/alfonsomelendez/Graph-Machine-Learning)

#### (Nota el ejemplo se encuentra en los archivos Explanation1.md a Explanation5.md )
   
### Actividad final ChatGPT

Como Actividad final se propuso usar el ChatGpt haciendo consultas de la forma más detallada posible con el objetivo de obtener un apoyo en la generación de código Python para el Proyecto Personal.
En este caso se realizó la interacción con ChatGpt con el objetivo de :

1. Construir un algoritmo para convertir archivos de redes o grafos en formato GML, al formato usado por la librería PYG (Py Torch Geometric) de la Universidad  de Stanford con el fin de usar estos archivos en procesos de Graph Machine Learning como:
      a. Predicción de nodos en una red
      b. Predicción de enalces en una red.

Después de varios intentos, la pregunta realizada al ChatGpt fue la siguiente:

> **_Pregunta:_** Hello I am a teacher working  in an area called Graph machine Learning I hae a collection of graphs or networks in GML format and I Want to convert them to the format that uses the Libary PY Torch Geometric of standfors University. This format is a format  that uses the following attributes:

> **_Pregunta:_**data.x: Node feature matrix with shape [num_nodes, num_node_features]
 data.edge_index: Graph connectivity in COO format with shape [2, num_edges] and type torch.long
 data.edge_attr: Edge feature matrix with shape [num_edges, num_edge_features]
data.y: Target to train against (may have arbitrary shape), e.g., node-level targets of shape [num_nodes, *] or graph-level targets of shape [1, *]
data.pos: Node position matrix with shape [num_nodes, num_dimensions]

