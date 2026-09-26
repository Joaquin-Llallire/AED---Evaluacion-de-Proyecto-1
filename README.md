# Proyecto 1: Hash Tables en Sistemas de Transacciones

**Curso:** CS2023 — Algoritmos y Estructuras de Datos  
**Integrantes:** Itta Saavedra, Joaquin Llallire  
**Fecha:** Septiembre 2026

---

## 📖 Descripción

Este proyecto consiste en una animación educativa desarrollada con **Manim** (biblioteca de Python) que ilustra el funcionamiento de una **Hash Table** aplicada al monitoreo de transacciones en tiempo real. La animación muestra paso a paso:

- **INSERT:** Inserción de una nueva clave en la tabla.
- **SEARCH:** Búsqueda rápida de una clave existente.
- **UPDATE:** Actualización del valor asociado a una clave.
- **CHAINING:** Resolución de colisiones mediante encadenamiento.

Se presentan dos casos de uso reales en sistemas financieros:

1. **Monitoreo de patrones inusuales:** Detección de comportamientos sospechosos (muchas operaciones en poco tiempo, montos elevados, cuentas nuevas).
2. **Prevención de reprocesamiento:** Evitar procesar dos veces la misma transacción usando el TX-ID como clave.

---

## 🎥 Video demo

https://youtu.be/EA7c30ejOeI

> Duración aproximada: 3 minutos.

---

## 🛠️ Requisitos

- **Python 3.9 o superior**
- **Manim Community v0.18 o superior** (probado con v0.21.0)
- **FFmpeg** (para conversión a formato MPEG)
- **Visual Studio Code** (opcional, entorno sugerido)

### Instalación de dependencias

```bash
pip install manim
```

### Para verificar la instalación

```bash
manim --version
```

Si no funciona, usar:

```bash
python -m manim --version
```

---

## 📂 Estructura del proyecto

```text
proyecto/
├── hash_transactions.py    # Código principal de la animación Manim
├── README.md               # Este archivo
├── requirements.txt        # Dependencias del proyecto
└── media/                  # Video generado (opcional)
```

---

## 🚀 Cómo ejecutar

1. **Clonar el repositorio:**

```bash
git clone https://github.com/joaquin-llallire/AED---Evaluacion-de-Proyecto-1.git
cd AED---Evaluacion-de-Proyecto-1
```

2. **Ejecutar la animación en calidad media (prueba rápida):**

```bash
python -m manim -pql hash_transactions.py HashTransactions
```

3. **Generar el video en alta calidad (1080p):**

```bash
python -m manim -pqh hash_transactions.py HashTransactions
```

4. **Convertir a formato MPEG (si es necesario):**

```bash
ffmpeg -i media/videos/hash_transactions/1080p60/HashTransactions.mp4 -c:v mpeg2video -q:v 2 HashTransactions.mpeg
```

---

## 🧠 Estructura de datos: Hash Table

Una **Hash Table** es una estructura de datos que permite almacenar pares **clave → valor** y acceder a ellos en tiempo promedio **O(1)**. Funciona aplicando una **función hash** a la clave, la cual devuelve un índice dentro de un arreglo de buckets.

### Operaciones principales

| Operación | Descripción | Complejidad promedio |
|-----------|-------------|----------------------|
| **INSERT** | Guardar una nueva clave | O(1) |
| **SEARCH** | Encontrar una clave existente | O(1) |
| **UPDATE** | Modificar el valor asociado | O(1) |
| **DELETE** | Eliminar una clave | O(1) |

### Colisiones y Chaining

Cuando dos claves distintas producen el mismo índice, ocurre una **colisión**. En este proyecto se resuelve mediante **chaining**: cada bucket contiene una lista enlazada con todas las claves que caen en ese índice.

---

## 📊 Casos de uso

### Caso 1: Monitoreo de patrones inusuales

Cada transacción de un usuario actualiza su perfil en la Hash Table. El perfil acumula:

- Número de operaciones recientes
- Monto total acumulado
- Cantidad de cuentas nuevas

Estos datos se envían a reglas de monitoreo que detectan comportamientos sospechosos.

### Caso 2: Prevención de reprocesamiento

Usando el **TX-ID** como clave, el sistema verifica si una transacción ya fue procesada. Si el hash ya existe en la tabla, se evita procesarla nuevamente, garantizando la idempotencia del sistema.

---

## 👥 Contribuciones

| Integrante | Contribución |
|------------|--------------|
| **Itta Saavedra** | Diseño del guion, animación de casos de uso, montaje final del video  |
| **Joaquin Llallire** | Diseño del guion, animación de INSERT, SEARCH, UPDATE, colisiones y chaining |

---

## 📚 Referencias

- [Manim Community Documentation](https://docs.manim.community/)
- [3Blue1Brown — Manim](https://www.3blue1brown.com/)
- [Hash Table — Wikipedia](https://en.wikipedia.org/wiki/Hash_table)

---

## 📝 Licencia

Proyecto académico desarrollado para el curso CS2023 — Algoritmos y Estructuras de Datos.
