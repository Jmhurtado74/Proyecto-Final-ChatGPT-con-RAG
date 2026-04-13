# Proyecto-Final-ChatGPT-con-RAG
# ChatBot Académico RAG con Ollama + LangChain + Gradio

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Transformers](https://img.shields.io/badge/Transformers-HuggingFace-yellow)
![LangChain](https://img.shields.io/badge/LangChain-RAG-green)
![Ollama](https://img.shields.io/badge/Ollama-LLM-orange)
![FAISS](https://img.shields.io/badge/FAISS-VectorDB-red)
![Gradio](https://img.shields.io/badge/Gradio-UI-lightgrey)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## Descripción

Este proyecto implementa un **ChatBot académico basado en Retrieval-Augmented Generation (RAG)**, integrando modelos generativos con recuperación de información para mejorar la precisión y trazabilidad de las respuestas.

El sistema combina:

* **Recuperación semántica (FAISS + Embeddings)**
* **Modelo generativo local (Ollama - LLaMA 3.2)**
* **Orquestación con LangChain**
* **Interfaz interactiva con Gradio**

El chatbot responde preguntas en español **basándose exclusivamente en documentos recuperados**, evitando alucinaciones y mostrando las fuentes utilizadas.

---

## Objetivo del Proyecto

Desarrollar un chatbot tipo ChatGPT que:

* Utilice una base de conocimiento distinta a la de los notebooks guía
* Implemente correctamente una arquitectura RAG
* Permita interacción conversacional
* Muestre evidencia de las fuentes utilizadas
* Sea reproducible y funcional desde cero

---

## Arquitectura del Sistema

```text
Usuario → Gradio UI → LangChain Chain → Retriever (FAISS)
                                      ↓
                             Embeddings (multilingüe)
                                      ↓
                               Documentos (MAGPIE)
                                      ↓
                          LLM (Ollama - LLaMA 3.2)
                                      ↓
                         Respuesta + Fuentes
```

---

## Dataset

Se utiliza el dataset:

`mrm8488/magpie_llama-3-8b_spanish`

Este dataset permite construir una base de conocimiento en español con contenido estructurado tipo:

* título
* sección
* resumen
* contenido

✔ Esto garantiza un corpus distinto al del notebook base (requisito del proyecto)

---

## Tecnologías utilizadas

| Tecnología  | Uso                     |
| ----------- | ----------------------- |
| Python      | Lenguaje principal      |
| LangChain   | Orquestación RAG        |
| FAISS       | Búsqueda vectorial      |
| HuggingFace | Embeddings              |
| Ollama      | Modelo generativo local |
| Gradio      | Interfaz del chatbot    |
| Pandas      | Procesamiento de datos  |

---

## Ejecución del Proyecto

### Clonar repositorio

```bash
git clone https://github.com/TU_USUARIO/TU_REPO.git
cd TU_REPO
```

---

### Instalar dependencias

```bash
pip install -r requirements.txt
```

---

### Instalar Ollama

Descargar desde:

https://ollama.com/download

---

### Ejecutar servidor

```bash
ollama serve
```

---

### Descargar modelo

```bash
ollama pull llama3.2:3b
```

---

### Ejecutar notebook

```bash
jupyter notebook
```

---

## Uso del ChatBot

El sistema permite:

* hacer preguntas en lenguaje natural
* recibir respuestas contextualizadas
* visualizar fuentes utilizadas
* mantener conversación multi-turno

Ejemplo:

```text
Usuario: ¿Qué es la inteligencia artificial?
Chatbot: ...
Fuentes:
- Documento 1
- Documento 2
```

---

## Evaluación

Se implementaron:

* ✔ Evaluación cualitativa (comparación de respuestas)
* ✔ Evaluación del retriever (top-k documentos)
* ✔ Pruebas multi-turno
* ✔ Visualización del corpus

---

## Resultados

* El modelo responde correctamente cuando la información está en el corpus
* Se reduce la alucinación gracias al uso de RAG
* La calidad depende principalmente del retriever
* La memoria conversacional mejora la coherencia del diálogo

---

## Limitaciones

* Dependencia de Ollama (requiere entorno local)
* Dataset generalista (no especializado)
* Sin reranking avanzado
* No se implementa evaluación cuantitativa formal

---

## Trabajo futuro

* Implementar reranking
* Mejorar chunking
* Usar datasets especializados
* Evaluación automática de respuestas
* Despliegue en producción

---

## Video demostración

https://youtu.be/aBkdelmI9Q0

Debe mostrar:

* ejecución del chatbot
* preguntas y respuestas
* evidencia de fuentes

---

## Autor

**Juan Manuel Hurtado Angulo / Manuel Alberto González González / William Alberto Reina García**
Maestría en Inteligencia Artificial Aplicada
Universidad ICESI

---

## Docente

**MSc. Luis Eduardo Ferro Diez**
Maestría en Inteligencia Artificial Aplicada
Universidad ICESI

---

## Licencia

Este proyecto es de uso académico.

---

## Conclusión

Este proyecto demuestra cómo un modelo generativo puede ser mejorado significativamente mediante la integración con sistemas de recuperación de información, permitiendo construir asistentes más confiables, explicables y alineados con el conocimiento disponible.
