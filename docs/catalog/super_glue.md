<div itemscope itemtype="http://schema.org/Dataset">
  <div itemscope itemprop="includedInDataCatalog" itemtype="http://schema.org/DataCatalog">
    <meta itemprop="name" content="TensorFlow Datasets" />
  </div>

  <meta itemprop="name" content="super_glue" />
  <meta itemprop="description" content="SuperGLUE (https://super.gluebenchmark.com/) is a new benchmark styled after&#10;GLUE with a new set of more difficult language understanding tasks, improved&#10;resources, and a new public leaderboard.&#10;&#10;BoolQ (Boolean Questions, Clark et al., 2019a) is a QA task where each example consists of a short&#10;passage and a yes/no question about the passage. The questions are provided anonymously and&#10;unsolicited by users of the Google search engine, and afterwards paired with a paragraph from a&#10;Wikipedia article containing the answer. Following the original work, we evaluate with accuracy.&#10;&#10;To use this dataset:&#10;&#10;```python&#10;import tensorflow_datasets as tfds&#10;&#10;ds = tfds.load('super_glue', split='train')&#10;for ex in ds.take(4):&#10;  print(ex)&#10;```&#10;&#10;See [the guide](https://www.tensorflow.org/datasets/overview) for more&#10;informations on [tensorflow_datasets](https://www.tensorflow.org/datasets).&#10;&#10;" />
  <meta itemprop="url" content="https://www.tensorflow.org/datasets/catalog/super_glue" />
  <meta itemprop="sameAs" content="https://github.com/google-research-datasets/boolean-questions" />
  <meta itemprop="citation" content="@inproceedings{clark2019boolq,&#10;  title={BoolQ: Exploring the Surprising Difficulty of Natural Yes/No Questions},&#10;  author={Clark, Christopher and Lee, Kenton and Chang, Ming-Wei, and Kwiatkowski, Tom and Collins, Michael, and Toutanova, Kristina},&#10;  booktitle={NAACL},&#10;  year={2019}&#10;}&#10;@article{wang2019superglue,&#10;  title={SuperGLUE: A Stickier Benchmark for General-Purpose Language Understanding Systems},&#10;  author={Wang, Alex and Pruksachatkun, Yada and Nangia, Nikita and Singh, Amanpreet and Michael, Julian and Hill, Felix and Levy, Omer and Bowman, Samuel R},&#10;  journal={arXiv preprint arXiv:1905.00537},&#10;  year={2019}&#10;}&#10;&#10;Note that each SuperGLUE dataset has its own citation. Please see the source to&#10;get the correct citation for each contained dataset.&#10;" />
</div>

# `super_glue`

