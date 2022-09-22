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
cron : This function is capable of carring out the model on every time you set.
Webhook : This function is notifying when an event occurs.
S3 Event : 
Github Trigger : 
Drift Detected : This function is capable of detecting the difference between the current state and the state that should be.

Codepipeline Setting
------------
Update Docker Image : to update the Docker image 
Manual Approve : How to implement a pipeline that requires two or more approvals in CodePipeline
   Target e-mail address (NotImplemented)
Deploy to Dev : to deploy the model to development environment.
Deploy to Prob : to deploy the model to production environment.
stepfunctions : to visualize and manipulate the flow of processing by defining each process of the application as a step.