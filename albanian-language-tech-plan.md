# Albanian Language Technology Development Plan (2026–2028)

**Cross-Border Initiative: Albania • Kosovo • North Macedonia**

**Version 0.2 | June 2026**

---

## Important Disclaimer

**This document was created using Large Language Models (LLMs) as a template to initiate discussion and planning around Albanian language technology development. The author is not a domain expert in Albanian NLP research, and this plan should be considered a starting point for community input rather than a definitive roadmap.**

**This plan will contain errors, omissions, and oversimplifications.** Timings and budgets are indicative estimates based on comparable initiatives and should be refined through consultation with Albanian NLP researchers, linguists, government officials, funding agencies, and technology practitioners. We strongly encourage feedback, corrections, and contributions from the Albanian language technology community to improve this document.

**Acknowledgments:** This plan builds upon existing work by Albanian NLP researchers who have documented the current state of Albanian language technology resources and tools.

---

## Plain Language Summary for Policymakers

**What is this plan?** A 3-year accelerated roadmap (2026-2028) to ensure Albanian language thrives in the digital age by developing technologies that allow computers to understand and generate Albanian text and speech.

**Why does this matter?** Without these technologies, Albanian speakers will face increasing barriers accessing digital services, AI systems like ChatGPT will struggle with Albanian, and young Albanians may increasingly switch to English for digital communication, threatening the language's long-term viability.

**What will we build?** 
- Large databases of Albanian text and speech for training AI systems
- Translation tools for Albanian↔English/German/Italian
- Speech recognition for Albanian (like Siri or Alexa, but for Albanian)
- Grammar checkers, spell-checkers, and writing assistants for Albanian

**How much will it cost?** €6.5-8.2 million total over 3 years, with **Albania and Kosovo governments contributing €500,000 annually each** (€3,000,000 total), while the remaining 49-70% comes from European Union grants that Albania and Kosovo are already eligible for, plus private sector contributions.

**What's the return?** By 2028, Albanian will have foundational digital language capabilities, ensuring our 8 million speakers can participate in the AI-driven economy and digital society.

**Open Licensing:** All outputs produced under this plan will be openly licensed (CC0, CC-BY, MIT, Apache 2.0, or similar) to maximize accessibility and reuse by the global Albanian-speaking community. This ensures that taxpayer-funded resources benefit everyone—researchers, students, businesses, and individuals—without restrictions.

---

## Author and Contributions

**Initial Author:** Arianit Dobroshi

This document represents a preliminary framework for developing Albanian language technology infrastructure. **We welcome contributions, feedback, and collaboration from NLP researchers, linguists, computer scientists, government officials, and all professionals working in language technology.** 

To contribute:
- Submit issues or pull requests via GitHub
- Contact: [to be added]
- Join our community discussions on advancing Albanian NLP

---

## Table of Contents

