k-nearest-neighbor
===================
.. autosummary::
   :toctree: generated

   lumache


.. _usage:
You use the the k-nearest neighbors (KNN) algorithm in this tutorial for estimating the likelihood that a data point.
The "Iris date set" is used to train this model. 
This model can predict to the type of Iris by several characteristics.


Data upload
------------
First, you go to the AWS website https://aws.amazon.com/jp/.
After that, search for "S3" and go to this page.
Next page, you find buckets by searching for your project name and go to your buckets page.
Click the orange "Upload" button, and you select a file or a folder you want to use a database.

.. _target to image:

.. figure:: /image/data_Upload.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　Click to enlarge!


Write programs
------------
train.py
^^^^^^^^^^
You create the python file to be able to use the your model.

Firstly, you import modules you'll use in "train.py".
.. code-block:: python
   import os
   import sys
   import pickle
   import pandas as pd
   from sklearn.metrics import accuracy_score
   from sklearn.svm import SVC
   from sklearn.model_selection import train_test_split

Next, you define a function. This function is roughly divided into four steps.

First step is creating training data and test data. You need to load and devide data.

.. code-block:: python
   def main():
    print(os.listdir("data/input"))
    df = pd.read_csv(
        "data/input/train.csv",
        header=None,
        names=["label", "feat1", "feat2", "feat3", "feat4"])

    X = df[["feat1", "feat2", "feat3", "feat4"]].values
    y = df[["label"]].values.ravel()

    X_train, X_test, y_train, y_test = train_test_split(X, y)
    print("X_train:", X_train.shape)
    print("X_test:", X_test.shape)
    print("y_train:", y_train.shape)
    print("y_test:", y_test.shape)

Second step is training a model. You will initialize and train the model.
.. code-block:: python
   clf = SVC()
    print("fitting...")
    clf.fit(X_train, y_train)

Third step is prediction from the model. You test the classifer to to see if it learned well.  

.. code-block:: python
    y_predictions = clf.predict(X_test)
    accuracy = accuracy_score(y_test, y_predictions)

Finally, this python file is stored.
.. code-block:: python
    os.makedirs("data/output", exist_ok=True)
    model_path = "data/output/model.pkl"
    pickle.dump(clf, open(model_path, 'wb'))


requirements.txt
^^^^^^^^^^^

You enter version of the third party libraries used in this text file.
The third party libraries are  available in Python other than the standard library

.. note::
   A requirements.txt's name can only be used "requirements.txt".
   If you use this name, selected packages are installed automatically.

.. code-block:: python

   pandas==1.4.3
   scikit-learn==1.1.2
   cloudpickle==2.1.0


inference.py
^^^^^^^^^^^^
This python file works for inference used the "train.py".
You create a predict function in this python file. This function has two arguments. The first argument is a model saved as "train.py".  The second argument is "input_json" whose type is data frames. 

.. code-block:: python
   import pandas as pd
   def predict(model, input: pd.core.frame.DataFrame) -> np.ndarray[float]:
      prediction = model.predict(input)
      print(f"prediction : {prediction}")
      return prediction


Creating a new repository
------------

Next step is Creating a new repository.
You Open the website https://github.com/, log in to the account and create a new repository.
You create one directory and copy "inference.py", "requirements.txt" and "train.py".


Initialize Project
------------
Click the home page of the project page, and you enter github credential.
After you fill out the form, you click the green "Initialize Project" button.
A few minutes later, the blue "Pending" button and the red "Delete Resources in AWS" button will be displayed on the page.
If you click the "Delete Resources in AWS" button, you can't run your project.


Run
------------

Go the Model page, and fill out this page.

* Github Name : Your github name.
* Github repository : The repository name with some scripts. 
* Github path : The path to the upload some scripts.
* S3 Source : The path to the upload folder.
* Container Destination : Type in "data/input"
* Container Source Path : Type in "data/output"
* S3 Destination : The path to the folder stored the result of execute the model.
* Training Command : The path to the training script. 


※A system run in a container using the data in S3.

.. _target to image:

.. figure:: /image/model_tab.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　Click to enlarge!


After then, you click the dark blue "run" button.
The form will pops up on the page, and you enter Image Tag Name and click Deploy to Dev(Dev).
The program does from building an enviroment to model deployment.

.. note::
   The same rule applies to the Image Tag Name and the Project Name. 
   Image Tag Name must be between 3 (min) and 63 (max) characters long.
   Image Tag Name can consist only of lowercase letters, numbers, dots (.), and hyphens (-).
   


.. _target to image:

.. figure:: /image/model_deployment.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　Click to enlarge!



You can check if the program is done on the history page. Click the "history" button and check out the "Status" section.


* Status is Pending
   The program is executed at present.
* Status is Success
   The program is done and you can see the result on AWS website. Refer to the following for the way.
* Status is Failed
   The program is failed because of some reasons. You can investigate a cause to see the "pipeline" page in the AWS site. 
 


.. _target to image:

.. figure:: /image/confirm_history.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　Click to enlarge!

Endpoint
------------
Endpoints is the URL required to connect to AWS services
You can check the Endpoint on the AWS website. Go to https://aws.amazon.com/jp/.
Search for "Amazon SageMaker", and go to this page.
Click the "Inference" button on the left-hand side of the Amazon SageMaker page, and click the "Endpoints" button.
You will see the Endpoint on this page.


.. _target to image:

.. figure:: /image/Endpoint_result.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　Click to enlarge!