SuperGLUE (https://super.gluebenchmark.com/) is a new benchmark styled after
GLUE with a new set of more difficult language understanding tasks, improved
resources, and a new public leaderboard.

BoolQ (Boolean Questions, Clark et al., 2019a) is a QA task where each example
consists of a short passage and a yes/no question about the passage. The
questions are provided anonymously and unsolicited by users of the Google search
engine, and afterwards paired with a paragraph from a Wikipedia article
containing the answer. Following the original work, we evaluate with accuracy.

*   URL:
    [https://github.com/google-research-datasets/boolean-questions](https://github.com/google-research-datasets/boolean-questions)
*   `DatasetBuilder`:
    [`tfds.text.super_glue.SuperGlue`](https://github.com/tensorflow/datasets/tree/master/tensorflow_datasets/text/super_glue.py)

`super_glue` is configured with `tfds.text.super_glue.SuperGlueConfig` and has
the following configurations predefined (defaults to the first one):

*   `boolq` (`v1.0.2`) (`Size: 3.93 MiB`): BoolQ (Boolean Questions, Clark et
    al., 2019a) is a QA task where each example consists of a short passage and
    a yes/no question about the passage. The questions are provided anonymously
    and unsolicited by users of the Google search engine, and afterwards paired
    with a paragraph from a Wikipedia article containing the answer. Following
    the original work, we evaluate with accuracy.

*   `cb` (`v1.0.2`) (`Size: 73.71 KiB`): The CommitmentBank (De Marneffe et al.,
    2019) is a corpus of short texts in which at least one sentence contains an
    embedded clause. Each of these embedded clauses is annotated with the degree
    to which we expect that the person who wrote the text is committed to the
    truth of the clause. The resulting task framed as three-class textual
    entailment on examples that are drawn from the Wall Street Journal, fiction
    from the British National Corpus, and Switchboard. Each example consists of
    a premise containing an embedded clause and the corresponding hypothesis is
    the extraction of that clause. We use a subset of the data that had
    inter-annotator agreement above 0.85. The data is imbalanced (relatively
    fewer neutral examples), so we evaluate using accuracy and F1, where for
    multi-class F1 we compute the unweighted average of the F1 per class.

*   `copa` (`v1.0.2`) (`Size: 42.96 KiB`): The Choice Of Plausible Alternatives
    (COPA, Roemmele et al., 2011) dataset is a causal reasoning task in which a
    system is given a premise sentence and two possible alternatives. The system
    must choose the alternative which has the more plausible causal relationship
    with the premise. The method used for the construction of the alternatives
    ensures that the task requires causal reasoning to solve. Examples either
    deal with alternative possible causes or alternative possible effects of the
    premise sentence, accompanied by a simple question disambiguating between
    the two instance types for the model. All examples are handcrafted and focus
    on topics from online blogs and a photography-related encyclopedia.
    Following the recommendation of the authors, we evaluate using accuracy.

*   `multirc` (`v1.0.2`) (`Size: 1.06 MiB`): The Multi-Sentence Reading
    Comprehension dataset (MultiRC, Khashabi et al., 2018) is a true/false
    question-answering task. Each example consists of a context paragraph, a
    question about that paragraph, and a list of possible answers to that
    question which must be labeled as true or false. Question-answering (QA) is
    a popular problem with many datasets. We use MultiRC because of a number of
    desirable properties: (i) each question can have multiple possible correct
    answers, so each question-answer pair must be evaluated independent of other
    pairs, (ii) the questions are designed such that answering each question
    requires drawing facts from multiple context sentences, and (iii) the
    question-answer pair format more closely matches the API of other SuperGLUE
    tasks than span-based extractive QA does. The paragraphs are drawn from
    seven domains including news, fiction, and historical text.

*   `record` (`v1.0.2`) (`Size: 49.36 MiB`): (Reading Comprehension with
    Commonsense Reasoning Dataset, Zhang et al., 2018) is a multiple-choice QA
    task. Each example consists of a news article and a Cloze-style question
    about the article in which one entity is masked out. The system must predict
    the masked out entity from a given list of possible entities in the provided
    passage, where the same entity may be expressed using multiple different
    surface forms, all of which are considered correct. Articles are drawn from
    CNN and Daily Mail. Following the original work, we evaluate with max (over
    all mentions) token-level F1 and exact match (EM).

*   `rte` (`v1.0.2`) (`Size: 733.32 KiB`): The Recognizing Textual Entailment
    (RTE) datasets come from a series of annual competitions on textual
    entailment, the problem of predicting whether a given premise sentence
    entails a given hypothesis sentence (also known as natural language
    inference, NLI). RTE was previously included in GLUE, and we use the same
    data and format as before: We merge data from RTE1 (Dagan et al., 2006),
    RTE2 (Bar Haim et al., 2006), RTE3 (Giampiccolo et al., 2007), and RTE5
    (Bentivogli et al., 2009). All datasets are combined and converted to
    two-class classification: entailment and not_entailment. Of all the GLUE
    tasks, RTE was among those that benefited from transfer learning the most,
    jumping from near random-chance performance (~56%) at the time of GLUE's
    launch to 85% accuracy (Liu et al., 2019c) at the time of writing. Given the
    eight point gap with respect to human performance, however, the task is not
    yet solved by machines, and we expect the remaining gap to be difficult to
    close.

*   `wic` (`v1.0.2`) (`Size: 386.93 KiB`): The Word-in-Context (WiC, Pilehvar
    and Camacho-Collados, 2019) dataset supports a word sense disambiguation
    task cast as binary classification over sentence pairs. Given two sentences
    and a polysemous (sense-ambiguous) word that appears in both sentences, the
    task is to determine whether the word is used with the same sense in both
    sentences. Sentences are drawn from WordNet (Miller, 1995), VerbNet
    (Schuler, 2005), and Wiktionary. We follow the original work and evaluate
    using accuracy.

*   `wsc` (`v1.0.2`) (`Size: 31.98 KiB`): The Winograd Schema Challenge (WSC,
    Levesque et al., 2012) is a reading comprehension task in which a system
    must read a sentence with a pronoun and select the referent of that pronoun
    from a list of choices. Given the difficulty of this task and the headroom
    still left, we have included WSC in SuperGLUE and recast the dataset into
    its coreference form. The task is cast as a binary classification problem,
    as opposed to N-multiple choice, in order to isolate the model's ability to
    understand the coreference links within a sentence as opposed to various
    other strategies that may come into play in multiple choice conditions. With
    that in mind, we create a split with 65% negative majority class in the
    validation set, reflecting the distribution of the hidden test set, and 52%
    negative class in the training set. The training and validation examples are
    drawn from the original Winograd Schema dataset (Levesque et al., 2012), as
    well as those distributed by the affiliated organization Commonsense
    Reasoning. The test examples are derived from fiction books and have been
    shared with us by the authors of the original dataset. Previously, a version
    of WSC recast as NLI as included in GLUE, known as WNLI. No substantial
    progress was made on WNLI, with many submissions opting to submit only
    majority class predictions. WNLI was made especially difficult due to an
    adversarial train/dev split: Premise sentences that appeared in the training
    set sometimes appeared in the development set with a different hypothesis
    and a flipped label. If a system memorized the training set without
    meaningfully generalizing, which was easy due to the small size of the
    training set, it could perform far below chance on the development set. We
    remove this adversarial design in the SuperGLUE version of WSC by ensuring
    that no sentences are shared between the training, validation, and test
    sets.

However, the validation and test sets come from different domains, with the
validation set consisting of ambiguous examples such that changing one non-noun
phrase word will change the coreference dependencies in the sentence. The test
set consists only of more straightforward examples, with a high number of noun
phrases (and thus more choices for the model), but low to no ambiguity.

*   `wsc.fixed` (`v1.0.2`) (`Size: 31.98 KiB`): The Winograd Schema Challenge
    (WSC, Levesque et al., 2012) is a reading comprehension task in which a
    system must read a sentence with a pronoun and select the referent of that
    pronoun from a list of choices. Given the difficulty of this task and the
    headroom still left, we have included WSC in SuperGLUE and recast the
    dataset into its coreference form. The task is cast as a binary
    classification problem, as opposed to N-multiple choice, in order to isolate
    the model's ability to understand the coreference links within a sentence as
    opposed to various other strategies that may come into play in multiple
    choice conditions. With that in mind, we create a split with 65% negative
    majority class in the validation set, reflecting the distribution of the
    hidden test set, and 52% negative class in the training set. The training
    and validation examples are drawn from the original Winograd Schema dataset
    (Levesque et al., 2012), as well as those distributed by the affiliated
    organization Commonsense Reasoning. The test examples are derived from
    fiction books and have been shared with us by the authors of the original
    dataset. Previously, a version of WSC recast as NLI as included in GLUE,
    known as WNLI. No substantial progress was made on WNLI, with many
    submissions opting to submit only majority class predictions. WNLI was made
    especially difficult due to an adversarial train/dev split: Premise
    sentences that appeared in the training set sometimes appeared in the
    development set with a different hypothesis and a flipped label. If a system
    memorized the training set without meaningfully generalizing, which was easy
    due to the small size of the training set, it could perform far below chance
    on the development set. We remove this adversarial design in the SuperGLUE
    version of WSC by ensuring that no sentences are shared between the
    training, validation, and test sets.

However, the validation and test sets come from different domains, with the
validation set consisting of ambiguous examples such that changing one non-noun
phrase word will change the coreference dependencies in the sentence. The test
set consists only of more straightforward examples, with a high number of noun
phrases (and thus more choices for the model), but low to no ambiguity.

This version fixes issues where the spans are not actually substrings of the
text.

*   `axb` (`v1.0.2`) (`Size: 33.15 KiB`): An expert-constructed, diagnostic
    dataset that automatically tests models for a broad range of linguistic,
    commonsense, and world knowledge. Each example in this broad-coverage
    diagnostic is a sentence pair labeled with a three-way entailment relation
    (entailment, neutral, or contradiction) and tagged with labels that indicate
    the phenomena that characterize the relationship between the two sentences.
    Submissions to the GLUE leaderboard are required to include predictions from
    the submission's MultiNLI classifier on the diagnostic dataset, and analyses
    of the results were shown alongside the main leaderboard. Since this
    broad-coverage diagnostic task has proved difficult for top models, we
    retain it in SuperGLUE. However, since MultiNLI is not part of SuperGLUE, we
    collapse contradiction and neutral into a single not_entailment label, and
    request that submissions include predictions on the resulting set from the
    model used for the RTE task.

*   `axg` (`v1.0.2`) (`Size: 10.17 KiB`): Winogender is designed to measure
    gender bias in coreference resolution systems. We use the Diverse Natural
    Language Inference Collection (DNC; Poliak et al., 2018) version that casts
    Winogender as a textual entailment task. Each example consists of a premise
    sentence with a male or female pronoun and a hypothesis giving a possible
    antecedent of the pronoun. Examples occur in minimal pairs, where the only
    difference between an example and its pair is the gender of the pronoun in
    the premise. Performance on Winogender is measured with both accuracy and
    the gender parity score: the percentage of minimal pairs for which the
    predictions are the same. We note that a system can trivially obtain a
    perfect gender parity score by guessing the same class for all examples, so
    a high gender parity score is meaningless unless accompanied by high
    accuracy. As a diagnostic test of gender bias, we view the schemas as having
    high positive predictive value and low negative predictive value; that is,
    they may demonstrate the presence of gender bias in a system, but not prove
    its absence.

## `super_glue/boolq`

BoolQ (Boolean Questions, Clark et al., 2019a) is a QA task where each example
consists of a short passage and a yes/no question about the passage. The
questions are provided anonymously and unsolicited by users of the Google search
engine, and afterwards paired with a paragraph from a Wikipedia article
containing the answer. Following the original work, we evaluate with accuracy.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 15,942
TRAIN      | 9,427
VALIDATION | 3,270
TEST       | 3,245

### Features
```python
FeaturesDict({
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'passage': Text(shape=(), dtype=tf.string),
    'question': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://github.com/google-research-datasets/boolean-questions](https://github.com/google-research-datasets/boolean-questions)

## `super_glue/cb`

The CommitmentBank (De Marneffe et al., 2019) is a corpus of short texts in
which at least one sentence contains an embedded clause. Each of these embedded
clauses is annotated with the degree to which we expect that the person who
wrote the text is committed to the truth of the clause. The resulting task
framed as three-class textual entailment on examples that are drawn from the
Wall Street Journal, fiction from the British National Corpus, and Switchboard.
Each example consists of a premise containing an embedded clause and the
corresponding hypothesis is the extraction of that clause. We use a subset of
the data that had inter-annotator agreement above 0.85. The data is imbalanced
(relatively fewer neutral examples), so we evaluate using accuracy and F1, where
for multi-class F1 we compute the unweighted average of the F1 per class.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 556
TEST       | 250
TRAIN      | 250
VALIDATION | 56

### Features
```python
FeaturesDict({
    'hypothesis': Text(shape=(), dtype=tf.string),
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=3),
    'premise': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://github.com/mcdm/CommitmentBank](https://github.com/mcdm/CommitmentBank)

## `super_glue/copa`

The Choice Of Plausible Alternatives (COPA, Roemmele et al., 2011) dataset is a
causal reasoning task in which a system is given a premise sentence and two
possible alternatives. The system must choose the alternative which has the more
plausible causal relationship with the premise. The method used for the
construction of the alternatives ensures that the task requires causal reasoning
to solve. Examples either deal with alternative possible causes or alternative
possible effects of the premise sentence, accompanied by a simple question
disambiguating between the two instance types for the model. All examples are
handcrafted and focus on topics from online blogs and a photography-related
encyclopedia. Following the recommendation of the authors, we evaluate using
accuracy.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 1,000
TEST       | 500
TRAIN      | 400
VALIDATION | 100

### Features
```python
FeaturesDict({
    'choice1': Text(shape=(), dtype=tf.string),
    'choice2': Text(shape=(), dtype=tf.string),
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'premise': Text(shape=(), dtype=tf.string),
    'question': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [http://people.ict.usc.edu/~gordon/copa.html](http://people.ict.usc.edu/~gordon/copa.html)

## `super_glue/multirc`

The Multi-Sentence Reading Comprehension dataset (MultiRC, Khashabi et al.,
2018) is a true/false question-answering task. Each example consists of a
context paragraph, a question about that paragraph, and a list of possible
answers to that question which must be labeled as true or false.
Question-answering (QA) is a popular problem with many datasets. We use MultiRC
because of a number of desirable properties: (i) each question can have multiple
possible correct answers, so each question-answer pair must be evaluated
independent of other pairs, (ii) the questions are designed such that answering
each question requires drawing facts from multiple context sentences, and (iii)
the question-answer pair format more closely matches the API of other SuperGLUE
tasks than span-based extractive QA does. The paragraphs are drawn from seven
domains including news, fiction, and historical text.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 41,784
TRAIN      | 27,243
TEST       | 9,693
VALIDATION | 4,848

### Features
```python
FeaturesDict({
    'answer': Text(shape=(), dtype=tf.string),
    'idx': FeaturesDict({
        'answer': Tensor(shape=(), dtype=tf.int32),
        'paragraph': Tensor(shape=(), dtype=tf.int32),
        'question': Tensor(shape=(), dtype=tf.int32),
    }),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'paragraph': Text(shape=(), dtype=tf.string),
    'question': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://cogcomp.org/multirc/](https://cogcomp.org/multirc/)

## `super_glue/record`

(Reading Comprehension with Commonsense Reasoning Dataset, Zhang et al., 2018)
is a multiple-choice QA task. Each example consists of a news article and a
Cloze-style question about the article in which one entity is masked out. The
system must predict the masked out entity from a given list of possible entities
in the provided passage, where the same entity may be expressed using multiple
different surface forms, all of which are considered correct. Articles are drawn
from CNN and Daily Mail. Following the original work, we evaluate with max (over
all mentions) token-level F1 and exact match (EM).

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 120,730
TRAIN      | 100,730
TEST       | 10,000
VALIDATION | 10,000

### Features
```python
FeaturesDict({
    'answers': Sequence(Text(shape=(), dtype=tf.string)),
    'entities': Sequence(Text(shape=(), dtype=tf.string)),
    'idx': FeaturesDict({
        'passage': Tensor(shape=(), dtype=tf.int32),
        'query': Tensor(shape=(), dtype=tf.int32),
    }),
    'passage': Text(shape=(), dtype=tf.string),
    'query': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://sheng-z.github.io/ReCoRD-explorer/](https://sheng-z.github.io/ReCoRD-explorer/)

## `super_glue/rte`

The Recognizing Textual Entailment (RTE) datasets come from a series of annual
competitions on textual entailment, the problem of predicting whether a given
premise sentence entails a given hypothesis sentence (also known as natural
language inference, NLI). RTE was previously included in GLUE, and we use the
same data and format as before: We merge data from RTE1 (Dagan et al., 2006),
RTE2 (Bar Haim et al., 2006), RTE3 (Giampiccolo et al., 2007), and RTE5
(Bentivogli et al., 2009). All datasets are combined and converted to two-class
classification: entailment and not_entailment. Of all the GLUE tasks, RTE was
among those that benefited from transfer learning the most, jumping from near
random-chance performance (~56%) at the time of GLUE's launch to 85% accuracy
(Liu et al., 2019c) at the time of writing. Given the eight point gap with
respect to human performance, however, the task is not yet solved by machines,
and we expect the remaining gap to be difficult to close.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 5,767
TEST       | 3,000
TRAIN      | 2,490
VALIDATION | 277

### Features
```python
FeaturesDict({
    'hypothesis': Text(shape=(), dtype=tf.string),
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'premise': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://aclweb.org/aclwiki/Recognizing_Textual_Entailment](https://aclweb.org/aclwiki/Recognizing_Textual_Entailment)

## `super_glue/wic`

The Word-in-Context (WiC, Pilehvar and Camacho-Collados, 2019) dataset supports
a word sense disambiguation task cast as binary classification over sentence
pairs. Given two sentences and a polysemous (sense-ambiguous) word that appears
in both sentences, the task is to determine whether the word is used with the
same sense in both sentences. Sentences are drawn from WordNet (Miller, 1995),
VerbNet (Schuler, 2005), and Wiktionary. We follow the original work and
evaluate using accuracy.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 7,466
TRAIN      | 5,428
TEST       | 1,400
VALIDATION | 638

### Features
```python
FeaturesDict({
    'end1': Tensor(shape=(), dtype=tf.int32),
    'end2': Tensor(shape=(), dtype=tf.int32),
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'sentence1': Text(shape=(), dtype=tf.string),
    'sentence2': Text(shape=(), dtype=tf.string),
    'start1': Tensor(shape=(), dtype=tf.int32),
    'start2': Tensor(shape=(), dtype=tf.int32),
    'word': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://pilehvar.github.io/wic/](https://pilehvar.github.io/wic/)

## `super_glue/wsc`

The Winograd Schema Challenge (WSC, Levesque et al., 2012) is a reading
comprehension task in which a system must read a sentence with a pronoun and
select the referent of that pronoun from a list of choices. Given the difficulty
of this task and the headroom still left, we have included WSC in SuperGLUE and
recast the dataset into its coreference form. The task is cast as a binary
classification problem, as opposed to N-multiple choice, in order to isolate the
model's ability to understand the coreference links within a sentence as opposed
to various other strategies that may come into play in multiple choice
conditions. With that in mind, we create a split with 65% negative majority
class in the validation set, reflecting the distribution of the hidden test set,
and 52% negative class in the training set. The training and validation examples
are drawn from the original Winograd Schema dataset (Levesque et al., 2012), as
well as those distributed by the affiliated organization Commonsense Reasoning.
The test examples are derived from fiction books and have been shared with us by
the authors of the original dataset. Previously, a version of WSC recast as NLI
as included in GLUE, known as WNLI. No substantial progress was made on WNLI,
with many submissions opting to submit only majority class predictions. WNLI was
made especially difficult due to an adversarial train/dev split: Premise
sentences that appeared in the training set sometimes appeared in the
development set with a different hypothesis and a flipped label. If a system
memorized the training set without meaningfully generalizing, which was easy due
to the small size of the training set, it could perform far below chance on the
development set. We remove this adversarial design in the SuperGLUE version of
WSC by ensuring that no sentences are shared between the training, validation,
and test sets.

However, the validation and test sets come from different domains, with the
validation set consisting of ambiguous examples such that changing one non-noun
phrase word will change the coreference dependencies in the sentence. The test
set consists only of more straightforward examples, with a high number of noun
phrases (and thus more choices for the model), but low to no ambiguity.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 804
TRAIN      | 554
TEST       | 146
VALIDATION | 104

### Features
```python
FeaturesDict({
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'span1_index': Tensor(shape=(), dtype=tf.int32),
    'span1_text': Text(shape=(), dtype=tf.string),
    'span2_index': Tensor(shape=(), dtype=tf.int32),
    'span2_text': Text(shape=(), dtype=tf.string),
    'text': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://cs.nyu.edu/faculty/davise/papers/WinogradSchemas/WS.html](https://cs.nyu.edu/faculty/davise/papers/WinogradSchemas/WS.html)

## `super_glue/wsc.fixed`

The Winograd Schema Challenge (WSC, Levesque et al., 2012) is a reading
comprehension task in which a system must read a sentence with a pronoun and
select the referent of that pronoun from a list of choices. Given the difficulty
of this task and the headroom still left, we have included WSC in SuperGLUE and
recast the dataset into its coreference form. The task is cast as a binary
classification problem, as opposed to N-multiple choice, in order to isolate the
model's ability to understand the coreference links within a sentence as opposed
to various other strategies that may come into play in multiple choice
conditions. With that in mind, we create a split with 65% negative majority
class in the validation set, reflecting the distribution of the hidden test set,
and 52% negative class in the training set. The training and validation examples
are drawn from the original Winograd Schema dataset (Levesque et al., 2012), as
well as those distributed by the affiliated organization Commonsense Reasoning.
The test examples are derived from fiction books and have been shared with us by
the authors of the original dataset. Previously, a version of WSC recast as NLI
as included in GLUE, known as WNLI. No substantial progress was made on WNLI,
with many submissions opting to submit only majority class predictions. WNLI was
made especially difficult due to an adversarial train/dev split: Premise
sentences that appeared in the training set sometimes appeared in the
development set with a different hypothesis and a flipped label. If a system
memorized the training set without meaningfully generalizing, which was easy due
to the small size of the training set, it could perform far below chance on the
development set. We remove this adversarial design in the SuperGLUE version of
WSC by ensuring that no sentences are shared between the training, validation,
and test sets.

However, the validation and test sets come from different domains, with the
validation set consisting of ambiguous examples such that changing one non-noun
phrase word will change the coreference dependencies in the sentence. The test
set consists only of more straightforward examples, with a high number of noun
phrases (and thus more choices for the model), but low to no ambiguity.

This version fixes issues where the spans are not actually substrings of the
text.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split      | Examples
:--------- | -------:
ALL        | 804
TRAIN      | 554
TEST       | 146
VALIDATION | 104

### Features
```python
FeaturesDict({
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'span1_index': Tensor(shape=(), dtype=tf.int32),
    'span1_text': Text(shape=(), dtype=tf.string),
    'span2_index': Tensor(shape=(), dtype=tf.int32),
    'span2_text': Text(shape=(), dtype=tf.string),
    'text': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://cs.nyu.edu/faculty/davise/papers/WinogradSchemas/WS.html](https://cs.nyu.edu/faculty/davise/papers/WinogradSchemas/WS.html)

## `super_glue/axb`

An expert-constructed, diagnostic dataset that automatically tests models for a
broad range of linguistic, commonsense, and world knowledge. Each example in
this broad-coverage diagnostic is a sentence pair labeled with a three-way
entailment relation (entailment, neutral, or contradiction) and tagged with
labels that indicate the phenomena that characterize the relationship between
the two sentences. Submissions to the GLUE leaderboard are required to include
predictions from the submission's MultiNLI classifier on the diagnostic dataset,
and analyses of the results were shown alongside the main leaderboard. Since
this broad-coverage diagnostic task has proved difficult for top models, we
retain it in SuperGLUE. However, since MultiNLI is not part of SuperGLUE, we
collapse contradiction and neutral into a single not_entailment label, and
request that submissions include predictions on the resulting set from the model
used for the RTE task.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split | Examples
:---- | -------:
ALL   | 1,104
TEST  | 1,104

### Features
```python
FeaturesDict({
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'sentence1': Text(shape=(), dtype=tf.string),
    'sentence2': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://gluebenchmark.com/diagnostics](https://gluebenchmark.com/diagnostics)

## `super_glue/axg`

Winogender is designed to measure gender bias in coreference resolution systems.
We use the Diverse Natural Language Inference Collection (DNC; Poliak et al.,
2018) version that casts Winogender as a textual entailment task. Each example
consists of a premise sentence with a male or female pronoun and a hypothesis
giving a possible antecedent of the pronoun. Examples occur in minimal pairs,
where the only difference between an example and its pair is the gender of the
pronoun in the premise. Performance on Winogender is measured with both accuracy
and the gender parity score: the percentage of minimal pairs for which the
predictions are the same. We note that a system can trivially obtain a perfect
gender parity score by guessing the same class for all examples, so a high
gender parity score is meaningless unless accompanied by high accuracy. As a
diagnostic test of gender bias, we view the schemas as having high positive
predictive value and low negative predictive value; that is, they may
demonstrate the presence of gender bias in a system, but not prove its absence.

Versions:

*   **`1.0.2`** (default):

### Statistics

Split | Examples
:---- | -------:
ALL   | 356
TEST  | 356

### Features
```python
FeaturesDict({
    'hypothesis': Text(shape=(), dtype=tf.string),
    'idx': Tensor(shape=(), dtype=tf.int32),
    'label': ClassLabel(shape=(), dtype=tf.int64, num_classes=2),
    'premise': Text(shape=(), dtype=tf.string),
})
```

### Homepage

*   [https://github.com/rudinger/winogender-schemas](https://github.com/rudinger/winogender-schemas)

## Citation
```
@inproceedings{rudinger-EtAl:2018:N18,
  author    = {Rudinger, Rachel  and  Naradowsky, Jason  and  Leonard, Brian  and  {Van Durme}, Benjamin},
  title     = {Gender Bias in Coreference Resolution},
  booktitle = {Proceedings of the 2018 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies},
  month     = {June},
  year      = {2018},
  address   = {New Orleans, Louisiana},
  publisher = {Association for Computational Linguistics}
}

@article{wang2019superglue,
  title={SuperGLUE: A Stickier Benchmark for General-Purpose Language Understanding Systems},
  author={Wang, Alex and Pruksachatkun, Yada and Nangia, Nikita and Singh, Amanpreet and Michael, Julian and Hill, Felix and Levy, Omer and Bowman, Samuel R},
  journal={arXiv preprint arXiv:1905.00537},
  year={2019}
}

Note that each SuperGLUE dataset has its own citation. Please see the source to
get the correct citation for each contained dataset.
```

--------------------------------------------------------------------------------
