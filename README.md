#  Generación de Escenario 3D con Animación de Cámara en Blender mediante Python

<p align="center">
Creación automática de un pasillo con tramo curvo, iluminación y recorrido animado de cámara
</p>


##  Introducción

Este script genera automáticamente un **escenario 3D completo** en Blender que incluye:

* Pasillo recto
* Curva en 90°
* Materiales
* Iluminación
* Cámara animada

Simula un recorrido en primera persona a través del entorno.

##  Objetivo

* Automatizar creación de escenarios
* Aplicar geometría paramétrica
* Generar curvas mediante trigonometría
* Aplicar materiales dinámicos
* Animar una cámara en trayectoria


#  Fundamento Matemático

El tramo curvo se genera usando:

```
x = cx + r * cos(angulo)
y = cy + r * sin(angulo)
```

Esto permite crear paredes siguiendo un arco de 90°.

La cámara también usa esta fórmula para recorrer la curva.

#  Requisitos

* Blender 5.0+
* Espacio Scripting


#  Procedimiento


##  Paso 1: Limpieza de escena


Se eliminan todos los objetos previos.


##  Paso 2: Creación de materiales


Se generan dos materiales:

* Oscuro (estructura)
* Naranja (detalle)


##  Paso 3: Generación del pasillo recto

Se crean paredes laterales mediante un ciclo.

<img width="945" height="648" alt="image" src="https://github.com/user-attachments/assets/1927bc5d-e85d-400c-9b06-b7471b472a1f" />

##  Paso 4: Generación del tramo curvo


Las paredes siguen un arco de 90°.


##  Paso 5: Creación del suelo


Se añade una base que cubre todo el entorno.


##  Paso 6: Iluminación


Se agregan:

* Luz solar
* Dos luces puntuales


##  Paso 7: Cámara

Se posiciona a altura humana:

```
Z = 1.5
```

---

##  Paso 8: Animación del recorrido


La animación dura:

```
250 fotogramas
```

### Tramos:

| Frames    | Movimiento    |
| --------- | ------------- |
| 1 → 100   | Pasillo recto |
| 101 → 250 | Curva         |

---

# 💻 Código Completo

```python
import bpy
import random
import math
```

### Crear materiales

```python
def crear_material(nombre, color_rgb):
    mat = bpy.data.materials.new(name=nombre)
    mat.use_nodes = True
    bsdf = mat.node_tree.nodes["Principled BSDF"]
    bsdf.inputs['Base Color'].default_value = (*color_rgb, 1.0)
    bsdf.inputs['Roughness'].default_value = 0.7
    return mat
```


### Generar escenario

```python
def generar_escenario():
```

Incluye:

✔ Pasillo recto
✔ Curva
✔ Suelo
✔ Luces
✔ Cámara
✔ Animación


### Ejecutar

```python
generar_escenario()
```

#  Resultado
<img width="1332" height="687" alt="image" src="https://github.com/user-attachments/assets/e3cb1ab4-8b5c-4f8e-ba40-6dfbc0928d68" />

<img width="411" height="682" alt="image" src="https://github.com/user-attachments/assets/94825b72-29d7-4aeb-bc6f-1d043358f45e" />

Se obtiene:

✔ Escenario completo
✔ Recorrido animado
✔ Curva suave
✔ Iluminación dinámica


#  Personalización

Cambiar tamaño del pasillo:

```python
largo_pasillo = 15
```

Cambiar curva:

```python
radio_curva = 20
```

Cambiar duración:

```python
bpy.context.scene.frame_end = 400
```


#  Conclusión

Este script demuestra cómo Blender puede utilizarse como motor de generación procedural para:

* Crear entornos
* Simular recorridos
* Generar animaciones
