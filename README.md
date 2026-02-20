Perfecto 🚀
Este ya es un **nivel más avanzado** (escenario + animación de cámara), así que aquí tienes tu documentación estilo repositorio con diseño visual 👇

---

# 🎥 Generación de Escenario 3D con Animación de Cámara en Blender mediante Python

<p align="center">
Creación automática de un pasillo con tramo curvo, iluminación y recorrido animado de cámara
</p>

---

## 📌 Introducción

Este script genera automáticamente un **escenario 3D completo** en Blender que incluye:

* Pasillo recto
* Curva en 90°
* Materiales
* Iluminación
* Cámara animada

Simula un recorrido en primera persona a través del entorno.

---

## 🎯 Objetivo

* Automatizar creación de escenarios
* Aplicar geometría paramétrica
* Generar curvas mediante trigonometría
* Aplicar materiales dinámicos
* Animar una cámara en trayectoria

---

# 🧠 Fundamento Matemático

El tramo curvo se genera usando:

```
x = cx + r * cos(angulo)
y = cy + r * sin(angulo)
```

Esto permite crear paredes siguiendo un arco de 90°.

La cámara también usa esta fórmula para recorrer la curva.

---

# 🛠️ Requisitos

* Blender 5.0+
* Espacio Scripting

---

# ⚙️ Procedimiento

---

## 🔹 Paso 1: Limpieza de escena

![Image](https://i.sstatic.net/ajbBh.png)

![Image](https://help.maxon.net/r3d/blender/en-us/Content/Resources/Images/Blender_Viewport_Rendered.png)

![Image](https://i.sstatic.net/CYq32.gif)

![Image](https://blenderartists.org/uploads/default/1e473ffbbaff2c7e2d5e63428045ddaca5c6d840)

Se eliminan todos los objetos previos.

---

## 🔹 Paso 2: Creación de materiales

![Image](https://i.sstatic.net/KYgYs.png)

![Image](https://i.imgur.com/cq7LEku.png)

![Image](https://docs.blender.org/manual/en/2.81/_images/editors_shader-editor_introduction_main.png)

![Image](https://devtalk.blender.org/uploads/default/original/2X/3/3351381e41872dfbbfb93bbcc293cd663b7f39ce.png)

Se generan dos materiales:

* Oscuro (estructura)
* Naranja (detalle)

---

## 🔹 Paso 3: Generación del pasillo recto

![Image](https://blenderartists.org/uploads/default/original/4X/b/3/6/b36c304342c838c2a44657ce824b928fc4e83117.jpeg)

![Image](https://public.blenderkit.com/thumbnails/assets/af3f38e89719406aaf62eb354a1373ac/files/thumbnail_b671fb4f-a105-40f9-a76b-4145f8b6899a.jpg.256x256_q85.jpg.webp?webp_generated=1766469516)

![Image](https://assets.superhivemarket.com/store/product/184138/image/90718b4b61b084d747f09b252002a168.png)

![Image](https://assets.superhivemarket.com/store/product/151808/image/xlarge-448f9cddd8698891d270c203085e6db6.jpg)

Se crean paredes laterales mediante un ciclo.

---

## 🔹 Paso 4: Generación del tramo curvo

![Image](https://blenderartists.org/uploads/default/954b6b0f5e33113a864a4a1df81f738d0c22bc70)

![Image](https://blenderartists.org/uploads/default/original/3X/2/2/222e0c8ecba0ab2f70c413455bb78c37a5c5f5aa.jpg)

![Image](https://i.sstatic.net/ccami.jpg)

![Image](https://blenderartists.org/uploads/default/ebd2606bed33e1a3de4d12529848405684ea793a)

Las paredes siguen un arco de 90°.

---

## 🔹 Paso 5: Creación del suelo

![Image](https://blenderartists.org/uploads/default/original/4X/7/b/c/7bc26bb4fa412464c0a9f493e1f29d75c5f30dbe.jpeg)

![Image](https://blenderartists.org/uploads/default/optimized/3X/8/e/8e1fb9a1258c8d3e619bc47785a65db9734f86f0_2_1024x573.jpg)

![Image](https://i.stack.imgur.com/ExewY.jpg)

![Image](https://blenderartists.org/uploads/default/original/4X/e/6/d/e6da8013e0f075b45a0cba941315be6ce89a056a.jpeg)

Se añade una base que cubre todo el entorno.

---

## 🔹 Paso 6: Iluminación

![Image](https://docs.blender.org/manual/en/2.83/_images/addons_lighting_sun-position_env-selection.jpg)

![Image](https://blenderartists.org/uploads/default/404b9c6aed031da6764ba296b89dfb442c2d5760)

![Image](https://assets.superhivemarket.com/store/productimage/587477/image/94809866e8ac12b8243b5d210aa98c10.png)

![Image](https://assets.superhivemarket.com/store/productimage/587480/image/94ff0530b1c3667bfe4e695aaec816a8.png)

Se agregan:

* Luz solar
* Dos luces puntuales

---

## 🔹 Paso 7: Cámara

![Image](https://docs.blender.org/manual/en/latest/_images/editors_3dview_navigate_camera-view_example.png)

![Image](https://i.sstatic.net/QaVNg.jpg)

![Image](https://blenderartists.org/uploads/default/original/4X/5/b/f/5bfe520238cc4fbf820506ba7387b7908bbf975f.png)

![Image](https://blenderartists.org/uploads/default/optimized/4X/4/1/3/413fb2d7fc7ceb7e29f132c9b7feed61c9db7c9b_2_1024x576.png)

Se posiciona a altura humana:

```
Z = 1.5
```

---

## 🔹 Paso 8: Animación del recorrido

![Image](https://i.sstatic.net/sGPiG.png)

![Image](https://blenderartists.org/uploads/default/0b34cfa571bd715dbc02343bcc995551e0c9fb30)

![Image](https://docs.blender.org/manual/fr/2.81/_images/addons_camera_rigs.jpg)

![Image](https://docs.blender.org/manual/en/latest/_images/editors_timeline_interface.png)

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

---

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

---

### Ejecutar

```python
generar_escenario()
```

---

# 🟢 Resultado

![Image](https://blenderartists.org/uploads/default/original/4X/c/d/2/cd2c01ecee277ddc1d39edd8aa7a734321faa362.jpeg)

![Image](https://blenderartists.org/uploads/default/original/4X/8/6/6/8662cd9de2c3ac41cfadf3efe2228fdabaf585e4.jpeg)

![Image](https://petapixel.com/assets/uploads/2023/06/EkyGMg5-800x420.jpg)

![Image](https://docs.blender.org/manual/en/latest/_images/editors_3dview_navigate_camera-view_example.png)

Se obtiene:

✔ Escenario completo
✔ Recorrido animado
✔ Curva suave
✔ Iluminación dinámica

---

# 🎛️ Personalización

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

---

# ✅ Conclusión

Este script demuestra cómo Blender puede utilizarse como motor de generación procedural para:

* Crear entornos
* Simular recorridos
* Generar animaciones

Todo mediante programación.

---

Si quieres, el siguiente nivel sería:

🔥 Simular videojuego
🔥 Movimiento en tiempo real
🔥 Exportar como render final

Solo dime 😎
