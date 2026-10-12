# Awesome PII Redaction

> A curated list of libraries, models, datasets, and resources for detecting, redacting, and anonymizing Personally Identifiable Information (PII).

PII appears wherever user input does - chat logs, support tickets, training corpora, clinical notes, telemetry, code. Removing it well is a prerequisite for GDPR, HIPAA, the EU AI Act, PCI DSS, and not leaking your users' data to an LLM.

## Contents

- [Libraries](#libraries)
- [Models](#models)
- [Datasets](#datasets)
- [Benchmarks](#benchmarks)
- [Differential Privacy](#differential-privacy)
- [Secrets Scanning](#secrets-scanning)
- [Standards & Regulations](#standards--regulations)
- [Hosted Services](#hosted-services)
- [Papers](#papers)
- [Tutorials & Demos](#tutorials--demos)
- [Books](#books)

## Libraries

### General-Purpose

- [Microsoft Presidio](https://github.com/microsoft/presidio) - The de-facto open-source PII SDK for text, images, and structured data. <img src="https://img.shields.io/github/stars/microsoft/presidio?style=social" align="center">
- [scrubadub](https://github.com/LeapBeyond/scrubadub) - Locale-aware Python scrubber for names, emails, phones, SSNs. <img src="https://img.shields.io/github/stars/LeapBeyond/scrubadub?style=social" align="center">
- [DataFog](https://github.com/DataFog/datafog-python) - Regex + spaCy/GLiNER pipeline for PII in text and images. <img src="https://img.shields.io/github/stars/DataFog/datafog-python?style=social" align="center">
- [PII-Codex](https://github.com/EdyVision/pii-codex) - PII detection with risk scoring, built on Presidio. <img src="https://img.shields.io/github/stars/EdyVision/pii-codex?style=social" align="center">
- [HydroXai/pii-masker](https://github.com/HydroXai/pii-masker) - DeBERTa-v3-based masker with a 1024-token window. <img src="https://img.shields.io/github/stars/HydroXai/pii-masker?style=social" align="center">
- [OpenAI Privacy Filter](https://github.com/openai/privacy-filter) - Bidirectional token classifier for context-aware masking, 128k context. <img src="https://img.shields.io/github/stars/openai/privacy-filter?style=social" align="center">
- [OpenPipe pii-redaction](https://github.com/OpenPipe/pii-redaction) - Local LLM-driven redactor for cleaning fine-tuning data. <img src="https://img.shields.io/github/stars/OpenPipe/pii-redaction?style=social" align="center">
- [Phileas](https://github.com/philterd/phileas) / [Philter](https://github.com/philterd/philter) - JVM redaction engine with policy-driven replacement and a REST front-end. <img src="https://img.shields.io/github/stars/philterd/phileas?style=social" align="center">
- [PIISA pii-extract-base](https://github.com/piisa/pii-extract-base) / [pii-process](https://github.com/piisa/pii-process) - Modular PII pipeline following the PIISA spec. <img src="https://img.shields.io/github/stars/piisa/pii-extract-base?style=social" align="center">
- [thoughtworks/pii-anonymizer](https://github.com/thoughtworks/pii-anonymizer) - PII identification, anonymization, and de-anonymization. <img src="https://img.shields.io/github/stars/thoughtworks/pii-anonymizer?style=social" align="center">
- [worka-ai/pii](https://github.com/worka-ai/pii) - Deterministic CPU-only PII library in Rust. <img src="https://img.shields.io/github/stars/worka-ai/pii?style=social" align="center">
- [Faker](https://github.com/joke2k/faker) - Synthetic-data generator across 50+ locales. <img src="https://img.shields.io/github/stars/joke2k/faker?style=social" align="center">

### LLM Guardrails

- [LLM Guard](https://github.com/protectai/llm-guard) - Anonymize/Deanonymize and other scanners for LLM apps. <img src="https://img.shields.io/github/stars/protectai/llm-guard?style=social" align="center">
- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) - NVIDIA's programmable guardrails with Presidio integration. <img src="https://img.shields.io/github/stars/NVIDIA/NeMo-Guardrails?style=social" align="center">
- [Guardrails AI](https://github.com/guardrails-ai/guardrails) - Validator-based input/output Guards (see also [guardrails_pii](https://github.com/guardrails-ai/guardrails_pii)). <img src="https://img.shields.io/github/stars/guardrails-ai/guardrails?style=social" align="center">
- [Llama Guard / PurpleLlama](https://github.com/meta-llama/PurpleLlama) - Meta's content-safety classifiers, useful as a final PII filter. <img src="https://img.shields.io/github/stars/meta-llama/PurpleLlama?style=social" align="center">
- [LiteLLM](https://github.com/BerriAI/litellm) - LLM proxy with built-in [Presidio guardrail](https://docs.litellm.ai/docs/tutorials/presidio_pii_masking). <img src="https://img.shields.io/github/stars/BerriAI/litellm?style=social" align="center">
- [anonipy](https://github.com/eriknovak/anonipy) - LLM-powered anonymization with consistent pseudonymization. <img src="https://img.shields.io/github/stars/eriknovak/anonipy?style=social" align="center">
- [anonLLM](https://github.com/fsndzomga/anonLLM) - Anonymizes prompts before they hit the API; reverses on response. <img src="https://img.shields.io/github/stars/fsndzomga/anonLLM?style=social" align="center">
- [Promptfoo](https://github.com/promptfoo/promptfoo) - LLM eval and red-team CLI; probes for PII leaks. <img src="https://img.shields.io/github/stars/promptfoo/promptfoo?style=social" align="center">
- [openai-guardrails-python](https://github.com/openai/openai-guardrails-python) - Drop-in OpenAI client wrapper with safety/PII guardrails. <img src="https://img.shields.io/github/stars/openai/openai-guardrails-python?style=social" align="center">

### Database & Structured Data

- [Greenmask](https://github.com/GreenmaskIO/greenmask) - Stateless Postgres/MySQL anonymizer; drop-in `pg_dump` replacement. <img src="https://img.shields.io/github/stars/GreenmaskIO/greenmask?style=social" align="center">
- [Neosync](https://github.com/nucleuscloud/neosync) - PII anonymization, synthetic data, and environment sync with referential integrity. <img src="https://img.shields.io/github/stars/nucleuscloud/neosync?style=social" align="center">
- [ARX](https://github.com/arx-deidentifier/arx) - k-anonymity, l-diversity, t-closeness, and DP with risk analysis and a GUI. <img src="https://img.shields.io/github/stars/arx-deidentifier/arx?style=social" align="center">
- [PostgreSQL Anonymizer](https://gitlab.com/dalibo/postgresql_anonymizer) - Postgres extension for declarative masking and pseudonymization.
- [pg-anonymizer](https://github.com/rap2hpoutre/pg-anonymizer) - Node.js CLI for streaming anonymized Postgres dumps. <img src="https://img.shields.io/github/stars/rap2hpoutre/pg-anonymizer?style=social" align="center">
- [Anonimatron](https://github.com/realrolfje/anonimatron) - Java tool with persistent synonyms across copies. <img src="https://img.shields.io/github/stars/realrolfje/anonimatron?style=social" align="center">
- [PIICatcher](https://github.com/tokern/piicatcher) - Scans Postgres, Snowflake, Redshift, Athena, and BigQuery for PII. <img src="https://img.shields.io/github/stars/tokern/piicatcher?style=social" align="center">
- [pdscan](https://github.com/ankane/pdscan) - Fast Go scanner for unencrypted personal data across DBs and files. <img src="https://img.shields.io/github/stars/ankane/pdscan?style=social" align="center">
- [anjana](https://github.com/IFCA-Advanced-Computing/anjana) - Python implementations of k-anonymity, l-diversity, t-closeness. <img src="https://img.shields.io/github/stars/IFCA-Advanced-Computing/anjana?style=social" align="center">

### Image, OCR & Documents

- [presidio-image-redactor](https://microsoft.github.io/presidio/image-redactor/) - Presidio's OCR-driven image and DICOM redactor.
- [Octopii](https://github.com/redhuntlabs/Octopii) - AI-powered scanner for IDs, passports, and faces in documents and images. <img src="https://img.shields.io/github/stars/redhuntlabs/Octopii?style=social" align="center">
- [pydicom/deid](https://github.com/pydicom/deid) - DICOM header and pixel anonymization with policy-driven rules. <img src="https://img.shields.io/github/stars/pydicom/deid?style=social" align="center">
- [dicognito](https://github.com/blairconrad/dicognito) - DICOM anonymizer that preserves study/series grouping. <img src="https://img.shields.io/github/stars/blairconrad/dicognito?style=social" align="center">
- [doc_redaction](https://github.com/seanpedrick-case/doc_redaction) - GUI tool for redacting PDFs, images, Word, and CSV/XLSX. <img src="https://img.shields.io/github/stars/seanpedrick-case/doc_redaction?style=social" align="center">

### Healthcare / Clinical

- [Microsoft Tools-for-Health-Data-Anonymization](https://github.com/microsoft/Tools-for-Health-Data-Anonymization) - De-identification for FHIR and DICOM. <img src="https://img.shields.io/github/stars/microsoft/Tools-for-Health-Data-Anonymization?style=social" align="center">
- [Philter (UCSF)](https://github.com/BCHSI/philter-ucsf) - Open-source clinical-text PHI de-identifier. <img src="https://img.shields.io/github/stars/BCHSI/philter-ucsf?style=social" align="center">
- [philter-lite](https://github.com/SironaMedical/philter-lite) - Production-oriented refactor of Philter. <img src="https://img.shields.io/github/stars/SironaMedical/philter-lite?style=social" align="center">
- [pyDeid](https://github.com/GEMINI-Medicine/pyDeid) - Python rewrite of the PhysioNet Perl PHI de-identifier. <img src="https://img.shields.io/github/stars/GEMINI-Medicine/pyDeid?style=social" align="center">
- [obi/ehr_deidentification](https://github.com/obi-ml-public/ehr_deidentification) - Transformer-based de-identification of EHR notes. <img src="https://img.shields.io/github/stars/obi-ml-public/ehr_deidentification?style=social" align="center">
- [DEDUCE](https://github.com/vmenger/deduce) - Pattern-matching de-identifier for Dutch medical text. <img src="https://img.shields.io/github/stars/vmenger/deduce?style=social" align="center">
- [nedap/deidentify](https://github.com/nedap/deidentify) - Clinical de-identification with Dutch pre-trained models. <img src="https://img.shields.io/github/stars/nedap/deidentify?style=social" align="center">
- [CRATE](https://github.com/ucam-department-of-psychiatry/crate) - End-to-end clinical research-DB de-id pipeline. <img src="https://img.shields.io/github/stars/ucam-department-of-psychiatry/crate?style=social" align="center">
- [medspaCy](https://github.com/medspacy/medspacy) - Clinical NLP toolkit, common substrate for PHI pipelines. <img src="https://img.shields.io/github/stars/medspacy/medspacy?style=social" align="center">
- [Synthea](https://github.com/synthetichealth/synthea) - Synthetic FHIR/CCDA/CSV patient generator. <img src="https://img.shields.io/github/stars/synthetichealth/synthea?style=social" align="center">

### Pseudonymization & Synthetic Data

- [Mimesis](https://github.com/lk-geimfari/mimesis) - High-performance Python synthetic-data generator across 46 locales. <img src="https://img.shields.io/github/stars/lk-geimfari/mimesis?style=social" align="center">
- [SDV](https://github.com/sdv-dev/SDV) - Tabular, relational, and sequential synthetic data with constraints. <img src="https://img.shields.io/github/stars/sdv-dev/SDV?style=social" align="center">
- [MOSTLY AI SDK](https://github.com/mostly-ai/mostlyai) - High-fidelity synthetic data with differential privacy. <img src="https://img.shields.io/github/stars/mostly-ai/mostlyai?style=social" align="center">
- [veil](https://github.com/primait/veil) - Rust derive macro for safe `Debug` redaction. <img src="https://img.shields.io/github/stars/primait/veil?style=social" align="center">
- [redacter-rs](https://github.com/abdolence/redacter-rs) - Rust CLI to copy and redact files across cloud storage. <img src="https://img.shields.io/github/stars/abdolence/redacter-rs?style=social" align="center">
- [cockroachdb/redact](https://github.com/cockroachdb/redact) - Go package separating safe vs unsafe data for log redaction. <img src="https://img.shields.io/github/stars/cockroachdb/redact?style=social" align="center">
- [logstop](https://github.com/ankane/logstop) - Ruby gem keeping personal data out of Rails logs (also [Python port](https://github.com/ankane/logstop.py)). <img src="https://img.shields.io/github/stars/ankane/logstop?style=social" align="center">
- [redact-pii](https://github.com/solvvy/redact-pii) - Node.js library; regex + optional Google DLP. <img src="https://img.shields.io/github/stars/solvvy/redact-pii?style=social" align="center">
- [redactomatic](https://github.com/eisenzopf/redactomatic) - CLI for redacting PII in conversation/voice transcripts. <img src="https://img.shields.io/github/stars/eisenzopf/redactomatic?style=social" align="center">
- [MASCHERA](https://github.com/semprerudi/maschera) - Reversible pseudonymization of Swiss documents (de/fr/it/en) with checksum-validated Swiss identifiers (AHV, UID, IBAN, EGID) and a local ModernBERT model; desktop app and Docker. <img src="https://img.shields.io/github/stars/semprerudi/maschera?style=social" align="center">

## Models

### Multilingual

- [bardsai/eu-pii-anonimization-multilang](https://huggingface.co/bardsai/eu-pii-anonimization-multilang) - 24 EU languages, 36 entity types incl. GDPR Art. 9 special categories. [Demo](https://eu-pii.bards.ai/).
- [urchade/gliner_multi_pii-v1](https://huggingface.co/urchade/gliner_multi_pii-v1) - Zero-shot, 50+ PII labels, 6 languages.
- [iiiorg/piiranha-v1](https://huggingface.co/iiiorg/piiranha-v1-detect-personal-information) - 17 PII types across 6 languages. CC-BY-NC-ND.
- [knowledgator/gliner-pii-base-v1.0](https://huggingface.co/knowledgator/gliner-pii-base-v1.0) - 60+ PII/PHI/PCI categories with ONNX FP16/UINT8.
- [knowledgator/gliner-pii-edge-v1.0](https://huggingface.co/knowledgator/gliner-pii-edge-v1.0) - Edge-optimized GLiNER PII variant.
- [betterdataai/PII_DETECTION_MODEL](https://huggingface.co/betterdataai/PII_DETECTION_MODEL) - Qwen2-0.5B causal LM, 7 languages, 29 PII tags.
- [Babelscape/wikineural-multilingual-ner](https://huggingface.co/Babelscape/wikineural-multilingual-ner) - General multilingual NER (mBERT) over 9 languages.
- [Davlan/distilbert-base-multilingual-cased-ner-hrl](https://huggingface.co/Davlan/distilbert-base-multilingual-cased-ner-hrl) - DistilBERT NER over 10 high-resource languages.
- [semprerudi/maschera-ch-v63b](https://huggingface.co/semprerudi/maschera-ch-v63b) - 45 entity types in German, French, Italian and English, incl. Swiss identifiers; trained on synthetic Swiss documents only. MIT.

### English

- [lakshyakh93/deberta_finetuned_pii](https://huggingface.co/lakshyakh93/deberta_finetuned_pii) - DeBERTa, 15+ PII categories incl. crypto and VIN/IMEI.
- [Isotonic/deberta-v3-base_finetuned_ai4privacy_v2](https://huggingface.co/Isotonic/deberta-v3-base_finetuned_ai4privacy_v2) - DeBERTa-v3, F1 0.976 over 54 PII classes.
- [Isotonic/distilbert_finetuned_ai4privacy_v2](https://huggingface.co/Isotonic/distilbert_finetuned_ai4privacy_v2) - DistilBERT (66M) edge variant.
- [ab-ai/pii_model](https://huggingface.co/ab-ai/pii_model) - bert-base-cased over 33 PII categories.
- [dslim/bert-base-NER](https://huggingface.co/dslim/bert-base-NER) - The most-downloaded English NER baseline.
- [Jean-Baptiste/roberta-large-ner-english](https://huggingface.co/Jean-Baptiste/roberta-large-ner-english) - RoBERTa-large NER tested on emails and chat.
- [LiquidAI/LFM2-350M-PII-Extract-JP](https://huggingface.co/LiquidAI/LFM2-350M-PII-Extract-JP) - Japanese PII extractor producing structured JSON.

### Healthcare / PHI

- [obi/deid_roberta_i2b2](https://huggingface.co/obi/deid_roberta_i2b2) - RoBERTa-large on i2b2 2014 (11 PHI categories).
- [StanfordAIMI/stanford-deidentifier-base](https://huggingface.co/StanfordAIMI/stanford-deidentifier-base) - PubMedBERT-based PHI detector for radiology.
- [OpenMed PII SuperClinical Large](https://huggingface.co/OpenMed/OpenMed-PII-SuperClinical-Large-434M-v1) - DeBERTa-v3-large, 54 PII types incl. HIPAA MRNs.
- [OpenMed PII SuperClinical Small](https://huggingface.co/OpenMed/OpenMed-PII-SuperClinical-Small-44M-v1) - 44M-param edge sibling.
- [OpenMed PII Portuguese SnowflakeMed](https://huggingface.co/OpenMed/OpenMed-PII-Portuguese-SnowflakeMed-Large-568M-v1) - Portuguese clinical PII model.

### Zero-Shot / GLiNER

- [urchade/gliner_multi-v2.1](https://huggingface.co/urchade/gliner_multi-v2.1) - Multilingual GLiNER base.
- [urchade/gliner_large-v2](https://huggingface.co/urchade/gliner_large-v2) - English GLiNER-large.
- [nvidia/gliner-PII](https://huggingface.co/nvidia/gliner-PII) - GLiNER (570M) fine-tuned on Nemotron-PII.
- [knowledgator/gliner-multitask-large-v0.5](https://huggingface.co/knowledgator/gliner-multitask-large-v0.5) - Multi-task GLiNER (NER + relation + QA + sentiment).

### Code & Secrets

- [bigcode/starpii](https://huggingface.co/bigcode/starpii) - Encoder NER for PII inside source code, used to clean The Stack.

## Datasets

- [ai4privacy/pii-masking-300k](https://huggingface.co/datasets/ai4privacy/pii-masking-300k) - 225k examples, 6 languages, 27 PII classes.
- [ai4privacy/pii-masking-400k](https://huggingface.co/datasets/ai4privacy/pii-masking-400k) - 407k-row successor.
- [ai4privacy/pii-masking-200k](https://huggingface.co/datasets/ai4privacy/pii-masking-200k) - 209k rows, 4 languages, 54 PII classes.
- [nvidia/Nemotron-PII](https://huggingface.co/datasets/nvidia/Nemotron-PII) - 200k English examples across 30 industry domains.
- [Babelscape/multinerd](https://huggingface.co/datasets/Babelscape/multinerd) - 3.35M rows, 10 languages, 15 entity types.
- [urchade/synthetic-pii-ner-mistral-v1](https://huggingface.co/datasets/urchade/synthetic-pii-ner-mistral-v1) - LLM-synthesized PII training data (5 languages).
- [bigcode/bigcode-pii-dataset](https://huggingface.co/datasets/bigcode/bigcode-pii-dataset) - 12k annotated code samples across 31 languages. Gated.
- [Text Anonymization Benchmark (TAB)](https://github.com/NorskRegnesentral/text-anonymization-benchmark) - 1,268 ECHR cases annotated for evaluating anonymization. <img src="https://img.shields.io/github/stars/NorskRegnesentral/text-anonymization-benchmark?style=social" align="center">
- [n2c2 / i2b2 De-identification](https://n2c2.dbmi.hms.harvard.edu/data-sets) - The de facto medical de-id benchmarks. DUA required.
- [bigbio/n2c2_2014_deid](https://huggingface.co/datasets/bigbio/n2c2_2014_deid) - HF mirror of the 2014 i2b2 track.
- [CoNLL-2003](https://huggingface.co/datasets/eriktks/conll2003) - Canonical English/German NER benchmark.
- [OntoNotes 5.0](https://catalog.ldc.upenn.edu/LDC2013T19) - Multi-genre 18-entity corpus.
- [MultiCoNER v2](https://multiconer.github.io/) - 33 fine-grained entity classes across 12 languages.

## Benchmarks

- [PII-Bench (2025)](https://arxiv.org/abs/2502.18545) - 2,842 samples, 55 PII categories.
- [PII-Scope](https://arxiv.org/abs/2410.06704) - Training-data PII leakage benchmark.
- [PrivLM-Bench](https://arxiv.org/abs/2311.04044) - Multi-level privacy evaluation across LMs.
- [LLM-PBE (VLDB 2024)](https://www.vldb.org/pvldb/vol17/p3201-li.pdf) - Memorization, MIAs, and prompt-injection privacy attacks.
- [Unmasking PII Masking Models (2025)](https://arxiv.org/abs/2504.12308) - Independent third-party benchmark.

## Differential Privacy

- [OpenDP](https://github.com/opendp/opendp) - Harvard-led DP library (Rust core, Python bindings). <img src="https://img.shields.io/github/stars/opendp/opendp?style=social" align="center">
- [Google differential-privacy](https://github.com/google/differential-privacy) - Google's DP libraries (C++/Go/Java + PyDP). <img src="https://img.shields.io/github/stars/google/differential-privacy?style=social" align="center">
- [PyDP](https://github.com/OpenMined/PyDP) - Python wrapper over Google's DP library. <img src="https://img.shields.io/github/stars/OpenMined/PyDP?style=social" align="center">
- [Opacus](https://github.com/pytorch/opacus) - DP-SGD for PyTorch. <img src="https://img.shields.io/github/stars/pytorch/opacus?style=social" align="center">
- [TensorFlow Privacy](https://github.com/tensorflow/privacy) - DP optimizers and analysis for TF/Keras. <img src="https://img.shields.io/github/stars/tensorflow/privacy?style=social" align="center">
- [DP-Wizard](https://github.com/opendp/dp-wizard) - Web app for differentially private data releases. <img src="https://img.shields.io/github/stars/opendp/dp-wizard?style=social" align="center">

## Secrets Scanning

- [trufflehog](https://github.com/trufflesecurity/trufflehog) - 800+ credential detectors with active verification. <img src="https://img.shields.io/github/stars/trufflesecurity/trufflehog?style=social" align="center">
- [gitleaks](https://github.com/gitleaks/gitleaks) - Fast regex/entropy secret scanner. <img src="https://img.shields.io/github/stars/gitleaks/gitleaks?style=social" align="center">
- [detect-secrets](https://github.com/Yelp/detect-secrets) - Enterprise-friendly secret scanner with audit workflow. <img src="https://img.shields.io/github/stars/Yelp/detect-secrets?style=social" align="center">

## Standards & Regulations

- [GDPR Art. 4(5) - Pseudonymisation](https://gdpr-info.eu/art-4-gdpr/) - Legal definition.
- [GDPR Recital 26](https://gdpr-info.eu/recitals/no-26/) - The "reasonably likely means" identifiability test.
- [GDPR Art. 9 - Special categories](https://gdpr-info.eu/art-9-gdpr/) - Health, biometric, racial, political, religious, and similar data.
- [EDPB Guidelines on Pseudonymisation (2025)](https://www.edpb.europa.eu/system/files/2025-01/edpb_guidelines_202501_pseudonymisation_en.pdf) - Latest EU guidance.
- [HHS HIPAA De-Identification](https://www.hhs.gov/hipaa/for-professionals/special-topics/de-identification/index.html) - Safe Harbor and Expert Determination.
- [NIST SP 800-122](https://csrc.nist.gov/pubs/sp/800/122/final) - US baseline for protecting PII.
- [ISO/IEC 27018](https://www.iso.org/standard/76559.html) - Cloud-processor PII controls.
- [ISO/IEC 27701](https://www.iso.org/standard/71670.html) - Privacy Information Management System.
- [EU AI Act, Art. 10](https://artificialintelligenceact.eu/article/10/) - Data governance for high-risk AI.
- [California CCPA / CPRA](https://oag.ca.gov/privacy/ccpa).
- [PCI DSS](https://www.pcisecuritystandards.org/) - Cardholder-data classification and storage rules.

## Hosted Services

- [Amazon Comprehend PII](https://docs.aws.amazon.com/comprehend/latest/dg/how-pii.html) - 20+ entity types, English and Spanish.
- [Google Cloud Sensitive Data Protection](https://cloud.google.com/security/products/sensitive-data-protection) - 200+ infoTypes.
- [Azure AI Language PII](https://learn.microsoft.com/en-us/azure/ai-services/language-service/personally-identifiable-information/overview) - Cloud PII/PHI detection.
- [Private AI](https://www.private-ai.com/) - PII/PHI/PCI across 50+ entity types and 52 languages.
- [Skyflow](https://www.skyflow.com/) - Polymorphic-encryption vault for PII.
- [Tonic Textual](https://www.tonic.ai/textual) - NER-based de-identification + synthetic data.
- [Lakera Guard](https://www.lakera.ai/) - Runtime LLM-security layer.
- [BigID](https://bigid.com/) / [Privacera](https://privacera.com/) / [Immuta](https://www.immuta.com/) / [OneTrust](https://www.onetrust.com/) - Enterprise privacy platforms.
- [Snowflake Dynamic Data Masking](https://docs.snowflake.com/en/user-guide/security-column-ddm-intro) - Column-level masking in the warehouse.

## Papers

### Foundations

- [Sweeney (2002): k-Anonymity](https://epic.org/wp-content/uploads/privacy/reidentification/Sweeney_Article.pdf).
- [Machanavajjhala et al. (2007): l-Diversity](https://personal.utdallas.edu/~muratk/courses/privacy08f_files/ldiversity.pdf).
- [Li et al. (2007): t-Closeness](https://www.cs.purdue.edu/homes/ninghui/papers/t_closeness_icde07.pdf).
- [Dwork (2006): Differential Privacy](https://link.springer.com/chapter/10.1007/11787006_1).
- [Dwork, McSherry, Nissim, Smith (2006): Calibrating Noise to Sensitivity](https://people.csail.mit.edu/asmith/PS/sensitivity-tcc-final.pdf).

### Text Anonymization

- [Lison et al. (2021): Anonymisation Models for Text Data](https://aclanthology.org/2021.acl-long.323/).
- [Pilán et al. (2022): Text Anonymization Benchmark](https://aclanthology.org/2022.cl-4.19/).
- [Staab et al. (2024): LLMs are Advanced Anonymizers](https://arxiv.org/abs/2402.13846).
- [Vats et al. (2024): Robust Utility-Preserving Text Anonymization](https://arxiv.org/html/2407.11770v2).
- [Wang et al. (2025): A False Sense of Privacy](https://arxiv.org/abs/2504.21035).
- [Survey on Trends in Text Anonymization (2025)](https://arxiv.org/abs/2508.21587).

### LLM Memorization & Leakage

- [Carlini et al. (2021): Extracting Training Data from LLMs](https://arxiv.org/abs/2012.07805).
- [Huang, Shao, Chang (2022): Are LPLMs Leaking Your Personal Information?](https://aclanthology.org/2022.findings-emnlp.148/).
- [Kim et al. (2023): ProPILE](https://arxiv.org/abs/2307.01881).
- [Gao et al. (2025): Understanding PII Leakage in LLMs](https://www.ijcai.org/proceedings/2025/1156.pdf).
- [Privacy Auditing of LLMs (2025)](https://arxiv.org/abs/2503.06808).

## Tutorials & Demos

- [Microsoft Presidio docs](https://microsoft.github.io/presidio/).
- [Plugging transformer NER into Presidio](https://microsoft.github.io/presidio/analyzer/nlp_engines/transformers/).
- [HF Blog: Automatic PII Detection on the Hub](https://huggingface.co/blog/presidio-pii-detection).
- [HF Cookbook: LLM Gateway for PII Detection](https://huggingface.co/learn/cookbook/llm_gateway_pii_detection).
- [LiteLLM: Presidio PII Masking](https://docs.litellm.ai/docs/tutorials/presidio_pii_masking).
- [Philipp Schmid: PII with HF Transformers and SageMaker](https://www.philschmid.de/pii-huggingface-sagemaker).
- [Ploomber: Preventing PII Leakage with LLMs](https://ploomber.io/blog/presidio/).
- [DifferentialPrivacy.org: Deploying ML with DP](https://differentialprivacy.org/how-to-deploy-ml-with-dp/).
- [eu-pii.bards.ai](https://eu-pii.bards.ai/) - Browser demo of multilingual EU PII detection.

## Books

- [El Emam & Arbuckle: Anonymizing Health Data](https://www.oreilly.com/library/view/anonymizing-health-data/9781449363062/) (O'Reilly, 2014).
- [Dwork & Roth: The Algorithmic Foundations of Differential Privacy](https://www.cis.upenn.edu/~aaroth/privacybook.html) (free PDF).

## Contributing

Contributions welcome - see [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, contributors have waived all copyright and related rights to this work.
