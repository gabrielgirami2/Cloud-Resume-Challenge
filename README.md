# AWS Cloud Resume Challenge 🚀

Este projeto é um currículo online hospedado de forma 100% serverless na AWS. Ele utiliza uma arquitetura moderna para garantir alta disponibilidade, segurança e baixo custo.

## 🔗 Link do Projeto
[Acesse meu currículo aqui](https://d1st7qdsrl40d0.cloudfront.net/)

## 🏗️ Arquitetura
A solução foi desenhada utilizando os pilares do **AWS Well-Architected Framework**:

- **Frontend:** HTML/CSS estático hospedado no **Amazon S3**.
- **Distribuição:** **Amazon CloudFront** com certificado SSL (HTTPS) para entrega global de baixa latência.
- **Segurança:** Configuração de **Origin Access Control (OAC)** para restringir o acesso ao S3 apenas através do CloudFront.
- **API:** **Amazon API Gateway (HTTP API)** com CORS habilitado.
- **Computação:** **AWS Lambda** escrita em **Python 3.14** utilizando a biblioteca `boto3`.
- **Banco de Dados:** **Amazon DynamoDB** para armazenar e incrementar o contador de visitas em tempo real.

## 🛠️ Desafios Técnicos Superados
1. **Configuração de CORS:** Implementação de headers específicos na Lambda e no API Gateway para permitir requisições cross-origin seguras.
2. **Políticas de IAM:** Aplicação do princípio de privilégio mínimo, permitindo que a Lambda acesse apenas a tabela específica do DynamoDB.
3. **Invalidação de Cache:** Gerenciamento de TTL e invalidações no CloudFront para garantir que as atualizações do frontend sejam refletidas instantaneamente.

## 📝 Como replicar
1. Suba os arquivos do site para um bucket S3 privado.
2. Crie uma distribuição CloudFront apontando para o bucket com OAC.
3. Crie uma tabela no DynamoDB com a chave primária `id`.
4. Faça o deploy da função Lambda com o código disponível na pasta `/backend`.
5. Configure o trigger do API Gateway e atualize a URL no arquivo `index.html`.

---
*Este projeto foi desenvolvido como parte dos meus estudos para a certificação AWS Certified Cloud Practitioner.*