<p align="center">
   <a href="https://github.com/jbesomi/texthero/stargazers">
    <img src="https://img.shields.io/github/stars/jbesomi/texthero.svg?colorA=orange&colorB=orange&logo=github"
         alt="Github stars">
   </a>
   <a href="https://pypi.org/search/?q=texthero">
      <img src="https://img.shields.io/pypi/v/texthero.svg?colorB=brightgreen"
           alt="pip package">
   </a>
   <a href="https://pypi.org/project/texthero/">
      <img alt="pip downloads" src="https://img.shields.io/pypi/dm/texthero">
   </a>
   <a href="https://github.com/jbesomi/texthero/issues">
        <img src="https://img.shields.io/github/issues/jbesomi/texthero.svg"
             alt="Github issues">
   </a>
   <a href="https://github.com/jbesomi/texthero/blob/master/LICENSE">
        <img src="https://img.shields.io/github/license/jbesomi/texthero.svg"
             alt="Github license">
   </a>   
</p>

<p align="center">
    <img src="https://github.com/jbesomi/texthero/raw/master/github/logo.png">
</p>

<p style="font-size: 20px;" align="center">Text preprocessing, representation and visualization from zero to hero.</p>


<p align="center">
  <a href="#zero-to-hero">From zero to hero</a> •
  <a href="#installation">Installation</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#documentation">Documentation</a> •
  <a href="#contributions">Contributions</a>
</p>


<h2 align="center">From zero to hero</h2>

**Texthero is a python toolkit that help you work with text-based dataset quickly and effortlessly**. Texthero is very simple to learn and designed to be used on top of Pandas.

You can think of Texthero as a tool to help you _understand_ and work with text-based dataset. Given a tabular dataset, it's easy to _grasp the main concept_. Instead, given a text dataset it's harder to have quick insights of the underline data. With Texthero, preprocessing (cleaning), mapping words into vectors and visualize the reduced vector space takes only a couple lines of code.

To use Texthero, you don't have to spend hours understanding complex and messy code. Texthero is composed of only three python modules *preprocessing.py*, *representation.py*, *visualization.py* and it's <a href="https://texthero.org/docs/getting-started">well documented</a>. Other than that, Texthero is optimized to be very fast.

<h2 align="center">Installation</h2>

Texthero is available on the <a href="https://pypi.org/project/texthero/" target="\_blank">Python Package Index</a> and can be installed via `pip`.

```bash
pip install texthero
```

> ☝️Under the hoods, Texthero makes use of multiple NLP and machine learning toolkits such as Gensim, NLTK, SpaCy and scikit-learn. You don't need to install them all separately, pip will take care of that for you.

<h2 align="center">Getting started</h2>

The best way to learn Texthero is probably via the <a href="">Getting Started</a> official documentation. In case you are a pro python user, then `help(texthero)` should suffices.

<h2 align="center">Example</h2>



```python
import texthero.texthero as hero
import pandas as pd

df = pd.DataFrame(["hello world", "hello", "world"], columns='text')
df = hero.do_preprocess(df)
df = hero.do_tfidf(df)
df = hero.do_pca(df)
hero.scatterplot(df)
```

(The same example can also be found as a "getting-started guide" here: ...)

<h2 align="center">API</h2>

Texthero is composed of three modules: [preprocessing.py](/texthero/preprocessing.py), [representation.py](/texthero/representation.py) and [visualization.py])(/texthero/visualization.py).

<h3>⚒️ 1. Preprocessing</h3>

**Scope:** prepare the **text** data for further analysis.

Complete documentation: [preprocessing](https://jbesomi.github.io/texthero/preprocessing.html)

<h3>📒 2. Representation</h3>

**Job:** map text data into vectors and do dimensionality reduction.

Supported representation algorithms:
1. Term frequency, inverse document frequency (`do_tfidf`)
3. Word2Vec from Gensim [🔜]
4. GloVe [🔜]
5. Transformers [🔜]

Supported dimensionality reduction algorithms:
1. Principal component analysis (`do_pca`)
2. Non-negative matrix factorization (`do_nmf`)

Complete documentation: [representation](https://jbesomi.github.io/texthero/representation.html)

<h3>🔮 3. Visualization</h3>

**Job:** collection of functions to both summarize the main facts regarding the data and visualize the results. This part is very opinionated and ideal for anyone that needs a quick solution to visualize on screen the text data for instance during a text exploratory data analysis (EDA).

Most common functions:
   - Text scatterplot. Handy when coupled with dimensionality reduction algorithms such as pca.
   - Most common words
   - Most common words between two entities [🔜]

Complete documentation: [visualization](https://jbesomi.github.io/texthero/visualization.html)

<h2 align="center">Contributions</h2>

Pull requests are amazing and most welcome.

Any help, feedback and contribution are very welcome. You can simply fork this repository and [open an issue](https://github.com/jbesomi/texthero/issues).
