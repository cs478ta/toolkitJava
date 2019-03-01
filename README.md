# toolkitJava
This is the Java toolkit for CS 478, Tools for Machine Learning, at Brigham Young University.

## Build Instructions for Linux:

* Clone the repo by downloading from the website, or running the command:
 
    ```git clone https://github.com/cs478ta/toolkitJava.git```
* Navigate to the folder and run: ```javac *.java```

* (Optional) See https://www.youtube.com/watch?v=gNC5eIJygl8 for a screencast on how to setup the toolkit in Eclipse

(We do not use Windows, but there is nothing fancy and I imagine that it should work in Microsoft Visual C++. You will need to create a project solution. If you use Windows and have trouble, come see us for help.)


## Usage Instructions:
	MLSystemManager -L [learningAlgorithm] -A [ARFF_File] -E [EvaluationMethod] {[ExtraParamters]}-N {-R [seed]}
        (Note that 3 of the evaluation methods require at least one extra parameter)
	You can also additionally supply the following optional parameters:
	-N          Wrap the learning algorithm in a normalization filter.
	-D          Wrap the learning algorithm in a discretization filter.
	-C          Wrap the learning algorithm in a nominal-to-categorical filter.
	            (It is common to use both -N and -C together. You will do this in
		    the perceptron/neural net lab. The -D filter is useful for the
		    naive Bayes lab.)
	-R [seed]   Specify a seed for the random number generator. (It is a lot easier
	            to debug problems when the algorithm behaves deterministically, so
		    I recommend always specifying a seed.)

	Possible evaluation methods are:
	- Training (using same data set for training and testing)
		MLSystemManager -L [learningAlgorithm] -A [ARFF_File] -E training
	- Static Split (2 distinct datasets/ARFF files; one for training and one for testing
		MLSystemManager -L [learningAlgorithm] -A [ARFF_File] -E static [TestARFF_File]
	- Random Split (1 dataset is split randomly providing x% for training and the rest for testing)
		MLSystemManager -L [learningAlgorithm] -A [ARFF_File] -E random [PercentageForTesting]
	- N-fold Cross-validation (1 dataset is partitioned into N partitions.  The learning algorithm is
	  evaluated on each partion and then the average accuracy is returned.
		MLSystemManager -L [learningAlgorithm] -A [ARFF_File] -E cross [numOfFolds]

### Remarks about the code:
This code is provided to help you learn, not to help you avoid
learning. Hence, you are responsible to become familiar with this
code, not merely to use it blindly. You may opt not to use it. It
is really okay to implement it all yourself from scratch. (That
is how we used to do it, and you just might learn more that way.)
This toolkit should not constrain you. You should plan to modify
it. If you encounter difficulty understanding this code, the TA
can walk you through it. If there are bugs, then you are
responsible to fix them. So "the toolkit is confusing and buggy"
is not a valid excuse for lateness.
