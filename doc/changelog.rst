Changelog/release notes
=======================

3.5
---

* Stanford CoreNLP is now downloaded automatically.

3.4
---

* Added: emotion classifier for film reviews (and maybe other English text).
* Documentation updates.
* Latent dirichlet allocation (LDA, topic modeling) is now performed using
  scikit-learn instead of Gensim. This removes one dependency.
* xtas now requires NLTK 3.1. The previously required version, 3.0a2,
  conflicted with some versions of six, causing cryptic ImportErrors when
  loading xtas in some setups.

3.3
---

* New fast NER tagger for Dutch. Contributed by Daan Odijk of UvA, and based on the CoNLL dataset.
* Fixed a bug that prevented parsimonious language models from returning top-k words for large k. Patch contributed by Sicco van Sas.
* Various minor fixes.

3.2
---

The xtas REST server can now run within an application container such as
uwsgi. By default, it uses Tornado for improved throughput.

A wrapper for the Heideltime temporal tagger has been added.

3.1
---

xtas 3.1 has improved integration with Elasticsearch compared to its
predecessor, storing processing results as child documents. (Previously, they
were stored as fields.) Documentation has also been greatly improved to
demonstrate the use of xtas as a preprocessing engine for semantic search.

Other new features are:

* Stemming support for English, German, Norwegian, Italian, Dutch,
  Portuguese, French, Swedish (via PyStemmer).
* TCP port for communication with Frog (POS tagger/NER/parser for Dutch) is
  now configurable.
* Various bugfixes and small optimizations.

3.0
---

xtas 3.0 is a complete rewrite of the University of Amsterdam's xTAS system
(retroactively, xtas 2) and its predecessor, Fietstas (xtas 1). No attempt
has been made to retain backward compatibility, so that code could be
redesigned in a clean, simple, scalable way.

Features introduced in xtas 3 include:

* Communication with Elasticsearch
* REST API to single-document tasks
* Python API for both synchronous and asynchronous execution (with Celery)

And the following NLP tasks:

* Tokenization, based on NLTK
* Named-entity recognition with Stanford NER (``stanford_ner_tag``)
* Wrapper for the Frog Dutch POS tagger/NER tagger/dependency parser
* Wrapper for the Alpino parser for Dutch
* Language guessing
* English lemmatization with morphy
* Movie review polarity classification
* English POS tagging with NLTK
* Wrapper for the Semafor semantic parser
* Word-level sentiment polarity tagging with SentiWords
* Document clustering with :math:`k`-means (``kmeans``, ``big_kmeans``)
* Topic modeling with latent semantic analysis (LSA), latent dirichlet
  allocation (LDA), based on scikit-learn and Gensim
* Parsimonious language modeling, useful for discriminative word clouds

Preliminary versions of 3.0 were named 2.99.
