# Simulación
Instrucciones para crear una cuenta en GitHub:
---

---
1.- Buscar en internet la plataforma de "Github"

---
<img width="600" height="660" alt="image" src="https://github.com/user-attachments/assets/04d4b84b-8229-4d48-bd13-c7524905b26e" />

---

2.- Crea tu propia cuenta

---
<img width="600" height="660" alt="image" src="https://github.com/user-attachments/assets/b944fbf1-3602-4639-9f4f-3c8a59465e0b" />

---

3.- Crea tu primer repositorio

---
<img width="600" height="660" alt="image" src="https://github.com/user-attachments/assets/ab3b04c6-4f18-41a8-93ee-ea5810155188" />

---

4.- Empieza a realizar tu actividad asignada 

---
<img width="600" height="660" alt="image" src="https://github.com/user-attachments/assets/08b0820e-1fbb-4d71-9937-f8856a31042f" />




Instrucciones para descargar Blender:
---

---

1.- Busca en internet la app de "Blender"

---
<img width="600" height="660" alt="image" src="https://github.com/user-attachments/assets/73b41299-d1a9-479a-aa85-673857040e30" />

---

2.- Descarga la versión más reciente 

---
<img width="600" height="660" alt="image" src="https://github.com/user-attachments/assets/e3a7deab-d7a8-45e4-a491-de18554c3edd" />

---

3.- Ejecutalo en tu laptop y empieza a navegar entre sus herramientas para que puedas entender todas sus funciones

---
<img width="600" height="660" alt="image" src="https://github.com/user-attachments/assets/41bcb79a-4e7c-42b2-829f-54a4ab8a9de9" />




Explicación del código de un polígono en Blender:
---

---

1.- Foto del polígono y su código

---
<img width="800" height="860" alt="image" src="https://github.com/user-attachments/assets/3d51830b-3b8a-4a74-838d-a2e0d1f71bc3" />

---

2.-Importación de Librerías y Dependencias

---

El script comienza importando los módulos necesarios para la ejecución:

    ¬bpy (Blender Python): La interfaz de programación de aplicaciones que permite la manipulación del núcleo de Blender (escena, objetos, mallas).
    ¬math: Proporciona las funciones de biblioteca estándar para cálculos de punto flotante, esenciales para la traslación de coordenadas polares a cartesianas.

---

3.- Definición de la Función: "crear_poligono_2d"
   
---
   
Se establece un método que encapsula la lógica de construcción. Recibe tres parámetros: un identificador de cadena (nombre), un entero para la resolución topológica (lados) y un valor numérico para la escala espacial (radio).

  A. Instanciación de Estructuras de Datos (Líneas 5-10)
  
Antes de generar la geometría, se deben reservar los contenedores de datos:

    ¬Se crea un mesh (malla) vacío en la base de datos interna.
    ¬Se vincula esa malla a un nuevo objeto de tipo geométrico.
    ¬Se realiza el link del objeto a la colección activa de la escena para que sea renderizable y visible en el viewport.


  B. Algoritmo de Posicionamiento de Vértices (Líneas 12-20)Para determinar la posición de los vértices en un plano bidimensional (XY), el código utiliza una iteración sobre el número de lados. La posición de cada vértice $i$ se calcula mediante: 
  

<img width="500" height="560" alt="image" src="https://github.com/user-attachments/assets/23e46c4d-81d0-4973-894d-cce4879e46b7" />             
<img width="200" height="260" alt="image" src="https://github.com/user-attachments/assets/a1473e97-4671-41ea-ad16-03adad57f69b" />


Esto distribuye los puntos de manera equidistante sobre una circunferencia teórica de radio r. Nótese que el componente  $Z$  se mantiene en  $0$  para preservar la naturaleza 2D de la entidad.



  C. Definición de la Topología (Líneas 22-24)Se establecen las aristas (edges) mediante una lista de tuplas. El operador módulo (%) es crucial aquí: permite que el último vértice se conecte con el primero ($i + 1$ vuelve a $0$ cuando llega al límite), cerrando así el perímetro del polígono.


  D. Inyección de Datos y Actualización (Líneas 26-28)
El método from_pydata toma las listas de coordenadas y conectividad para construir la estructura interna de la malla. Posteriormente, update() recalcula las normales y la visualización para reflejar los cambios en el motor gráfico.


--- 

4.- Gestión del Entorno y Ejecución
   
---
   
¬Limpieza de Escena (Líneas 30-32): Se utiliza bpy.ops para seleccionar y eliminar todos los objetos preexistentes. Esto garantiza que el script se ejecute en un entorno controlado (un "sandbox" limpio).

¬Llamada a la Función: Se invoca el método pasando los argumentos específicos (un hexágono de radio 5).







