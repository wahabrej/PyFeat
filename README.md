
# <center>PyFeat : A Python-based Effective Features Generation Tool from DNA, RNA, and Protein Sequences </center>

## <center> `Authors: A, B and C` </center>

&nbsp;

## 1. Download Package
### 1.1. Direct Download
We can directly [download](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/mrzResearchArena/PyFeat)  by clicking the link.

**Note:** The package will download in zip format `(.zip)` named `PyFeat-master.zip`.

***`or,`***


### 1.2. Clone a GitHub Repository (Optional)

Cloning a repository syncs it to our local machine. After clone, we can add and edit files and then push and pull updates.
- Clone over HTTPS: `user@machine:~$ git clone https://github.com/mrzResearchArena/PyFeat.git `
- Clone over SSH: `user@machine:~$ git clone git@github.com:mrzResearchArena/PyFeat.git `

**Note:** If the clone was successful, a new sub-directory appears on our local drive. This directory has the same name (PyFeat) as the `GitHub` repository that we cloned.


## 2. Installation Process
### 2.1. Required Python Packages
`Major (Generate Features):`
- Install: python (version >= 3.5)
- Install: numpy (version >= 1.13.1)

`Minor (Performance Measures):`
- Install: sklearn (version >= 0.19.1)
- Install: pandas (version >= 0.21.0)
- Install: matplotlib (version >= 2.1.0)

### 2.2. How to download
`Using PIP:`  pip install `<package name>`
```console
user@machine:~$ pip install scikit-learn
```
**`or,`**

`Using anaconda environment:` conda install `<package name>`

```console
user@machine:~$ conda install scikit-learn
```

## 3. Working Procedure

Run command on your console or terminal.

### 3.1. Generate Features
#### 3.1.1. Training Purpose
```console
user@machine:~$ python main.py --sequenceType=DNA --fasta=/home/mrz/FASTAs.txt --label=/home/mrz/Labels.txt --kTuple=5 --kGap=15 --fullDataset=1 --optimumDataset=1 --pseudoKNC=1 --zCurve=1 --gcContent=1 --cumulativeSkew=1 --atgcRatio=1 --monoMono=1 --monoDi=1 --monoTri=1 --diMono=1 --diDi=1 --diTri=1 --triMono=1 --triDi=1
```
***`or,`***

```console
user@machine:~$ python main.py -seq=DNA -fa=/home/mrz/FASTAs.txt -la=/home/mrz/Labels.txt -ktuple=5 -kgap=15 -full=1 -optimum=1 -pseudo=1 -zcurve=1 -gc=1 -skew=1 -atgc=1 -f11=1 -f12=1 -f13=1 -f21=1 -f22=1 -f23=1 -f31=1 -f32=1
```

#### 3.1.2. Evaluation Purpose

```console
user@machine:~$ python main.py --sequenceType=DNA --fasta=/home/mrz/independentFASTAs.txt --label=/home/mrz/independentLabels.txt --kTuple=5 --kGap=15 --testDataset=1 --pseudoKNC=1 --zCurve=1 --gcContent=1 --cumulativeSkew=1 --atgcRatio=1 --monoMono=1 --monoDi=1 --monoTri=1 --diMono=1 --diDi=1 --diTri=1 --triMono=1 --triDi=1
```
***`or,`***

```console
user@machine:~$ python main.py -seq=DNA -fa=/home/mrz/independentFASTAs.txt -la=/home/mrz/independentLabels.txt -ktuple=5 -kgap=15 -test -pseudo=1 -zcurve=1 -gc=1 -skew=1 -atgc=1 -f11=1 -f12=1 -f13=1 -f21=1 -f22=1 -f23=1 -f31=1 -f32=1
```


[ Comment: The `= sign` is optional. ]

**Note #1:** It will generate a full dataset named **fullDataset.csv** (if -full=1 `or,` --fullDataset==1) <br>
**Note #2:** It will generate a selected features dataset named **optimumDataset.csv** (if -optimum=1 `or,` --optimumDataset==1), and It will also track the selected features index. <br>
**Note #3:** It will generate a full dataset named **testDataset.csv** (if -test=1 `or,` --testDataset==1) [ Especially for the independent (testing) dataset purpose. ] **[ 3.1.2. ]** <br>
**Note #4:** The process will run smoothly for valid FASTA sequences and row-wise class label.

&nbsp;

