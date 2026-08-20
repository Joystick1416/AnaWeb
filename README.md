# AnaWeb

Repositorio de clases y sesiones para el curso de **Analítica de la Web**.

## Sinopsis del curso

El curso combina tres bloques temáticos, aplicados siempre "desde cero" (implementando los algoritmos propios, sin depender de librerías que resuelvan el problema directamente):

1. **Fundamentos de algoritmia y eficiencia** — recursión, programación dinámica, complejidad temporal, manejo de I/O de archivos. Sirve de base/nivelación para los bloques siguientes.
2. **Web scraping** — extracción de datos estructurados desde páginas reales (portales de empleo, IMDB, resultados electorales, Wikipedia).
3. **Analítica de texto y de grafos web**:
   - Recuperación de información (IR): vectorización TF / TF-IDF, clasificación por distancia a centroides (coseno/euclidiana).
   - Minería de grafos de enlaces: construcción de matrices de adyacencia y algoritmos de relevancia (PageRank, HITS).

## Contenidos (Controles)

| Control | Tema | Resumen |
|---|---|---|
| [Control0](Controles/Control0.md) | Algoritmia — manipulación de dígitos | Detección de "números similares" (rotación de dígitos), fuerza bruta vs. optimización, generación de archivos de entrada/salida. |
| [Control1](Controles/Control1.md) | Algoritmia — DP y teoría de números | Conteo de formas de subir escaleras (tipo Fibonacci/DP) y conteo de números primos con restricción de tiempo (criba de Eratóstenes). |
| [Control2](Controles/Control2.md) | Web scraping + TF/TF-IDF | Scraping de bolsa de trabajo e IMDB Top 250; vectorización de texto (TF, TF-IDF) y clasificación de películas por categoría según distancia a feature vectors promedio. |
| [Control3](Controles/Control3.md) | Web scraping + clasificación de texto | Scraping de resultados históricos de ONPE; clasificación de wikis en 2 clases usando TF/TF-IDF (con y sin top-N), train/test split y similitud coseno. |
| [Control4](Controles/Control4.md) | Grafos web — PageRank y HITS | Crawling de Wikipedia a 2 niveles, construcción de matriz de adyacencia, cálculo iterativo de PageRank y HITS (autoridad/hub) hasta convergencia, y comparación de rankings. |

## Estructura del repositorio

- `Controles/` — enunciados de los controles pasados, usados como guía de repaso.
- `Clases/` — material de clases (pendiente).
- `Ejercicios/` — ejercicios de práctica (pendiente).

## Herramientas recomendadas (VS Code)

- **[vscode-pdf](https://marketplace.visualstudio.com/items?itemName=tomoki1207.pdf)** — permite abrir y visualizar los PDFs de `PDFs/` directamente en una pestaña del editor, sin salir de VS Code.
- **[Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)** — necesaria para que los diagramas en bloques ` ```mermaid ` (como los de `Clases/Sesión1.md`) se rendericen en la vista previa de Markdown.
