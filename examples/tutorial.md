## What is FastText and FastText.js
[FastText](https://github.com/facebookresearch/fastText) is a library for efficient learning of word representations and sentence classification. FastText is provided by Facebook Inc. 
_FastText.js_ is a JavaScript library  that wraps _FastText_ to run smoothly within _Node.js_.

## FastText.js APIs
This version of _FastText.js_ comes with the following JavaScript APIs

```javascript
FastText.new(options)
FastText.load()
FastText.loadnn() [NEW API]
FastText.word2vec() [NEW API]
FastText.train()
FastText.test()
FastText.predict(string)
FastText.nn() [NEW API]
```

## How to Install

```bash
git clone https://github.com/loretoparisi/fasttext.js.git
cd fasttext.js
npm install
```

### Install via NPM
_FastText.js_ is available as a npm module [here](https://www.npmjs.com/package/fasttext.js). To add the package to your project

```bash
npm i

#### Train Supervised
To train the model you must specificy the training set as _trainFile_ and the file where the model must be serialized as _serializeTo_. All the _FastText_ supervised options are supported. See [here](https://github.com/facebookresearch/fastText#full-documentation) for more details about training options. Note that _serializeTo_ does not need to have the file extension in. A `bin` extension for the quantized model will be automatically added. You can use the `pretrainedVectors` option to load an unsupervised pre-trained model. Please use the `word2vec` api to train this model.


    var fastText = new FastText({
        serializeTo: './band_model',
        trainFile: './band_train.txt'
    });
    fastText.train()
    .then(done=> {
        console.log("train done.");
    })
    .catch(error => {
        console.error(error);
    })


#### Train Unsupervised
To train an unsupervised model use the _word2vec_ api. You can specify the words representation to train using _word2vec.model_ parameter set to _skipgram_ or _cbow_ and use the _train_ parameters as usual:


    fastText.word2vec()
    .then(done => {
    })
    .catch(error => {
        console.error("Train error", error);
    })
