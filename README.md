<h1>AWS - Exemplo de deploy de API utilizando SAM</h1>

<h2>
    Objetivo
</h2>
Demonstrar como realizar o deploy de uma API utilizando o <a href="https://aws.amazon.com/pt/serverless/sam/">SAM (Serverless Application Model)</a> de forma simples e prática.<br>

O resultado final será uma API acessível na internet utilizando AWS Lambda e API Gateway, criados pelo SAM.


Este repositório contém os passos e os códigos necessários para obtenção do cenário final.

<b>IMPORTANTE: A realização desse tutorial pode gerar custos.</b>

<h2>Arquitetura</h2>
<br>

![Desenho arquitetura](https://github.com/paulomulotto/AWS-exemplo_api_sam/blob/main/img/arquitetura%20basica.png)

<h2>Tutorial</h2>
<h3>Criando e configurando workspace AWS Cloud9</h3>
Vá até o <a href="https://console.aws.amazon.com/cloud9">console do Cloud9 da AWS</a> e crie um workspace.

Será necessário atualizar o SAM CLI para uma versão mais recente do que a que o Cloud9 traz instalada. Para isso, execute o seguinte código (pode levar alguns minutos para executar):

```
wget https://cicd.serverlessworkshops.io/assets/bootstrap.sh
chmod +x bootstrap.sh
./bootstrap.sh
sam --version
```

Verifique se a versão do SAM instalada é 1.29.0 ou maior.

<h3>Projeto SAM</h3>
Agora iremos configurar um novo projeto SAM que será responsável por criar a arquitetura desejada.

Execute o comando e siga as instruções
```
sam init
```

Digite <b>2</b> para selecionar <b>Custom Template Location</b> e depois <b>1</b> insira o caminho do GitHub <a href="https://github.com/paulomulotto/AWS-exemplo_api_sam">https://github.com/paulomulotto/AWS-exemplo_api_sam</a>

<h3>Rodando o projeto localmente</h3>
Instale as dependências:

```
cd ~/environment/sam-api-app/api_basica
pip3 install -r requirements.txt
```

Rode o projeto usando o SAM CLI
```
cd ~/environment/sam-api-app
sam local start-api --port 8080

```
