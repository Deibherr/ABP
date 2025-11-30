# Simulación Web - Competencia de Rodadura en un Plano Inclinado

## 📋 Descripción

Simulación interactiva en HTML/JavaScript que representa la caída simultánea por un mismo plano inclinado de tres cuerpos rígidos: **esfera maciza**, **cilindro macizo** y **aro (cilindro hueco)**. El objetivo es entender y demostrar, tanto numérica como visualmente, cuál objeto llega primero a la base y por qué, apoyándose en la física rotacional y la condición de rodadura sin deslizamiento.

## 🎯 Objetivos de Aprendizaje

- Comprender y aplicar las ecuaciones de la dinámica de cuerpos rígidos en rodadura sin deslizamiento
- Diseñar una simulación interactiva que muestre el comportamiento dinámico de cuerpos rodantes
- Usar herramientas digitales (p5.js) para implementar y validar modelos físicos
- Comparar resultados teóricos con simulaciones numéricas

## 🚀 Características

### Objetos Simulados
- **Esfera maciza**: Momento de inercia I = (2/5)mR²
- **Cilindro macizo**: Momento de inercia I = (1/2)mR²
- **Aro (cilindro hueco)**: Momento de inercia I = mR²

### Controles Interactivos
- **Ángulo del plano θ**: Ajustable de 1° a 45°
- **Altura inicial h**: Ajustable de 0.2 m a 3.0 m
- **Radio R**: Ajustable de 0.02 m a 0.2 m
- **Masa m**: Ajustable de 0.1 kg a 5.0 kg

### Visualización en Tiempo Real
- **Posición s(t)**: Distancia recorrida a lo largo de la rampa
- **Velocidad lineal v(t)**: Velocidad del centro de masa
- **Velocidad angular ω(t)**: Velocidad de rotación
- **Tiempos finales**: Tiempo que tarda cada objeto en llegar a la base
- **Gráfica v(t)**: Comparación visual con curvas teóricas superpuestas

### Funcionalidades Adicionales
- ✅ Visualización 3D con p5.js WEBGL
- ✅ Vectores de fuerza opcionales (peso, fricción)
- ✅ Rastro de trayectoria de cada objeto
- ✅ Exportación de datos a CSV
- ✅ Rotación de cámara interactiva
- ✅ Validación de condición de rodadura sin deslizamiento

## 📐 Fundamentos Físicos

### Ecuación de Aceleración

Para un objeto que rueda sin deslizar sobre un plano inclinado:

```
a = (g·sin(θ)) / (1 + k)
```

donde:
- `g` = 9.80665 m/s² (aceleración gravitacional)
- `θ` = ángulo de inclinación del plano
- `k = I/(mR²)` = factor de inercia rotacional

### Factores k por Tipo de Objeto

- **Esfera maciza**: k = 2/5 = 0.4
- **Cilindro macizo**: k = 1/2 = 0.5
- **Aro**: k = 1 = 1.0

### Predicción Teórica

Comparando los factores multiplicativos de `g·sin(θ)`:

- **Esfera**: a = (5/7)g·sin(θ) ≈ 0.714·g·sin(θ)
- **Cilindro**: a = (2/3)g·sin(θ) ≈ 0.667·g·sin(θ)
- **Aro**: a = (1/2)g·sin(θ) = 0.5·g·sin(θ)

**Resultado**: La esfera acelera más rápido, seguida del cilindro, y finalmente el aro.

## 🛠️ Tecnologías Utilizadas

- **HTML5**: Estructura y marcado
- **CSS3**: Estilos y diseño responsive
- **JavaScript (ES6+)**: Lógica de simulación
- **p5.js v1.6.0**: Visualización 3D y renderizado WEBGL

## 📦 Instalación y Uso

### Requisitos
- Navegador web moderno (Chrome, Firefox, Edge)
- No requiere instalación de dependencias (usa CDN)

### Ejecución
1. Clonar o descargar el repositorio
2. Abrir `sim3D_gina_edit_.html` en un navegador web
3. Ajustar los parámetros deseados (ángulo, altura, radio, masa)
4. Hacer clic en **"Iniciar"** para comenzar la simulación

### Controles
- **Iniciar**: Comienza la simulación desde el reposo
- **Pausar/Reanudar**: Pausa o reanuda la simulación
- **Reset**: Reinicia la simulación a condiciones iniciales
- **Cam Reset**: Restablece la posición de la cámara 3D
- **Snapshot CSV**: Exporta los datos de la simulación a un archivo CSV

## 📊 Exportación de Datos

La función de exportación CSV genera un archivo con las siguientes columnas:
- `t`: Tiempo (s)
- `body`: Nombre del cuerpo
- `type`: Tipo de cuerpo (sphere, cyl, ring)
- `v`: Velocidad lineal (m/s)
- `s`: Posición (m)
- `a`: Aceleración (m/s²)
- `omega`: Velocidad angular (rad/s)
- `friction`: Fuerza de fricción estática (N)

## 📚 Referencias

- Marion & Thornton, *Dinámica Clásica de Partículas y Sistemas*
- Kleppner & Kolenkow, *An Introduction to Mechanics*
- Serway & Jewett, *Física para Ciencias e Ingeniería*

## 👥 Autores

**Deibherr** - Deibherr@gmail.com

Proyecto desarrollado como parte del Aprendizaje Basado en Problemas (ABP) de Física Mecánica 1 - Universidad de Antioquia

## 📄 Licencia

Este proyecto es de uso educativo y académico.

---

**Nota**: Esta simulación utiliza integración numérica (método de Euler explícito) para resolver las ecuaciones de movimiento. Para mayor precisión en casos extremos, se recomienda usar métodos de integración más avanzados (RK2, RK4).

