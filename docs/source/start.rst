GET STARTED
=====

.. _starting:

Set up
----------
**Create the folk**

You go to https://github.com/TDAILab/mlops-test and clck the "folk" button to create the folk.
Folked repository will be created in your account.

.. figure:: /image/create_folk.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

**Create New GitHub App**

You go to the "Settings" page of your account in GitHub website and click "developer settings" in the lower left corner to go to the "GitHub Apps" page.
You follow three actions in this page.
1. You fill in the "Github App name" and "Homepage URL" with whatever you think.

.. figure:: /image/GithubApp_Homepage.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

2. You remove the check mark "Webhook" and grant Contents in the permisson filed the authority of "read only".

.. figure:: /image/Webhook.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

.. figure:: /image/contents.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

3. You select "only on this account" to be able to this GitHub App installed only on your account.
You click the green "Create Github App" button after three actions.

.. figure:: /image/only_on_this_account.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!


**Install New GitHub App**

You configure the settings so that only folked repository has access and install the GitHub App in your account in this section.
After that, you generate a new private key and download it.

**Clone Repository**

You clone the mlops-sdk repository in your terminal.

.. code-block:: python

   git clone https://github.com/TDAILab/mlops-sdk.git

You go to the "mlops-sdk" directory and copy the private key in this directory.
You open this directory in VS code and rewrite "KEYPAIR_PATH" and "ACCESS_TOKEN" in "secret_manager.sh".
You enter pass of private key for "KEYPAIR_PATH" and some string for "ACCESS_TOKEN".
If you execute the "secret_manager.sh" file, you register this with AWS Secret.

.. figure:: /image/manager.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

.. code-block:: python

   bash secret_manager.sh



You execute the Sam command to create a resource in AWS.

.. code-block:: python

   sam build


If the build is complete, you deploy with a guide.

.. code-block:: python

   sam beploy --guided


When prompted for some information, take the following actions.
* Stack Name : some strings
* AS Region : press enter
* Parameter InitStateMachineName : ??
* Parameter InitLambdaFunctionName : ??
* Parameter SecretName : KEYPAIR_NAME set in the "secret_manager.sh".
* Parameter AccessTokenName : TOKEN_NAME set in the "secret_manager.sh".
* Others : press enter

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
This step is creating a new project.
Click on the "project" button inside the page header to navigate to the project page.
Then, click on the dark blue "New Project" button on this page, and enter the name of the new project.

.. note::
   The project name must be between 3 (min) and 63 (max) characters long.
   The project name can consist only of lowercase letters, numbers, dots (.), and hyphens (-).

After that, click on the dark blue Create a new project button, which will generate a new project on your personal account.


Connecting AWS and Github
----------------
This step is connecting AWS and Github.
Select a project you want to initialize and click its button, you will move a selected project page.
After that, click the "Home" button on the left-hand side of the screen. 
Next, you fill out this page. 
You click on the dark blue "Initialize Project" button.
Base API : The URL written in the "Value" field output by the deployment
API token : Access_Token 
Github App ID : Github App ID ust created.
Secret Name in Secret Manager : KEYPAIR_NAME in "secret_manager.sh".
GitHub Name : Your GitHub account name

.. _target to image:

.. figure:: /image/connect_github.png
   :alt: Log
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

After that, you click the dark blue "Initialize" button.
The "Initialize" button will be labeled "Success" if the connection is successful.





補足
---------------------------------------------------------------------------------------------------------------------------------------------------
必要かわからないため残してある
And then, you rewrite parameters "SecretName" and "AccessTokenName" in "template.yaml".

.. figure:: /image/yaml.png
   :alt: Logo 
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


