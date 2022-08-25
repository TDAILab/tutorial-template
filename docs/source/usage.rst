Usage
=====

.. _usage:


Initialize Project
------------
Click the home page of the project page, and you enter github credential.
After you fill out the form, you click the green "Initialize Project" button.
A few minutes later, this message will be displayed on the page.

.. _target to image:

.. figure:: /image/build_setting.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!

Data upload
------------
First, you go to the AWS website https://aws.amazon.com/jp/.
After that, search for "Amazon SageMaker" and go to this page.
Next page, you find buckets by searching for your project name and go to your buckets page.
Click the orange "Upload" button, and you select a file or a folder you want to use a database.


Run
------------
Click the Model page, and fill out this page.
After then, you click the dark blue "run" button.
The form will pops up on the page, and you enter Image Tag Name and click Deploy to Dev(Dev).
Be careful you cannot use sthe following characters in the Image Tag Name. #使えない文字を記載する。
If you check the "end point" box, #デプロイまでやってくれる


.. _target to image:

.. figure:: /image/model_deployment.png
   :alt: Logo 
   :align: center
   :width: 600px
　　　　　　　　　　　　　　　　　　Click to enlarge!



You can check if the program is done on the history page. Click the "history" button and check out the "Status" section.

・ Status is Pending : the program is executed at present.

・ Status is Success : the program is done and you can see the result on AWS website. Refer to the following for the way.

・ Status is Failed : the program is failed because of some reasons.
#主語がprogramでよいか
#原因確認方法や解決方法も書くか。 


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

ー－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－
   メモ
   ・使えない文字の話（命名規則）
   ・エンドポイントの話追記
   ・データの入れ方
     →S3→バッケトから自分のデータを探す→ローカルからフォルダまたはファイルを選択してアップロード
   ・結果の見方
     →Amazon SageMaker→Inference→Endpoints