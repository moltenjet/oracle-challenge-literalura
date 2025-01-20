# LiterAlura

## Descripción del Proyecto
LiterAlura es una aplicación desarrollada en Java con Spring Boot que interactúa con la API Gutendex para buscar y gestionar información sobre libros. Además, utiliza una base de datos PostgreSQL para almacenar y consultar datos relacionados con libros y autores. Este proyecto ofrece funcionalidades como la búsqueda de libros por título, el listado de todos los libros, la cantidad de libros en un idioma específico, y la identificación de autores vivos en un año determinado.

---

## Características Principales
- **Búsqueda de libros por título**: Realiza consultas a la API Gutendex para encontrar libros según el título proporcionado.
- **Listado de libros**: Muestra todos los libros almacenados en la base de datos.
- **Listado de autores**: Presenta una lista de todos los autores registrados en la base de datos.
- **Autores vivos en un año específico**: Permite consultar autores que estaban vivos en un año indicado por el usuario.
- **Cantidad de libros en un idioma**: Genera estadísticas sobre la cantidad de libros disponibles en un idioma específico.

---

## Requisitos
### Tecnologías y Herramientas Necesarias
- **Java JDK**: 17
- **Maven**: 4
- **Spring Boot**: 3.2.3
- **PostgreSQL**: 16+
- **Dependencias**:
  - Spring Data JPA
  - PostgreSQL Driver
  - Jackson para manejo de JSON

---

## Configuración del Proyecto
1. **Clonar el repositorio**:
   ```bash
   git clone <URL-del-repositorio>
   cd literAlura
   ```

2. **Configurar la base de datos PostgreSQL**:
   - Crear una base de datos llamada `literAlura`.
   - Actualizar el archivo `application.properties` con los detalles de la conexión a la base de datos:
     ```properties
     spring.datasource.url=jdbc:postgresql://localhost:5432/literAlura
     spring.datasource.username=<tu-usuario>
     spring.datasource.password=<tu-contraseña>
     spring.jpa.hibernate.ddl-auto=update
     spring.jpa.show-sql=true
     ```

3. **Ejecutar la aplicación**:
   ```bash
   mvn spring-boot:run
   ```

4. **Interacción con la aplicación**:
   La aplicación presenta un menú interactivo en la consola para realizar las operaciones disponibles.

---

## Estructura del Proyecto
### Principales Componentes
- **Entidades (JPA)**:
  - `Book`: Representa un libro.
  - `Author`: Representa un autor.

- **Repositorios (Spring Data JPA)**:
  - `BookRepository`: Gestor de datos para libros.
  - `AuthorRepository`: Gestor de datos para autores.

- **Lógica Principal**:
  - `LiterAluraApplication`: Contiene la interfaz principal para interactuar con el usuario y las lógicas de negocio.

- **API Gutendex**:
  - Las solicitudes HTTP se realizan a `https://gutendex.com/books/` para buscar información sobre libros.

---

## Uso de las Funcionalidades
1. **Buscar un libro por título**:
   - Ingresa el título de un libro.
   - La aplicación realizará una búsqueda en la API Gutendex y presentará los resultados.

2. **Listar todos los libros**:
   - Muestra todos los libros almacenados en la base de datos PostgreSQL.

3. **Listar autores**:
   - Presenta una lista completa de los autores registrados.

4. **Listar autores vivos en un año específico**:
   - Introduce un año, y la aplicación mostrará los autores que estaban vivos durante ese periodo.

5. **Cantidad de libros en un idioma**:
   - Proporciona un código de idioma (e.g., `en`, `es`) y la aplicación contará los libros correspondientes en la base de datos.

---

## Ejemplo de Interacción
```text
--- LiterAlura Menu ---
1. Buscar libro por título
2. Listar todos los libros
3. Listar autores
4. Listar autores vivos en un año
5. Cantidad de libros en un idioma
6. Salir
Elige una opción: 1

Ingresa el título del libro: Hamlet
Título: Hamlet
Autores: [{"name":"William Shakespeare","birth_year":1564,"death_year":1616}]
Idiomas: ["en"]
---
```

---

## Recursos y Referencias
- **API Gutendex**: [https://gutendex.com/](https://gutendex.com/)
- **Spring Boot Documentation**: [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot)
- **PostgreSQL Documentation**: [https://www.postgresql.org/docs/](https://www.postgresql.org/docs/)
- **Jackson Library**: [https://github.com/FasterXML/jackson](https://github.com/FasterXML/jackson)
