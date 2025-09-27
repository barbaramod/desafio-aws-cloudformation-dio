**Desafio DIO: Implementando Infraestrutura Automatizada com AWS CloudFormation**

Este repositório documenta a minha jornada e os resultados do desafio proposto pela **DIO** focado em **Infrastructure as Code (IaC)** utilizando o **AWS CloudFormation**.

**Descrição do Desafio**
O objetivo deste laboratório foi criar, configurar e gerenciar uma infraestrutura na nuvem da AWS de forma automatizada. Para isso, utilizei um template JSON do CloudFormation para provisionar recursos de maneira padronizada e replicável. O projeto simula um cenário real, onde a automação é crucial para agilidade e segurança.

**Arquitetura Implementada**
A infraestrutura provisionada através do template CloudFormation consiste nos seguintes recursos:

**1 Instância EC2**: Servidor virtual que servirá como a base para a nossa aplicação.

**1 Security Group**: Atua como um firewall virtual para a instância EC2, controlando o tráfego de entrada e saída. Neste projeto, ele permite o acesso via porta 22 (SSH) e 80 (HTTP).

**1 Elastic IP**: Um endereço IP público estático que é associado à instância EC2, garantindo que o IP de acesso não mude mesmo após reinicializações.

**Como Executar o Template**
Para replicar esta infraestrutura na sua conta AWS, siga os passos abaixo:

**Faça o download** do arquivo infra-basica.json deste repositório.

**Crie um Key Pair (Chave)** na sua conta AWS. Vá para o serviço EC2, selecione "Key pairs" no menu lateral e clique em "Create key pair". Salve o arquivo .pem em um local seguro.

**Acesse o serviço AWS CloudFormation** no console da AWS.

Clique em **"Create stack"**.

Selecione **"Upload a template file"** e faça o upload do arquivo template.json.

Clique em **"Next"**.

Na tela de "Specify stack details", dê um nome para sua pilha (ex: desafio-dio-iac).

Nos "Parameters", preencha o campo KeyPairName com o nome da chave que você criou no passo 2.

Clique em **"Next"** até a tela final de revisão. Marque a caixa de "I acknowledge..." e clique em **"Create stack"**.

O CloudFormation irá agora provisionar a infraestrutura. Você pode acompanhar o status na aba "Events".

**Anotações e Aprendizados**
Durante a execução deste desafio, pude aprofundar meu conhecimento sobre:

**Infrastructure as Code (IaC)**: A prática de gerenciar e provisionar infraestrutura usando arquivos de código, em vez de processos manuais.

**Estrutura de Templates JSON**: Entendendo a sintaxe de Parameters, Resources e Outputs para criar templates reutilizáveis.

**Parametrização**: Como usar parâmetros para tornar os templates mais flexíveis, permitindo a personalização de recursos (como o tipo de instância ou o nome da chave SSH) sem a necessidade de editar o código.

**Orquestração de Recursos**: O CloudFormation gerencia a ordem correta de criação e exclusão dos recursos, garantindo que as dependências sejam respeitadas (por exemplo, o IP Elástico só pode ser associado após a instância EC2 ser criada).

Este desafio foi uma excelente oportunidade para aplicar a teoria na prática e entender como a automação de infraestrutura é fundamental em ambientes de nuvem modernos.
