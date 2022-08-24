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
If you check the "end point" box, #書き終えていない


.. _target to image:

.. figure:: /image/model_deployment.png
   :alt: Logo 
   :align: center
   :width: 600px




You can check if it's done on the history page. Click the "history" button and check out the "Status" section.
Status is Success
Status is Pending
Status is Failed

  #モデルが実行中という書き方でよいか？

.. _target to image:

.. figure:: /image/confirm_history.png
   :alt: Logo 
   :align: center
   :width: 600px


Result
------------
You can check the result on the AWS website. Go to https://aws.amazon.com/jp/.
Search for "Amazon SageMaker", go to this page.
Click the "Inference" button on the left-hand side of the Amazon SageMaker page, and click the "Endpoints" button.
(After clicking submit on the Enter Bug page, you will go to the Posting Bug page.)


ー－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－
   メモ
   ・ヒストリーの話
   ・使えない文字の話（命名規則）
   ・エンドポイントの話追記
   ・データの入れ方
     →S3→バッケトから自分のデータを探す→ローカルからフォルダまたはファイルを選択してアップロード
   ・結果の見方
     →Amazon SageMaker→Inference→Endpoints