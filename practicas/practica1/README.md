# Práctica 1 — Plataformas y herramientas

Entrega: 

## Reproducir todo (dos comandos)

```bash
cd practicas/practica1/src
bash ../scripts/run_all.sh        # compila (make) y genera ../results/*.csv  (~5 min)
cd .. && python3 scripts/plot.py  # resumen.csv + practica1.png
```

## Contenido

- `entorno.txt` — salida de la verificación de la Parte A.
- `src/` — `matmul.c`, `matmul_pure.py`, `matmul_numpy.py`, `hello_omp.c`, `Makefile`.
- `scripts/` — `run_all.sh`, `plot.py`.
- `results/` — CSV, `resumen.csv`, `practica1.png`.
- `notebooks/p1_gpu.ipynb` — Parte E, con salidas.
- `reporte.pdf` — reporte del equipo.

## Máquina en la que se midió

| Campo | Valor |
| :--- | :--- |
| **Modelo de CPU** | 13th Gen Intel(R) Core(TM) i7-13620H |
| **Núcleos físicos / hilos lógicos** | 10 físicos / 16 hilos |
| **Frecuencia base / turbo** | 2.40 GHz / 4.90 GHz |
| **Caché L1/L2/L3** | L1: 640 KiB total / L2: 10 MiB / L3: 24 MiB |
| **Memoria RAM** | [16 GB] |
| **Extensiones vectoriales** | AVX, AVX2, FMA, SSE4_1, SSE4_2 |
| **Sistema operativo y kernel** | Ubuntu 24.04.1 LTS (vía WSL2 en Windows) |
| **Compilador** | gcc (Ubuntu 13.3.0) / OpenMP 201511 |
| **Python/NumPy / BLAS** | Python: 3.12.3 / NumPy: 2.5.3 |
| **GPU (si hay)** | NVIDIA GeForce RTX 4050 Laptop GPU |
| **Condiciones** | Ejecutado en WSL2 bajo entorno virtual de Python. |
