## Estructura de los buckets asociados a componente (Ciclo Vida de Datos)

En el siguiente arbol se representan la estructura de directorios y archivos asociados al ciclo de vida de los datos con los buckets de XXXX del componente de entrenamiento. Nota: El minimo producto viable del proyecto de XXXX se valido con los archivos de datalab proveidos:

- [raw/train/]() => En este directorio se encuentran subdividido los datos de entrenamiento de datalab de emplooyees y events.

- [stage/minable-view/]() => En este directorio se encuentran los archivos de X.pkl (caracteristicas codificadas para los modelos de entrenamiento) y y.pkl (valores de Y para el entrenamiento) 
que sirven como vista minable para el componente de entrenamiento

- [analytics/model]() => En este directorio se encuentra los resultados de los modelos de acuerdo a la fecha en que se haga ejecutado el componente de entrenamiento en la instancia de EC2 (t2.micro)
denominada cuidadovida-training

```
.
├──raw/
│   └── train/
│       ├── employees/
│       └── events/

└──stage/
    └── minable-view/
        └── model/
            └── train/
                ├── X.pkl
                └── y.pkl

├──analytics/
│   └── model/
│       └── dt-yyyy-mm-dd/
│           ├── model_yyyy-mm-dd.pkl
│           └── variables.pkl

```