- [Executive Summary](#executive-summary)
- [Context and Motivation](#context-and-motivation)
- [Alignment with International Frameworks](#alignment-with-international-frameworks)
- [Headline Goals (2026–2028)](#headline-goals-2026-2028)
- [Vision Statement](#vision-statement)
- [Comparative Learning from Estonia and Croatia](#comparative-learning-from-estonia-and-croatia)
- [Implementation Timeline and Key Phases](#implementation-timeline-and-key-phases)
- [Strategic Pillars](#strategic-pillars)
  - [Pillar 1: Language Resource Creation and Curation](#pillar-1-language-resource-creation-and-curation)
  - [Pillar 2: Open-Source NLP Tool and Model Development](#pillar-2-open-source-nlp-tool-and-model-development)
  - [Pillar 3: Integration in Public Services and Education](#pillar-3-integration-of-language-technologies-in-public-services-and-education)
  - [Pillar 4: Research Capacity Building](#pillar-4-research-capacity-building-and-academic-excellence)
  - [Pillar 5: Governance and Sustainability](#pillar-5-governance-funding-and-sustainability)
- [Funding Mechanisms](#funding-mechanisms)
- [Monitoring and Evaluation](#monitoring-and-evaluation-framework)
- [Appendix: Work Packages](#appendix-grant-based-work-packages-open-calls-for-proposals)
- [References](#references)

---

## Executive Summary

Albanian is spoken by approximately 8 million people across the Western Balkans, primarily in Albania (3 million), Kosovo (1.8 million), and North Macedonia (500,000+), with significant diaspora communities globally. Despite this substantial speaker population, Albanian remains severely underrepresented in [Natural Language Processing (NLP)](https://en.wikipedia.org/wiki/Natural_language_processing)—the branch of artificial intelligence that helps computers understand, interpret, and generate human language—and language technology development.

### Current State of Albanian NLP (2026)

Recent documentation of Albanian NLP resources by researchers reveals both progress and gaps:

**Existing Resources:**
- **Web Corpora**: OSCAR corpus (~462M words, 1.3M documents), CulturaX (~3.6B tokens, 5.2M documents)
- **Speech Data**: Mozilla Common Voice (Albanian: 9.2 hours validated, 145 speakers; Gheg Albanian: 11 hours, 14 speakers), Albanian ASR Dataset (18 hours), CASR corpus (20 hours)
- **Language Models**: Early transformer models (Visar/roberta_oscar_al, edisnord/albert-base-v2-sq trained on CulturaX), fastText word embeddings
- **Treebanks**: Universal Dependencies treebanks (TSA, STAF released January 2025, GPS-Gheg ~16K tokens, SALT-Standard ~24K tokens in development)
- **Translation**: OPUS parallel corpora, Helsinki-NLP/opus-mt-en-sq model
- **Tools**: Basic morphological analyzers (uniparser-albanian), Albanian National Corpus (31M words)
- **Community Contributions**: FLOSSK's pioneering Mozilla Common Voice campaigns establishing community-driven data collection model

**Remaining Challenges:**
- Limited production-ready tools integrated into major platforms (NLTK, spaCy)
- Insufficient domain-specific datasets (legal, medical, technical)
- Fragmented research efforts across borders
- No coordinated corpus development strategy
- Minimal funding mechanisms dedicated to Albanian language technology
- Speech recognition performance (best open model: ~5% WER) needs larger, more diverse test sets
- Lack of comprehensive benchmarking datasets for evaluating models

This **Albanian Language Technology Development Plan (2026–2028)** addresses these deficiencies through an accelerated, coordinated, cross-border strategy that aligns with successful models from [Estonia](https://www.keeletehnoloogia.ee/en) and [Croatia](https://www.clarin.eu/blog/introduction-hr-clarin), while adapting to the unique linguistic, political, and economic context of Albanian-speaking regions.

**Core Principles:** 
1. **Open Licensing**: All outputs produced under this plan will be openly licensed to ensure maximum accessibility, reusability, and community benefit.
2. **Open Competition**: All funding opportunities will be subject to transparent, merit-based competition with clear evaluation criteria.
3. **Co-funding Priority**: Projects that secure EU co-funding will receive priority in national fund allocation, maximizing total investment impact.

---

## Context and Motivation

### Current Challenges

Albanian faces severe digital underrepresentation despite its 8 million speakers. While foundational resources now exist thanks to Albanian NLP researchers, community organizations like FLOSSK, and contributors to projects like Mozilla Common Voice, significant gaps remain:

**Limited Language Resources:**
- The [Albanian National Corpus](https://albanian.web-corpora.net/) contains only 31.12 million words, compared to billions for major European languages
- Web corpora (OSCAR, CulturaX) provide large-scale data but require cleaning and domain-specific supplements
- Speech datasets remain small and insufficiently diverse for production systems
- Minimal parallel translation corpora for domain-specific machine translation

**Inadequate NLP Tools:**
- No production-grade Albanian spell-checkers or grammar checkers integrated into major platforms
- Albanian not supported by mainstream NLP libraries (NLTK, spaCy) as a first-class language
- Basic [open-source Albanian NLP tools](https://github.com/arditdine/albanian-nlp) remain in early development stages
- Limited [named entity recognition (NER)](https://en.wikipedia.org/wiki/Named-entity_recognition) systems
- Machine translation quality significantly below major language pairs
- Early language models (albert-base-v2-sq) require evaluation and potential retraining

**Speech Technology Gap:**
- Google Translate and [OpenAI Whisper](https://openai.com/index/whisper/) include Albanian, but performance lags
- [DeepL](https://www.deepl.com/) does not support Albanian
- Best open-source ASR (~5% WER on Mozilla Common Voice test set) needs validation on larger, more diverse test sets
- Mozilla Common Voice Albanian datasets (9.2 hours standard, 11 hours Gheg) need significant expansion
- FLOSSK's successful community campaigns provide a proven model for scaling

**Fragmented Research:**
- Research scattered across University of Tirana, University of Prishtina, individual researchers, and diaspora
- No coordinated corpus development efforts
- Limited international collaboration on Albanian NLP
- Individual researcher contributions not systematically supported

### Alignment with International Frameworks

This plan directly supports:

**[European Union (EU)](https://europa.eu/) Digital Europe Programme** – advancing digital skills, artificial intelligence infrastructure, and language equality across Europe ([Digital Europe Programme](https://digital-strategy.ec.europa.eu/en/activities/digital-programme))

**UNESCO's Language Preservation Goals** – safeguarding linguistic diversity through technology ([UNESCO Digital Initiatives](https://www.unesco.org/en/articles/digital-initiatives-indigenous-languages))

**Western Balkans Digital Agenda** – enhancing regional digital integration and connectivity ([Digital Agenda for Western Balkans](https://www.rcc.int/priority_areas/56/digital-economy))

**European Language Grid (ELG)** – contributing Albanian resources to the pan-European language technology platform ([European Language Grid](https://live.european-language-grid.eu/))

**[Instrument for Pre-Accession Assistance III (IPA III)](https://enlargement.ec.europa.eu/enlargement-policy/overview-instrument-pre-accession-assistance_en)** – leveraging EU funding specifically designed for candidate and potential candidate countries preparing for EU membership

**Mozilla Common Voice Initiative** – contributing to and expanding the open-source multilingual speech dataset ([Mozilla Common Voice](https://commonvoice.mozilla.org/))

**[EU AI Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689)** (in force August 2024) – the world's first comprehensive AI regulation. Open-source GPAI models below the 10²⁵ FLOP systemic risk threshold receive meaningful compliance exemptions (technical documentation, downstream provider obligations). Albanian-scale models (7B–34B parameters) are far below this threshold, making the plan's open licensing mandate not only an ethical choice but the legally optimal one under EU law.

**[AI Continent Action Plan](https://digital-strategy.ec.europa.eu/en/factpages/ai-continent-action-plan)** (European Commission, April 2025) – the EU's strategic shift from regulation to industrial AI competitiveness. The plan explicitly calls on EU leaders to "harness open source AI as a key enabler of Europe's digital sovereignty," directly mandating the approach this plan takes. The Apply AI strategy (October 2025) adds a "buy European" preference for public sector procurement, giving the e-government integration pillar a direct policy mandate.

**[European Technological Sovereignty Package](https://digital-strategy.ec.europa.eu/en/library/communication-european-tech-sovereignty-accompanied-eu-open-source-strategy)** (European Commission, June 2026) – a package of four interconnected instruments: the **EU Open Source Strategy**, the **Cloud and AI Development Act (CADA)**, Chips Act 2.0, and a Strategic Roadmap for Energy Digitalization. The Open Source Strategy places open source at the centre of EU digital sovereignty, establishes the **Open Source Maintenance Instrument** for long-term sustainability of critical components, and mandates procurement guidelines favouring open standards. CADA explicitly promotes open source components in AI development. The GenAI4EU initiative within the package supports "development and adoption of open and trustworthy AI solutions." This package directly validates and politically reinforces all open licensing commitments in this plan.

---

## Headline Goals (2026–2028)

1. **Establish a cross-border Albanian NLP Resource Center** by Q4 2026, serving as the centralized hub for dataset curation, tool development, and research coordination across Albania, Kosovo, and North Macedonia.

2. **Create and release a 60-million-token open-source Albanian corpus** (text, speech, and parallel translation datasets) by Q4 2028, covering multiple domains including news, government documents, literature, social media, and conversational speech. **All datasets will be openly licensed (CC0, CC-BY 4.0, or similar).**

3. **Develop and deploy at least 6-8 open-source Albanian NLP tools and models** by Q4 2028, including tokenizers, part-of-speech taggers, named entity recognizers, machine translation systems, and automatic speech recognition tools with documented benchmark performance. **All tools will be released under permissive open-source licenses (MIT, Apache 2.0).**

4. **Integrate Albanian language technologies into at least 8-10 public service platforms** by Q4 2028, including e-government portals, healthcare information systems, educational platforms, and digital citizen services.

5. **Expand Mozilla Common Voice Albanian datasets to 1,000+ hours** with contributions from 2,000+ speakers across dialectal varieties by Q4 2028, building on FLOSSK's successful community engagement model and expanding to universities and high schools throughout Albania, Kosovo, and North Macedonia.

6. **Support 30+ individual researchers and research teams** through microgrants, fellowships, and collaborative projects by Q4 2028.

7. **Extend mainstream NLP libraries** (NLTK, spaCy) to include Albanian as a first-class supported language by Q4 2028, enabling Albanian developers to use familiar tools.

---

## Vision Statement

By 2028, Albanian will have foundational digital language infrastructure, with growing academic and industry ecosystems, and improved access to language technologies for Albanian speakers, positioning the language for continued development in the digital age. **All resources, tools, and models will be openly licensed to ensure equitable access and enable innovation by the global Albanian-speaking community.**

---

## Comparative Learning from Estonia and Croatia

This plan draws extensively from two exemplary national language technology programs:

### Estonia's National Programme for Estonian Language Technology (2018-2027)

**Reference:** [Estonian Language Technology Programme](https://www.keeletehnoloogia.ee/en)

Estonia's programme demonstrates effective governance through the [Center of Estonian Language Resources (CELR)](https://keeleressursid.ee/en/), coordinated funding mechanisms through the Ministry of Education and Research (€811,000 annually), and strategic public-private partnerships. Estonia's model emphasizes open-source development, systematic resource creation, and integration with national digital infrastructure.

**Key achievements:**
- Speech recognition and synthesis for Estonian Parliament and broadcasting
- Large language models trained on LUMI supercomputer
- Integration with [CLARIN infrastructure](https://www.clarin.eu/blog/tour-de-clarin-estonia)
- 152 Estonian language resources in META-SHARE registry

**Key lessons:**
- Importance of sustainable institutional support
- Researcher capacity building through dedicated PhD programs
- Continuous stakeholder engagement
- Integration with European research infrastructure

### Croatia's HRVOJKA Platform and HR-CLARIN Initiative

**References:** 
- [HRVOJKA Platform](https://www.nltp-info.eu/post/croatia-has-launched-the-nltp-platform-hrvojka)
- [HR-CLARIN](https://www.clarin.eu/blog/introduction-hr-clarin)

Croatia's approach showcases successful regional cooperation through the CEF-funded National Language Technology Platform project, practical deployment of machine translation for public administration, and integration with European language infrastructure. The [HRVOJKA platform](https://total-croatia-news.com/news/meet-hrvojka-croatian-governments-language-portal/) (€62,000 CEF co-funding) provides secure translation for Croatian and all 24 EU languages specifically for government use.

**Key achievements:**
- Government-integrated machine translation portal
- [CLARIN full membership](https://www.clarin.eu/blog/tour-de-clarin-hr-clarin) achieved in 2018
- Six GPT-based models trained exclusively on Croatian
- Repository using Lindat DSpace v7

**Croatia's experience highlights:**
- Value of leveraging EU co-funding
- Building on existing platforms (Latvia's hugo.lv)
- Ensuring government adoption of language technologies
- Integration with European language infrastructure from the start

This Albanian action plan adapts these models to an accelerated 3-year timeline and cross-border context, recognizing the unique opportunities of regional cooperation among Albania, Kosovo, and North Macedonia while addressing specific challenges facing Albanian.

### National LLM Models: More Analogous Peers

Beyond Estonia and Croatia (language infrastructure programmes), more directly comparable models now exist for Albanian to study and build upon:

**BgGPT (Bulgarian, INSAIT — 2024)**

**Reference:** [insait.ai/insait-creates-leading-bulgarian-first-llm-with-gemma-2](https://insait.ai/insait-creates-leading-bulgarian-first-llm-with-gemma-2/)

Built by the Institute for Computer Science, Artificial Intelligence and Technology (INSAIT, Sofia) — a partnership between Sofia University, ETH Zurich, and EPFL — BgGPT demonstrates what a small-language community can achieve through strong institutional partnerships and the continual pretraining approach. Version 1 (February 2024) fine-tuned Google's Gemma family; BgGPT-GEMMA-2-27B (2024) outperforms Llama 3.1 70B and Qwen 2.5 72B on Bulgarian tasks despite being smaller. Training used ~85B Bulgarian tokens + 15B English. A nationwide public chat system was launched alongside the model. The INSAIT model — anchored by international university partnerships rather than requiring a standalone national AI institute — offers a direct institutional template for Albania and Kosovo.

**Key lessons:**
- International academic partnerships (ETH Zurich, EPFL equivalent) unlock resources and credibility unavailable to national institutions alone
- Bilingual training (target language + English) prevents catastrophic forgetting of general capabilities
- Launching a public-facing chat product immediately drives adoption and demonstrates impact to funders

**Meltemi 7B / Krikri 8B (Greek, ILSP Athena Research Center — 2024/2025)**

**References:**
- [Meltemi 7B (arXiv:2407.20743)](https://arxiv.org/html/2407.20743v1)
- [Krikri 8B (Hugging Face)](https://huggingface.co/ilsp/Llama-Krikri-8B-Base)

Built by the Institute for Language and Speech Processing (ILSP), Athena Research & Innovation Center, Greece. Meltemi (2024) continually pretrained Mistral-7B on 28.5B Greek tokens + 10.5B English, extending the tokenizer to 61,362 vocabulary entries to properly represent Greek. Krikri (February 2025) repeated this on Llama 3.1-8B with 56.7B Greek tokens + 21B English, achieving 128K context and supporting Ancient Greek and polytonic text. Both released under Apache 2.0.

This is the closest methodological template for Albanian: a research institute using continual pretraining of an existing open model, bilingual training mix, tokenizer extension, and fully open release — applied to a language with a similarly sized NLP resource base.

**Key lessons:**
- Continual pretraining of an existing open model (Mistral, Llama) requires far less compute than training from scratch and produces competitive results
- Extending the tokenizer for the target language's character set is essential for efficiency and quality
- Releasing successive model versions (Meltemi → Krikri) as data and base models improve is more sustainable than aiming for one large release

**OpenEuroLLM Consortium (EU-funded, 2025–2026)**

**Reference:** [openeurollm.eu](https://openeurollm.eu/)

Launched February 2025 with €37.4M from the Digital Europe Programme (€20.6M EU contribution), coordinated by Charles University Prague with 20 partner organizations including AMD SiloAI, Aleph Alpha, Barcelona Supercomputing Center, and AI Sweden. OpenEuroLLM targets all 24 EU official languages plus candidate-country languages, making Albanian potentially in scope. The project uses HPLT v2 dataset (52 trillion characters across 75+ languages) as its data foundation and trains on LUMI and other EuroHPC machines. Final delivery is July 2026.

**Immediate action required:** The plan's Phase 1 must include direct engagement with the OpenEuroLLM consortium to confirm Albanian inclusion and contribute Albanian data to the HPLT pipeline before the project's final training runs.

---

## Implementation Timeline and Key Phases

> **Note:** Implementation is planned to begin September 2026. The OpenEuroLLM consortium deadline (July 2026) requires pre-implementation engagement to secure Albanian inclusion before the project's final training runs.

### Pre-Implementation (July–August 2026)

- Engage OpenEuroLLM consortium to confirm Albanian inclusion as a candidate-country language and contribute cleaned Albanian data to the HPLT v2 pipeline — **must happen before July 2026 deadline**
- Check HPLT v2 dataset for existing Albanian coverage; prepare cleaned Albanian data contribution
- Finalise governance agreements and node appointments (Tirana, Prishtina, Tetova)
- Secure national funding commitments from Albania and Kosovo Ministries of Education
- Submit IPA III applications; apply for EuroHPC extreme-scale compute access on LUMI

### Phase 1 (September–December 2026): Foundation Building

- Establish Albanian NLP Resource Center with governance structure operational
- Launch corpus collection campaigns; initial contacts with media and university partners
- Publish inventory of existing Albanian NLP resources and tools
- Establish ASR baselines: evaluate zero-shot Whisper Large-v3 and Meta MMS on Albanian; publish results to set evidence-based WER targets
- Translate and validate MMLU-sq, HellaSwag-sq, ARC-sq benchmarks
- Launch Open Albanian LLM Leaderboard on Hugging Face Spaces
- Begin Mozilla Common Voice Albanian expansion with FLOSSK and university partners; target 100 hours by year end
- Release first open call for research grants, including microgrants for individual researchers
- **All releases openly licensed**

### Phase 2 (2027): Accelerated Development & Community Building

- Release 40M-token corpus milestone (Q4 2027)
- Develop core NLP tools (tokenizers, taggers, NER systems)
- **Launch Mozilla Common Voice sprint campaigns** targeting 500+ hours, expanding FLOSSK's work to universities and high schools
- **Begin NLTK and spaCy extension projects**
- **Begin Albanian LLM continual pretraining** on 40B+ token bilingual corpus (LUMI compute); release base model checkpoint
- **Launch synthetic data generation pipeline**; release 50,000+ Albanian instruction pairs (Q2 2027)
- Launch pilot integrations with 3-5 e-government services
- Conduct first Albanian NLP workshop/hackathon with **open competition**
- Submit Horizon Europe applications
- Apply for CLARIN Observer status
- **Award 20+ individual researcher microgrants**

### Phase 3 (2028): Integration & Sustainability Planning

- Complete 60M-token corpus (Q4 2028)
- Deploy language technologies in 8-10 public service platforms
- **Achieve 1,000+ hours Mozilla Common Voice data** across dialects through university and high school engagement
- **Release instruction-tuned Albanian LLM** with domain-adapted variants (legal, medical)
- **Complete NLTK and spaCy Albanian support**
- Finalize and benchmark all 6-8 open-source tools
- Establish partnerships for post-2028 continuation
- Prepare strategic plan for 2029-2031 continuation
- Publish comprehensive Albanian NLP resource catalog

---

## Strategic Pillars

## Pillar 1: Language Resource Creation and Curation

**Objective:** Build comprehensive, high-quality language datasets that serve as the foundation for all Albanian NLP research and development. **All resources will be openly licensed for maximum accessibility and reuse.**

### Current Situation

**Existing Albanian Language Resources:**

**Text Corpora:**
- [Albanian National Corpus](https://albanian.web-corpora.net/): 31.12 million words (press 23.4M, fiction 3.2M, nonfiction 4.3M, poetry 0.2M)
- **OSCAR Corpus**: ~462 million words, 1.3M+ documents
- **CulturaX**: ~3.6 billion tokens for Albanian (5.2M documents)
- AlbNER corpus: 900 Wikipedia sentences for named entity recognition
- AlbNews corpus: 600 labeled + 2,600 unlabeled news headlines
- Multi-dialectal Twitter corpus: 2,503 users

**Speech Resources:**
- **Mozilla Common Voice Albanian**: 9.2 hours (8.8 validated), 145 speakers
- **Mozilla Common Voice Gheg Albanian**: 11 hours, 14 speakers
- **FLOSSK's contribution campaigns**: Established successful community engagement model
- Albanian ASR Dataset (Kaggle): 18 hours (automatically labeled)
- CASR corpus: 20 hours audiobook recordings (not publicly available yet)

**Parallel Corpora:**
- OPUS collection: Limited Albanian-English pairs
- Helsinki-NLP translation model available

**Assessment:** Albanian has foundational resources but requires significant expansion to support production systems. FLOSSK's community campaigns demonstrate the viability of large-scale volunteer contribution. Web corpora provide volume but need cleaning and domain specialization.

### Key Actions

#### 1. Establish the Albanian Text Corpus Initiative

Create a 60-million-token corpus by 2028 covering:
- News media (collaboration with Top Channel, Gazeta Shqip, Koha Ditore)
- Government documents (leveraging [e-Albania platform](https://en.wikipedia.org/wiki/EAlbania))
- Literature (partnership with National Library of Albania)
- Social media and web content (building on OSCAR/CulturaX)
- Scientific articles and academic texts
- Historical texts and cultural heritage materials

**Licensing:** All collected corpora will be released under CC0 (public domain) or CC-BY 4.0 licenses to ensure maximum accessibility for research, education, and commercial applications.

**Implementation:** Ensure dialectal diversity by including content from Albania, Kosovo, and North Macedonia. Implement ethical data collection practices with proper consent and licensing. Follow [FAIR principles](https://www.go-fair.org/fair-principles/).

#### 2. Launch Albanian Speech Corpus Campaign

Develop a **1,000-hour** annotated speech dataset by 2028:

**Mozilla Common Voice Expansion (Priority):**
- **Target: 500+ hours by Q4 2027, 1,000+ hours by Q4 2028**
- **Build on FLOSSK's successful community campaign model**
- **Expand to universities and high schools** across Albania, Kosovo, and North Macedonia
- Engage student volunteers through:
  - University computer science and linguistics departments
  - High school technology clubs and language classes
  - Coordinated reading/recording sessions
  - Gamified contribution competitions between institutions
- Recruit 2,000+ speakers across age, gender, and dialectal backgrounds
- Provide validated, open-source speech data under **CC0 license**
- Support both Tosk (standard) and Gheg varieties
- Create promotional materials and engagement toolkits for educators

**Complementary Speech Data:**
- Read speech (audiobooks, news broadcasts)
- Conversational speech (call center recordings with consent, interviews)
- Broadcast news (RTSH, RTK, parliamentary proceedings)
- Regional accent coverage ensuring dialectal representation

**Implementation Strategy:**
1. Partner with FLOSSK to document and scale their proven campaign methodology
2. Develop educational curriculum integration for high schools and universities
3. Create student ambassador program for peer-to-peer recruitment
4. Organize inter-university competitions with recognition and prizes
5. Partner with Albanian broadcasters (RTSH, RTK) and parliamentary archives
6. **Prioritize Mozilla Common Voice contributions** for maximum open-source impact

**Target Milestones:**
- Q2 2026: Launch university pilot programs (3-5 institutions)
- Q4 2026: 100 hours achieved
- Q2 2027: Expand to high schools (20+ schools)
- Q4 2027: 500 hours achieved
- Q4 2028: 1,000 hours achieved

#### 3. Build Parallel Translation Datasets

Create Albanian-English (1.5M pairs), Albanian-German (500K pairs), and Albanian-Italian (500K pairs) parallel corpora including:
- Legal texts (EU acquis, national legislation)
- Medical and healthcare documents
- Technical documentation
- Administrative texts
- Literary translations

**Licensing:** Released under CC-BY 4.0 to enable commercial use while ensuring attribution.

#### 4. Develop Specialized Lexical Resources

Compile:
- Domain-specific lexicons (law, medicine, technology, education)
- Sentiment lexicons and opinion word lists
- Albanian WordNet integrated with [Princeton WordNet](http://wordnet.princeton.edu/)
- Terminology databases for specialized domains

**Licensing:** All lexical resources released under CC-BY 4.0 or more permissive licenses.

#### 5. Support Individual Researcher Contributions

- **Microgrants (€1,000-€5,000)** for individual data collection projects
- Recognition system for dataset contributors
- Technical infrastructure support (hosting, annotation tools)
- Collaborative annotation platforms for crowd-sourced efforts
- **All grant-funded data must be openly licensed**

#### 6. Implement Quality Assurance Framework

- Establish annotation guidelines following Universal Dependencies standards
- Require inter-annotator agreement scores > 0.85
- Conduct systematic quality reviews quarterly
- Ensure FAIR principles compliance
- Deposit all resources in [European Language Grid](https://live.european-language-grid.eu/)
- **Verify open licensing compliance for all deposited resources**

### Performance Indicators (2026-2028)

- 60 million tokens of text corpus released under open licenses (Q4 2028)
- 1,000 hours of annotated speech data (Q4 2028)
  - **Including 500+ hours Mozilla Common Voice (Q4 2027)**
  - **Including 1,000+ hours Mozilla Common Voice (Q4 2028)**
  - **2,000+ unique contributors to Mozilla Common Voice Albanian** (Q4 2028)
  - **50+ universities and high schools participating** (Q4 2028)
- 4 million parallel sentence pairs across 3 language pairs (Q2 2028)
- 3 specialized lexical resources published (Q4 2028)
- All datasets compliant with FAIR principles and deposited in ELG (ongoing)
- **100% of funded datasets openly licensed** (ongoing)

---

## Pillar 2: Open-Source NLP Tool and Model Development

**Objective:** Develop and release production-ready NLP tools and models that enable practical applications for Albanian language processing. **All tools and models will be released under permissive open-source licenses.**

### Current Situation

**Existing Albanian NLP Tools:**

**Open Source Tools:**
- [albanian-nlp](https://github.com/arditdine/albanian-nlp): Basic stemming, stop word filtering (Python)
- [nlp-for-albanian](https://github.com/thinkgradient/nlp-for-albanian): Planned word embeddings, sentiment analysis (incomplete)
- [Albanian ASR](https://github.com/florijanqosja/Albanian-ASR): Python-based speech-to-text with Docker support
- GiellaLT Albanian Grammar: Finite state analyzers for morphological analysis
- Uniparser-Albanian: Rule-based morphological analysis and lemmatization

**Language Models:**
- **Visar/roberta_oscar_al**: First Albanian RoBERTa attempt (convergence issues)
- **edisnord/albert-base-v2-sq**: Small MLM model trained on CulturaX
- **Kushtrim/Llama-3.1-8B-Instruct-bnb-4bit-shqip**: Instruction-tuned 8B parameter LLM for Albanian
- **fastText word embeddings**: Multilingual word vectors including Albanian

**Task-Specific Models:**
- **Kushtrim/bert-base-multilingual-cased-finetuned-albanian-ner**: Named Entity Recognition model
- **Kushtrim/bert-base-multilingual-cased-sq-sentiment-sst2**: Sentiment analysis for Albanian text
- **Kushtrim/speecht5_finetuned_cv_sq**: Text-to-Speech model fine-tuned on Common Voice Albanian

**Commercial Services:**
- Google Translate: Full Albanian support (text, speech, camera)
- Microsoft Translator: Albanian text and speech
- OpenAI Whisper: Albanian included in multilingual model
- DeepL: **No Albanian support**

**Best Performing Models:**
- ASR: Whisper medium fine-tuned (~5% WER on Mozilla Common Voice test set)
- Translation: Helsinki-NLP/opus-mt-en-sq (OPUS-based)
- NER: Kushtrim/bert-base-multilingual-cased-finetuned-albanian-ner
- Sentiment: Kushtrim/bert-base-multilingual-cased-sq-sentiment-sst2
- TTS: Kushtrim/speecht5_finetuned_cv_sq
- Instruction-following: Kushtrim/Llama-3.1-8B-Instruct-bnb-4bit-shqip

**2025 Additions:**
- **Albanian NER Corpus (2025):** Largest-ever Albanian NER corpus, sourced from Albanian news platforms; 10 ML models trained with Extra Trees and Random Forest achieving ~96% accuracy and 95% F1. (SpringerLink, 2025)
- **STAF Treebank (January 2025):** Saarbrücken Treebank of Albanian Fiction released, expanding UD coverage
- **HPLT v2 Dataset:** High Performance Language Technologies v2 (75+ languages, 52 trillion characters) likely contains Albanian web data; requires verification and contribution of cleaned Albanian data

**Assessment:** Foundational tools exist including recent contributions from researchers like Kushtrim Visoka (instruction-tuned LLM, NER, sentiment analysis, TTS), but production quality varies and comprehensive benchmarking is needed. Standardized evaluation benchmarks do not yet exist for Albanian — this is the most critical gap for tracking progress. **Albanian is not yet supported as a first-class language in mainstream NLP libraries like NLTK and spaCy.** Albanian is absent from EuroLLM-9B (35 languages) and TildeOpen-30B despite being an EU candidate-country language, making the OpenEuroLLM engagement a priority.

### Key Actions

#### 1. Fundamental Processing Tools

Develop and release:
- Albanian tokenizers and sentence segmenters
- Morphological analyzers handling Albanian's complex inflection system
- [Part-of-speech (POS) taggers](https://en.wikipedia.org/wiki/Part-of-speech_tagging) with accuracy benchmarks (target: 90%+)
- Dependency parsers compatible with [Universal Dependencies](https://universaldependencies.org/)

**Licensing:** All tools released under **MIT or Apache 2.0 licenses** to enable both academic and commercial use without restrictions.

**Priority:** Extend existing tools (NLTK, spaCy) to support Albanian directly

#### 2. Named Entity Recognition and Classification

Build NER systems identifying:
- Persons, organizations, locations (standard entities)
- Dates, monetary values, percentages
- Domain-specific entities (legal, medical, technical)
- Target F1-scores: 80%+ (recognizing limited training data)

**Licensing:** Models and training code released under **MIT license**.

#### 3. Machine Translation Systems

Train neural machine translation models:
- Albanian-English, Albanian-German, Albanian-Italian pairs
- Fine-tune for specialized domains (legal, medical, technical)
- Conduct rigorous evaluation using [BLEU](https://en.wikipedia.org/wiki/BLEU) scores (target: 25+ for Albanian-English, recognizing current limitations)
- Human evaluation studies with professional translators
- Integration with public sector platforms

**Licensing:** Models released under **Apache 2.0**, training data under **CC-BY 4.0**.

#### 4. Automatic Speech Recognition (ASR)

Develop [ASR](https://en.wikipedia.org/wiki/Speech_recognition) systems using a two-baseline approach:
- **Establish baselines first:** Evaluate zero-shot performance of (1) **Whisper Large-v3** (OpenAI, November 2023 — 10–20% WER improvement over v2) and (2) **Meta MMS** (Massively Multilingual Speech, 1,100+ languages including Albanian) before any fine-tuning work begins. This establishes realistic targets.
- **Fine-tune Whisper Large-v3** on Mozilla Common Voice Albanian data as the primary approach; the Whisper-LM technique (combining Whisper with a language model decoder) offers additional gains for low-resource settings
- **Integrate Mozilla Common Voice data** as primary training resource
- Target Word Error Rates: <8% for broadcast news, <15% for conversational speech — to be recalibrated after baseline evaluation against Whisper Large-v3
- Support dialect variation (Gheg and Tosk)
- Create applications for transcription services

**Licensing:** Models and inference code released under **Apache 2.0 license**.

#### 5. Text Analytics and Applications

Build:
- Sentiment analysis tools for Albanian social media
- Text classification systems for document categorization
- Information extraction tools for structured data
- Question-answering systems for Albanian

**Licensing:** All applications released under **MIT license**.

#### 6. Language Model Development

The field has converged on **continual pretraining of existing open models** as the cost-effective approach for low-resource European languages, demonstrated by Meltemi/Krikri (Greek, ILSP), BgGPT (Bulgarian, INSAIT), Bielik (Polish, SpeakLeash), and EstLLM (Estonian). Training a model from scratch is not warranted at current Albanian data volumes.

**Recommended approach:**
- **Phase 1 (2026):** Evaluate existing models (albert-base-v2-sq, Kushtrim/Llama-3.1-8B-Instruct-bnb-4bit-shqip) on standardized benchmarks; establish the Albanian NLP Leaderboard (see §9 below) to create comparable baselines
- **Phase 2 (2027):** Continually pretrain Llama 3.x or Mistral on a bilingual Albanian/English corpus (~80% Albanian, ~20% English) using a minimum of 40B Albanian tokens. The English retention component is essential to prevent catastrophic forgetting of general capabilities — established practice from Meltemi (28.5B Greek tokens) and BgGPT (85B Bulgarian tokens). Extend the tokenizer vocabulary to include Albanian-specific characters and morphological patterns for training efficiency.
- **Phase 3 (2028):** Instruction-tune the pretrained base model on synthetic and human-verified Albanian instruction data; create domain-adapted variants for legal and medical use cases
- **Engage OpenEuroLLM consortium** (EU-funded, €37.4M, deadline July 2026) to secure Albanian inclusion as a candidate-country language — this may provide a multilingual base model at no additional training cost

**Ensure ethical AI practices** including bias mitigation and GDPR-compliant data processing throughout.

**Licensing:** Model weights under **Apache 2.0**, training code under **MIT**, documentation under **CC-BY 4.0**.

#### 7. Integration with Mainstream NLP Libraries

**Objective:** Make Albanian a first-class citizen in widely-used open-source NLP frameworks, ensuring Albanian developers can use familiar tools without building from scratch.

**NLTK Extensions:**
- **Albanian Stemmer**: Develop AlbanianStemmer class for SnowballStemmer, handling Albanian's complex morphology including:
  - Definite article suffixation
  - Plural formations
  - Verbal conjugations
- **Albanian Punkt Tokenizer**: Train sentence segmentation model on Albanian corpus data
- **Albanian Stopwords**: Curate comprehensive stopword list
- Implementation: Fork or direct contribution to NLTK repository

**spaCy Pipeline Development:**
- Train complete spaCy pipeline using available annotated data:
  - Universal Dependencies treebanks (TSA, STAF, GPS-Gheg ~16K tokens, SALT-Standard ~24K tokens)
  - Albanian National Corpus (31M words)
- Components to develop:
  - Tokenizer optimized for Albanian orthography
  - Part-of-speech tagger (target: 90%+ accuracy)
  - Dependency parser
  - Named entity recognizer
  - Lemmatizer

**Licensing:** All extensions released under **MIT license** for maximum compatibility and adoption.

**Implementation Strategy:**
- Microgrants (€2,000-€5,000) for individual developers contributing to NLTK/spaCy
- Code review and mentorship from maintainers
- Documentation in both English and Albanian
- Integration testing with existing Albanian NLP resources

#### 8. Individual Researcher Support

- **Tool development microgrants** (€2,000-€10,000) for individual developers
- Code review and mentorship programs
- Infrastructure support (compute credits, GPU access)
- Recognition for open-source contributions
- **All grant-funded tools must be openly licensed (MIT or Apache 2.0)**

#### 9. Albanian Evaluation Benchmarks and Leaderboard

Without standardized benchmarks, it is impossible to measure whether Albanian NLP is improving or to compare models fairly. Every successful national LLM programme (BgGPT, Bielik/Open PL LLM Leaderboard, NorwAI/NorBench) built evaluation infrastructure before or alongside model development. This is a prerequisite, not a follow-on.

**Deliverables:**
- Translate and validate standard benchmarks into Albanian: **MMLU-sq** (57-subject multiple choice), **HellaSwag-sq** (commonsense reasoning), **ARC-sq** (grade-school science), and **TruthfulQA-sq** (factual accuracy)
- Establish an **Open Albanian LLM Leaderboard** (hosted on Hugging Face Spaces) to provide continuous, publicly visible model comparison — motivating community contributions and making progress measurable for funders
- Create Albanian-specific evaluation sets for domain tasks: legal text comprehension, medical Q&A, government document summarization

**Licensing:** All benchmark datasets released under **CC-BY 4.0**; leaderboard infrastructure under **MIT**.

**Timeline:** Q3 2026 (benchmark translation), Q4 2026 (leaderboard launch) — must precede Phase 2 model development to enable meaningful evaluation.

#### 10. Synthetic Data Generation Pipeline

For low-resource languages, synthetic data generation — using existing capable multilingual LLMs to produce Albanian instruction and task data, then filtering for quality — is now standard practice (used in Bielik, EstLLM, and multiple EMNLP 2025 findings). Albanian lacks sufficient annotated instruction data for fine-tuning without this approach.

**Deliverables:**
- Build a reproducible pipeline using existing multilingual LLMs (e.g., EuroLLM-9B, Llama 3.x) to generate Albanian instruction pairs across diverse domains
- Validate quality via back-translation to English and human review by Albanian linguists
- Release the pipeline code and the resulting dataset openly
- Target: 50,000+ verified Albanian instruction pairs by Q2 2027

**Licensing:** Pipeline code under **MIT**; generated dataset under **CC-BY 4.0** (with explicit disclosure of synthetic origin in dataset documentation).

### Performance Indicators (2026-2028)

- 6-8 open-source NLP tools released (Q4 2028)
- POS tagger accuracy: 90%+ (Q4 2027)
- NER F1-score: 80%+ (Q4 2028)
- ASR WER: targets to be set after Whisper Large-v3 and MMS baseline evaluation (Q2 2026); indicative targets <8% broadcast, <15% conversational (Q4 2028)
- Machine translation BLEU: 25+ for Albanian-English (Q4 2028)
- **Albanian LLM via continual pretraining** on 40B+ tokens, with instruction-tuned variant released (Q4 2027)
- **OpenEuroLLM Albanian inclusion confirmed or Albanian model released independently** (Q4 2027)
- **Open Albanian LLM Leaderboard live** with MMLU-sq, HellaSwag-sq, ARC-sq benchmarks (Q4 2026)
- **50,000+ synthetic instruction pairs** released for Albanian (Q2 2027)
- **Albanian support in NLTK** (Q4 2027)
- **Albanian support in spaCy** (Q4 2028)
- 500+ GitHub stars/downloads across all tools (Q4 2028)
- **20+ individual researchers contributing tools** (Q4 2028)
- **100% of funded tools released under permissive open-source licenses** (ongoing)

---

## Pillar 3: Integration of Language Technologies in Public Services and Education

**Objective:** Deploy Albanian NLP tools in practical applications that improve digital service delivery, accessibility, and educational outcomes.

### Current Situation

**Existing Deployments:**

**Government Digital Services:**
- [e-Albania platform](https://en.wikipedia.org/wiki/EAlbania): 1,253 online services, 95% digitalization
- GovNet fiber-optic network: 250+ public institutions

**Machine Translation:**
- Basic Google Translate integration in some portals
- No specialized government MT systems like Croatia's HRVOJKA

**Education:**
- Limited Albanian language learning apps
- No automated essay scoring for Albanian
- Basic spell-checking available

**Assessment:** Albania has strong digital government infrastructure but lacks Albanian-specific language technologies.

### Key Actions

#### 1. E-Government Language Technology Integration

Deploy in 8-10 government platforms:
- Machine translation in government portals for multilingual access
- ASR for voice-based citizen service interfaces and call centers
- Automated document processing using NER and text classification
- Chatbot systems for frequently asked questions

**Target platforms:**
- e-Albania portal (Albania)
- e-Kosova portal (Kosovo)

**Licensing:** Deployed systems will use openly licensed models and tools to avoid vendor lock-in.

#### 2. Education Technology Applications

Develop:
- Automated essay scoring and feedback systems for Albanian
- Language learning platforms with integrated speech recognition
- Accessible digital textbooks with text-to-speech
- Plagiarism detection tools for Albanian academic writing

**Licensing:** Educational tools released under **MIT license** for maximum adoption by schools.

#### 3. Healthcare Information Systems

Deploy:
- Medical translation tools for patient-physician communication
- Medical information retrieval for Albanian health portals
- Clinical text processing for electronic health records
- [GDPR](https://gdpr.eu/)-compliant data privacy protocols

#### 4. Media and Cultural Heritage

Implement:
- Automatic captioning and subtitling for Albanian broadcast media
- Digital archive search for national libraries
- Semantic search for Albanian newspaper archives

#### 5. Accessibility and Inclusion

Ensure:
- [WCAG 2.1](https://www.w3.org/WAI/standards-guidelines/wcag/) compliance for all deployed technologies
- Assistive technologies for visually impaired users (screen readers, [TTS](https://en.wikipedia.org/wiki/Speech_synthesis))
- Tools for minority language communities
- Bias monitoring and mitigation in deployed AI systems

### Performance Indicators (2026-2028)

- 8-10 public service platforms with integrated language technologies (Q4 2028)
- 4-5 e-government portals with machine translation (Q4 2027)
- 2-3 educational platforms with Albanian NLP tools (Q4 2028)
- 1-2 healthcare systems with language technology integration (Q4 2028)
- User satisfaction scores: 70%+ for deployed services (ongoing)
- 25,000+ citizens actively using language technology services (Q4 2028)

---

## Pillar 4: Research Capacity Building and Academic Excellence

**Objective:** Establish a robust, sustainable research ecosystem capable of continuous innovation in Albanian language technology, **with explicit support for individual researchers and early-career scientists**.

### Current Situation

**Academic Institutions:**

**Albania:**
- University of Tirana: Double-degree master's in NLP with University Sorbonne Paris Nord
- Key researchers active in Albanian NLP
- University of New York Tirana: Published comprehensive Albanian NLP survey (2022)

**Kosovo:**
- [University of Prishtina](https://en.wikipedia.org/wiki/University_of_Pristina): 42,000+ students, highest-ranked Albanian-language university
- [Albanological Institute of Prishtina](https://en.wikipedia.org/wiki/Institute_of_Albanology_in_Pristina): 34 researchers focusing on linguistics

**North Macedonia:**
- South East European University, Tetovo: First-ranked Albanian-language university in North Macedonia
- State University of Tetovo: Founded 1994

**Community Organizations:**
- **FLOSSK (Free Libre Open Source Software Kosova)**: Pioneering work on Mozilla Common Voice campaigns, demonstrating effective community mobilization

**Individual Researchers:**
- Active diaspora researchers contributing remotely
- Recent graduates developing language models and documenting resources
- Lack of systematic support for independent researchers

**International Collaboration:**
- Limited participation in major NLP conferences (ACL, EMNLP, LREC)
- Few Horizon Europe project participations
- No systematic researcher exchange programs

**Assessment:** Academic capacity exists but remains fragmented. **Individual researchers lack support structures.** No coordinated PhD programs for Albanian NLP. FLOSSK's success demonstrates the power of community-driven initiatives.

### Key Actions

#### 1. Research Training Programs

Launch:
- Annual summer schools on NLP and language technology
- Workshops on deep learning, transformer architectures, evaluation
- Hands-on training with Albanian datasets and tools
- Guest lectures from international experts
- **All training materials released under CC-BY 4.0 license**

#### 2. PhD and Postdoctoral Fellowships

Fund:
- **12 PhD scholarships** dedicated to Albanian NLP (2026-2028)
- **6 postdoctoral fellowships** for advanced research
- Co-supervision with international research groups
- Research visits to leading NLP labs (Edinburgh, Stanford, TU Delft)
- **Requirement: All funded research outputs must be openly licensed**

#### 3. Individual Researcher Support Program

**New Initiative:**
- **Microgrants (€3,000-€8,000)** for independent researchers
- **Conference travel grants** (€1,000-€2,000) for paper presentations
- **Compute credits** for model training (Google TPU, AWS, Azure)
- **Mentorship matching** with established researchers
- **Open-source contribution bounties** for tool development
- **Documentation and publication support**
- **Requirement: All funded work must be openly licensed**

**Target:** Support 30+ individual researchers over 3 years

#### 4. Academic-Industry Partnerships

Establish:
- Collaborative research projects between universities and tech companies
- Internship programs placing students in industry NLP teams
- Joint research positions with shared funding
- Knowledge transfer through secondments
- **Partnership agreements must include open-source clauses**

#### 5. Research Infrastructure

Provide:
- Access to high-performance computing ([GPU clusters](https://en.wikipedia.org/wiki/Graphics_processing_unit))
- Subscriptions to essential NLP tools and datasets
- Conference travel and publication support
- Shared computational resources for model training

#### 6. International Collaboration

Join:
- [CLARIN-ERIC](https://www.clarin.eu/) as associate members (observer status 2027)
- Horizon Europe research projects on multilingual NLP
- Collaboration with under-resourced language communities
- [European Language Equality initiative](https://european-language-equality.eu/)

#### 7. Albanian NLP Workshop/Hackathon

Host annual events (2027, 2028):
- Showcase Albanian language technology research
- **Organize open competitions with transparent judging criteria**
- **Competitions open to all researchers, students, and developers**
- Publish proceedings in open-access format
- Award prizes for best contributions
- **All competition outputs released under open licenses**
- **Collaboration with FLOSSK for community engagement**

### Performance Indicators (2026-2028)

- 60+ researchers trained in NLP methods (Q4 2028)
- 12 PhD scholarships awarded (distributed 2026-2028)
- 6 postdoctoral fellowships awarded (distributed 2026-2028)
- **30+ individual researchers supported** through microgrants (Q4 2028)
- 30+ peer-reviewed publications on Albanian NLP (Q4 2028)
- 3-4 academic-industry collaborative projects initiated (Q2 2027)
- 2 workshops/hackathons with **open competitions** hosted (2027, 2028)
- Gender parity in funded researchers: 45-55% female representation (ongoing)
- **100% of funded research outputs openly licensed** (ongoing)

---

## Pillar 5: Governance, Funding, and Sustainability

**Objective:** Establish sustainable institutional structures and diversified funding mechanisms to ensure continuity beyond 2028.

### Key Actions

#### 1. Albanian NLP Resource Center Establishment

Create a distributed center with nodes in:
- **Tirana Node:** University of Tirana + Albanian Academy of Sciences
- **Prishtina Node:** University of Prishtina + Academy of Sciences and Arts of Kosovo
- **Tetova Node:** South East European University + State University of Tetovo

**Governance Structure:**
- Steering Committee with government, academic, and international representatives
- Technical Working Groups for specific domains
- **Individual Researcher Advisory Board**
- **Community Organization Representatives (e.g., FLOSSK)**
- Annual planning cycles with stakeholder consultations
- **Open licensing policy mandate for all center outputs**

#### 2. National Funding Mechanisms

**Proportional Contributions (3 Years - Albania & Kosovo Only):**

**Annual Funding Commitments:**
- **Albania:** €500,000 annually (€1,500,000 total)
  - Ministry of Education, Sports and Youth: €300,000
  - Ministry of Infrastructure and Energy: €200,000
- **Kosovo:** €500,000 annually (€1,500,000 total)
  - Ministry of Education, Science, Technology and Innovation: €300,000
  - Ministry of Economy: €200,000

**Total National Contribution:** €1,000,000 annually (€3,000,000 over 2026-2028)

**Note:** North Macedonia participates as academic and research partner without government funding commitment.

#### 3. EU and International Funding

**Funding Prioritization Strategy:**
Projects that secure co-funding from EU sources will receive **priority** in the allocation of national funds. This leveraging strategy maximizes total investment and aligns with successful models from Estonia and Croatia.

**IPA III (Instrument for Pre-Accession Assistance)**
- Target: €1.5-2 million for regional cooperation in digital innovation
- Reference: [IPA III Overview](https://enlargement.ec.europa.eu/enlargement-policy/overview-instrument-pre-accession-assistance_en)
- **Projects with IPA III co-funding receive 2x matching priority**

**Horizon Europe**
- Target: €700K-1M through Cluster 4 (Digital, Industry and Space)
- Reference: [Horizon Europe Programme](https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe_en)
- **Projects with Horizon Europe participation receive 2x matching priority**

**Connecting Europe Facility (CEF)**
- Target: €300K-500K for language technology platform development
- Reference: [CEF Telecom](https://hadea.ec.europa.eu/news/cef-telecom-funding-keeps-advancing-machine-translation-and-language-technologies-2023-01-30_en)
- **CEF co-funded projects receive priority support**

**Digital Europe Programme**
- Target: €600K-900K through Alliance for Language Technologies
- Reference: [Digital Europe Programme](https://digital-strategy.ec.europa.eu/en/activities/digital-programme)
- **Digital Europe co-funded projects receive priority support**

**GenAI4EU**
- Part of the European Technological Sovereignty Package (June 2026); supports "development and adoption of open and trustworthy AI solutions"
- Potential funding for the Albanian LLM continual pretraining work package
- Reference: [GenAI4EU (European Commission)](https://digital-strategy.ec.europa.eu/en/policies/genai4eu)

**European Technological Sovereignty Package — Candidate Country Access (Partial)**

The Tech Sovereignty Package (June 2026) — comprising the EU Open Source Strategy, Cloud and AI Development Act (CADA), Chips Act 2.0, and Strategic Roadmap for Energy Digitalization — is primarily designed for EU member states. Direct access by candidate countries is not confirmed and the legislative text does not include explicit candidate-country provisions. However, three indirect pathways exist:

1. **OpenEuroLLM** (Digital Europe Programme, €37.4M) explicitly covers candidate-country languages — this is the most direct route into EU AI sovereignty infrastructure that is already open to Albanian participation
2. **CADA "associated third country" derogation** (Article 18): Applies to countries with EU GDPR adequacy decisions. Albania does not yet have a full adequacy decision; progress toward one would unlock formal participation pathways in CADA's sovereignty framework

**Recommendation:** Frame all open source language technology outputs explicitly in terms of EU tech sovereignty alignment in communications to the EC. This positions the plan advantageously as CADA and the Open Source Strategy move through the legislative process and accession negotiations advance.

**Open Source Maintenance Instrument** (EU Open Source Strategy, June 2026)
- New instrument for long-term sustainability of critical open source components
- Target Albanian NLP tools (NLTK extension, spaCy pipeline) for this instrument once released and widely used; eligibility for candidate countries is not yet confirmed but warrants monitoring as the instrument is operationalized

**EuroHPC Extreme-Scale Access Grants**
- LUMI supercomputer (Finland) and other EuroHPC machines available to EU and candidate-country institutions
- Used by Poro 34B, Viking, TildeOpen, OpenEuroLLM; directly applicable for Albanian model continual pretraining
- Apply in Phase 1 (2026) for Phase 2 (2027) training runs
- Reference: [LUMI supercomputer](https://lumi-supercomputer.eu/)

**UNESCO and Research Foundations**
- Target: €100K-200K for language preservation
- OpenAI, Google, Microsoft AI for Good programs

**Total Estimated EU/International:** €3.2-4.6M over 2026-2028

**Co-funding Requirement:** All EU-funded projects must commit to **open licensing of all outputs** as a condition of receiving national matching funds.

#### 4. Public-Private Partnerships

- Corporate sponsorships: €30K-100K annually from Albanian tech companies
- Collaborative research projects with revenue-sharing
- In-kind contributions (cloud credits, software licenses)
- Target: €300K-600K over three years
- **Partnership agreements must include open-source output clauses**

### Total Funding Summary (2026-2028)

| Source | Amount (3 years) | Annual Average |
|--------|------------------|----------------|
| Albania Government | €1,500,000 | €500,000 |
| Kosovo Government | €1,500,000 | €500,000 |
| EU/International | €3,200,000-4,600,000 | €1,067,000-1,533,000 |
| Private Sector | €300,000-600,000 | €100,000-200,000 |
| **TOTAL** | **€6.5-8.2 million** | **€2.2-2.7 million** |

**Note:** This accelerated model relies on substantial national government commitment complemented by European Union co-funding (49-70% of total budget), following Croatia's successful approach. **Projects with EU co-funding receive priority for national matching funds.** **Timings and budgets are indicative** and should be refined through detailed consultation with funding agencies and stakeholders.

---

## Monitoring and Evaluation Framework

### Continuous Tracking

- Real-time dashboards tracking KPIs
- GitHub-integrated analytics for tool development
- Usage analytics for deployed services
- Semi-annual progress reports from each node
- **Open licensing compliance tracking**

### Mid-Term Evaluation (Q2 2027)

Independent assessment including:
- Progress review against 2026-2027 milestones
- Technical review of datasets, tools, documentation
- **Individual researcher impact assessment**
- **Open licensing compliance audit**
- Stakeholder consultations
- Financial audit
- Strategic recommendations for 2027-2028

### Final Evaluation (Q4 2028)

Comprehensive assessment including:
- Goal achievement measurement
- Impact analysis (digital inclusion, economic development, research capacity)
- Comparison with Estonia, Croatia benchmarks
- Sustainability analysis
- **Assessment of open-source ecosystem development**
- Policy recommendations for 2029-2031 continuation

### Quality Assurance Protocols

- Inter-annotator agreement scores > 0.85 for all annotations
- Systematic benchmarking against international standards
- Comprehensive documentation requirements
- GDPR compliance for all data processing
- Bias mitigation assessments for deployed AI
- **Open licensing verification for all funded outputs**

---

## Appendix: Grant-Based Work Packages (Open Calls for Proposals)

**All work packages are subject to open competition with transparent evaluation criteria. Proposals will be evaluated by independent review panels including international experts. Projects that secure EU co-funding will receive priority for national matching funds.**

**Critical Funding Note:** The budgets listed below represent **indicative total project costs**. Given national budgets (€1,000,000 annually), **securing EU co-funding (IPA III, Horizon Europe, CEF, Digital Europe) is essential for most work packages to proceed at full scale.** Projects with confirmed EU co-funding receive 2x priority in national fund allocation.

**Mandatory Licensing Requirements:** All outputs from funded projects must be released under open licenses:
- **Code:** MIT or Apache 2.0
- **Models:** Apache 2.0 or CC-BY 4.0
- **Data:** CC0 or CC-BY 4.0
- **Documentation:** CC-BY 4.0

### WP1: Albanian Speech Donation Campaign (Mozilla Common Voice Expansion)
- **Total Budget:** €80,000 | **Duration:** 18 months
- **Funding Strategy:** Requires IPA III or Digital Europe co-funding; national contribution €30,000-40,000
- **Target:** 500+ hours validated speech by Q4 2027, 1,000+ hours by Q4 2028, 2,000+ speakers
- **Deliverables:** 
  - Web/mobile contribution platform based on Mozilla Common Voice
  - Expansion of FLOSSK's successful campaign model to universities and high schools
  - Student engagement toolkit and curriculum integration materials
  - Community campaigns across Albania, Kosovo, and North Macedonia
  - Dialectal coverage (Gheg and Tosk)
  - All data released under **CC0 license** via Mozilla Common Voice platform
- **Open to:** Community organizations (including FLOSSK), universities, individual coordinators, academic teams
- **Priority:** Projects demonstrating existing community engagement capacity and confirmed EU co-funding
- **Open competition with transparent criteria**

### WP2: Albanian Named Entity Recognition System
- **Total Budget:** €50,000 | **Duration:** 18 months
- **Funding Strategy:** Requires Horizon Europe or Digital Europe co-funding; national contribution €20,000-30,000
- **Deliverables:** 30,000+ token NER corpus, F1≥80% model, open-source release under **MIT/Apache 2.0**, comprehensive documentation
- **Open to:** Individual researchers, academic teams
- **Mandatory licensing:** Code (MIT), Models (Apache 2.0), Data (CC-BY 4.0)
- **Open competition**

### WP3: Machine Translation for Albanian Government
- **Total Budget:** €180,000 | **Duration:** 30 months
- **Funding Strategy:** Requires CEF or IPA III co-funding; national contribution €60,000-80,000
- **Deliverables:** 300K+ Albanian-English pairs, 150K+ Albanian-German/Italian, BLEU≥25, integration with 2+ government portals, all resources openly licensed
- **Open to:** Research consortia, academic-industry partnerships
- **Mandatory licensing:** Code (Apache 2.0), Models (Apache 2.0), Data (CC-BY 4.0)
- **Co-funding priority:** Projects with CEF or IPA III co-funding receive priority
- **Open competition**

### WP4: Individual Researcher Microgrants for NLP Tools
- **Total Budget Pool:** €200,000 | **Grant Size:** €3,000-€8,000 per grant | **Duration:** 6-12 months
- **Funding Strategy:** Can be funded from national budget with rolling allocations
- **Deliverables:** Open-source tools (spell-checkers, sentiment analysis, QA systems, parsers) released under **MIT or Apache 2.0**
- **Open to:** Individual researchers, graduate students, independent developers
- **Mandatory licensing:** All outputs under MIT or Apache 2.0
- **Rolling application deadlines**

### WP5: Albanian Digital Library Search System
- **Total Budget:** €60,000 | **Duration:** 18 months
- **Funding Strategy:** Requires Digital Europe or Horizon Europe co-funding; national contribution €20,000-30,000
- **Deliverables:** Semantic search engine, recommendation system, integration with 1-2 national libraries, all code openly licensed
- **Open to:** Research teams, library partnerships
- **Mandatory licensing:** Code (MIT), Models (Apache 2.0)
- **Open competition**

### WP6: Albanian Language Technology Summer School
- **Total Budget:** €40,000 annually (€120,000 total) | **Duration:** Annual 2026-2028
- **Funding Strategy:** Requires IPA III or Horizon Europe co-funding; national contribution €15,000-20,000 annually
- **Deliverables:** 2-week intensive training, 25-30 participants annually, all educational materials released under **CC-BY 4.0**
- **Open to:** Academic consortia, research centers
- **Mandatory licensing:** All materials CC-BY 4.0
- **Multi-year commitment preferred**

### WP7: PhD Scholarship Program in Albanian NLP
- **Total Budget:** €720,000 (€60,000 per scholarship × 12 scholarships)
- **Funding Strategy:** Requires IPA III or Horizon Europe Marie Skłodowska-Curie Actions co-funding; national contribution €200,000-300,000 total
- **Individual Grant:** €60,000 (€20K/year × 3 years)
- **Requirements:** 
  - PhD dissertation on Albanian language technology
  - 2+ peer-reviewed publications in reputable venues
  - Open-source contributions (code, data, or models)
  - All research outputs openly licensed
- **Open to:** Individual PhD candidates at partner institutions
- **Competitive selection with transparent criteria**

### WP8: Albanian-English Parallel Corpus from EU Documents
- **Total Budget:** €45,000 | **Duration:** 15 months
- **Funding Strategy:** Can leverage CEF or Digital Europe co-funding; national contribution €20,000-25,000
- **Deliverables:** 750K+ aligned sentence pairs from EU acquis, released under **CC-BY 4.0**
- **Open to:** Research teams, individual researchers
- **Mandatory licensing:** CC-BY 4.0
- **Open competition**

### WP9: Academic-Industry Partnership for Chatbots
- **Total Budget:** €120,000 (50% co-funded with industry) | **Duration:** 24 months
- **Funding Strategy:** Requires private sector match + Horizon Europe or IPA III; national contribution €40,000-50,000
- **Deliverables:** Conversational dataset, chatbot framework, 1-2 commercial deployments, all core technology openly licensed
- **Open to:** Academic-industry consortia
- **Mandatory licensing:** Core framework (Apache 2.0), Training data (CC-BY 4.0)
- **Private sector contributions may retain proprietary deployment layers**
- **Open competition**

### WP10: National Competence Center Infrastructure
- **Total Budget:** €200,000 | **Duration:** 30 months (establishment phase)
- **Funding Strategy:** Requires IPA III regional cooperation funding; national contribution €80,000-100,000
- **Deliverables:** Physical offices in Tirana/Prishtina/Tetovo, centralized repository, GPU cluster, full-time staff, open-source infrastructure
- **Open to:** Academic consortia, government partnerships
- **Infrastructure must support open-source development**

### WP11: NLTK and spaCy Albanian Extensions
- **Total Budget:** €70,000 | **Duration:** 24 months
- **Funding Strategy:** Requires Horizon Europe or Digital Europe co-funding; national contribution €30,000-40,000
- **Deliverables:**
  - Albanian Stemmer for NLTK SnowballStemmer
  - Albanian Punkt sentence tokenizer for NLTK
  - Complete spaCy pipeline (tokenizer, POS tagger, parser, NER, lemmatizer)
  - Documentation and integration tests
  - All code released under **MIT license**
- **Open to:** Individual developers, research teams
- **Mandatory licensing:** MIT
- **Priority:** Developers with prior contributions to NLTK or spaCy
- **Open competition**

---

## Glossary of Key Terms

For policymakers and non-technical readers, here are quick definitions of the main technical terms used in this plan:

**[NLP (Natural Language Processing)](https://en.wikipedia.org/wiki/Natural_language_processing):** The branch of artificial intelligence that enables computers to understand, interpret, and generate human language. Examples: Google Translate, Siri, ChatGPT.

**[ASR (Automatic Speech Recognition)](https://en.wikipedia.org/wiki/Speech_recognition):** Technology that converts spoken language into written text. Examples: voice dictation, live captions, virtual assistants.

**[TTS (Text-to-Speech)](https://en.wikipedia.org/wiki/Speech_synthesis):** Technology that converts written text into spoken audio. Used for audiobooks, GPS navigation, screen readers.

**[Machine Translation (MT)](https://en.wikipedia.org/wiki/Machine_translation):** Automated translation from one language to another using AI. Examples: Google Translate, DeepL.

**[NER (Named Entity Recognition)](https://en.wikipedia.org/wiki/Named-entity_recognition):** Technology that identifies and classifies proper names in text (people, places, organizations). Used for document search, information extraction.

**[POS (Part-of-Speech) Tagging](https://en.wikipedia.org/wiki/Part-of-speech_tagging):** Labeling each word in a sentence with its grammatical category (noun, verb, adjective). Foundation for grammar checkers.

**[LLM (Large Language Model)](https://en.wikipedia.org/wiki/Large_language_model):** Advanced AI systems trained on vast amounts of text that can understand and generate human-like language. Examples: ChatGPT, Claude, Gemini.

**[BLEU Score](https://en.wikipedia.org/wiki/BLEU):** A metric (0-100) measuring machine translation quality by comparing it to human translations. Scores of 25+ indicate reasonable quality for under-resourced languages.

**[WER (Word Error Rate)](https://en.wikipedia.org/wiki/Word_error_rate):** The percentage of words incorrectly transcribed by speech recognition. Lower is better; <10% is considered production-ready.

**[FAIR Principles](https://www.go-fair.org/fair-principles/):** Guidelines ensuring research data is Findable, Accessible, Interoperable, and Reusable—maximizing scientific and societal value.

**[GDPR](https://gdpr.eu/):** General Data Protection Regulation—the EU's comprehensive law protecting personal data and privacy.

**[CLARIN](https://www.clarin.eu/):** Common Language Resources and Technology Infrastructure—a European network providing researchers with access to language data and tools.

**[IPA III](https://enlargement.ec.europa.eu/enlargement-policy/overview-instrument-pre-accession-assistance_en):** Instrument for Pre-Accession Assistance—EU funding specifically for candidate countries preparing for EU membership.

**Corpus (plural: corpora):** A large, structured collection of texts or speech recordings used to train language technology systems.

**Open-source:** Software or data whose source code/content is freely available for anyone to use, modify, and distribute.

**GPU (Graphics Processing Unit):** Specialized computer processors that dramatically accelerate AI model training.

**Open licensing:** Legal framework that allows others to freely use, modify, and distribute creative works (code, data, models, documentation) with certain conditions like attribution (CC-BY, MIT, Apache 2.0) or no conditions at all (CC0).

**NLTK (Natural Language Toolkit):** A widely-used Python library for working with human language data, providing tools for tokenization, stemming, tagging, parsing, and more.

**spaCy:** An open-source library for advanced NLP in Python, designed for production use with pre-trained models for multiple languages.

---

## References

### Language Technology Programmes

**Estonian Language Technology (2018-2027):** https://www.keeletehnoloogia.ee/en

**Center of Estonian Language Resources (CELR):** https://keeleressursid.ee/en/

**Croatia HRVOJKA Platform:** https://www.nltp-info.eu/post/croatia-has-launched-the-nltp-platform-hrvojka

**HR-CLARIN Initiative:** https://www.clarin.eu/blog/introduction-hr-clarin

### European Funding and Frameworks

**IPA III Overview:** https://enlargement.ec.europa.eu/enlargement-policy/overview-instrument-pre-accession-assistance_en

**Horizon Europe:** https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe_en

**Digital Europe Programme:** https://digital-strategy.ec.europa.eu/en/activities/digital-programme

**CEF Language Technologies:** https://hadea.ec.europa.eu/news/cef-telecom-funding-keeps-advancing-machine-translation-and-language-technologies-2023-01-30_en

**European Language Grid:** https://live.european-language-grid.eu/

**CLARIN-ERIC:** https://www.clarin.eu/

**European Language Equality:** https://european-language-equality.eu/

### Albanian Language Resources

**Albanian National Corpus:** https://albanian.web-corpora.net/

**AlbNER Corpus (2023):** https://arxiv.org/abs/2309.08741

**AlbNews Corpus (2024):** https://arxiv.org/abs/2402.04028

**Albanian Multi-dialectal Twitter Corpus:** https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10681245/

**Albanian NLP State-of-the-Art Survey (2022):** https://www.researchgate.net/publication/365910257_Natural_language_processing_for_Albanian_a_state-of-the-art_survey

**OSCAR Corpus:** https://oscar-project.org/

**CulturaX Dataset:** https://huggingface.co/datasets/uonlp/CulturaX

### Albanian NLP Tools and Models

**albanian-nlp GitHub:** https://github.com/arditdine/albanian-nlp

**nlp-for-albanian GitHub:** https://github.com/thinkgradient/nlp-for-albanian

**Albanian ASR GitHub:** https://github.com/florijanqosja/Albanian-ASR

**Google FLEURS Dataset:** https://huggingface.co/datasets/google/fleurs

**Helsinki-NLP OPUS-MT:** https://huggingface.co/Helsinki-NLP/opus-mt-en-sq

**fastText Word Embeddings:** https://fasttext.cc/docs/en/crawl-vectors.html

**edisnord/albert-base-v2-sq:** https://huggingface.co/edisnord/albert-base-v2-sq

**Visar/roberta_oscar_al:** https://huggingface.co/Visar/roberta_oscar_al

**Kushtrim Visoka Hugging Face Models:**
- **Llama-3.1-8B-Instruct-bnb-4bit-shqip:** https://huggingface.co/Kushtrim/Llama-3.1-8B-Instruct-bnb-4bit-shqip
- **speecht5_finetuned_cv_sq:** https://huggingface.co/Kushtrim/speecht5_finetuned_cv_sq
- **bert-base-multilingual-cased-sq-sentiment-sst2:** https://huggingface.co/Kushtrim/bert-base-multilingual-cased-sq-sentiment-sst2
- **bert-base-multilingual-cased-finetuned-albanian-ner:** https://huggingface.co/Kushtrim/bert-base-multilingual-cased-finetuned-albanian-ner

### Speech Data Resources

**Mozilla Common Voice:** https://commonvoice.mozilla.org/

**Mozilla Common Voice Albanian:** https://commonvoice.mozilla.org/sq

**CASR: Albanian Speech Recognition Corpus:** https://ieeexplore.ieee.org/document/9596689

**Albanian ASR Dataset (Kaggle):** https://www.kaggle.com/datasets/flooxperia/albanian10

**Whisper Medium Albanian Model:** https://dataloop.ai/library/model/kushtrim_whisper-medium-sq/

### Community Organizations

**FLOSSK (Free Libre Open Source Software Kosova):** https://flossk.org/

### Government Digital Initiatives

**e-Albania Platform:** https://en.wikipedia.org/wiki/EAlbania

**Western Balkans Digital Agenda:** https://www.rcc.int/priority_areas/56/digital-economy

### International Organizations

**UNESCO Digital Initiatives for Languages:** https://www.unesco.org/en/articles/digital-initiatives-indigenous-languages

**LT4All Conference Series:** https://www.gcedclearinghouse.org/events/language-technologies-all-–-lt4all-2025

### Academic Institutions

**University of Pristina:** https://en.wikipedia.org/wiki/University_of_Pristina

**Albanological Institute of Pristina:** https://en.wikipedia.org/wiki/Institute_of_Albanology_in_Pristina

### Technical Benchmarks and Standards

**Universal Dependencies:** https://universaldependencies.org/

**Universal Dependencies Albanian Treebanks:**
- **TSA:** https://universaldependencies.org/treebanks/sq_tsa/
- **STAF:** https://universaldependencies.org/treebanks/sq_staf/
- **GPS-Gheg:** https://universaldependencies.org/treebanks/aln_gps/

**META-NET White Papers:** http://www.meta-net.eu/whitepapers/

**FAIR Data Principles:** https://www.go-fair.org/fair-principles/

**OpenAI Whisper:** https://openai.com/index/whisper/

### NLP Libraries and Tools

**NLTK (Natural Language Toolkit):** https://www.nltk.org/

**spaCy:** https://spacy.io/

**OPUS Parallel Corpora:** https://opus.nlpl.eu/

### EU Policy Frameworks

**EU AI Act:** https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689

**AI Continent Action Plan (April 2025):** https://digital-strategy.ec.europa.eu/en/factpages/ai-continent-action-plan

**European Technological Sovereignty Package (June 2026):** https://digital-strategy.ec.europa.eu/en/library/communication-european-tech-sovereignty-accompanied-eu-open-source-strategy

**EU Open Source Strategy:** https://digital-strategy.ec.europa.eu/en/policies/open-source-strategy

**GenAI4EU:** https://digital-strategy.ec.europa.eu/en/policies/genai4eu

**Cloud and AI Development Act (CADA):** https://digital-strategy.ec.europa.eu/en/policies/cloud-and-ai-development-act

### National LLM Models and European AI Infrastructure

**BgGPT (INSAIT, Bulgaria):** https://insait.ai/insait-creates-leading-bulgarian-first-llm-with-gemma-2/

**Meltemi 7B paper (arXiv):** https://arxiv.org/html/2407.20743v1

**Krikri 8B (Hugging Face):** https://huggingface.co/ilsp/Llama-Krikri-8B-Base

**Bielik 7B v0.1 paper (arXiv):** https://arxiv.org/abs/2410.18565

**EuroLLM-9B (Hugging Face):** https://huggingface.co/blog/eurollm-team/eurollm-9b

**OpenEuroLLM Project:** https://openeurollm.eu/

**HPLT Project:** https://hplt-project.org/

**LUMI Supercomputer:** https://lumi-supercomputer.eu/

**Poro 34B (arXiv):** https://arxiv.org/pdf/2404.01856

**Meta MMS (Massively Multilingual Speech):** https://ai.meta.com/blog/multilingual-model-speech-recognition/

**Whisper Large-v3 (Hugging Face):** https://huggingface.co/openai/whisper-large-v3

### Albanian NLP — 2025 Updates

**Albanian NER Corpus 2025 (SpringerLink):** https://link.springer.com/chapter/10.1007/978-3-031-87769-8_14

**STAF Treebank (January 2025):** https://universaldependencies.org/treebanks/sq_staf/

### Key Research Papers

**Abadji, J. et al. (2022).** "Towards a Cleaner Document-Oriented Multilingual Crawled Corpus." *arXiv:2201.06642*. https://arxiv.org/abs/2201.06642

**Nguyen, T. et al. (2023).** "CulturaX: A Cleaned, Enormous, and Multilingual Dataset for Large Language Models in 167 Languages."

**Joulin, A. et al. (2016).** "Bag of Tricks for Efficient Text Classification." *arXiv:1607.01759*. https://arxiv.org/abs/1607.01759

**Rista, A. & Kadriu, A. (2021).** "CASR: A Corpus for Albanian Speech Recognition." *Proceedings of MIPRO 2021*, pp. 438-441. https://ieeexplore.ieee.org/document/9596689

**Tiedemann, J. et al. (2023).** "Democratizing Neural Machine Translation with OPUS-MT." *arXiv:2212.01936*. https://arxiv.org/abs/2212.01936

**Morozova, M., Rusakov, A., & Arkhangelskiy, T. (2025).** Albanian National Corpus. http://albanian.web-corpora.net

**University of Tirana et al. (2024).** "Universal Dependencies Treebank for Standard Albanian: A New Approach." *Proceedings of CLIB 2024*, pp. 80-89. https://dcl.bas.bg/wp-content/uploads/2024/11/2024.clib-1.7.pdf

**Li, M. et al. (2022).** "TrOCR: Transformer-based Optical Character Recognition with Pre-trained Models." *arXiv:2109.10282*. https://arxiv.org/abs/2109.10282

---

## Conclusion

This **accelerated 3-year Albanian Language Technology Development Plan (2026–2028)** represents a focused, evidence-based strategy to advance the Albanian language into the digital age. Drawing from successful models in Estonia and Croatia while adapting to the cross-border context of Albanian-speaking regions, this plan addresses critical gaps in language resources, tools, applications, research capacity, and governance.

### Key Features of This Plan

- **Condensed timeline** focusing on foundational infrastructure and rapid deployment
- **Explicit support for individual researchers** through microgrants, compute resources, and recognition systems
- **Acknowledgment of existing work** by Albanian NLP researchers and community organizations like FLOSSK
- **Prioritization of Mozilla Common Voice** as a key open-source speech data platform, with ambitious target of **1,000+ hours**
- **Expansion to universities and high schools** for systematic speech data collection
- **Integration with mainstream NLP libraries** (NLTK, spaCy) to make Albanian a first-class supported language
- **Open licensing mandate** for all funded outputs to ensure maximum accessibility and reuse
- **Open competition** for all work packages with transparent evaluation criteria
- **Co-funding prioritization** to leverage EU resources and maximize total investment
- **Realistic budget requirements** clearly indicating EU co-funding as essential for implementation
- **Substantial government commitment** with €1 million annually from Albania and Kosovo combined, leveraging EU funding for 49-70% of the total €6.5-8.2M budget

### Expected Outcomes by 2028

By 2028, Albanian will have:
- Foundational digital infrastructure including a 60-million-token corpus and **1,000 hours of speech data**
- 6-8 open-source NLP tools with documented performance, **all openly licensed**
- **First-class support in NLTK and spaCy** enabling familiar workflows for Albanian developers
- Integration into 8-10 public service platforms
- A growing research community of 60+ trained researchers plus 30+ supported individual contributors
- **Thriving open-source ecosystem** with 2,000+ speech contributors across universities and high schools
- Institutional structures for continued development beyond 2028
- **All outputs openly licensed** for maximum community benefit

The cross-border collaboration among Albania, Kosovo, and North Macedonia sets a precedent for regional cooperation, demonstrating how shared linguistic heritage can be leveraged for mutual technological and economic benefit.

### Critical Success Factors

1. **Sustained government commitment** to substantial annual funding (€1M annually)
2. **Active engagement** from Albanian NLP researchers (institutional and independent)
3. **Strategic pursuit** of EU funding opportunities (IPA III, Horizon Europe, CEF, Digital Europe)
4. **Community mobilization** for data contribution, building on FLOSSK's proven model
5. **University and high school engagement** for systematic speech data collection
6. **Open licensing compliance** ensuring all outputs remain freely accessible
7. **Prioritization of mainstream tool integration** (NLTK, spaCy) for maximum developer impact
8. **Iterative refinement** of this plan based on community feedback and evolving needs

### Important Reminder

This plan was developed rapidly using AI assistance as a conversation starter. **Timings, budgets, and technical specifications are indicative** and require validation by domain experts, funding agencies, and government officials. We encourage the Albanian language technology community to provide feedback, corrections, and improvements to this document.

**Success requires collective action beginning in 2026.** With this plan as a starting point and immediate mobilization of resources, Albanian is positioned to achieve foundational digital language capabilities, ensuring that 8 million speakers can participate in and benefit from the digital society.

---

## Next Steps for Implementation

### Immediate Actions (June–August 2026)

1. Circulate plan to Albanian NLP researchers, linguists, FLOSSK, and stakeholders for feedback
2. Present plan to Ministers of Education in Albania and Kosovo
3. Secure formal commitments for national baseline funding (€1M annually)
4. Sign bilateral memorandum of understanding establishing governance and **open licensing mandate**
5. **Engage OpenEuroLLM consortium before July 2026 deadline** to confirm Albanian inclusion and contribute data
6. Identify and contact National IPA III Coordinators for Digital Economy programmes
7. Begin preparing competitive EU funding applications (IPA III, Horizon Europe, CEF, Digital Europe)
8. Apply for EuroHPC extreme-scale compute access on LUMI for Phase 2 model training
9. Host planning workshop with key Albanian NLP researchers and FLOSSK representatives
10. Establish open communication channels (GitHub, Discord, mailing list)
11. Publish work package descriptions with transparent evaluation criteria

### Phase 1 Actions (September–December 2026)

1. Stand up Albanian NLP Resource Center with governance structure operational
2. Launch corpus collection campaigns and European Language Grid provider accounts
3. Establish ASR baselines (Whisper Large-v3, Meta MMS zero-shot) and publish results
4. Translate and validate MMLU-sq, HellaSwag-sq, ARC-sq benchmark sets
5. Launch Open Albanian LLM Leaderboard
6. Launch Mozilla Common Voice expansion campaign; target 100 hours by year end
7. Release first round of individual researcher microgrants
8. Initiate NLTK and spaCy extension projects with open calls for developers

### Contact Information

**For feedback and collaboration:**
- GitHub: https://github.com/arianit/albanian-language-tech-plan
- Email: [to be added]

**Existing Community Resources:**
- FLOSSK: https://flossk.org/
- Mozilla Common Voice Albanian: https://commonvoice.mozilla.org/sq

---

**Document Version:** 0.2 (Draft for Community Consultation)
**Publication Date:** June 2026 (v0.1: November 2025)
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)

**Changes in v0.2:**
- Added alignment with EU AI Act, AI Continent Action Plan (April 2025), and European Technological Sovereignty Package / EU Open Source Strategy (June 2026)
- Added national LLM case studies: BgGPT (Bulgaria), Meltemi/Krikri (Greece), OpenEuroLLM consortium
- Updated LLM development strategy to continual pretraining methodology
- Updated ASR baseline references to Whisper Large-v3 and Meta MMS
- Added synthetic data generation pipeline as a named strategy (§10)
- Added Albanian evaluation benchmarks and Open Albanian LLM Leaderboard (§9)
- Updated timeline to reflect June 2026 current status; split Phase 1 into completed (Q1–Q2) and remaining (Q3–Q4) with urgency flags
- Added Albanian LLM and synthetic data milestones to Phase 2
- Added analysis of Tech Sovereignty Package access pathways for candidate countries (indirect via OpenEuroLLM and CADA adequacy track)
- Added EuroHPC/LUMI, GenAI4EU, CADA, and Open Source Maintenance Instrument to funding mechanisms
- Updated resource inventory with STAF treebank (January 2025), new NER corpus (2025), HPLT v2 dataset

**Disclaimer:** This document was created using Large Language Models as a planning template and is an evolving draft open to community input. It requires ongoing expert review before implementation. All funded outputs will be openly licensed to ensure maximum accessibility and community benefit.
