# A few additional basic tips on how to run Edward Choi's `medgan`

Here is the link to Edward Choi's medGAN on GitHub: https://github.com/mp2893/medgan. Congrats to his excellent work.

In this markdown, I add a few very basic details that complete Choi's `README.md` and can help run medGAN. My specs: Windows 10. I would like to thank [@ZwAnto](https://github.com/ZwAnto) for his assistance. The goal of this markdown is just to run `medgan` and not to obtain useful results: we try to minimize the computing time at the cost of having poorly realistic generated samples.

### 1) Process the MIMIC-III dataset with `process_mimic.py`.

First of all, we need to open _Anaconda Navigator_, then go to _Environments_, click on the right triangle next to _base (root)_ and _Open Terminal_: this opens a command prompt with the following path: `(base) C:\Users\myusername>`.

In the command prompt, we change the directory to the folder where `ADMISSIONS.csv` and `DIAGNOSES_ICD.csv` from the MICMIC-III dataset (we only need these two) and the python codes are saved:
```
cd C:\Users\myusername\Documents\medgan-master
```
Still in the command prompt, we can then process the MIMIC-III dataset:
```
python process_mimic.py ADMISSIONS.csv DIAGNOSES_ICD.csv test1 "binary"
```
This will create 3 files in our folder: `test1.matrix`, `test1.pids` and `test1.types`.

### 2) Run `medgan.py` using the `test1.matrix` file generated by `process_mimic.py`.

With the command `python medgan.py --help`, we can see all the parameters we can choose. Please read the NumPy version issue I added on Edward Choi's GitHub: https://github.com/mp2893/medgan/issues/14.

In our `medgan-master` folder, we create a `train` folder. Then we use the command:
```
python medgan.py test1.matrix ./train/test --data_type="binary" --n_epoch=10 --n_pretrain_epoch=10
```
Once again, the goal here is just to run medGAN, not to obtain useful results: we try to minimize the computing time by taking small values for `n_epoch` and `n_pretrain_epoch`.
This will create 32 files in our `train` folder: `checkpoint`, `test`, `test-0.data-00000-of-00001`, `test-0.index` etc.

### 3) Generate synthetic records.

We use the command:
```
python medgan.py test1.matrix output1 --model_file=./train/test-9 --generate_data=True
 ```
Instead of 9, we take the last epoch (here we took 10 epochs starting from the index 0). This will create the `output1.npy` file in the `medgan-master` folder.

In order to obain a csv file, we can execute the following script in Python:
```
import numpy as np
import os
os.getcwd()
os.chdir('C:\\Users\\myusername\\Documents\\medgan-master')
data = np.load('output1.npy')

import csv
with open('output1.csv', 'w') as csvFile:
    writer = csv.writer(csvFile)
    writer.writerows(data)
csvFile.close()
 ```
This will create a `output1.csv` file in the `medgan-master` folder.
