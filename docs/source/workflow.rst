Workflow
=====

.. autosummary::
   :toctree: generated

   lumache

Model Selector
------------
You choose the model that you developed.


Dev or Prob
------------

- Dev : A development environment. Safe place to work on models. 
- Prob :  A production environment. Customers can use your model.
- ARCHIVE : A archive environment. You stored the model without anyone seeing it.


Trigger Setting
------------
Trigger setting is the parameters that define the circumstances in which the workflow performs its actions.

- cron
   Capable of carring out the model on every time you set.
- Webhook
   Notifying when an event occurs.
- S3 Event
   Receive notifications when specific events occur in your S3 bucket.
- Github Trigger
   
- Drift Detected
   This function is capable of detecting the difference between the current state and the state that should be.


Codepipeline Setting
------------
CodePipeline is one of the services that automatically builds or deploys and tests source code.

- Update Docker Image
   to update the Docker image.
- Manual Approve
   How to implement a pipeline that requires two or more approvals in CodePipeline. You need to enter the target e-mail address.
- Deploy to Dev
   to deploy the model to development environment.
- Deploy to Prob
   to deploy the model to production environment.
- stepfunctions
   to visualize and manipulate the flow of processing by defining each process of the application as a step.


Step function
^^^^^^^^

edit with GUI

- Lambda

- Training job

- Batch prediction

- Processing job 
