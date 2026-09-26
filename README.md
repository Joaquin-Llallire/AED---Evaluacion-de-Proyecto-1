
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


pip install manim

### Para verificar la instalación:
manim --version
- Si no funciona, usar:
python -m manim --version

## 📂 Estructura del proyecto
proyecto/
├── hash_transactions.py    # Código principal de la animación Manim
├── README.md               # Este archivo
├── requirements.txt        # Dependencias del proyecto
└── media/                  # Video generado (opcional)

##🚀 Cómo ejecutar
1. Clonar el repositorio:
git clone https://github.com/tu-usuario/tu-repo.git
cd tu-repo

2. Ejecutar la animación en calidad media (prueba rápida):
python -m manim -pql hash_transactions.py HashTransactions

3. Generar el video en alta calidad (1080p):
python -m manim -pqh hash_transactions.py HashTransactions

4. Convertir a formato MPEG (si es necesario):
ffmpeg -i media/videos/hash_transactions/1080p60/HashTransactions.mp4 \
       -c:v mpeg2video -q:v 2 HashTransactions.mpeg

