# Especificaciones del Proyecto: Registro de Productos

Este documento recopila los requerimientos y restricciones establecidos para el desarrollo de la aplicación web de inventario, basado en las instrucciones de la evaluación "Segunda parcial".

## 1. Interfaz de Usuario (UI)
La aplicación debe contar con un formulario de captura con los siguientes elementos:
*   **Campos de entrada:**
    *   `No. de inventario`: Campo numérico.
    *   `Descripción`: Campo de texto.
    *   `Departamento`: Botones de opción (Radio buttons) con las opciones **Frutas**, **Verduras** y **Lácteos**.
*   **Botones de acción principal:**
    *   `Guardar datos`
    *   `Lista completa`
    *   `Lista de frutas`
    *   `Lista de verduras`
    *   `Lista de lácteos`
*   **Visualización de datos:**
    *   Una tabla que muestre las columnas: *No. Inventario*, *Descripción* y *Departamento*.
    *   Un botón `Cerrar lista` ubicado debajo de la tabla.

## 2. Requerimientos Funcionales
El objetivo de la aplicación es almacenar en memoria un inventario de productos. Las acciones de los botones son las siguientes:

*   **Guardar datos:** Almacena en memoria los datos capturados por el usuario y limpia los campos del formulario para permitir la captura de un nuevo producto.
    *   *Regla de negocio:* El **Número de inventario debe ser único**; el sistema debe validar que no se repita con un registro existente.
*   **Lista completa:** Muestra en la tabla el listado total de los productos que se encuentran almacenados en la memoria.
*   **Listas filtradas (Frutas, Verduras, Lácteos):** Al hacer clic en cualquiera de estos botones, la tabla solo debe mostrar los productos que pertenecen al departamento correspondiente.
*   **Cerrar lista:** Oculta la tabla y quita el listado de productos de la pantalla.

## 3. Restricciones Técnicas
El código fuente debe cumplir estrictamente con los siguientes lineamientos de programación:

*   **Tecnología:** C# y HTML (Componente Razor de Blazor).
*   **Ruta de la página:** Debe incluir la directiva `@page "/Registro_productos"` al inicio del archivo.
*   **Cero Clases u Objetos Personalizados:** **No** se permite la creación de clases (POCOs), `structs` o registros (`records`) para representar un "Producto".
*   **Almacenamiento:** Los datos deben guardarse utilizando estructuras de datos básicas de C#, específicamente `List<T>` paralelas (una lista para los IDs, otra para descripciones, otra para departamentos).
*   **Estructuras de control:** El código debe implementar obligatoriamente los siguientes ciclos:
    *   Ciclo `while` (utilizado para la validación de números de inventario únicos).
    *   Ciclo `for` (utilizado para recorrer las listas y construir las tablas, tanto generales como filtradas).
    *   Ciclo `foreach` (utilizado en la vista HTML para renderizar las filas de la tabla).

## 4. Escala de Calificación (Rúbrica)
*   **5 puntos:** Interfaz de usuario completa.
*   **2 puntos:** Botón "Guardar datos" funcionando correctamente (incluyendo la validación de que el número de inventario no se repita).
*   **2 puntos:** Botón "Lista completa" funcionando correctamente.
*   **1 punto:** Botones de listas por departamentos ("Lista de frutas", "Lista de verduras", "Lista de lácteos") funcionando correctamente.