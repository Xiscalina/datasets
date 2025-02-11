<div itemscope itemtype="http://schema.org/Dataset">
  <div itemscope itemprop="includedInDataCatalog" itemtype="http://schema.org/DataCatalog">
    <meta itemprop="name" content="TensorFlow Datasets" />
  </div>
  <meta itemprop="name" content="cnn_dailymail" />
  <meta itemprop="description" content="CNN/DailyMail non-anonymized summarization dataset.&#10;&#10;There are two features:&#10;  - article: text of news article, used as the document to be summarized&#10;  - highlights: joined text of highlights with &lt;s&gt; and &lt;/s&gt; around each&#10;    highlight, which is the target summary&#10;&#10;&#10;To use this dataset:&#10;&#10;```python&#10;import tensorflow_datasets as tfds&#10;&#10;ds = tfds.load('cnn_dailymail', split='train')&#10;for ex in ds.take(4):&#10;  print(ex)&#10;```&#10;&#10;See [the guide](https://www.tensorflow.org/datasets/overview) for more&#10;informations on [tensorflow_datasets](https://www.tensorflow.org/datasets).&#10;&#10;" />
  <meta itemprop="url" content="https://www.tensorflow.org/datasets/catalog/cnn_dailymail" />
  <meta itemprop="sameAs" content="https://github.com/abisee/cnn-dailymail" />
  <meta itemprop="citation" content="@article{DBLP:journals/corr/SeeLM17,&#10;  author    = {Abigail See and&#10;               Peter J. Liu and&#10;               Christopher D. Manning},&#10;  title     = {Get To The Point: Summarization with Pointer-Generator Networks},&#10;  journal   = {CoRR},&#10;  volume    = {abs/1704.04368},&#10;  year      = {2017},&#10;  url       = {http://arxiv.org/abs/1704.04368},&#10;  archivePrefix = {arXiv},&#10;  eprint    = {1704.04368},&#10;  timestamp = {Mon, 13 Aug 2018 16:46:08 +0200},&#10;  biburl    = {https://dblp.org/rec/bib/journals/corr/SeeLM17},&#10;  bibsource = {dblp computer science bibliography, https://dblp.org}&#10;}&#10;&#10;@inproceedings{hermann2015teaching,&#10;  title={Teaching machines to read and comprehend},&#10;  author={Hermann, Karl Moritz and Kocisky, Tomas and Grefenstette, Edward and Espeholt, Lasse and Kay, Will and Suleyman, Mustafa and Blunsom, Phil},&#10;  booktitle={Advances in neural information processing systems},&#10;  pages={1693--1701},&#10;  year={2015}&#10;}&#10;" />
</div>
# `cnn_dailymail`

CNN/DailyMail non-anonymized summarization dataset.

There are two features: - article: text of news article, used as the document to
be summarized - highlights: joined text of highlights with <s> and </s> around
each highlight, which is the target summary

*   URL:
    [https://github.com/abisee/cnn-dailymail](https://github.com/abisee/cnn-dailymail)
*   `DatasetBuilder`:
    [`tfds.summarization.cnn_dailymail.CnnDailymail`](https://github.com/tensorflow/datasets/tree/master/tensorflow_datasets/summarization/cnn_dailymail.py)

`cnn_dailymail` is configured with
`tfds.summarization.cnn_dailymail.CnnDailymailConfig` and has the following
configurations predefined (defaults to the first one):

*   `plain_text` (`v0.0.2`) (`Size: 558.32 MiB`): Plain text

*   `bytes` (`v0.0.2`) (`Size: 558.32 MiB`): Uses byte-level text encoding with
    `tfds.features.text.ByteTextEncoder`

*   `subwords32k` (`v0.0.2`) (`Size: 558.32 MiB`): Uses
    `tfds.features.text.SubwordTextEncoder` with 32k vocab size

## `cnn_dailymail/plain_text`
Plain text

Versions:

*   **`0.0.2`** (default):
*   `1.0.0`: New split API (https://tensorflow.org/datasets/splits)

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 311,971
TRAIN      | 287,113
VALIDATION | 13,368
TEST       | 11,490

### Features
```python
FeaturesDict({
    'article': Text(shape=(), dtype=tf.string),
    'highlights': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://github.com/abisee/cnn-dailymail](https://github.com/abisee/cnn-dailymail)

### Supervised keys (for `as_supervised=True`)
`(u'article', u'highlights')`

## `cnn_dailymail/bytes`
Uses byte-level text encoding with `tfds.features.text.ByteTextEncoder`

Versions:

*   **`0.0.2`** (default):
*   `1.0.0`: New split API (https://tensorflow.org/datasets/splits)

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 311,971
TRAIN      | 287,113
VALIDATION | 13,368
TEST       | 11,490

### Features
```python
FeaturesDict({
    'article': Text(shape=(None,), dtype=tf.int64, encoder=<ByteTextEncoder vocab_size=257>),
    'highlights': Text(shape=(None,), dtype=tf.int64, encoder=<ByteTextEncoder vocab_size=257>),
})
```

### Homepage

*   [https://github.com/abisee/cnn-dailymail](https://github.com/abisee/cnn-dailymail)

### Supervised keys (for `as_supervised=True`)
`(u'article', u'highlights')`

## `cnn_dailymail/subwords32k`
Uses `tfds.features.text.SubwordTextEncoder` with 32k vocab size

Versions:

*   **`0.0.2`** (default):
*   `1.0.0`: New split API (https://tensorflow.org/datasets/splits)

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 311,971
TRAIN      | 287,113
VALIDATION | 13,368
TEST       | 11,490

### Features
```python
FeaturesDict({
    'article': Text(shape=(None,), dtype=tf.int64, encoder=<SubwordTextEncoder vocab_size=32915>),
    'highlights': Text(shape=(None,), dtype=tf.int64, encoder=<SubwordTextEncoder vocab_size=32915>),
})
```

### Homepage

*   [https://github.com/abisee/cnn-dailymail](https://github.com/abisee/cnn-dailymail)

### Supervised keys (for `as_supervised=True`)
`(u'article', u'highlights')`

## Citation
```
@article{DBLP:journals/corr/SeeLM17,
  author    = {Abigail See and
               Peter J. Liu and
               Christopher D. Manning},
  title     = {Get To The Point: Summarization with Pointer-Generator Networks},
  journal   = {CoRR},
  volume    = {abs/1704.04368},
  year      = {2017},
  url       = {http://arxiv.org/abs/1704.04368},
  archivePrefix = {arXiv},
  eprint    = {1704.04368},
  timestamp = {Mon, 13 Aug 2018 16:46:08 +0200},
  biburl    = {https://dblp.org/rec/bib/journals/corr/SeeLM17},
  bibsource = {dblp computer science bibliography, https://dblp.org}
}

@inproceedings{hermann2015teaching,
  title={Teaching machines to read and comprehend},
  author={Hermann, Karl Moritz and Kocisky, Tomas and Grefenstette, Edward and Espeholt, Lasse and Kay, Will and Suleyman, Mustafa and Blunsom, Phil},
  booktitle={Advances in neural information processing systems},
  pages={1693--1701},
  year={2015}
}
```

--------------------------------------------------------------------------------
