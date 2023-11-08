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

### Pregunta al ChatGpt
Después de **muchos** intentos, la pregunta realizada al ChatGpt fue la siguiente:

> **_Pregunta:_** Hello I am a teacher working  in an area called Graph machine Learning I hae a collection of graphs or networks in GML format and I Want to convert them to the format that uses the Libary PY Torch Geometric of standfors University. This format is a format  that uses the following attributes:

1. Node feature matrix with shape [num_nodes, num_node_features]
2. data.edge_index: Graph connectivity in COO format with shape [2, num_edges] and type torch.long
3. data.edge_attr: Edge feature matrix with shape [num_edges, num_edge_features]
4. data.y: Target to train  (may have arbitrary shape), e.g., node-level targets of shape [num_nodes, *] or graph-level  of shape [1, *]
5. data.pos: Node position matrix with shape [num_nodes, num_dimensions]

### Respuesta del ChatGpt

La respuesta dada por el ChatGpt fue la siguiente:

To convert your GML format graphs into the format required by PyTorch Geometric, which includes the attributes `data.x`, `data.edge_index`, `data.edge_attr`, `data.y`, and `data.pos`, you'll need to follow a specific process for each of these attributes:

1. **data.x (Node Feature Matrix)**:
   - Extract node features from your GML graphs and represent them as a NumPy or PyTorch tensor with shape `[num_nodes, num_node_features]`.
   - Load this tensor into a PyTorch Geometric `Data` object using the `x` attribute.

Here's a simplified example for `data.x`:

```python
import torch
from torch_geometric.data import Data

# Load node features into a tensor (replace this with your GML parsing)
node_features = torch.tensor([[0.1, 0.2, 0.3], [0.4, 0.5, 0.6], ...], dtype=torch.float)

data = Data(x=node_features)
```

2. **data.edge_index (Graph Connectivity)**:
   - Extract the graph connectivity information from your GML graphs. This typically involves specifying which nodes are connected to each other. You can represent this as a NumPy or PyTorch tensor in COO (Coordinate List) format with shape `[2, num_edges]`.
   - Load this tensor into the PyTorch Geometric `Data` object using the `edge_index` attribute.

Here's a simplified example for `data.edge_index`:

```python
import torch
from torch_geometric.data import Data

# Load graph connectivity in COO format (replace this with your GML parsing)
edge_index = torch.tensor([[0, 1, 1, 2], [1, 0, 2, 1]], dtype=torch.long)

data = Data(edge_index=edge_index)
```

3. **data.edge_attr (Edge Feature Matrix)**:
   - Extract edge features from your GML graphs and represent them as a NumPy or PyTorch tensor with shape `[num_edges, num_edge_features]`.
   - Load this tensor into the PyTorch Geometric `Data` object using the `edge_attr` attribute.

Here's a simplified example for `data.edge_attr`:

```python
import torch
from torch_geometric.data import Data

# Load edge features into a tensor (replace this with your GML parsing)
edge_features = torch.tensor([[0.1, 0.2], [0.3, 0.4], ...], dtype=torch.float)

data = Data(edge_attr=edge_features)
```

4. **data.y (Target)**:
   - Extract the target values you want to train against (e.g., node-level or graph-level targets) from your GML graphs and represent them as a NumPy or PyTorch tensor. The shape of this tensor may vary depending on your specific task.
   - Load this tensor into the PyTorch Geometric `Data` object using the `y` attribute.

Here's a simplified example for `data.y` (assuming node-level targets):

```python
import torch
from torch_geometric.data import Data

# Load target values into a tensor (replace this with your GML parsing)
target_values = torch.tensor([0, 1, 0, 2, ...], dtype=torch.long)

data = Data(y=target_values)
```

5. **data.pos (Node Position Matrix)**:
   - Extract node positions (coordinates) from your GML graphs and represent them as a NumPy or PyTorch tensor with shape `[num_nodes, num_dimensions]`.
   - Load this tensor into the PyTorch Geometric `Data` object using the `pos` attribute.

Here's a simplified example for `data.pos`:

```python
import torch
from torch_geometric.data import Data

# Load node positions into a tensor (replace this with your GML parsing)
node_positions = torch.tensor([[x1, y1], [x2, y2], ...], dtype=torch.float)

data = Data(pos=node_positions)
```

Once you've completed these steps for each of the attributes, you can create a PyTorch Geometric `Data` object that represents your graph in the desired format. You can then use these data objects for graph machine learning tasks with PyTorch Geometric.

