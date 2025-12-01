# 🚀 ABP Simulación Web: Competencia de Rodadura 3D

## 📝 Resumen del Proyecto

Este proyecto es la implementación de un **Aprendizaje Basado en Problemas (ABP)** de Física Mecánica. Consiste en una simulación web interactiva y visualmente atractiva que modela la competencia de rodadura de tres cuerpos rígidos diferentes (Esfera maciza, Cilindro macizo y Aro/Cilindro hueco) en un plano inclinado, bajo la condición de rodadura sin deslizamiento.

El objetivo es determinar y demostrar, mediante el modelado físico y la visualización 3D, cuál objeto llega primero y por qué, basándose en el concepto de **Momento de Inercia** ($I$) y la distribución de masa.

## 🛠️ Stack Tecnológico

La simulación es una aplicación frontend (ejecutable directamente en el navegador) desarrollada para ser altamente interactiva y visual.

| Categoría | Tecnología | Uso Específico |
|-----------|------------|----------------|
| **Estructura** | HTML5 | Estructuración de la interfaz de usuario (UI) y Controles. |
| **Estilos** | CSS3 | Diseño limpio, responsive y moderno (Dark Mode). |
| **Lógica** | JavaScript ES6+ | Implementación de la lógica de la simulación y el motor de física numérico. |
| **Gráficos** | p5.js | Librería de JavaScript para la creación del loop de animación y el dibujo. |
| **Renderizado** | WEBGL (Vía p5.js) | Utilizado para el renderizado de la escena 3D, incluyendo la rampa y los objetos rodantes con perspectiva e iluminación. |

## 💡 Fundamento Físico: El Factor $k$

La clave del problema reside en el cálculo de la aceleración lineal ($a$) a partir del factor $k$ (o factor de inercia rotacional), que es una medida adimensional de cómo se distribuye la masa del cuerpo:

$$\mathbf{k = \frac{I}{m R^{2}}}$$

La aceleración lineal está determinada por:

$$\mathbf{a=\frac{g \sin \theta}{1+k}}$$

Un menor valor de $k$ significa que una menor proporción de la Energía Potencial se convierte en Energía Cinética de Rotación, dejando más para la traslación. Por lo tanto, $\mathbf{k}$ es inversamente proporcional a la aceleración $\mathbf{a}$.

### Valores Clave

| Cuerpo Rígido | Momento de Inercia (I) | Factor k | Conclusión |
|---------------|------------------------|---------|------------|
| **Esfera Maciza** | $I=\frac{2}{5}mR^{2}$ | $\mathbf{0.4}$ | Gana (Mayor $a$) |
| **Cilindro Macizo** | $I=\frac{1}{2}mR^{2}$ | $\mathbf{0.5}$ | Segundo |
| **Aro (Hueco)** | $I=mR^{2}$ | $\mathbf{1.0}$ | Pierde (Menor $a$) |

## 📈 Características de la Simulación

La aplicación incluye herramientas avanzadas para la experimentación y el análisis:

- **Implementación Física Manual**: En lugar de usar un motor de física avanzado (como Cannon.js), se implementó la física manualmente con un integrador numérico semi-implícito de Euler para controlar la precisión del cálculo de aceleración, posición y velocidad.

- **Controles Interactivos**: Permite al usuario modificar en tiempo real el ángulo del plano ($\theta$), la altura ($h$), el radio ($R$) y la masa ($m$).

- **Análisis Gráfico**: Gráfico comparativo en vivo de la velocidad ($v$) vs. tiempo ($t$), mostrando tanto la curva simulada como la curva teórica.

- **Métricas Dinámicas**: Display de posición ($s$), velocidad lineal ($v$) y velocidad angular ($\omega$) en el panel de control.

- **Herramientas Pedagógicas**: Opciones para mostrar el rastro de movimiento y los vectores de fuerza (Gravedad, Normal y Fricción).

- **Exportación de Datos**: Funcionalidad para exportar un archivo `.csv` con todos los datos de la simulación, facilitando el análisis numérico posterior.

## 🏁 Conclusiones del Estudio

Los resultados de la simulación confirman de manera visual y numérica las predicciones teóricas de la mecánica clásica:

1. **La Esfera Maciza siempre llega primero**. Su factor $k$ de 0.4 es el menor, lo que minimiza la inercia rotacional y maximiza la aceleración lineal.

2. **El Aro (Cilindro Hueco) siempre llega de último**. Su factor $k=1.0$ (masa concentrada en el borde) es el mayor, lo que maximiza la inercia rotacional y le da la menor aceleración.

3. **Independencia de $m$ y $R$**: La aceleración y el orden de llegada son completamente independientes de la masa total y del radio de los cuerpos, siempre y cuando rueden sin deslizar. Solo dependen de la geometría ($k$).

## ⚙️ Instrucciones de Uso

Para ejecutar la simulación:

1. Clonar el repositorio:
   ```bash
   git clone <url-del-repositorio>
   ```

2. Abrir el archivo principal `sim3D_unificado.html` en cualquier navegador web moderno (Chrome, Firefox, Edge). **No se requiere servidor web**.

3. Utilizar los sliders en el panel lateral para configurar los parámetros iniciales.

4. Presionar **"Iniciar Simulación"** para ver la competencia en 3D y analizar los resultados.

## 👥 Créditos

**Desarrollado por:**
- Gina Márquez Garzón
- Deiber Alexander Herrera Gamarra
- Eidys Marcela Guzman Arrieta
- Luis Carlos Vanegas Zapata

**Institución:** Facultad de Ingeniería, Universidad de Antioquia

**Fecha:** Noviembre 2025

**Referencia al Informe Completo:** `ABP_simulador.pdf` (Adjunto en el repositorio)
