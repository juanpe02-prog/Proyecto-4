
README - DIGITALIZADOR DE CURVAS EN IMÁGENES


1. DESCRIPCIÓN GENERAL


Este proyecto implementa un digitalizador de curvas a partir de imágenes de gráficas.

El programa:
- Carga una imagen de una gráfica (formato PNG, JPG, etc.).
- Permite calibrar los ejes X y Y haciendo clic sobre el gráfico.
- Detecta automáticamente la curva mediante análisis geométrico (bordes y contornos).
- Convierte los puntos de la curva de coordenadas en píxeles a coordenadas reales.
- Guarda los puntos digitalizados en un archivo de texto (.txt).

El código está pensado para ejecutarse de forma local en cualquier entorno de Python
(Spyder, VS Code, PyCharm, consola, etc.).


2. CONTENIDO DEL ARCHIVO .ZIP


El archivo .zip contiene (al menos):

- `digitalizador_curvas.py`
    Script principal del digitalizador (versión geométrica).

- `README.txt`
    Este archivo con las instrucciones de uso.

- Ejemplos
    Imágenes de prueba de gráficas para digitalizar.


3. REQUISITOS PREVIOS


Debe tener instalado en su equipo:

- Python 3.x (recomendado 3.8 o superior)
- Las siguientes librerías de Python:
    - OpenCV (cv2)
    - NumPy

Si no las tiene instaladas, puede hacerlo desde una terminal o consola con:

    pip install opencv-python numpy

Estas instrucciones aplican si usa:
- Spyder (Anaconda)
- VS Code
- Terminal de Windows / Linux / macOS
- Cualquier otro entorno donde pueda ejecutar Python.


4. CÓMO EJECUTAR EL PROGRAMA


1) Descargar y descomprimir el archivo .zip en una carpeta de su preferencia.

2) Verificar que el archivo `digitalizador_curvas.py` y las imágenes
   que desee usar estén en la misma carpeta (o ajustar la ruta de la imagen
   dentro del código en la variable `image_path`).

   Ejemplo dentro del código:
       image_path = "hola.png"

   Cambie `"hola.png"` por el nombre de la imagen que quiera digitalizar.

3) Abrir un entorno de trabajo de Python:
   - Spyder (Anaconda), o
   - VS Code, o
   - Una terminal / cmd / PowerShell.

4) Ejecutar el script. Ejemplos:

   - En terminal:
        python digitalizador_curvas.py

   - En Spyder:
        Abrir el archivo y presionar el botón de "Run".

5) Se abrirá una ventana con la imagen de la gráfica.


5. FLUJO DE USO DENTRO DEL PROGRAMA


El programa funciona por fases. En la consola se irán mostrando
mensajes indicando qué hacer en cada momento.

Fase 1 – Calibración eje X:
    - Hacer 2 clics IZQUIERDOS sobre el eje X (línea horizontal de la gráfica).
      IMPORTANTE: los dos clics deben estar sobre la MISMA línea del eje X.
    - En la consola, escribir los valores reales correspondientes a esos puntos
      (por ejemplo: 1 y 4, o 2000 y 2025, etc.).

Fase 2 – Calibración eje Y:
    - Hacer 2 clics IZQUIERDOS sobre el eje Y (línea vertical de la gráfica).
      IMPORTANTE: los dos clics deben estar sobre la MISMA línea del eje Y.
    - En la consola, escribir los valores reales correspondientes a esos puntos
      (por ejemplo: 20 y 80, o 0 y 100, etc.).

Fase 3 – Procesamiento:
    - Una vez completada la calibración, se puede cerrar la ventana con la tecla ESC.
    - El programa detectará automáticamente la curva mediante:
        * detección de bordes (Canny),
        * eliminación de líneas rectas (ejes y cuadrícula),
        * extracción del contorno principal,
        * muestreo de un número fijo de puntos.

6. SALIDA DEL PROGRAMA


Al finalizar, el programa:

- Imprime por consola una lista de puntos digitalizados:
    x = ..., y = ...

- Guarda los puntos en un archivo de texto en la misma carpeta, por ejemplo:
    puntos_digitalizados_geom.txt

El archivo contiene dos columnas:
    x   y

donde:
- x = coordenada real en el eje X,
- y = coordenada real en el eje Y.

Este archivo puede abrirse con:
- Excel
- LibreOffice Calc
- MATLAB
- Python (NumPy, pandas)
- Cualquier otro software de análisis de datos.


7. NOTAS Y RECOMENDACIONES


- Es importante que los clics de calibración se hagan EXACTAMENTE sobre los ejes,
  y no sobre la cuadrícula o por encima/debajo de los números.

- Si la imagen está muy comprimida, borrosa o con mucho ruido, la detección puede
  no ser perfecta.

- Para mejores resultados:
    * usar imágenes claras, con buena resolución,
    * evitar capturas borrosas o muy comprimidas,
    * evitar gráficos con demasiadas curvas superpuestas.

- Si se cambia el nombre del archivo principal (por ejemplo a `main.py`), las
  instrucciones siguen siendo las mismas, solo debe ajustar el comando:

    python main.py


8.AUTORES


Autores del proyecto:
- Juan David Pereira
- Andrés Cadena
- Jean Pierre


