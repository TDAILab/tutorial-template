Src
=====

.. _usage:

Data upload
------------
First, you go to the AWS website https://aws.amazon.com/jp/.
After that, search for "Amazon SageMaker" and go to this page.
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
You use the used the accuracy_score, SVC, train_test_split methods in train.py.
You enter a package and specific version to retrieve in requirements.txt. 

.. note::
   A requirements.txt's name can only be used "requirements.txt" 
   If you can use this name, selected packages are installed automatically.

.. _target to image:

.. figure:: /image/src_require.png
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

* Github Name: Your github name
* Github repository : The repository name with some scripts. 
* Github path:The path to the upload some scripts.
* S3 Source : The path to the upload folder.
* Container Destination : The path 
* Container Source Path : The path 
* S3 Destination : The path 
* Processing Command:The path to the preprocessing scripts used the argparse, tarfile, warnings and numpy modules.
* Training Command:The path to the training script. 
* Prediction Command:The path 

※A system run in a container using the data in S3.

.. _target to image:

.. figure:: /image/model_run.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　Click to enlarge!


After then, you click the dark blue "run" button.\n
The form will pops up on the page, and you enter Image Tag Name and click Deploy to Dev(Dev).\n
Be careful you cannot use the following characters in the Image Tag Name. \n
If you check the "end point" box, the program does from building an enviroment to model deployment.
If not, the program does nothing but to build an enviroment.\n

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


Result
------------
You can check the result on the AWS website. Go to https://aws.amazon.com/jp/.
Search for "Amazon SageMaker", and go to this page.
Click the "Inference" button on the left-hand side of the Amazon SageMaker page, and click the "Endpoints" button.
You will see results on this page.

.. _target to image:

.. figure:: /image/Endpoint_result.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　Click to enlarge!


.. code-block:: console

   {'ResponseMetadata': 
   {'RequestId': 'ef97246d-0c93-498c-b074-e6b4eb77a1a2', 
   'HTTPStatusCode': 200, 
   'HTTPHeaders': {'x-amzn-requestid': 'ef97246d-0c93-498c-b074-e6b4eb77a1a2', 'x-amzn-invoked-production-variant': 'AllTraffic', 'date': 'Mon, 29 Aug 2022 23:44:07 GMT', 'content-type': 'text/csv; charset=utf-8', 'content-length': '17'}, 
   'RetryAttempts': 0}, 
   'ContentType': 'text/csv; charset=utf-8', 'InvokedProductionVariant': 'AllTraffic', 'Body': <botocore.response.StreamingBody object at 0x000002294E573DF0>}

