# Automatic Speech Recognition (ASR) Models for Child Speech

This document contains instructions to download and use ASR models tailored for child speech. It is well known that child speech is harder for computers to understand when compared to adult speech. While a number of contributing factors have been identified and worked upon, child WERs are usually significantly higher than adult WERs. Further, freely available child speech corpora are few in number and scarce. 

### Models

At the moment, there are two DNN-HMM hybrid models available based on [time-delay](https://www.danielpovey.com/files/2015_interspeech_multisplice.pdf) neural network (TDNN) and [self-attention](https://www.danielpovey.com/files/2018_icassp_attention.pdf). Both models were trained using 2700 hours (clean speech: 700 hrs, noise and reverb augmented: 2000 hrs) of prompted and spontaneous child speech. The models are benchmarked using a subset of the [CIDMIC](https://asa.scitation.org/doi/10.1121/1.426686) corpus, containing 3.2 hours of prompted speech from children between the ages 5 and 17 years

| Model | [Deepspeech](https://github.com/mozilla/DeepSpeech) | [ASPIRE](http://kaldi-asr.org/models/m1) | TDNN | Attention |
| -- | -- | -- | -- | -- |
| WER | 52.32 | 36.38 | 29.50 | 29.76 |


### Decoding 

Download the archive from http://bit.ly/2PKkuP3 and extract it. You will find the following:

```` 
child_asr/  cmd.sh  decode.sh  libri_data/ libri_demo/ mfcc.conf  path.sh  
````

The following variables need to be set in ````decode.sh````:

* suffix : A string, to name your test data
* dataDir : Kaldi [data directory](http://kaldi-asr.org/doc/data_prep.html)
* kaldiPath: Path to Kaldi installation 

You might need to install ````flac```` to decode the demo data.

### Contact

Manoj Kumar (prabakar@usc.edu)
