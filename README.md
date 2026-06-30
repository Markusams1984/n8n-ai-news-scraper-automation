# 📰 Automatización de Scraping de Noticias con IA (n8n + OpenAI + Firecrawl)

Este repositorio contiene un flujo de trabajo avanzado de n8n diseñado para extraer, filtrar, analizar y consolidar noticias desde feeds RSS utilizando Inteligencia Artificial y Web Scraping profundo.

## 🎯 Objetivo del Proyecto
Automatizar la vigilancia tecnológica e informativa. El sistema lee un listado de fuentes (URLs), filtra el ruido mediante IA, extrae el texto completo de las noticias relevantes, y genera reportes consolidados listos para consumo humano en Google Docs y Google Sheets.

## 🏗️ Arquitectura y Tecnologías
* **Orquestador:** n8n
* **Web Scraping:** Firecrawl API
* **Procesamiento de Lenguaje Natural (NLP):** OpenAI (GPT-4/GPT-3.5)
* **Almacenamiento y Reportes:** Google Workspace (Docs & Sheets)

## 💡 Características Clave (Nivel Senior)

1. **Diseño Modular y Desacoplado:** Las fuentes de entrada (URLs) se gestionan desde un Google Sheet (`urls_config`), permitiendo a usuarios no técnicos agregar o modificar fuentes sin tocar el código de n8n.
2. **Optimización de Costos de API:** Implementación de un procesamiento de IA en dos fases. Primero, un filtrado ligero para descartar noticias irrelevantes, y segundo, un procesamiento profundo (resumen y formateo) exclusivo para las noticias validadas.
3. **Resiliencia y Manejo de Errores (Tolerancia a Fallos):** El nodo de scraping (Firecrawl) está configurado con reintentos automáticos y un enrutamiento condicional (`If Node`). Si una URL falla o da timeout, el error es capturado silenciosamente y descartado, permitiendo que el workflow continúe procesando el resto de las noticias sin interrupciones.

## 📸 Demostración Visual

*Arquitectura del Workflow en n8n:*
![Workflow de n8n](n8n%20Vista%20previa.png)

*Resultado Consolidado en Google Docs:*
![Reporte Google Docs](n8n%20resultado%201.png)

## 🚀 Cómo instalar este workflow

1. Clona este repositorio o descarga el archivo `n8n_ai_news_scraper.json`.
2. En tu instancia de n8n, ve a **Workflows > Import from File** y selecciona el archivo JSON.
3. Configura tus credenciales (Ver sección de Credenciales).
4. Activa el flujo.
