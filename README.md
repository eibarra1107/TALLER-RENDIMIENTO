# Taller de Rendimiento en Sistemas Operativos – Multiplicación de Matrices
Nombre: Elier Ibarra

Curso: Sistemas Operativos – Pontificia Universidad Javeriana

Descripción: Taller de rendimiento con enfoque en programación paralela (Fork, Pthreads, OpenMP).

Repositorio del taller de Sistemas Operativos enfocado en **medir y comparar el rendimiento** de la multiplicación clásica de matrices usando tres enfoques:

- Procesos con `fork()`
- Hilos POSIX (`pthread`)
- Directivas de **OpenMP**

El objetivo principal es ver en la práctica cómo influyen:
- La **complejidad del algoritmo**
- El **número de hilos/procesos**
- Y el **hardware** (PC física vs máquinas virtuales)

en los tiempos de ejecución de una misma tarea computacionalmente pesada.

---

## 1. Contenido del repositorio

```text
Taller_Rendimiento_SO/
├── src/
│   ├── mmClasicaFork.c        # Versión con procesos (fork)
│   ├── mmClasicaPosix.c       # Versión con hilos POSIX (pthread)
│   ├── mmOpenMP.c             # Versión con OpenMP
│   └── utils.h                # Funciones de apoyo (si aplica)
├── scripts/
│   └── lanzador.pl            # Script para ejecutar varias pruebas seguidas
├── data/
│   └── resultados_ejecuciones.csv   # Resultados exportados desde Excel
├── docs/
│   ├── informe_SO.pdf         # Informe final del taller
│   └── Taller_Rendimiento_SO.xlsx   # Hoja de cálculo con tiempos y análisis
├── Makefile                   # Compilación automática de las tres versiones
├── LICENSE                    # Licencia MIT
└── .gitignore                 # Archivos a ignorar por Git
2. Objetivo del taller
El taller busca responder preguntas como:

¿Qué tanto mejora el rendimiento al paralelizar la multiplicación de matrices?

¿Hasta qué punto vale la pena aumentar el número de hilos/procesos?

¿Qué diferencias reales hay entre usar fork, pthread y OpenMP?

¿Cómo afecta el hardware (PC vs VM) a los resultados?

Para eso se implementó la misma operación (multiplicación clásica de matrices cuadradas) en tres variantes y se midió su tiempo de ejecución para distintos tamaños de matriz y distintos números de hilos/procesos.

3. Requisitos
Para compilar y ejecutar el código se necesita:

Sistema tipo Unix (Linux recomendado)

gcc con soporte para OpenMP

Biblioteca de hilos POSIX (normalmente incluida en glibc)
