<div align="center">

# Ernesto Investing AI

**Sistema web integrado para explorar el mercado, comparar modelos de IA y construir portafolios, con accesibilidad avanzada.**

Proyecto del curso **Interacción Humano-Computador (IHC 2026-II)** · Facultad de Ingeniería de Sistemas e Informática, **UNMSM** · **Equipo A**

[![Sitio en GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-2ea44f?logo=github)](https://mbaernestocr-tech.github.io/ernesto-investing-ai-equipo-a/)
[![QA](https://github.com/mbaernestocr-tech/ernesto-investing-ai-equipo-a/actions/workflows/qa.yml/badge.svg)](https://github.com/mbaernestocr-tech/ernesto-investing-ai-equipo-a/actions/workflows/qa.yml)
[![WCAG 2.2 AA](https://img.shields.io/badge/accesibilidad-WCAG%202.2%20AA-005a9c)](#accesibilidad)
[![i18n](https://img.shields.io/badge/idiomas-ES--PE%20%7C%20EN--US-6f42c1)](#características)
[![Licencia](https://img.shields.io/badge/licencia-CC%20BY%204.0-lightgrey)](LICENSE)

**[Abrir el sitio](https://mbaernestocr-tech.github.io/ernesto-investing-ai-equipo-a/)**

</div>

> [!IMPORTANT]
> Proyecto **educativo**. Los pronósticos, carteras y backtests **no son asesoría de inversión**. El Trading y la liga son **simulados**: no se conectan cuentas ni se ejecutan órdenes reales.


> [!NOTE]
> **Copia propia con historial completo.** Este repositorio es una copia de [JosMart04/EquipoA_ErnestoInvestingAI](https://github.com/JosMart04/EquipoA_ErnestoInvestingAI) (trabajo del Equipo A, IHC 2026-II, UNMSM), publicada bajo la misma licencia CC BY 4.0 con atribución al equipo original y al material base de Ernesto D. Cancho-Rodríguez. La evaluación de qué es real y qué es simulado está en la carpeta de informes del curso (Tema 13).

---

## Contenido

- [Acerca del proyecto](#acerca-del-proyecto)
- [Módulos](#módulos)
- [Características](#características)
- [Tecnologías](#tecnologías)
- [Arquitectura](#arquitectura)
- [Empezar](#empezar)
- [Pruebas y calidad](#pruebas-y-calidad)
- [Datos y procedencia](#datos-y-procedencia)
- [Accesibilidad](#accesibilidad)
- [Entregables](#entregables)
- [Créditos y uso de IA](#créditos-y-uso-de-ia)
- [Licencia](#licencia)

## Acerca del proyecto

**Ernesto Investing AI** reúne en un solo sitio web los **9 módulos** del sistema propuesto en el curso. Hay 4 heredados del material base: Dashboard, Watchlist, Trading y Leaderboard. Los otros 5 son nuevos: Clasificación, Regresión, Optimizador, Portafolios y Backtesting.

El objetivo de IHC es que una persona sin formación financiera **entienda qué hace cada modelo, qué tan bien lo hace y por qué dice lo que dice**. Por eso cada módulo trae una ficha de la IA, verificaciones visibles y resultados publicados **tal como salen**, aunque sean desfavorables. La accesibilidad cubre teclado, lector de pantalla, sonido, cámara (cabeza o manos), un interruptor y voz.

El sitio funciona con dos fuentes de datos intercambiables:

| Modo | Fuente | Para qué |
|---|---|---|
| **Profesor** (por defecto) | Los 13 JSON sintéticos del curso (`data/`), intocables | Cumplir la guía del curso al pie de la letra |
| **Real** | Precios de Yahoo Finance y modelos entrenados por el equipo (`data_real/`), con 12 cortes mensuales | Ver el mismo sistema con datos y modelos reales |

## Módulos

| Módulo | Qué hace |
|---|---|
| **Dashboard** | Indicadores del mercado, velas OHLC por periodo o fechas y el universo de 26 activos con filtros. |
| **Watchlist y alertas** | Lista de seguimiento con minigráficos y alertas de precio o variación. |
| **Trading simulado** | Órdenes a mercado con vista previa, validación en línea, posiciones e historial (en el navegador). |
| **Leaderboard** | Liga ficticia con tu posición calculada desde tu cartera de Trading. |
| **Clasificación** | 18 modelos (11 de Machine Learning y 7 de Deep Learning) dicen **SUBE** o **BAJA** a 30 sesiones. Incluye mapa de calor, consenso, métricas y matriz de confusión. |
| **Regresión a 30 sesiones** | Pronóstico de precio con mediana, banda p10–p90 y cono de volatilidad. Se verifica el último precio contra el retorno proyectado. |
| **Optimizador** | Frontera de Markowitz y frentes NSGA-II y NSGA-III (con CVaR), composición de cada cartera y paso a Trading. |
| **Portafolios** | Tres niveles de riesgo con la razón de cada activo. Se pueden excluir activos y llevar la cartera a Trading. |
| **Backtesting** | Curvas de capital y caídas de las carteras frente a SPY, QQQ, EPU y 1/N, con línea de tiempo de rebalanceos e interpretación generada a partir de las cifras. |

## Características

- **Ninguna cifra escrita a mano:** todo se lee de los JSON o se deriva y se declara ([contrato de datos](docs/CONTRATO_DATOS.md)).
- **Solo dos clases:** SUBE ▲ o BAJA ▼, siempre con palabra y símbolo, nunca solo con color.
- **Bilingüe ES-PE / EN-US** sin recargar la página, con formatos de número y fecha de `Intl`.
- **Temas claro y oscuro** (también en los gráficos), alto contraste y diseño adaptable hasta 390 px.
- **Recálculo en el navegador** en el Modo real: el backtesting y las fronteras se recalculan en Web Workers con otro periodo o ventana.
- **Cortes históricos:** se puede ver cómo estaban los modelos al cierre de cada uno de los últimos 12 meses.
- **Estado compartido** entre módulos: la watchlist, la cartera elegida, «Llevar a Trading» y las migas de pan.
- **Sin compilación:** HTML, CSS y JavaScript puros. El sitio se sirve tal cual desde GitHub Pages.

## Tecnologías

### Lenguajes

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python%203.12-3776AB?logo=python&logoColor=white)

| Capa | Tecnologías |
|---|---|
| **Sitio web** | HTML5, CSS3 (una sola hoja con variables de tema), JavaScript sin frameworks ni compilación (scripts clásicos) |
| **Visualización** | [Apache ECharts](https://echarts.apache.org/) 5.5.1 (por CDN): velas, líneas, dispersión, mapas de color y gráficos conectados |
| **Visión por computadora** | [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe/solutions/vision) 1.2.3 (Face Landmarker y Hand Landmarker), cargado solo al activar la cámara |
| **APIs del navegador** | Web Speech API (reconocimiento y síntesis de voz), Web Audio API (sonificación), Web Workers (recálculo), `Intl` (i18n), `getUserMedia`, `localStorage` y `sessionStorage` |
| **Algoritmos propios (JS)** | Markowitz (KKT exacto), NSGA-II y NSGA-III, backtesting walk-forward, estadística (Ledoit-Wolf, métricas), símplex, filtro One Euro |
| **Datos y modelos (Python)** | yfinance 1.8.0, NumPy 2.5.5, pandas 3.1.1, SciPy 1.18.0, scikit-learn 1.9.1, XGBoost 3.4.0, LightGBM 4.7.0, PyTorch 2.15.0 (CPU), cvxpy 1.9.3, pymoo 0.6.2, exchange-calendars 4.13.3 |
| **Pruebas** | `node:test` (Node.js 22), Playwright 1.65.1, axe-core 4.14.0, `unittest` de Python |
| **CI/CD** | GitHub Actions (pruebas, Gitleaks, E2E y actualización diaria de datos) y GitHub Pages |
| **Diseño** | Figma y Figma Make. El export (`figma-src/`: React, TypeScript, Vite, Tailwind CSS y Recharts) se conserva **sin editar**, como referencia de diseño |

## Arquitectura

```text
├── index.html … backtesting.html   9 páginas, una por módulo (contenedores vacíos + data-i18n)
├── css/styles.css                  única hoja de estilos (temas, alto contraste, componentes)
├── js/
│   ├── common.js                   núcleo EIA: datos, modos, i18n, formatos, componentes, ciclo de vida
│   ├── <módulo>.js                 modelo de vista puro (probado en Node) + pintado
│   ├── lib/                        algoritmos puros: markowitz, nsga2, nsga3, backtest, estadística, señales…
│   ├── workers/                    recálculo fuera del hilo de la interfaz (Modo real)
│   └── a11y/                       panel, bus de entrada, puntero, cámara, cabeza, manos, barrido, voz, sonido
├── i18n/es-PE.json · en-US.json    todos los textos visibles
├── data/                           13 JSON del profesor (no se modifican)
├── data_real/                      mismo esquema con datos reales + cortes/ + precios/
├── pipeline/                       descarga, entrenamiento de modelos, optimización y backtesting (Python)
├── tests/                          unit/ (Node), e2e/ y a11y/ (Playwright + axe), datos/ (Python)
├── tools/validar_contrato.py       validación del contrato de datos en ambos modos
├── figma-src/                      export de Figma Make, sin editar
└── docs/                           contrato de datos, plan, coordinación, auditoría P08
```

Cada módulo sigue el mismo patrón: `EIA.modulo({ id, cargar, pintar })`. Las funciones de «modelo de vista» son puras y tienen pruebas; el pintado vuelve a ejecutarse al cambiar de idioma, modo, tema o corte sin recargar la página. Todas las modalidades de accesibilidad emiten los mismos comandos semánticos a un bus común.

## Empezar

**Requisitos:** un navegador moderno (Chrome o Edge para la voz) y, para servirlo en local, Python 3 o cualquier servidor estático.

```bash
git clone https://github.com/mbaernestocr-tech/ernesto-investing-ai-equipo-a.git
cd ernesto-investing-ai-equipo-a
python -m http.server 8000
```

Abre <http://127.0.0.1:8000>. La cámara y la voz necesitan `localhost` o HTTPS.

Parámetros útiles en la URL: `?modo=real`, `?lang=en-US`, `?t=NVDA` (activo) y `?nivel=Moderado` (Backtesting).

### Regenerar los datos reales (opcional)

```bash
python -m venv .venv
.venv/Scripts/python -m pip install torch==2.15.0 --index-url https://download.pytorch.org/whl/cpu
.venv/Scripts/python -m pip install -r pipeline/requirements.txt
.venv/Scripts/python -m pipeline.ejecutar --salida data_real --modo completo
.venv/Scripts/python tools/validar_contrato.py data_real --modo real
```

El entrenamiento corre en CPU y puede tardar, sobre todo con los 12 cortes. Los detalles (embargo de 30 sesiones, prueba externa de 252 fechas, hiperparámetros y limitaciones) están en [pipeline/README.md](pipeline/README.md).

## Pruebas y calidad

```bash
node --test "tests/unit/*.test.mjs"          # pruebas unitarias del sitio
npm ci --prefix tests --ignore-scripts
npx --prefix tests playwright install chromium
npm --prefix tests run test:e2e              # E2E y axe en ambos temas, modos y anchos
python tools/validar_contrato.py data --modo profesor
```

- **144 pruebas unitarias** de JavaScript, **31 de Python** y **244 casos de navegador** (Playwright + axe sin violaciones *serious* o *critical*) al 17-nov-2026.
- Cada PR pasa por GitHub Actions: pruebas, escaneo de secretos con Gitleaks y la suite E2E. Solo se fusiona con todo en verde.
- La [auditoría P08](docs/informe/auditoria_P08.md) revisa el sistema completo de forma independiente.

## Datos y procedencia

- **Modo profesor (`data/`):** historia y resultados **sintéticos** del curso, al cierre del 11-nov-2026. No se modifican ni se «corrigen». Por ejemplo, en Backtesting las tres carteras pierden frente a SPY y se explica por qué.
- **Modo real (`data_real/`):** precios ajustados de **Yahoo Finance, obtenidos con yfinance** (proyecto no afiliado a Yahoo), con fines educativos. Pueden tener retrasos o errores. Los modelos los entrena el equipo con una prueba temporal externa y embargo. La fecha de corte y la procedencia están en `meta.json`.
- **Actualización automática:** un flujo de GitHub Actions actualiza los datos reales de lunes a viernes a las 22:15 UTC y los cortes cada domingo.
- **Limitaciones declaradas:** la historia ajustada puede revisarse después de un corte, el universo fijo introduce sesgo de supervivencia y los modelos predicen poco (se muestra con honestidad en cada ficha).

## Accesibilidad

El sitio apunta a **WCAG 2.2 AA**. Hay un **Centro de accesibilidad** en la cabecera (`Alt+Shift+A`):

| Modalidad | Cómo |
|---|---|
| Teclado y lector de pantalla | Todo se opera con teclado, foco visible, «Saltar al contenido», regiones vivas y tabla alternativa en cada gráfico |
| Lectura y sonido | Resumen automático de cada gráfico, «Leer en voz alta» y exploración punto a punto con ←/→ y un tono por valor |
| Preferencias visuales | Tamaño de texto, alto contraste, reducir movimiento, espaciado, subrayar enlaces, tramas en gráficos, fuente legible y cursor grande |
| Cabeza | Puntero con la orientación de la cabeza (MediaPipe), calibración de 5 puntos y clic por permanencia, parpadeo largo o boca |
| Manos | Puntero con la mano, pellizco para hacer clic, puño para pausar y «V» con dos dedos para desplazar |
| Un interruptor | Barrido por grupos y elementos con Espacio o Enter |
| Voz | «Ir a clasificación», «activo Apple», «tema oscuro», «clic en…», en español e inglés (`Alt+Shift+V`) |

La cámara y la voz piden consentimiento. La imagen de la cámara se procesa **solo en el navegador**. Para entender la voz, Chrome y Edge envían el audio a su propio servicio de reconocimiento.

La guía paso a paso para usuarios está en [docs/guia-usuario/accesibilidad.md](docs/guia-usuario/accesibilidad.md).

## Entregables

| Entregable | Dónde |
|---|---|
| Informe (PDF, 10 páginas con carátula) | [docs/informe/S13_EquipoA_Informe.pdf](docs/informe/S13_EquipoA_Informe.pdf) · editable en [.docx](docs/informe/S13_EquipoA_Informe.docx) |
| Prompts literales usados | [PROMPTS_USADOS.md](PROMPTS_USADOS.md) |
| Guía de accesibilidad para usuarios | [docs/guia-usuario/accesibilidad.md](docs/guia-usuario/accesibilidad.md) |
| Auditoría P08 | [docs/informe/auditoria_P08.md](docs/informe/auditoria_P08.md) |
| Diseño en Figma Make | [archivo](https://www.figma.com/make/BWA9B3JoRbAWZiVoPSyoBO) · [prototipo navegable](https://misty-umber-07813177.figma.site/) · export sin editar en [`figma-src/`](figma-src/) |
| Capturas del sitio y de Figma | [docs/capturas/](docs/capturas/) |

El informe se regenera con los scripts de [`tools/informe/`](tools/informe/): las cifras se leen de los JSON, no se escriben a mano.

## Créditos y uso de IA

- **Material base y datos sintéticos:** Ernesto D. Cancho-Rodríguez (FISI-UNMSM), bajo [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- **Equipo A, IHC 2026-II:** diseño en Figma, dirección del proyecto y pruebas con usuarios.
- **Asistencia de IA declarada:** el código y los textos se desarrollaron con asistencia de IA (Claude Code y Codex). Todo se ejecutó, verificó y revisó antes de integrarse. Cada commit asistido lleva coautoría y los prompts literales están en [`PROMPTS_USADOS.md`](PROMPTS_USADOS.md) (por herramienta, en [`docs/ia/prompts/`](docs/ia/prompts/)).

## Licencia

El código, los textos y los datos sintéticos del material base se distribuyen bajo [CC BY 4.0](LICENSE). Los datos de Yahoo Finance de `data_real/` **no** se incluyen bajo esa licencia y se usan con fines educativos.
