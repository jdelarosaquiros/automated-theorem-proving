# Automated Theorem Proving

A difficult part of Automated Theorem Proving (ATP) is searching all the intermediate steps to finish a proof, and computers can only check whether the logical inference – guess of the researchers – is correct. Since humans must specify intermediate steps in many theorems, this is time-consuming work that could take a couple of years. To help with this problem, this model predicts the usefulness of a statement (ntermediate step) in proving a conjecture.

# Dataset

This model was trained and tested using the HOLStep dataset. It has 2013046 training examples and 196030 testing examples originating from 11,400 proofs. Also, half of the examples are statements that were useful in proving conjectures. The other examples were derived statements that were not necessary in final proof. For each proof, there is the conjecture being proven, its dependencies (axioms), and some examples. 

The structure of a conjecture block is as follows:<br>
*	N 〈name of conjecture〉
*	C 〈text representation of the conjecture〉
*	T 〈tokenization of the conjecture〉
The structure of each dependency block is:<br>
*	D 〈name of dependency (axiom)〉
*	A 〈text representation of the dependency (axiom)〉
*	T 〈tokenization of the conjecture
Each example block starts with + or -. The + means that the example is useful in the final proof, whereas the – means it isn’t. The structure of an example is the following:<br>
*	- / +〈text representation of the intermediate step〉
*	T 〈tokenization of the intermediate step〉

To download the dataset, click [here](http://cl-informatik.uibk.ac.at/cek/holstep/)

# Usage

The implementation of the model is saved as a notebook in google colab. There are three versions that use different inputs for the third input layer, click on the following to go to their colab:

* [Statement as input](https://colab.research.google.com/drive/1tmJ51kxW_C96Kkne5yEEDGVrgfryiBe0?usp=sharing). 
* [Conjecture as input](https://colab.research.google.com/drive/1-lr5yp6K8dkU0OOYPXABfLSDk3XgL8on?usp=sharing). 
* [Dendencies as input](https://colab.research.google.com/drive/1avlZircqzc9a4KBIGWScQep5qF5i1c1W?usp=sharing). 

To train and evalue the model, simply run all the cells.

Note: Before running the cells, you should place the folder of the holstep dataset in Google Drive the following path: /content/drive/My Drive/Colab Notebooks/holstep. You can use a different path by changing the value of the basePath variable.



