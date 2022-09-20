Workflow
=====

.. autosummary::
   :toctree: generated

   lumache

Model Selector
------------
過去のモデルから選択

Dev or Prob
------------
- Dev : The dev environment is a safe place to work on models. 
- Prob :  Prod or production is the “real” environment. 
- ARCHIVE

Trigger Setting
EventTriggerは、発生させたいイベントを自分で指定するためのコンポーネントです
------------
cron : The model are carried out on every time you set.
Webhook
S3 Event
Github Trigger
Drift Detected

Codepipeline Setting
------------
Update Docker Image : to update the Docker image 
Manual Approve : How to implement a pipeline that requires two or more approvals in CodePipeline
   Target e-mail address (NotImplemented)
Deploy to Dev
Deploy to Prob
stepfunctions