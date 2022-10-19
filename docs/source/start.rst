GET STARTED
=====

.. _starting:

Set up
----------

**Create New GitHub App**

You go to the "Settings" page of your account in GitHub website and click "developer settings" in the lower left corner to go to the "GitHub Apps" page.
In this page, you install the created Github App to the repository where the source code is located.
After you create "New GitHub App", you can dawnload a private key.

**Clone Repository**

You go to https://github.com/TDAILab/mlops-sdk and clone the "mlp_sdk" repository.
Next, you rewrite parameters in "secret_manager.sh".
You rewrite KEYPAIR_PATH as Github App private key and ACESS_TOKEN as API access token.

.. figure:: /image/manager.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

After that, you register this with AWS Secret.

And then, you rewrite parameters "SecretName" and "AccessTokenName" in "template.yaml".

.. figure:: /image/yaml.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

**Start up resources**

You start up resources using sam command.
You enter the following code.

.. code-block:: python

   sam sync --stack-name mlops-test  --watch --no-dependency-layer

Accessing MLOpsLight site 
------------
You go to https://mlops-tdai.bubbleapps.io/version-test/projects?debug_mode=true. 
Click on the dark blue SIGN UP OR LOGIN button, and sign up using your e-mail address and password.


Creating a new project
----------------
The second step is creating a new project.
Click on the "project" button inside the page header to navigate to the project page.
Then, click on the dark blue "New Project" button on this page, and enter the name of the new project.

.. note::
   The project name must be between 3 (min) and 63 (max) characters long.
   The project name can consist only of lowercase letters, numbers, dots (.), and hyphens (-).

After that, click on the dark blue Create a new project button, which will generate a new project on your personal account.


.. _target to image:

.. figure:: /image/AWS_credential.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

Initialize Project
------------
The third step is initialize a project.
Click the home page of the project page, and you enter github credential.
After you fill out the form, you click the green "Initialize Project" button.
A few minutes later, the blue "Pending" button and the red "Delete Resources in AWS" button will be displayed on the page.
If you click the "Delete Resources in AWS" button, you can't run your project.

Connecting AWS and Github
----------------
Next step is connecting AWS and Github.
Select a project you want to initialize and click its button, you will move a selected project page.
After that, click the "Home" button on the left-hand side of the screen. 
Next, you fill out this page and click on the dark blue "Initialize Project" button.
If the connection is successful, you will see the following screen

.. _target to image:

.. figure:: /image/connect_github.png
   :alt: Log
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!


This will bring you to the Github webpage. You can select Repository access All repositories or Only select repositories.
We recommend Only selecting repositories, and then you need to select repositories.


.. _target to image:

.. figure:: /image/repository_access.png
   :alt: Lo
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!


