# 🕵️‍♂️ Informe: Detectives de Código  
### Proyecto Analizado: [mdn/todo-react](https://github.com/mdn/todo-react)
### Nombre: Sebastián Ramos
---

## 📘 Introducción

En el presente informe se analiza el repositorio público **“todo-react”**, desarrollado por **MDN Web Docs**, cuyo propósito es demostrar la creación de una aplicación de lista de tareas utilizando **React (JavaScript)**.  

El objetivo del análisis es aplicar los principios de **buenas prácticas de programación**, evaluando la claridad de nombres, tamaño y propósito de las funciones, uso de comentarios, presencia de olores de código y la organización general de la estructura.  
Finalmente, se presentan **mejoras propuestas** que podrían aumentar la calidad y mantenibilidad del código.

---

## 🗂️ Archivos seleccionados

Se eligieron dos archivos con lógica significativa dentro del proyecto:

1. `src/App.js` → Componente principal que gestiona el estado y la lógica de la aplicación.  
2. `src/components/Todo.js` → Componente individual que representa cada tarea.

---

## 🔍 Análisis de código

### 1. Archivo `App.js`

**Descripción:**  
Controla las funcionalidades principales: agregar, editar, marcar y eliminar tareas, utilizando el hook `useState`.

**Análisis:**
- **Nombres claros:** En general, las funciones (`addTask`, `deleteTask`, `editTask`) son comprensibles, aunque algunos nombres genéricos como `handleChange` podrían ser más específicos.  
- **Funciones cortas:** La mayoría son breves, pero `editTask` combina lógica de filtrado y actualización que podría dividirse.  
- **Comentarios:** El archivo carece de comentarios explicativos, lo que dificulta la comprensión para quienes recién estudian React.  
- **Olores de código:** Hay repeticiones menores en el uso de `map` y `filter` para actualizar el estado.  
- **Estructura:** Bien organizada, aunque con riesgo de sobrecargar el componente principal si la app crece.

---

### 2. Archivo `Todo.js`

**Descripción:**  
Componente que renderiza una tarea con opciones de edición, eliminación y marcado como completado.

**Análisis:**
- **Nombres claros:** Variables y funciones como `completed`, `toggleTaskCompleted`, `isEditing` son intuitivas.  
- **Funciones cortas:** Cumplen el principio de una sola responsabilidad.  
- **Comentarios:** No hay comentarios, aunque se podrían incluir para explicar el cambio entre “modo vista” y “modo edición”.  
- **Olores de código:** La condición ternaria para alternar modos es extensa; podría simplificarse separando vistas.  
- **Estructura:** Correcta. El componente maneja su propio estado (`isEditing`) y recibe props claras desde el padre.

---

## 🧩 Mejoras propuestas

| Nº | Mejora | Justificación |
|:--:|:--|:--|
| 1 | **Agregar comentarios explicativos en `App.js` y `Todo.js`.** | Facilita la comprensión del flujo de datos y del manejo del estado. |
| 2 | **Extraer funciones auxiliares en un archivo `utils.js`.** | Evita duplicación de lógica y mejora la legibilidad del componente principal. |
| 3 | **Separar la lógica de edición en un subcomponente `EditForm.js`.** | Divide responsabilidades y simplifica el componente `Todo.js`. |
| 4 | **Renombrar variables genéricas (ej. `handleChange` → `handleTaskNameChange`).** | Mejora la claridad semántica y la autodescripción del código. |
| 5 | **Agregar validación de tipos con `prop-types` o TypeScript.** | Incrementa la robustez del código al asegurar los tipos esperados en los props. |

---

## 🧠 Conclusiones

El repositorio **`mdn/todo-react`** muestra un código limpio y educativo que sigue en gran parte las buenas prácticas de React:  
componentes reutilizables, funciones cortas y una estructura modular.  

No obstante, la aplicación podría beneficiarse de una mejor **documentación interna**, **separación de responsabilidades** y **validación de datos**, lo que haría su mantenimiento más sencillo y serviría como un ejemplo aún más claro para nuevos desarrolladores.

---

## 📚 Referencias

- MDN Web Docs. (s.f.). *Todo React Example*. Recuperado de [https://github.com/mdn/todo-react](https://github.com/mdn/todo-react)  
- React Documentation. (s.f.). *React – Declarative UI Framework*. [https://react.dev/](https://react.dev/)
