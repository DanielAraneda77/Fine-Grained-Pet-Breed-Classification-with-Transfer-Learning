# 🐾 Fine-Grained Pet Breed Classification with Transfer Learning and EfficientNetV2

## Objetivo

Construir un clasificador robusto de 37 razas de perros y gatos mediante Transfer Learning y Fine-Tuning, entrenado sobre el dataset [oxford_iiit_pet](https://www.tensorflow.org/datasets/catalog/oxford_iiit_pet), optimizando precisión y generalización en condiciones visuales variadas.

---

## Flujo de trabajo

### 1. Preprocesamiento
- Redimensionamiento 
- Normalización 
- Batching y prefetch para rendimiento óptimo

### 2. Fase 1: Transfer Learning
- Modelo base: `EfficientNetV2B0` (preentrenado en ImageNet, sin capa superior)
- Cabeza clasificadora
- Base congelada 
- Entrenamiento: 15 épocas

### 3. Fase 2: Fine-Tuning
- Descongelado parcial: últimas 40 capas entrenables
- Learning rate bajo
- Entrenamiento adicional: 10 épocas

### 4. Evaluación del modelo

### 5. Discusión y análisis

---

## Resultados

| Fase              | Precisión en Test |
|-------------------|-------------------|
| Transfer Learning | 92.61%            |
| Fine-Tuning       | 93.08%            |

- Mejora de 0.47 puntos porcentuales tras el fine-tuning
- Gráfico de `val_accuracy` muestra convergencia estable y mejora fina

---

## Análisis

- **Fine-Tuning:** mejora leve pero significativa en ajuste fino
- **Importancia de fases:**
  - Cabeza congelada evita sobreajuste temprano
  - Learning rate bajo protege filtros preentrenados
- **Confusión entre razas similares:** bulldogs, spaniels, ragdolls
- **Rendimiento alto en razas visualmente distintivas:** Abyssinian, Bengal, Egyptian Mau

---

## Posibles Mejoras futuras

Se propone aplicar técnicas de regularización como:

- **MixUp / CutMix:** para mejorar la generalización en razas morfológicamente similares
- **Justificación:** menor dependencia de detalles específicos del pelaje o pose

---

## 👤 Conéctate conmigo

[![Conectar en LinkedIn](https://img.shields.io/badge/LinkedIn-Conectar-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/daniel-araneda-yasic)

¿Eres reclutador o profesional del sector interesado en proyectos aplicados de Data Science, visualización de datos o inteligencia artificial eficiente?  
Este proyecto refleja mi enfoque técnico y comunicativo, y estoy abierto a oportunidades laborales, colaboración en equipos multidisciplinarios y desarrollo de soluciones prácticas y reproducibles.

📫 No dudes en contactarme para conversar sobre cómo puedo aportar valor desde la intersección entre análisis técnico, creatividad visual y documentación didáctica.
