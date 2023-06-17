# sagemaker-pipelines-sample

このノートブックは https://github.com/aws-samples/aws-ml-jp/blob/main/sagemaker/mlops/sagemaker-pipelines/sagemaker-pipelines-sample/sagemaker-pipelines-sample.ipynb を簡略化したバージョンです。変更点として 2日目以降の学習の際、前日までのデータを再使用せずその日のデータのみで学習しています。そのためprocessing.pyでのデータのconcat処理と、PipeLineステップでのPreProcessedXXXXXDataS3UriParamパラメータを省略しています。

また、変数名が増えて複雑になるのを防ぐためprocess.pyやpostprocess.pyにparameterとして渡していたディレクトリ変数、例えばPRE_PROCESS_RAW_DATA_INPUT_DIR (= '/opt/ml/processing/input/raw_data')をやめ、スクリプトおよびジョブ定義時にハードコーディングしています。パイプラインを組む時点で定形処理化が目的であるため、データの構成やインスタンスのディレクトリ構造は変える必要はなく、パラメータ（変数）化する必要はないと判断しました。

ただし、ノートブックでのジョブ定義時のディレクトリ名とスクリプトにハードコーディングしたディレクトリ名が異なるとエラーが出るため、注意してください。 変更しては行けない部分にコメントを記載しました。


※ SageMaker **Studio** Notebook を前提としており、カーネルは Python3(Data Science) をご利用ください。 
※ confirms this notebook works under data science kernel on SageMaker **Studio** notebook

SageMaker Pipelines のサンプルコードです。  
[sagemaker-pipelines-sample.ipynb](./sagemaker-pipelines-sample.ipynb)を開いてご利用ください。  

SageMaker Pipelines の一通りの機能を利用することができます。
