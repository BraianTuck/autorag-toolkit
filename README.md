# 🚀 AutoRAG Toolkit

![AutoRAG Logo](https://raw.githubusercontent.com/BraianTuck/autorag-toolkit/main/assets/autorag-logo.png)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Docker](https://img.shields.io/badge/Docker-Supported-blue)](https://www.docker.com/)

## 📋 Descripción

AutoRAG Toolkit es una herramienta avanzada para optimizar automáticamente pipelines de Retrieval Augmented Generation (RAG). Esta herramienta permite encontrar la configuración óptima de RAG para tus datos específicos, evaluando diferentes combinaciones de componentes y parámetros para maximizar el rendimiento.

## 🌟 Características Principales

- **Optimización Automática**: Encuentra la mejor combinación de componentes RAG para tu caso de uso específico.
- **Evaluación Integral**: Evalúa tus pipelines RAG con múltiples métricas de rendimiento.
- **Procesamiento de Datos**: Herramientas para parsear, dividir y preparar tus documentos.
- **Generación de Datos de Prueba**: Crea conjuntos de datos de preguntas y respuestas para evaluar tus pipelines.
- **Interfaz Gráfica**: Panel de control visual para monitorear y analizar resultados.
- **Despliegue Sencillo**: Implementa fácilmente tu pipeline optimizado en producción.

## 🛠️ Componentes del Pipeline RAG

AutoRAG Toolkit optimiza cada componente del pipeline RAG:

1. **Parsing**: Extracción de texto de diferentes formatos de documentos.
2. **Chunking**: División inteligente de documentos en fragmentos manejables.
3. **Embedding**: Selección del mejor modelo de embedding para tus datos.
4. **Indexing**: Optimización de estructuras de índices vectoriales.
5. **Retrieval**: Ajuste de estrategias de recuperación de información.
6. **Reranking**: Refinamiento de resultados de búsqueda.
7. **Generation**: Configuración óptima para la generación de respuestas.

## 🚀 Instalación

### Usando pip

```bash
pip install autorag-toolkit
```

### Usando Docker

```bash
# Clonar el repositorio
git clone https://github.com/BraianTuck/autorag-toolkit.git
cd autorag-toolkit

# Iniciar con Docker Compose
docker compose up -d
```

## 📊 Flujo de Trabajo

1. **Preparación de Datos**:
   ```python
   from autorag_toolkit import DataProcessor
   
   processor = DataProcessor()
   corpus = processor.parse_documents("ruta/a/documentos")
   chunks = processor.chunk_documents(corpus)
   qa_pairs = processor.generate_qa_pairs(chunks)
   ```

2. **Optimización del Pipeline**:
   ```python
   from autorag_toolkit import Optimizer
   
   optimizer = Optimizer(
       qa_data=qa_pairs,
       corpus_data=chunks,
       metrics=["relevance", "faithfulness", "answer_correctness"]
   )
   
   results = optimizer.run()
   best_pipeline = results.get_best_pipeline()
   ```

3. **Despliegue**:
   ```python
   from autorag_toolkit import Deployer
   
   deployer = Deployer(pipeline=best_pipeline)
   deployer.deploy(host="0.0.0.0", port=8000)
   ```

## 📈 Métricas de Evaluación

AutoRAG Toolkit evalúa los pipelines RAG utilizando diversas métricas:

- **Relevancia**: Evalúa si los documentos recuperados son relevantes para la consulta.
- **Fidelidad**: Verifica si la respuesta generada se basa fielmente en los documentos recuperados.
- **Corrección**: Compara la respuesta generada con la respuesta correcta.
- **Latencia**: Mide el tiempo de respuesta del pipeline.
- **Diversidad**: Evalúa la variedad de información en los documentos recuperados.

## 🖥️ Interfaz Gráfica

AutoRAG Toolkit incluye una interfaz web para:

- Configurar y ejecutar experimentos
- Visualizar resultados y comparar pipelines
- Analizar métricas detalladas
- Probar interactivamente los pipelines optimizados

Para acceder a la interfaz:

```bash
autorag-toolkit dashboard --port 3000
```

O visita `http://localhost:3000` si estás usando Docker.

## 📚 Ejemplos de Uso

### Caso de Uso: Documentación Técnica

```python
from autorag_toolkit import AutoRAG

# Configurar el experimento
experiment = AutoRAG(
    data_path="./datos_tecnicos",
    experiment_name="optimizacion_docs_tecnicos",
    embedding_models=["sentence-transformers/all-MiniLM-L6-v2", "openai/text-embedding-3-small"],
    retrieval_methods=["vector_search", "hybrid_search"],
    llm_models=["gpt-3.5-turbo", "llama-3-8b"]
)

# Ejecutar la optimización
experiment.run()

# Obtener el mejor pipeline
best_pipeline = experiment.get_best_pipeline()
```

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Si deseas contribuir:

1. Haz un fork del repositorio
2. Crea una rama para tu característica (`git checkout -b feature/nueva-caracteristica`)
3. Haz commit de tus cambios (`git commit -m 'Añadir nueva característica'`)
4. Haz push a la rama (`git push origin feature/nueva-caracteristica`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

## 📞 Contacto

Para preguntas o soporte, por favor abre un issue en este repositorio o contacta al equipo de desarrollo.

---

⭐ Si encuentras útil este proyecto, ¡no olvides darle una estrella en GitHub! ⭐