### Table 1: Arguments Details for the Features Generation
|   Argument     |   Optional   |     Type     |   Default | Help   |
|     :---       |    :---:     |  :---:       |  :---:    | ---:|
| --sequenceType | -seq | string | --sequenceType=DNA | DNA, RNA, and Protein (prot); Case is not sensitive. |
| --fasta | -fa  | string |  | Enter a UNIX-like path; Example: /home/User/FASTA.txt |
| --label | -la  | string |  | Enter a UNIX-like path; Example: /home/User/Label.txt |
| --kGap | -kgap  | integer | --kGap=10  | Maximum number of gapped; Example: -kGap=15  |
| --kTuple | -ktuple  | integer | --kTuple=3  | Maximum number of nucleotides; Example: -kTuple=5 |
| --fullDataset | -full  | integer |  --fullDataset=0  | Set --fullDataset=1, if we don want to save full dataset. |
| --testDataset | -test  | integer |  --testDataset=0  | Set --testDataset=1, if we don want to save test dataset. |
| --optimumDataset | -optimum  | integer |  --optimumDataset=0  | Set --optimumDataset=1, if we don want to save optimum dataset. |
| --pseudoKNC | -pseudo  | integer |  --pseudoKNC=0  | Set --pseudoKNC=1, if we want to generate features. |
| --zCurve | -zcurve  | integer |  --zCurve=0  | Set --zCurve=1, if we want to generate features. |
| --gcContent | -gc  | integer |  --gcContent=0  | Set --gcContent=1, if we want to generate features. |
| --cumulativeSkew | -skew  | integer |  --cumulativeSkew=0  | Set --cumulativeSkew=1, if we want to generate features. |
| --atgcRatio | -atgc  | integer |  --atgcRatio=0  | Set --atgcRatio=1, if we want to generate features. |
| --monoMono | -f11  | integer |  --monoMono=0  | Set --monoMono=1, if we want to generate features. |
| --monoDi | -f12  | integer |  --monoDi=0  | Set --monoDi=1, if we want to generate features. |
| --monoTri | -f13  | integer |  --monoTri=0  | Set --monoTri=1, if we want to generate features. |
| --diMono | -f21  | integer |  --diMono=0  | Set --diMono=1, if we want to generate features. |
| --diDi | -f22  | integer |  --diDi=0  | Set --diDi=1, if we want to generate features. |
| --diTri | -f23  | integer |  --diTri=0  | Set --diTri=1, if we want to generate features. |
| --triMono | -f31  | integer |  --triMono=0  | Set --triMono=1, if we want to generate features. |
| --triDi | -f32  | integer |  --triDi=0  | Set --triDi=1, if we want to generate features. |


&nbsp;
&nbsp;
&nbsp;

### Table 2: Features Description
| Feature Name | Feature Structure / Formula | Number of Features | Applicable |
| :---         |        :---:      |         :---:      |    ---:    |
|zCurve| x_axis = (A+G)-(C+T); y_axis = (A+C)-(G+T); z_axis = (A+T)-(G+C) | 3 features for DNA/RNA | DNA, RNA |
|gcContent| ( (G+C)/(A+C+G+T) ) x 100 % | 1 features for DNA/RNA | DNA, RNA |
|atgcRatio| (A+T)/(G+C) |1 features for DNA/RNA| DNA, RNA |
|cumulativeSkew|gcSkew=(G-C)/(G+C); atSkew=(A-T)/(A+T) |2 features for DNA/RNA| DNA, RNA |
|pseudoKNC| X, XX, XXX | when --kTuple=3, 84 features for DNA/RNA and 8,420 features for protein  | DNA, RNA, Protein |
|monoMonoKGap| X_X |when --kGap=1, 16 features for DNA/RNA and 400 features for protein|DNA, RNA, Protein|
|monoDiKGap| X_XX |when --kGap=1, 64 features for DNA/RNA and 8,000 features for protein|DNA, RNA, Protein|
|monoTriKGap| X_XXX |when --kGap=1, 256 features for DNA/RNA and 160,000 features for protein|DNA, RNA, Protein|
|diMonoKGap| XX_X |when --kGap=1, 64 features for DNA/RNA and 8,000 features for protein|DNA, RNA, Protein|
|diDiKGap| XX_XX |when --kGap=1, 256 features for DNA/RNA and 160,000 features for protein|DNA, RNA, Protein|
|diTriKGap| XX_XXX |when --kGap=1, 1024 features for DNA/RNA and 3,200,000 features for protein|DNA, RNA, Protein|
|triMonoKGap| XXX_X |when --kGap=1, 256 features for DNA/RNA and 160,000 features for protein|DNA, RNA, Protein|
|triDiKGap| XXX_XX |when --kGap=1, 1024 features for DNA/RNA and 3,200,000 features for protein|DNA, RNA, Protein|

**Note:** When sequence becomes DNA, RNA, and Protein then X = {A,C,G,T}, X = {A,C,G,U}, and
X = {A,C,D,E,F,G,H,I,K,L,M,N,P,Q,R,S,T,V,W,Y} respectively.


&nbsp;
&nbsp;
&nbsp;


