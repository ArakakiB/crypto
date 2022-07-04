para o mlflow junto com a aws s3

do meu repositorio: https://github.com/ArakakiB/basic_mlflow/blob/main/server.txt

Local
mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./artifacts --host 0.0.0.0

S3
Precisamos criar um user no IAM da AWS
Só add new user > colocar um nome > programmatic access
depois para configurar o tipo de permisao, vamos selecionar o attach existing policies directly e selecionar apenas a opçao AdministratorAccess
no linux colocar a key e secret na pasta .aws (pode ficar em root) dessa forma:
  [default]
  aws_access_key_id =
  aws_secret_access_key =
  region =
mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root s3://crypto-mlflow-bucket/ --host 0.0.0.0