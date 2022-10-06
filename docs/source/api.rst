api
=====

Init
------------
Parameters
^^^^^^^^

* app_name (string) --[REQUIRED]
* region (string) --[REQUIRED]



Describe
------------
Parameters
^^^^^^^^

- execution (string) --[REQUIRED]

create_codepipeline
------------
Parameters
^^^^^^^^

- codepipeline_name (string) --[REQUIRED]
- code_repository_name (string) --[REQUIRED]
- mlworkflow_name (string) --[REQUIRED]
- bucket_name (string) --[REQUIRED]
- event_role (string) --[REQUIRED]
- codepipeline_role (string) --[REQUIRED]
- sagemaker_role (string) --[REQUIRED]
- stepfunctions_role (string) --[REQUIRED]
- model_package_group_arn (string) --[REQUIRED]
- experiment_name (string) --[REQUIRED]
- ml_info_secret_name (string) --[REQUIRED]
- ml_info_GitHubAppId (string) --[REQUIRED]
- ml_info_GitHubName (string) --[REQUIRED]
- ml_info_GitHubRepo (string) --[REQUIRED]
- ml_info_GitHubPath (string) --[REQUIRED]
- ml_info_train_container_destination (string) --[REQUIRED]
- ml_info_train_container_source (string) --[REQUIRED]
- ml_info_train_command (string) --[REQUIRED]
- ml_info_preprocess_command (string) --[REQUIRED]
- ml_info_inference_command (string) --[REQUIRED]
- simple_or_specific (string) --[REQUIRED]
- workflow_dict (dict) --[REQUIRED]

   - flow (list) --
      - (dict) --
         - type (string) --[REQUIRED]"Update Docker Image" | "stepfunctions" | "Deploy to Dev" | "Deploy to Prod" 
         if type == "Update Docker Image"

            - parameters (dict) --
            - codebuild_project_name (string) --[REQUIRED]
            - ECR_repository_name (string) --[REQUIRED]
            - tag (string) --[REQUIRED]
         if type == "stepfunctions"

            - content (list) --[REQUIRED]
               - (dict) --
                  - type (string) --[REQUIRED]"Batch Prediction" | "Lambda" | "Processing Job" | "Training Job";

                  if type == "Lambda"
                     - parameters (dict) --[REQUIRED]
                        - FunctionName (string)--[REQUIRED]
                        - Payload (dict)--
                        - body (dict)--

                  if type == "Training Job"
                     - parameters (dict) --
                        - sagemaker_execution_role (string) --[REQUIRED]
                        - output_path (string) --[REQUIRED]
                        - train_data_path (string) --[REQUIRED]
                        - validation_data_path (string) --[REQUIRED]
                        - image_uri (string) --[REQUIRED]
                        - ECR_repository (string) --[REQUIRED]
                        - tag (string) --[REQUIRED]
                        - hyperparameters (dict)
                  if type == "Processing Job"
                     - parameters (dict) --[REQUIRED]
                        - inputs (list) --[REQUIRED]
                           - source (string)
                           - destination (string)
                           - input_name (string)
                        - outputs (list) --[REQUIRED]
                           - source (string)
                           - destination (string)
                           - output_name (string)
                        - container_entrypoint (list) --[REQUIRED]
                           - (string)
                        - container_arguments (list) --[REQUIRED]
                           - (string)
         if type == "Deploy to Dev"
            - parameters (dict) --[REQUIRED]
            - codebuild_project_name_deploy (string) --[REQUIRED]
         if type == "Deploy to Prod"
            - parameters (dict) --[REQUIRED]
            - codebuild_project_name_deploy (string) --[REQUIRED]


describe_codepipeline
------------
Parameters
^^^^^^^^

- pipelineExecutionId
- codepipeline_name