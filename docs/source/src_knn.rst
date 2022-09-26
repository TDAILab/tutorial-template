Src_knn
=====

.. _usage:

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

Creating a new repository
------------

Next step is Creating a new repository.
You Open the website https://github.com/, log in to the account and create a new repository.
You prepare three scripts, inference.py, requirements.txt and train.py in one directory.
You create a predict function in inference.py. This function has two arguments. The first argument is a model you use.  The second argument is "input_json" that was stored some data. 
You use used the accuracy_score, KNeighborsClassifier, train_test_split methods in train.py.
You enter a package and specific version to retrieve in requirements.txt. 

.. note::
   A requirements.txt's name can only be used "requirements.txt" 
   If you can use this name, selected packages are installed automatically.

.. _target to image:

.. figure:: /image/src_knn.png
   :alt: Logo 
   :align: center
   :width: 300px
　　　　　　　　　　　　　　　　Click to enlarge!


Initialize Project
------------
Click the home page of the project page, and you enter github credential.
After you fill out the form, you click the green "Initialize Project" button.
A few minutes later, the blue "Pending" button and the red "Delete Resources in AWS" button will be displayed on the page.
If you click the "Delete Resources in AWS" button, you can't run your project.


Run
------------

Go the Model page, and fill out this page.

* Github Name: Your github name.
* Github repository : The repository name with some scripts. 
* Github path:The path to the upload some scripts.
* S3 Source : The path to the upload folder.
* Container Destination : Type in "data/input/"
* Container Source Path : Type in "data/output/"
* S3 Destination : The path to the folder stored the result of execute the model.
* Processing Command:The path to the preprocessing scripts used the argparse, tarfile, warnings and numpy modules.
* Training Command:The path to the training script. 
* Prediction Command:The path 

※A system run in a container using the data in S3.

.. _target to image:

.. figure:: /image/model_tab.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　Click to enlarge!


After then, you click the dark blue "run" button.\n
The form will pops up on the page, and you enter Image Tag Name and click Deploy to Dev(Dev).\n
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


* Status is Pending : The program is executed at present.
* Status is Success : The program is done and you can see the result on AWS website. Refer to the following for the way.
* Status is Failed : The program is failed because of some reasons. You can investigate a cause to see the "pipeline" page in the AWS site. 
 


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

