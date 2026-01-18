# Integrating Web Data into AI Knowledge Graphs

This repository contains two end-to-end implementations of a web-powered knowledge graph pipeline:

1. A manual pipeline that extracts, processes, and models web data using open-source tools

2. An automated pipeline that shortens time-to-graph using Diffbot’s AI-driven extraction

Both projects demonstrate how live web data can be transformed into a queryable Neo4j knowledge graph and integrated into LLM-powered question-answering (RAG) workflows.

## Why This Project Exists

Large Language Models are powerful, but they lack:

1. Freshness

2. Explicit structure

3. Traceability of facts

Knowledge graphs solve this by storing entities and relationships explicitly, while web data ensures the graph stays relevant and up-to-date.


## Project Overview
**Core Use Case**

A company information knowledge graph that answers questions such as:

- “Which company does Satya Nadella own?”

- “Where is Nvidia located?”

- “Which organizations is Elon Musk associated with?”

This graph is designed to serve as a retrieval layer for RAG systems.

### Project A: Manual Web-to-Graph Pipeline (Without Diffbot)

This implementation builds the entire pipeline step by step, giving you full control over each stage.
| Stage                      | Tool                                              |
| -------------------------- | ------------------------------------------------- |
| Web data extraction        | Wikipedia API                                     |
| NLP / NER                  | Hugging Face Transformers (`dslim/bert-base-NER`) |
| Data handling              | Python, Pandas                                    |
| Graph storage              | Neo4j AuraDB                                      |
| Graph queries              | Cypher                                            |
| Natural language interface | OpenAI GPT-4.1                                    |
| Visualization              | PyVis                                             |
| Automation (optional)      | Prefect                                           |

### Project B: Automated Web-to-Graph Pipeline (With Diffbot)

This implementation removes most of the manual steps by using Diffbot’s AI-driven extraction and graph transformation.
| Stage                | Tool                              |
| -------------------- | --------------------------------- |
| Web extraction + NLP | Diffbot APIs                      |
| Graph transformation | LangChain DiffbotGraphTransformer |
| Graph storage        | Neo4j AuraDB                      |
| Querying             | LangChain + GPT-4.1               |

#### What Diffbot Automates

Diffbot replaces:

- Manual scraping

- Data preprocessing

- Named entity recognition

- Relationship extraction

It directly outputs graph-ready documents.

### Key Design Decisions

- Property graph model chosen for flexibility

- Provenance tracking added for auditability

- Incremental updates preferred over full rebuilds

- LLM + graph hybrid querying for explainability
