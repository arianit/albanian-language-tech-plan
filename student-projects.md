# Student Projects

**Existing language software that can be improved for Albanian — a menu of BSc, MSc and graduation-project topics**

*Part of the [Albanian Language Technology Development Plan (2026–2028)](albanian-language-tech-plan.md) · Status snapshot: 2026-10-03 · License: CC BY 4.0*

---

## How to use this list

Each entry names an existing, widely used open-source tool or dataset, links to where the Albanian (`sq`) support lives, states what that support looks like **today**, and proposes a concrete project. Most are contributions to an upstream project, so the result is used by real users instead of sitting in a thesis PDF.

- **Level** is indicative: **BSc** (a few weeks to one semester, narrow scope), **MSc** (one to two semesters, needs evaluation or training), **BSc/MSc** (can be scoped either way).
- **Class project** is a smaller slice for a team assignment of 2–6 weeks inside a regular course, with the course named. Course names are generic (computer science, linguistics, translation); match them to your own curriculum. See [Class projects by subject](#class-projects-by-subject).
- **Status** facts were checked against the primary source (repository, package index or API) on the snapshot date above. Anything I could not confirm is listed at the end under [Unverified leads](#unverified-leads) and is not asserted anywhere else.
- Contribute upstream first, and open an issue before starting large work. Upstream maintainers often have views on structure and style.
- Licensing matters for this plan, which requires CC0, CC-BY, MIT or Apache 2.0 outputs. Licence conflicts are flagged per entry.

## Summary

| # | Tool | Area | `sq` status today | Level |
|---|------|------|-------------------|-------|
| 1 | [eSpeak NG](#1-espeak-ng) | Speech synthesis / G2P | Present but thin; large rewrite PR open | BSc/MSc |
| 2 | [Piper TTS](#2-piper-tts) | Neural TTS | One single-speaker voice | MSc |
| 3 | [MMS-TTS `sqi`](#3-meta-mms-tts-sqi) | Neural TTS | Exists, non-commercial licence | MSc |
| 4 | [Mozilla Common Voice](#4-mozilla-common-voice) | Speech data | ~9 h, 154 speakers | BSc |
| 5 | [Vosk / Kaldi](#5-vosk--kaldi) | Offline ASR | No Albanian model | MSc |
| 6 | [Hunspell `sq_AL`](#6-hunspell-sq_al-spell-checker) | Spell checking | 2011 dictionary, no `sq_XK` | BSc/MSc |
| 7 | [Hyphenation `hyph_sq_AL`](#7-libreoffice-hyphenation-hyph_sq_al) | Typesetting | Semi-automatic 2021 patterns | BSc |
| 8 | [LanguageTool](#8-languagetool) | Grammar checking | Not supported | MSc |
| 9 | [xkeyboard-config `al`](#9-linux-keyboard-layouts-xkb-al) | Keyboard input | 3 layouts, no Kosovo/Gheg layout | BSc |
| 10 | [spaCy](#10-spacy) | NLP library | Skeleton only (stop words) | BSc/MSc |
| 11 | [NLTK + Snowball](#11-nltk-and-snowball-stemmer) | NLP library / stemming | Stop words only; no stemmer | BSc |
| 12 | [Stanza](#12-stanza) | NLP pipeline | Tokenize, POS, lemma, parse; no NER | MSc |
| 13 | [Morphological analyzer (FST)](#13-albanian-morphological-analyzer-hfst--apertium) | Morphology | No released analyzer found | MSc |
| 14 | [Language ID (fastText, lingua)](#14-language-identification-fasttext-lingua) | Language ID | Standard Albanian only | BSc |
| 15 | [Epitran](#15-epitran) | G2P | `sqi-Latn` rules exist | BSc |
| 16 | [num2words](#16-num2words) | Number spelling | No Albanian | BSc |
| 17 | [Unicode CLDR / Babel](#17-unicode-cldr-sq-locales) | Locale data | `sq`, `sq_AL`, `sq_MK`, `sq_XK` exist | BSc |
| 18 | [Firefox Translations, Argos, OPUS-MT](#18-offline-machine-translation-firefox-translations-argos-opus-mt) | Machine translation | `en↔sq` models exist, quality unknown | MSc |
| 19 | [Tesseract `sqi`](#19-tesseract-sqi) | OCR | Training data last updated 2015 | BSc/MSc |
| 20 | [Wikidata Lexemes / Wiktionary](#20-wikidata-lexemes-and-wiktionary) | Lexical data | 5,318 Wikidata lexemes | BSc |
| 21 | [NVDA + screen readers](#21-nvda-and-screen-reader-testing) | Accessibility | `sq` UI; speech depends on eSpeak NG | BSc |

## Class projects by subject

| Subject | Items |
|---------|-------|
| Introduction to programming / software testing | [16](#16-num2words) |
| Software engineering (open-source contribution) | [10](#10-spacy), [16](#16-num2words) |
| Introduction to NLP | [6](#6-hunspell-sq_al-spell-checker), [10](#10-spacy), [14](#14-language-identification-fasttext-lingua), [18](#18-offline-machine-translation-firefox-translations-argos-opus-mt) |
| Machine learning | [5](#5-vosk--kaldi), [14](#14-language-identification-fasttext-lingua) |
| Information retrieval | [11](#11-nltk-and-snowball-stemmer) |
| Formal languages and automata | [7](#7-libreoffice-hyphenation-hyph_sq_al), [13](#13-albanian-morphological-analyzer-hfst--apertium) |
| Speech processing | [2](#2-piper-tts), [3](#3-meta-mms-tts-sqi), [5](#5-vosk--kaldi) |
| Image processing / computer vision | [19](#19-tesseract-sqi) |
| Databases / semantic web (SPARQL) | [20](#20-wikidata-lexemes-and-wiktionary) |
| Human-computer interaction / accessibility | [9](#9-linux-keyboard-layouts-xkb-al), [21](#21-nvda-and-screen-reader-testing) |
| Data analysis / research methods | [2](#2-piper-tts), [4](#4-mozilla-common-voice) |
| Phonetics and phonology | [1](#1-espeak-ng), [15](#15-epitran) |
| Morphology / syntax | [12](#12-stanza), [13](#13-albanian-morphological-analyzer-hfst--apertium) |
| Albanian grammar and orthography | [6](#6-hunspell-sq_al-spell-checker), [7](#7-libreoffice-hyphenation-hyph_sq_al), [8](#8-languagetool) |
| Corpus linguistics / lexicology | [4](#4-mozilla-common-voice), [12](#12-stanza), [20](#20-wikidata-lexemes-and-wiktionary) |
| Translation studies / localization | [17](#17-unicode-cldr-sq-locales), [18](#18-offline-machine-translation-firefox-translations-argos-opus-mt) |

---

## Speech and text-to-speech

### 1. eSpeak NG

- **URL:** <https://github.com/espeak-ng/espeak-ng> · Albanian rules: [`dictsource/sq_rules`](https://github.com/espeak-ng/espeak-ng/blob/master/dictsource/sq_rules), [`dictsource/sq_list`](https://github.com/espeak-ng/espeak-ng/blob/master/dictsource/sq_list), [`espeak-ng-data/lang/ine/sq`](https://github.com/espeak-ng/espeak-ng/blob/master/espeak-ng-data/lang/ine/sq)
- **`sq` status:** Albanian is supported, but the data is small. `sq_rules` is 174 lines and `sq_list` is 158 lines, against 1,587 lines for `de_rules`. The language file is 4 lines and defines a single `sq` voice with no regional variants. Open [PR #2547 "Albanian (sq) pronunciation improvements"](https://github.com/espeak-ng/espeak-ng/pull/2547) (opened 2026-09-12, unreviewed) rewrites stress and letter-to-phoneme rules, treats `ë`/`ç` correctly, makes word-final `ë` audible, and adds pronunciation tests. An earlier [issue #571](https://github.com/espeak-ng/espeak-ng/issues/571) (2018) is a user asking for a better Albanian voice.
- **Why it matters:** eSpeak NG is the default synthesizer in NVDA and Orca and is widely used as the phonemizer backend for neural TTS toolchains (including Piper), so errors in `sq` pronunciation propagate into everything built on it.
- **Project ideas:**
  1. Review and test PR #2547 with a panel of native speakers (Tosk and Gheg), and report systematic errors. Check word-final `ë` in particular: in standard pronunciation, unstressed final `ë` is usually silent or very weak (*punë*, *nënë*), so making it audible may be wrong for many words.
  2. Build a **gold pronunciation test set** (a few thousand words with IPA, for example from Wiktionary) and a script that scores eSpeak NG output against it. This is reusable for items 1, 2 and 15.
  3. Extend rules for numbers, dates, abbreviations, currency (lek, euro) and Kosovo/North Macedonia place names.
  4. Add a Gheg variant voice (`sq-gheg`-style) and document the phonological differences.
  5. Improve prosody (stress and intonation) and compare intelligibility with listening tests.
- **Level:** BSc (test set, text rules) to MSc (variant voice, listening-test evaluation). **Skills:** phonetics or linguistics background helps; no C required for rule files.
- **Class project:** *Phonetics and phonology*. Each student transcribes 100–200 words into IPA for the gold test set (idea 2); the class then scores eSpeak NG against it and lists the most frequent error types.

### 2. Piper TTS

- **URL:** <https://github.com/rhasspy/piper> · Voice: [`rhasspy/piper-voices` → `sq/sq_AL/edon/medium`](https://huggingface.co/rhasspy/piper-voices/tree/main/sq/sq_AL/edon/medium)
- **`sq` status:** One voice, `sq_AL-edon-medium`: single speaker, 22.05 kHz, ~63.5 MB ONNX, fine-tuned from the US-English *lessac* voice, dataset licence CC0 ([model card](https://huggingface.co/rhasspy/piper-voices/blob/main/sq/sq_AL/edon/medium/MODEL_CARD)).
- **Project ideas:** record or collect a CC0 multi-speaker or second-gender dataset and train additional voices; add a Gheg/Kosovo-accent voice; build an Albanian **text-normalization front end** (numbers, abbreviations, dates) in front of Piper; run a MOS (mean opinion score) listening study comparing Piper, eSpeak NG and MMS-TTS.
- **Level:** MSc. **Skills:** Python, audio recording, basic ML training (GPU access needed).
- **Class project:** *Speech processing* or *research methods*: a small MOS listening test comparing Piper, eSpeak NG and MMS-TTS on 20 fixed sentences (check your faculty's rules for tests with human listeners). *Introduction to programming*: a normalizer for dates, times and abbreviations, without any model training.

### 3. Meta MMS-TTS `sqi`

- **URL:** <https://huggingface.co/facebook/mms-tts-sqi>
- **`sq` status:** A VITS model for Albanian exists, but its licence is **CC-BY-NC 4.0** (non-commercial), which conflicts with this plan's open-licence requirement.
- **Project ideas:** use it only as a comparison baseline; train an openly licensed replacement and show with listening tests that it matches or beats it (combine with item 2).
- **Level:** MSc.
- **Class project:** only as a baseline system in item 2's listening test.

### 4. Mozilla Common Voice

- **URL:** <https://commonvoice.mozilla.org/sq> · Dataset: [Common Voice Scripted Speech 25.0 – Albanian](https://datacollective.mozillafoundation.org/datasets/cmn29zkso01aimm07wb1ar40j) · Sentence list: [`server/data/sq`](https://github.com/common-voice/common-voice/tree/main/server/data/sq)
- **`sq` status:** Release 25.0 (2026-03-22, CC0) has 6,548 clips, 9.25 h total, 9 h validated, 154 speakers, from 52,644 sentences. The dataset has barely grown past the figures in the main plan. Gheg Albanian and Arvanitika Albanian have separate *spontaneous speech* datasets on the same platform.
- **Project ideas:** build a pipeline that extracts public-domain / CC0 Albanian sentences (suitable length, no proper-noun-heavy lines) for the sentence-submission ("Write") page; run a recording campaign at a university and measure contributor retention; analyze speaker/gender/age/dialect balance and publish a gap report.
- **Level:** BSc (campaign, analysis) or BSc/MSc (extraction pipeline with quality filters). **Caution:** only submit sentences you may legally release under CC0.
- **Class project:** *Data analysis* or *corpus linguistics*: analyse the speaker, gender, age and accent metadata of release 25.0 and write a short gap report; or run a one-week recording drive and report how many validated hours it produced.

### 5. Vosk / Kaldi

- **URL:** <https://alphacephei.com/vosk/models> · <https://github.com/kaldi-asr/kaldi>
- **`sq` status:** The published Vosk model list (checked 2026-10-03) has **no Albanian model**. Albanian is covered only by large multilingual models: Whisper has `sq` in its [tokenizer](https://github.com/openai/whisper/blob/main/whisper/tokenizer.py), and Meta [MMS](https://huggingface.co/facebook/mms-1b-all) covers Albanian.
- **Project ideas:** train a small, fast, offline Albanian recognizer (for example Vosk-style or a small Whisper/Conformer distillation) for phones and Raspberry Pi; benchmark it against Whisper and MMS on Common Voice test data and on real speech (parliament, TV). Publish the WER results and the model under Apache 2.0.
- **Level:** MSc. **Skills:** Python, ML training, evaluation methodology.
- **Class project:** *Speech processing* or *machine learning*: run the smaller Whisper sizes and MMS on the Common Voice `sq` test split, compute WER, and classify the errors (diacritics, proper names, numbers). No training needed.

---

## Text input and proofing

### 6. Hunspell `sq_AL` spell checker

- **URL:** <https://github.com/LibreOffice/dictionaries/tree/master/sq_AL> (used by LibreOffice and packaged as `hunspell-sq` / `myspell-sq` in Linux distributions)
- **`sq` status:** `sq_AL.dic` has 229,505 entries and `sq_AL.aff` has 298 lines. The README says version **1.6.4 dated 2011-07-15**, licence **GPL-2.0 or later**, upstream at `shkenca.org/k6i` (not checked whether the upstream is still reachable). The only LibreOffice commits are 2017 (dictionary created from those files) and 2021 (UTF-8 conversion and hyphenation added). There is no `sq_XK` (Kosovo) or `sq_MK` dictionary and no thesaurus, although CLDR defines `sq_XK` and `sq_MK` locales.
- **Project ideas:**
  1. Measure quality: take a modern corpus (for example Albanian Wikipedia text) and report the **out-of-vocabulary rate** and the most frequent false positives (words flagged wrongly) and false negatives (misspellings accepted).
  2. Add missing vocabulary and neologisms; check inflection (affix) coverage for verbs, definite/indefinite noun forms and clitics.
  3. Create `sq_XK` and `sq_MK` variants for regional spelling and vocabulary.
  4. Evaluate relicensing to a permissive licence, which requires contacting the original authors.
- **Level:** BSc (OOV analysis) to MSc (affix redesign, relicensing study).
- **Class project:** *Albanian grammar and orthography* (each student classifies a few hundred flagged words as true or false errors) or *Introduction to NLP* (the script that computes the OOV rate).

### 7. LibreOffice hyphenation `hyph_sq_AL`

- **URL:** <https://github.com/LibreOffice/dictionaries/blob/master/sq_AL/hyph_sq_AL.dic>
- **`sq` status:** A 127 KB pattern file by Isah Bllaca (version 1, 2021-01-04), described as "created semi-automatically", MPL-2.0.
- **Project ideas:** build a gold list of correctly hyphenated Albanian words (digraphs `dh`, `gj`, `ll`, `nj`, `rr`, `sh`, `th`, `xh`, `zh` must not be split), measure the patterns against it, and regenerate patterns with the [Liang/patgen](https://ctan.org/pkg/patgen) approach.
- **Level:** BSc.
- **Class project:** *Formal languages and automata* or *algorithms*: implement Liang's algorithm and test the existing patterns against a gold list built by an *Albanian orthography* class.

### 8. LanguageTool

- **URL:** <https://languagetool.org/languages> · <https://github.com/languagetool-org/languagetool>
- **`sq` status:** Albanian does not appear in the supported-language list checked.
- **Project ideas:** follow LanguageTool's [new-language process](https://dev.languagetool.org/) and build a minimal Albanian module: tokenizer, Hunspell-based spelling (item 6), and 20–50 hand-written grammar rules for the most common errors (definite-article agreement, `ë`/`e` and `ç`/`c` confusion, common clitic mistakes). Even a spelling-plus-few-rules module is a real graduation-project deliverable if it is evaluated against a corpus of real errors.
- **Level:** MSc. **Skills:** Java or XML rule writing, Albanian grammar.
- **Class project:** *Albanian grammar* or *applied linguistics*: collect and annotate 300–500 real errors from public text (forums, comment sections) by type. This error corpus is what any later checker gets evaluated on.

### 9. Linux keyboard layouts (xkb `al`)

- **URL:** [`xkeyboard-config/symbols/al`](https://gitlab.freedesktop.org/xkeyboard-config/xkeyboard-config/-/blob/master/symbols/al)
- **`sq` status:** Three layouts: `basic` ("Albanian"), `plisi` and `veqilharxhi`.
- **Project ideas:** survey which layout Kosovo and North Macedonia users actually use on Windows, Linux, Android and iOS; document how to type `ë` and `ç` on each; propose or test an additional layout or a mobile long-press mapping; write a short user guide. Mobile keyboards were not verified here (see [Unverified leads](#unverified-leads)).
- **Level:** BSc.
- **Class project:** *Human-computer interaction*: user survey plus a timed typing test comparing layouts or input methods for `ë` and `ç`.

---

## NLP libraries and pipelines

### 10. spaCy

- **URL:** <https://github.com/explosion/spaCy/tree/master/spacy/lang/sq>
- **`sq` status:** `spacy/lang/sq` exists with only three files: `__init__.py`, `examples.py` and a 229-line `stop_words.py`. There are **no tokenizer exceptions, punctuation rules, lexical attributes, lemmatizer or trained pipeline.** (The main plan says Albanian is "not supported", which is imprecise: it is a blank-language skeleton. See the note at the end.)
- **Project ideas:** add `tokenizer_exceptions.py` (abbreviations, clitic forms, `m'`, `s'`, `t'`), `punctuation.py` and `lex_attrs.py` (number words such as *një, dy, tre*; `like_num`); add tests; then train a pipeline from the Universal Dependencies treebanks (item 12) and publish `sq_core_news_*`-style packages.
- **Level:** BSc (tokenizer, attributes, tests) to MSc (full trained pipeline with evaluation). Aligns with plan WP11.
- **Class project:** *Software engineering* or *Introduction to NLP*: tokenizer exceptions, `lex_attrs.py` and tests submitted as one upstream pull request. Going through the maintainers' review is part of the exercise, but it can take longer than a semester.

### 11. NLTK and Snowball stemmer

- **URL:** <https://www.nltk.org/> · <https://github.com/snowballstem/snowball/tree/master/algorithms>
- **`sq` status:** The NLTK stopwords corpus has an `albanian` list. The Snowball repository has 38 algorithm files and **none for Albanian**, so no Albanian stemmer exists in Snowball, NLTK, Lucene/Elasticsearch or the many tools that reuse Snowball. I did not check whether NLTK's Punkt sentence tokenizer has Albanian; it is believed not to.
- **Project ideas:** design and implement an **Albanian Snowball stemmer** (the algorithm is written in the Snowball language and compiles to many programming languages), evaluated for retrieval quality on an Albanian test collection or against a hand-lemmatized sample; or train an Albanian Punkt sentence tokenizer.
- **Level:** BSc (stop-word audit, Punkt) to MSc (stemmer with retrieval evaluation).
- **Class project:** *Information retrieval*: a light suffix-stripping stemmer in Python, with search results compared with and without it on a small collection of Albanian documents and queries.

### 12. Stanza

- **URL:** <https://github.com/stanfordnlp/stanza> · Model: <https://huggingface.co/stanfordnlp/stanza-sq> · Treebanks: [UD Albanian TSA](https://universaldependencies.org/treebanks/sq_tsa), [UD Albanian STAF](https://universaldependencies.org/treebanks/sq_staf)
- **`sq` status:** The Stanza resource index lists Albanian with tokenizer, MWT, POS tagger, lemmatizer and dependency parser (packages `combined` and `staf`). It has **no NER and no sentiment model** for `sq`. The UD treebanks are small: TSA has 60 sentences / 922 tokens; STAF (202 sentences of fiction) joined UD at release 2.15; further treebanks are in development per the main plan.
- **Project ideas:** annotate additional UD sentences (news, legal, spoken, Gheg) following UD guidelines; train and publish an Albanian NER model (annotate a corpus first); evaluate Stanza's accuracy by genre and report where it fails.
- **Level:** MSc (NER, treebank). A BSc-sized slice is annotating 500–1,000 sentences with inter-annotator agreement.
- **Class project:** *Syntax* or *corpus linguistics*: each student annotates 30–50 sentences following UD guidelines, and the class measures inter-annotator agreement and discusses where it disagrees.

### 13. Albanian morphological analyzer (HFST / Apertium)

- **URL:** <https://wiki.apertium.org/> · <https://hfst.github.io/>
- **`sq` status:** Albanian has rich nominal and verbal morphology (cases, definiteness suffixes, many verb paradigms). I found **no released Albanian morphological analyzer**. The only Apertium trace is an incubator-stage Macedonian–Albanian bilingual dictionary (`apertium-mk-sq`) from Google Code-in 2011–2012 tasks.
- **Project ideas:** build a finite-state analyzer for a defined subset (for example regular nouns and the present tense of the main verb classes) with lexc/twolc, test it against Stanza lemmas (item 12) and UD annotations, and publish it as a lemmatizer other tools (spaCy, Hunspell affix generation) can use.
- **Level:** MSc. **Skills:** formal grammar, Albanian morphology; this is a strong linguistics + CS cross-over thesis.
- **Class project:** *Formal languages and automata* or *morphology*: a transducer for noun definiteness and case for one declension class (foma, HFST or Python `pynini`).

### 14. Language identification (fastText, lingua)

- **URL:** <https://fasttext.cc/docs/en/language-identification.html> · <https://github.com/pemistahl/lingua-py>
- **`sq` status:** Both include Albanian, as one language, built for standard written text.
- **Project ideas:** build and evaluate a **Tosk vs Gheg** identifier; handle Albanian typed **without diacritics** (`shqip pa e dhe c`) and social-media code-switching with English and Serbian/Macedonian; publish a labelled test set.
- **Level:** BSc.
- **Class project:** *Machine learning* or *Introduction to NLP*: a character n-gram classifier for Tosk vs Gheg, or a diacritic restorer (`e`→`ë`, `c`→`ç`). The diacritic task needs no manual labelling: strip diacritics from correct text to make the training data.

### 15. Epitran

- **URL:** <https://github.com/dmort27/epitran> (language `sqi-Latn`)
- **`sq` status:** Listed as supported.
- **Project ideas:** validate against the gold pronunciation set from item 1, compare with eSpeak NG on the same words, and fix disagreements (stress, `ë`, `ç`, `rr`, `ll`).
- **Level:** BSc.
- **Class project:** *Phonetics and phonology*, as part of item 1's class project (same gold set, second system).

### 16. num2words

- **URL:** <https://github.com/savoirfairelinux/num2words>
- **`sq` status:** No Albanian module (no `sq` file in the package, checked 2026-10-03).
- **Project ideas:** implement Albanian cardinals and ordinals, gender agreement, and currency (lek, euro); add tests. This also becomes the numeral component of text normalization for TTS (items 1–3).
- **Level:** BSc. A well-scoped first open-source contribution.
- **Class project:** *Introduction to programming* or *software testing*. Probably the best first class project in this list: small, clearly specified, and testable.

### 17. Unicode CLDR `sq` locales

- **URL:** <https://github.com/unicode-org/cldr/tree/main/common/main> · [Survey Tool](https://st.unicode.org/cldr-apps/)
- **`sq` status:** `sq.xml`, `sq_AL.xml`, `sq_MK.xml` and `sq_XK.xml` exist. I did not check the coverage level or the completeness of individual sections.
- **Project ideas:** audit month/day names, plural rules, number/currency/date patterns, spell-out rules and sort order against authoritative Albanian sources, and submit corrections. CLDR feeds Android, iOS, Java, ICU, Python Babel and browsers, so one fix reaches billions of devices.
- **Level:** BSc.
- **Class project:** *Software localization* or *translation studies*: split the CLDR sections between students, compare with normative sources (the *Drejtshkrimi* rules, official usage in Kosovo and North Macedonia), and submit corrections in the Survey Tool during an open cycle.

---

## Translation and OCR

### 18. Offline machine translation (Firefox Translations, Argos, OPUS-MT)

- **URLs:** [Firefox Translations models](https://firefox.settings.services.mozilla.com/v1/buckets/main/collections/translations-models/records) · [Argos Translate](https://github.com/argosopentech/argos-translate) · [`Helsinki-NLP/opus-mt-sq-en`](https://huggingface.co/Helsinki-NLP/opus-mt-sq-en) / [`opus-mt-en-sq`](https://huggingface.co/Helsinki-NLP/opus-mt-en-sq) · [Apertium mk-sq](https://wiki.apertium.org/)
- **`sq` status:** Firefox Translations, Argos and OPUS-MT have `sq↔en` (Apertium only has the incubator `mk-sq` pair, item 13). Firefox's Remote Settings lists `sq→en` v1.0 and `en→sq` v1.0a, each a ~17 MB model. I have not measured the quality of any of them.
- **Project ideas:** build a small **evaluation suite** (FLORES-style sentences plus real news and legal text) and compare all systems with BLEU/chrF and human ratings; document systematic errors (gender, definiteness, named entities, Gheg input). Improve the Firefox/Bergamot model with additional parallel data.
- **Level:** MSc. Overlaps with plan WP3 and WP8.
- **Class project:** *Translation studies*: human evaluation and an error typology of 100 sentences per system. *Introduction to NLP*: chrF scores on the FLORES-200 Albanian devtest (its Albanian is standard Tosk, `als_Latn`).

### 19. Tesseract `sqi`

- **URL:** <https://github.com/tesseract-ocr/tessdata> · [`tessdata_best`](https://github.com/tesseract-ocr/tessdata_best) · [`tessdata_fast`](https://github.com/tesseract-ocr/tessdata_fast) · training text: [`langdata/sqi`](https://github.com/tesseract-ocr/langdata/tree/main/sqi)
- **`sq` status:** `sqi.traineddata` exists in all three variants (8.6 MB, 4.6 MB and 1.9 MB). The source training data in `langdata/sqi` was last updated on **2015-06-24**; the training text is 6.7 KB. [EasyOCR](https://github.com/JaidedAI/EasyOCR) also lists `sq`.
- **Project ideas:** create a **ground-truth set** (scanned newspapers, books, forms, and the Albanian passport/ID card layouts that public services scan, using specimen or synthetic documents only, never real people's IDs) with correct `ë`/`ç`; measure character and word error rates for Tesseract and EasyOCR; fine-tune Tesseract with modern fonts and larger training text; test historical alphabets (Albanian Wikisource scans).
- **Level:** BSc (benchmark) to MSc (fine-tuning, historical documents).
- **Class project:** *Image processing*: transcribe 30–50 pages as ground truth, measure CER, and test how preprocessing (binarization, deskewing) changes it.

---

## Lexical data and accessibility

### 20. Wikidata Lexemes and Wiktionary

- **URLs:** [Wikidata lexemes for Albanian (Q8748)](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data) · [sq.wiktionary.org](https://sq.wiktionary.org/) · [English Wiktionary Albanian lemmas](https://en.wiktionary.org/wiki/Category:Albanian_lemmas)
- **`sq` status (counts on 2026-10-03):** 5,318 Albanian lexical entries in Wikidata; 13,776 pages in English Wiktionary's *Albanian lemmas* category; Albanian Wiktionary has 10,244 articles, 10 active users and 1 administrator. For scale, Albanian Wikipedia has 106,389 articles.
- **Project ideas:** write a Pywikibot or QuickStatements pipeline that adds lexemes **with forms and senses** from an openly licensed source; add audio pronunciations (recordings under CC0/CC BY-SA) to Wiktionary; build a coverage dashboard. This feeds spell checking (item 6), morphology (item 13) and MT.
- **Level:** BSc.
- **Class project:** *Databases / semantic web*: SPARQL queries and a coverage dashboard (how many lexemes have forms, senses, audio).

### 21. NVDA and screen reader testing

- **URL:** <https://github.com/nvaccess/nvda> (`source/locale/sq`)
- **`sq` status:** NVDA has an Albanian locale for its interface. Albanian speech in NVDA and Orca typically comes from eSpeak NG (item 1), so the quality gaps there are the quality gaps for blind and low-vision Albanian users.
- **Project ideas:** run structured usability tests with blind users on common Albanian content (news, forms, e-government portals); report mispronunciations to eSpeak NG; evaluate Piper (item 2) as an alternative voice.
- **Level:** BSc. Needs ethics approval and partnership with a blind-users organization.
- **Class project:** *Human-computer interaction / accessibility*: students audit Albanian e-government portals themselves with NVDA against WCAG 2.2 and report the problems found. Without outside participants this usually needs no ethics approval, but check local rules.

---

## Unverified leads

These came up while researching but were **not** confirmed against a primary source, so treat them as questions to check before choosing one as a project:

- Albanian support and quality in mobile keyboards and predictive text (Gboard, iOS, AnySoftKeyboard).
- Montreal Forced Aligner Albanian pronunciation dictionary and acoustic model.
- Kaldi / ESPnet recipes for Albanian.
- TeX `hyph-utf8` Albanian patterns.
- Aspell / Enchant / Chrome / Firefox Albanian spell-check dictionaries.
- Upstream availability of `shkenca.org/k6i`, the Hunspell dictionary's home page.
- Whether NLTK's Punkt has Albanian.
- Academic Albanian morphological analyzers and taggers (for example Trommer and Kallulli, LREC 2004) and whether any are openly released; relevant to item 13's claim that none is available.
- Whether GlotLID or OpenLID distinguish Gheg (`aln`) from Tosk (`als`); relevant to item 14.
- LibreTranslate Albanian support.
- CLDR `sq` coverage level.

## Notes on this document

- **Correction for the main plan:** the plan (and the repository's `CLAUDE.md`) says Albanian is not supported in spaCy and NLTK. More precisely, spaCy has a blank-language `sq` skeleton with stop words, and NLTK has an Albanian stop-word list; neither has a tokenizer, tagger, parser or stemmer for Albanian. The goals in WP11 stand, but the baseline wording should be updated.
- **Status of this list:** facts last spot-checked on 2026-10-05 (Snowball, num2words, Epitran, MMS licence, Stanza processors, UD STAF, hyphenation file); the rest are as of the 2026-10-03 snapshot.
- **Licences to watch:** MMS-TTS is CC-BY-NC (item 3); the Hunspell dictionary is GPL-2.0+ (item 6). Students should check licences before reusing data or code.
- Counts and dates are a snapshot and will drift. Re-check the linked source before citing a figure in a thesis.
- Corrections welcome via issues and pull requests, as for the rest of this repository.
