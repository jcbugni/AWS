# DIO-LiveCoding-AWS-BigData
Repositório de código do Desafio Dio-Cognizant "Live Coding com AWS EMR e Python"

Neste repositório contém os arquivos de configuração, execução e respostas obtidas da análise de dados.



## Instruções

* Acessar S3: https://s3.console.aws.amazon.com/s3/ 
  * Criar estrutura de data lake : _dio-cognizant-datalake-prod_
  * Criar estrutura de pastas:
    * _data_
    * _output_
    * _temp_
* Acessar EMR: https://console.aws.amazon.com/elasticmapreduce/
    * O cluster será criado pelo MrJob e não pelo console
    * Infraestrutura como código 
* Criar chave SSH
    * Acessar  Console do EC2: https://console.aws.amazon.com/ec2/ -> Key Pairs -> Create Key Pair	
    * Download .pem file
* Obter Id e chave secreta AWS para configurar MrJob
   * Profile
   * My Security Credentials: https://console.aws.amazon.com/iam/home?region={region}#/security_credentials
   * Access Keys - Create new access key
   * Fazer download - única chance de visualizar
* Ambiente linux (foi utilizado o WSL)
   * Criar ambiente virtual python: _virtualenv --python=python3.8 venv_dio
   * Instalar boto3: _pip install boto3_
   * Instalar mrjob: _pip install mrjob_
   * Acessar com o vs code (foi utilizado editor de texto puro)
* Instalar vscode no Ubuntu
   *  code .
* Criar algoritmo de análise de palavras
   * dio-live-wordcount-test.py
   * map-reduce-count : contar
* Acessar S3
   * Upload de arquivo para o bucket (/data/sherlock.txt)
* Ambiente virtual python
  * source venv_dio/bin/activate (ativando venv)
  * nano ~/.mrjob.conf (configurar o mrjob)
  * python3 dio-live-wordcount-test.py -r emr s3://dio-cognizant-datalake-prod/data/sherlock.txt --output-dir=s3://dio-cognizant-datalake-prod/output/logs01 --cloud-tmp-dir=s3://dio-cognizant-datalake-prod/temp/
