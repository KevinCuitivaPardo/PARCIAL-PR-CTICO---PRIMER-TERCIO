# DOSW-ParcialT1
**Estudiante:** KEVIN CUITIVA PARDO

## Compilar y ejecutar

### Compilar el proyecto
```
mvnw.cmd clean install
```

### Ejecutar la aplicación
```
mvnw.cmd spring-boot:run
```
### Ejecutar tests
```
 mvnw.cmd test
```

## Estructura del proyecto

```
DOSW-ParcialT1
|-- pom.xml
|-- src
|   |-- main
|   |   |-- java
|   |       |-- edu/dosw/parcial/App.java
|-- test
|   |-- java
|       |-- edu/dosw/parcial/AppTest.java
|-- docs/
|   |-- uml/          # Diagramas UML exportados en PDF o PNG
|   |-- images/       # Capturas de ejecución
|   |-- requirements/ # Requisitos funcionales y no funcionales
|-- .gitignore
|-- README.md
```

## PARTE PARCIAL TEORICO 
### PRIMERA PUNTO ( diagrama de contexto ):
<img width="1333" height="590" alt="image" src="https://github.com/user-attachments/assets/23ad45bd-568f-4592-a34b-b1c2e45ad1ed" />

- Desarrollo primer punto del parcial, generalidades del sistema (Resalto puntos importantes a tener en cuenta para entender el sistema y el uso de otros externos, tambien agrego usuarios que pueden usar el sistema y se hace entender que dependiendo las reglas cada uno tiene algunas restricciones de uso del sistema, aparte de esas restricciones tienes REGLAS de horarios, espacios y tiempos.

### SEGUNDO PUNTO ( patrones ):

- FACTORY (Creacional) : Este es bastante util para las reservas ya que a la hora del desarollo podemos evitar varias condicionales y codigo que tal vez no sea tan "eficiente" Cuando alicamos este metodo podemos hacer uso de los tipos de reserva que hay (Salones de clase, Oficinas, Salon de estudio y equipos de computo) sin hacer uso de condicionales como if para ingresar a cada uno, aparte de eso pues se pude hacer la creacionde diferentes metodos en cada uno o re usar los que se necesitan por ejemplo las personas que lo usan, tambien se puede definir tiempos de uso, cantidad de personas que van a hacer uso del espacio o equipo.

- Aapter (Estructura) :  Este nos ayudara a definir como necesita nuestro sistema su entrada de datos, este sera un intermedio entre enlace - silabinfo y recursoshumanos -silabinfo, ya que nosotros podriamos traer la informacion que necesitamos de estos sistemas pero filtrarla por este patron para el correcto funcionamiento de nuestro sistema. Por ejemplo si necesitara yo id, nombre, correo de un profesor podriamos traer la base de datos de alla, buscar la tabla profesor, que claro esta tendra mas info, lo que haremos es filtrar esta info y dejar solo la que resive nuestr sistema. Tambien es bueno si en algun momento necesitamos hacer uso de alguna funcion nueva, tal vez necesitemos mas informacion de la materia en el caso de enlace, o los horarios de atencion del profe en caso de recursos humanos.


