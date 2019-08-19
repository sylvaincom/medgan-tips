A few additional works and tips on Edward Choi's medGAN
====

In this repository, I share my own work that is based on [Edward Choi](https://github.com/mp2893/)'s [medGAN](https://github.com/mp2893/medgan). Congrats to Edward's excellent work!

medGAN is a generative adversarial network (GAN) for generating electronic health records (EHR). medGAN implements the algorithm introduced in the following [paper](https://arxiv.org/abs/1703.06490):

	Generating Multi-label Discrete Patient Records using Generative Adversarial Networks
	Edward Choi, Siddharth Biswal, Bradley Malin, Jon Duke, Walter F. Stewart, Jimeng Sun  
	Machine Learning for Healthcare (MLHC) 2017

I opened a few pull requests on Edward Choi's medGAN repository:
* [Fixing an error due to version 1.16.3 of NumPy](https://github.com/mp2893/medgan/pull/15): merged and closed.
* [Fixing an error when running step 2-3 with count variables](https://github.com/mp2893/medgan/pull/17): open.

### My own `medgan` repository's table of contents:
* `01_tips-for-medgan.md`: [A few additional tips on how to run Edward Choi's medGAN](https://github.com/sylvaincom/medgan-tips/blob/master/01_tips-for-medgan.md). In this markdown, I add a few tips that complete Edward Choi's `README.md` of his medGAN repository.
* `02_how-medgan-binary-works.ipynb`: [Understanding how medGAN works (with binary features)](https://github.com/sylvaincom/medgan-tips/blob/master/02_how-medgan-binary-works.ipynb). In this notebook, I provide a few code cells and explanations that can help better understand and run medGAN on binary features.
* `03_how-medgan-count-works.ipynb`: [Understanding how medGAN works (with count features)](https://github.com/sylvaincom/medgan-tips/blob/master/03_how-medgan-count-works.ipynb). In this notebook, I provide a few code cells and explanations that can help better understand and run medGAN on count features.
