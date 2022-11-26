## Origen, Problema y Objetivos

#### Origen

- El espacio de problemas optimizables por AutoGOAL es igual al espacio de problemas descriptibles por el
- No puede describir dependencias contextuales
- restricciones de tipo condicional, recurisivas o opecionales requiere de un alto conocimieto de la herramienta
- Esto provoca que en las ejecuciones del mismo aparezcan instancias invalidas
- las instancias invalidad son un problema cuando generar una muestra conlleva entrenar pipelines

#### Problema

- Herramienta cuyo objetivo principal es describir y generar muestras

#### Critica a AutoGOAL

- se apoya en el tipado dinámico de Python
- las descripciones muestran explicitamente los nombres de los samplers implementados
- dichos samplers determinan las distribuciones iniciales y los mecanismos de muestreo
- las restriciones son descritas de forma imperativa y se checkean despues de la generacion

#### Critica al Estado del Arte

- Solo Optuna puede reolver todos los problemas detectados, pero como mismo lo puede hacer Python
- Poco uso de la recursividad y el algebra de tipo para las descripciones. Como mucho tiene la operacion Union
- No se tienen en cuenta los espacios de dimensiones aleatorias como pueden ser los tensores
- Todo esto motivado en principio xq las herramietas descriptiva del estado del arte siempre tiene un objetivo pricipal (AutoML)
- Pero en general las soluciones de problemas de busqueda hasta hoy ha tenido que implementar su propio sample

#### Objetivos

- Vencer las barreras expresivas del estado del arte (tensores, recursividad, restricciones previas al sampler)
- Que las descripciones sean escalables, declarativas, ....
- Generar muestras coherentes con las descripciones y lo más optimas posibles
- Modularidad entre los conceptos descripcion y generacion

## Lista de Ejemplos

#### Propuesta planteada

- aboga por la sintaxis de tipado estatico de python
- Presenta una interface intermedia entre las descripciones y las implementaciones
- las restricciones se describen de forma declarativa, basadas en el algebra de dominios y se checkean previo a la fase final de la generaciones
- Cuanta con un mecanismo propio para generar muestras
- Dicho componente generador es totalmente configurable

#### Dependencias contextuales

- Declaracion de un elemento cualquiera de un espacio previamente definido
- Filosofia seleccionada para definir el protocol, porque la necesidad del elemento externo
- Dependencias circulares, como las intentamos evitar

#### Sklean

- Muchas bliblotecas de ML y de Python en generar definine una serie de parametros que su
  semantica son condicionales y sencibles a los valores de otros parametros (estudiarme el ejemplo)
- AutoGoal en estos casos explota y eventualmente la distribucion aprende que dichos paramentros son
  los conflictivos

#### Restricciones imperativas

- La gramatica descrita no abarca todas las restricciones necesarias
- Optuna es la propuestas más cercana a los objetivos
- Los dos casos de restricciones de caja negra

#### Grafos con matrix de adyacencia

- Dependencias circulares internas
- Espacios de sequencias

#### Grafos orientado a objetos

- Integracion con typing
- Explotacion de operaciones de alto nivel
- Estado anterior del ejemplo

#### Ejemplos Finales

- comosicion de espacios Orientados a objetos
- Optimizacion con espacio factible lineal
- Optimizacion con espacio factible combinatorio
- AutoML
- Integracion con los patrones herencias de clases y el polimorfismo

#### Implementacion

- Definicion de los tiempos de compilacion y ejecucion del DSL

- Interpretation of the constraint functions as HAGs
- Transformation of HAGs to propagate constraints and solve contextual dependencies
- Definition of a domain algebra
- Definition of a generation context, dependecias circulares, memora jerarquica

#### Resultados

- Coherencia y consitencia, test pasados
- casos basicos, clara y logica diferecia, evidencia la importacia de lo anterior
- dependecias contextuales de unicidad, eficiencia en intentos, no tan efectivo en tiempo
- espacio de caja negra
