# Comparador de Estado GPON

Herramienta web para comparar archivos CSV de equipos GPON entre dos días y detectar
cambios de estado en la columna `ESTADO_ENLACE` (de `En_Servicio` hacia otro valor).

## Características

- Lectura en **streaming** — filtra por nemónico durante la lectura, no carga el archivo completo en memoria
- Funciona con archivos CSV de cientos de MB
- **100% del lado del cliente** — ningún dato se envía a servidores
- Genera un Excel con 3 hojas: Detalle, Resumen por Splitter, Estadísticas
- Separador de CSV configurable (por defecto `;`)

## Columnas requeridas en los CSV

```
LINE_ID  |  DSLAM  |  ESTADO_ENLACE  |  SPLITTER_2_NAME
```

## Cómo usar

1. Ingresar el **nemónico** (filtro parcial sobre la columna DSLAM, ej: `CH_OLTS_PMN`)
2. Seleccionar el CSV de **ayer** y el CSV de **hoy**
3. Hacer click en **Procesar**
4. Descargar el Excel generado

## Despliegue en GitHub Pages

1. Crear un repositorio público en GitHub
2. Subir este `index.html` (y opcionalmente este `README.md`)
3. Ir a **Settings → Pages → Source → Deploy from branch → main / (root)**
4. La app queda disponible en `https://tu-usuario.github.io/nombre-repo/`

## Tecnologías

- [PapaParse 5.4](https://www.papaparse.com/) — parsing de CSV con streaming
- [SheetJS 0.18](https://sheetjs.com/) — generación de Excel en el navegador
- HTML/CSS/JS vanilla — sin frameworks, sin dependencias de build
