# Avaliação Sprint 8 - Programa de Bolsas Compass UOL / AWS e Univesp
###  Programa de Bolsas Compass UOL - Formação em Machine Learning com AWS
***
<div align="center">
 <img src= "https://github.com/Compass-pb-aws-2023-Univesp/sprint-8-pb-aws-univesp/assets/88354075/64187a38-281e-4287-afcc-dd9ec97be1ff" alt="capa github" 
  width="450"/>
</div>



***
 
## Introdução 

A inteligência artifical é um campo da Ciência da Computação que busca desenvolver algoritmos e modelos que possam aprender, raciocinar, tomar decisões e resolver problemas de maneira autônoma, sem intervenção humana direta.

Um dos ramos é area de visão computacional, que busca capacitar os sistemas a interpretarem e compreenderem informações visuais, como imagens e vídeos.

Para o desenvolvimento dessa Sprint foi utilizado técnicas de aprendizado de máquina e redes neurais através dos serviços das AWS  *funções Lambda*, *o Rekognition*, *CloudWatch* e *API Gateway*. 

Com as funções Lambda são uma forma de executar código sem precisar gerenciar servidores, o Rekognition é um serviço de análise de imagem e vídeo baseado em aprendizado de máquina (para esse projeto foi usado apenas imagens), e o API Gateway é uma plataforma para criar, gerenciar e proteger APIs.
O CloudWatch foi utilizado para monitorar e registrar métricas, logs e eventos em tempo real, fornecendo insights sobre o desempenho dos recursos e serviços da AWS.

Esses serviços, quando combinados, permitem o desenvolvimento de aplicativos escaláveis, seguros e com recursos avançados de análise visual, tornando-se uma ferramenta valiosa para empresas e desenvolvedores que desejam incorporar análise visual em suas aplicações e processos de tomada de decisão.




****

## Objetivo

Desenvolver função Lambdas para chamar os serviços Rekognition e CloudWatch para realizar análise de imagens carregadas no buket S3.
***

## Arquitetura

![arquitetura](https://github.com/Compass-pb-aws-2023-Univesp/sprint-8-pb-aws-univesp/assets/117780664/109a28e6-334f-4187-8631-61eea5403b4d)

***
## Funcionamento 

Será atráves da função lambda que chama os serviços Rekognition e CloudWatch e realiza a análise de imagens carregadas no buket S3, que deve ser criado.

Deverá seguir esses passso: 

1. Configure o ambiente de desenvolvimento
Certifique-se de ter o AWS CLI instalado e configurado com suas credenciais de acesso.

```bash
  $ aws configure
  AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
  AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
  Default region name [None]: us-east-1
  Default output format [None]: ENTER
```

Deverá alterar o nome do BucketS3 no arquivo `serverless.yml` para um nome exclusivo.

Navegue até o diretório `visao_computavcional` e faça o deploy:

```bash
serverless deploy
```

Depois anote os endpoits para as rotas que aparecerá no terminal.

2. Crie um arquivo para função lambda.

Nessa parte, a função lambda é acionada quando um objeto é criado em um bucket do S3. Ela usa o serviço Rekognition para realizar a análise de rostos na imagem e o serviço CloudWatch para enviar métricas contendo o número de rostos detectados.

3. Crie um arquivo template.yaml para definir a configuração do serviço lambda.

Para usar o Amazon Rekognition, é necessário formatar corretamente os campos de entrada e saída da API, além de definir os códigos de status adequados para sucesso e erro. 

Os dados da imagem são enviados no corpo da solicitação como um JSON, com o campo Image contendo um objeto Bytes que contém os bytes da imagem. 
A resposta da API será verificada quanto ao código de status HTTP.

Se for 200, a solicitação foi bem-sucedida e o resultado é impresso. Caso contrário, um erro ocorreu e o código de status e o conteúdo da resposta são impressos.


****
## Organização

O projeto foi desenvolvido em duas frentes, parte do grupo ficou com a organização e desenvolvimento na AWS Rekognition e outra parte ficou para desenvolver o conteúdo do README. 

*** 

## Dificuldades Conhecidas

As dificuldades foram em relação a configuração das politicas e permissões que deveriamos usar, entender e fazer a lógica do código no VScode rodar corretamente. E extrair o sentimentos do serviços do Rekognition.  



***
## Desenvolvedores do projeto

||<br><sub>  [<img src="https://avatars.githubusercontent.com/u/96358027?v=4"  width=115><br><sub>Diego Lopes </sub>](https://github.com/Diegox0301) | [<img src="https://avatars.githubusercontent.com/u/124359272?v=4" width=115><br><sub>Irati Gonçalves Maffra</sub>](https://github.com/IratiMaffra) | [<img src="https://avatars.githubusercontent.com/u/88354075?v=4" width=115><br><sub>Kelly Patricia Lopes Silva</sub>](https://github.com/KellyPLSilva) | [<img src="https://avatars.githubusercontent.com/u/117780664?v=4" width=115><br><sub>Viviane Alves</sub>](https://github.com/Vivianes86) |
| :---: | :---: | :---: |:---: |:---: |