### 3.2. Run Machine Learning Classifiers
```console
user@machine:~$ python runClassifiers.py --nFCV=10 --dataset=optimumDataset.csv --auROC=1 --boxPlot=1
```

**Note #1:** It will provide classification results (**evaluationResults.txt**) from the user provides binary class dataset (**.csv** format). <br>
**Note #2:** Generate a ROC Curve (**auROC.png**). <br>
**Note #3:** Generate an accuracy comparison via boxPlot (**AccuracyBoxPlot.png**).


&nbsp;

### Table 3: Arguments Details for the Machine Learning Classifiers
|   Argument     |   Optional   |     Type     |   Default | Help   |
|     :---       |    :---:     |  :---:       |  :---:    | ---:|
| --nFCV | -cv | integer | --nFCV=10 | How many numbers of cross-validation? |
| --dataset | -data  | string | --dataset=optimumDataset.csv | Enter a UNIX-like path for a .csv file; Example: /home/User/dataset.csv |
|--auROC|-roc|integer|--auROC=1|Set --auROC=0, if we didn't want to generate the ROC Curve.|
|--boxPlot|-box|integer|--boxPlot=1|Set --boxPlot=0, if we didn't want to generate the accuracy box-plot.|

&nbsp;
### 3.3. Training Model (Optional)

```console
user@machine:~$ python trainModel.py --dataset=optimumDataset.csv --model=LR
```

**Note #1:** It will provide a **dumpModel.pkl** from the user provides binary class dataset (**.csv** format). <br>

&nbsp;

### Table 4: Arguments Details for Training Model
|   Argument     |   Optional   |     Type     |   Default | Help   |
|     :---       |    :---:     |  :---:       |  :---:    | ---:|
| --dataset | -data  | string | --dataset=optimumDataset.csv | Enter a UNIX-like path for a .csv file; Example: /home/User/dataset.csv |
|--model|-m|string|--model=LR|We can use LR, SVM, KNN, DT, SVM, NB, Bagging, RF, AB, GB, and LDA as an option; All options are case sensitive.|
| --K | -k  | integer | --K=5 | Only for the KNN classifier; Number of neighbor |

**Note:** LR, SVM, KNN, DT, NB, Bagging, RF, AB, GB, and LDA represents Logistics Regression, Support Vector Machine, k-Nearest Neighbor, Decision Tree, Naive Bayes, Bagging, Random Forest, AdaBoost, Gradient Boosting, Linear Discriminant Analysis classifier respectively.

&nbsp;
&nbsp;
&nbsp;

### 3.4. Evaluation Model (Optional)

```console
user@machine:~$ python evaluateModel.py --optimumDatasetPath=optimumDataset.csv --testDatasetPath=testDataset.csv
```

**Note #1:** Here, **optimumDataset.csv**, and **testDataset.csv** using as a traing dataset and test dataset respectively.

&nbsp;

### Table 5: Arguments Details for Evaluation Model
|   Argument     |   Optional   |     Type     |   Default | Help   |
|     :---       |    :---:     |  :---:       |  :---:    | ---:|
| --optimumDatasetPath | -optimumPath  | string | --optimumDatasetPath=optimumDataset.csv | Enter a UNIX-like path for a .csv file; Example: /home/User/dataset.csv |
| --testDatasetPath | -testPath  | string | --testDatasetPath=testDataset.csv | Enter a UNIX-like path for a .csv file; Example: /home/User/dataset.csv |


&nbsp;
&nbsp;
&nbsp;

## References

**[1]** Bin Liu et al. (2015) repDNA: a Python package to generate various
modes of feature vectors for DNA sequences by
incorporating user-defined physicochemical
properties and sequence-order effects. Bioinformatics, 31(8), 1307–1309

**[2]** Dong-Sheng Cao et al. (2013) propy: a tool to generate various modes of Chou’s
PseAAC. Bioinformatics, 29, 960–962.


**[3]** Bin Liu et al. (2015) Pse-in-One: a web server for generating various
modes of pseudo components of DNA, RNA, and
protein sequences. Nucleic Acids Research, Vol. 43, Web Server issue W65–W71

**[4]** Bin Liu et al. (2017) Pse-Analysis: a python package for DNA/RNA and protein/peptide sequence analysis based on pseudo components and kernel methods. Oncotarget, Vol. 8, (No. 8), pp: 13338-13343

**[5]** Bin Liu (2017) BioSeq-Analysis: a platform for DNA, RNA and protein
sequence analysis based on machine learning
approaches. Briefings in Bioinformatics, 1–15

**[6]** Zhen Chen et al. (2018) iFeature: a python package and web server for
features extraction and selection from protein
and peptide sequences. Bioinformatics, doi: 10.1093/bioinformatics/bty140

