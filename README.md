# Hi, I'm Gabriel Lima Nunes

M.Sc. student in Computer Science (AI) at the **Federal University of Minas Gerais (UFMG)**, Brazil, and research fellow at **Kunumi**.
I work where **HPC, LLM systems and machine learning** meet: making many models share scarce GPUs, building and evaluating LLM pipelines and agents, and training models that need fewer labels and less compute.

## What I'm working on now

**Multi-LLM serving on shared GPUs** ([prism-research](https://github.com/gabrielliman/prism-research/tree/vllm-backend)), my M.Sc. research.
I extend and stress-test [Prism](https://arxiv.org/abs/2505.04021), an open-source system that serves many LLMs on one or more GPUs by time-sharing or splitting memory (SGLang + kvcached). Experiments run on NVIDIA H200 GPUs through a Polyaxon cluster.

- **vLLM engine backend** with a persistent worker pool and tensor parallelism (TP=2): completed requests went from 62% to **100%** on the 2-GPU example, with latency on par with SGLang.
- **Model eviction policies** evaluated over 57+ runs on replayed request traces: **p90 TTFT 53 s → 0.6 s** and SLO attainment 51% → 90%. A throughput-per-GB swap policy was the only setup that served 100% of requests in every scenario.
- **Out-of-memory robustness:** diagnosed five failure modes (crashed workers, OOM server crashes, full stalls) and fixed them on the Prism side, with dead-worker failover in ~4 s, OOM rollback and a cross-process memory arbiter. A memory-pressure scenario went from 70/337 requests with a server crash to **337/337**.

Every experiment has a dated report with the scripts and commands to reproduce it.

## Featured projects

| Project | What it is |
|---|---|
| [**prism-research**](https://github.com/gabrielliman/prism-research/tree/vllm-backend) | Research fork of Prism: vLLM backend, eviction policies and memory-robustness fixes for multi-LLM serving. |
| [**isadg-agents**](https://github.com/gabrielliman/isadg-agents) | Multi-agent pipeline (LangChain) with 4 specialized LLM/VLM agents (vision OCR, semantic router, normalizer, RAG archivist) that catalogs 19th-century documents under the ISAD(G) archival standard. 95–99% word-level OCR accuracy on 917 pages, with retries, self-healing and per-agent latency profiling. |
| [**VoxLab**](https://github.com/gabrielliman/VoxLab) | Reproducible LLM evaluation of stance-change detection in Brazilian public hearings: a contrast set checked by LLM verifiers, 7 open-weight models × 5 prompting architectures, frozen prompts and a content-hashed response cache so the whole study replays in under a minute with no API calls. |
| [**seismic-fsss**](https://github.com/gabrielliman/seismic-fsss) | PyTorch pipeline for episodic few-shot segmentation of 3D seismic volumes, with configurable data partitioning and support-selection strategies. |
| [**Seismic-Segmentation-Framework**](https://github.com/gabrielliman/Seismic-Segmentation-Framework) | TensorFlow benchmark that unifies training and evaluation of deep learning models for seismic facies segmentation. |

## Publications

- **G. L. Nunes** et al. *Spatial Data Partitioning and Support Locality in Few-Shot Seismic Facies Segmentation.* First author, 2026 (submitted).
- G. Amarante, M. T. P. Souza, **G. Lima** et al. *Enhancing Minority Class Recovery in High Resolution Land Cover Mapping with Dynamic Imbalance Aware Oversampling.* **Scientific Reports**, 2026. [doi:10.1038/s41598-026-52071-z](https://doi.org/10.1038/s41598-026-52071-z)
- L. M. Laboissiere, **G. L. Nunes**, C. T. Cunha. *Comparability Between Statements of the Same Actor: A Contrast Set for Stance-Change Detection with LLMs.* 1st Kunumi Data Challenge, 2026.
- **G. Lima** et al. *A Systematic Evaluation Methodology of Deep Learning on Seismic Facies Classification.* First author, **Earth Science Informatics**, 2025. [doi:10.1007/s12145-025-02024-3](https://doi.org/10.1007/s12145-025-02024-3)

## Tools I use

- **LLM systems:** vLLM, SGLang, KV-cache management, tensor parallelism, LangChain, RAG (ChromaDB)
- **ML:** Python, PyTorch, TensorFlow, sentence-transformers
- **HPC & infrastructure:** CUDA GPUs, Polyaxon, Docker, Kafka, Linux

## Get in touch

I'm interested in work on **LLM inference and serving, HPC and ML systems**.
Email: gabrielliman2002@gmail.com
