# Some additional works on Edward Choi's `medGAN`

In this repository, I share my own work that is based on [Edward Choi](https://github.com/mp2893/)'s [medGAN](https://github.com/mp2893/medgan). Congrats to Edward's excellent work!

medGAN (for medical GAN) is a generative adversarial network (GAN) for electronic health records (EHR). medGAN implements the algorithm introduced in the following [paper](https://arxiv.org/abs/1703.06490):

	Generating Multi-label Discrete Patient Records using Generative Adversarial Networks
	Edward Choi, Siddharth Biswal, Bradley Malin, Jon Duke, Walter F. Stewart, Jimeng Sun  
	Machine Learning for Healthcare (MLHC) 2017

I opened a few pull requests on Edward Choi's medGAN repository:
* [Fixing an error due to version 1.16.3 of NumPy](https://github.com/mp2893/medgan/pull/15): merged and closed (following this [issue](https://github.com/mp2893/medgan/issues/14) I opened).
* [Fixing an error when running step 2-3 with count variables](https://github.com/mp2893/medgan/pull/17): merged and closed.

## My own `medgan` repository's table of contents

* `01_tips-for-medgan.md`: [Additional explanations on how to run Edward Choi's medGAN](https://github.com/sylvaincom/medgan-tips/blob/master/01_tips-for-medgan.md). In this markdown, I add explanations that complete Edward Choi's `README.md` of his medGAN repository.
* `02_how-medgan-binary-works.ipynb`: [Understanding how medGAN works on the MIMIC-III dataset of shape (46 520, 1 071) with binary values](https://github.com/sylvaincom/medgan-tips/blob/master/02_how-medgan-binary-works.ipynb). In this notebook, I provide code cells and explanations to help better understand and run medGAN (on binary values). I also measure the accuracy of the fake generated dataset comparing to the real-life original one.
* `03_how-medgan-count-works.ipynb`: [Understanding how medGAN works (with count features)](https://github.com/sylvaincom/medgan-tips/blob/master/03_how-medgan-count-works.ipynb). In this notebook, I provide code cells and explanations that can help better understand and run medGAN on count features.
* `04_accuracy-medgan-binary-small.ipynb`: [Using medGAN on the MIMIC-III dataset of shape (1000, 100) with binary values](https://github.com/sylvaincom/medgan-tips/blob/master/04_accuracy-medgan-binary-small.ipynb). This is shorter version of `02_how-medgan-binary-works.ipynb`: we only sample from a dataset of shape (1000, 100) instead of (46520, 1071) and check the accuracy.
* `05_prediction-augmentation.ipynb`: [Using medGAN to boost the prediction score with data augmentation on the MIMIC-III dataset of shape (1000, 100) with binary values](https://github.com/sylvaincom/medgan-tips/blob/master/05_prediction-augmentation.ipynb). In this notebook, I use `medGAN` to perform data augmentation, thus to boost prediction performance. Spoiler: it works.
