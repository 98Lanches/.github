# 🍔 Projeto Dotlanches - TECH Challenge FIAP 2024 

Este é um projeto desenvolvido para o Tech Challenge curso de Software Architecture da FIAP em 2024. A proposta é um sistema construído de maneira incremental, aplicando tecnologias, metodologias e boas práticas aprendidas ao longo do curso.

# O Dotlanches

O sistema dotlanches é um sistema de controle de pedidos desenvolvido para uma lanchonete em expansão, que permite que a lanchonete possa atender os clientes de maneira eficiente e eficaz, gerenciando seus pedidos e estoques de forma adequada. 
A aplicação oferece as seguintes funcionalidades:
- **Pagamento**: O sistema possui uma opção de pagamento integrada, via QRCode (simulado).
- **Acompanhamento de Pedidos**: Uma vez que os pedidos são confirmados e pagos, eles são enviados para a cozinha para serem preparados. Simultaneamente aparecerem em um monitor para os clientes acompanharem o progresso de seus pedidos.
- **Gestão de clientes**: Identificação e autenticação de clientes.
- **Gerenciamento de Produtos**: Os produtos dispostos para escolha dos clientes são gerenciados pelo estabelecimento, definindo nome, categoria, preço e descrição.

## Integrantes do grupo 98:
- André Torres Corrêa
- Angelo Costa Neto
- Mauro Tuyoshi Imamura Júnior

# Arquitetura

O sistema foi desenvolvido utilizando uma arquitetura de microsserviços, publicada utilizando em um cluster EKS (Kubernetes) na AWS. Os serviços se comunicam sincronamente via HTTP e cada microsserviço possui seu próprio banco de dados, variando entre bancos relacionais e não relacionais. Além disto, a aplicação está exposta via API Gateway da AWS, com Lambda Functions realizando a integração com o Cognito para autenticação e autorização dos usuários. Todo provisionamento de infraestrutura é feito via Terraform em repositórios específicos para IaC.

![Arquitetura_dotlanche](https://github.com/user-attachments/assets/c71289ee-6a73-493c-86f9-ed7673782f0f)

## Serviços
- **Pedidos API**: Responsável por receber os pedidos criados no frontend e o seu gerenciamento antes do início da produção.
- **Produtos API**: Responsável pelo gerenciamento do catálogo de produtos.
- **Pagamentos API**: Responsável pelo processamento dos pagamentos e pela integração com provedores de pagamento.
- **Produção API**: Responsável pela gestão do ciclo de vida do pedido após o início da sua produção.

## Autenticação
A autenticação é feita via cognito utilizando Lambda Functions para comunicação com os pools. As Functions existentes são:
- **Get User**: Permite que usuários se identifiquem através do seu CPF, buscando os usuários cadastrados no cognito.
- **Sign Up**: Permite que usuários se cadastrem enviando suas informações básicas como CPF, Nome, email e senha.
- **Sign In**: Realiza a autenticação do usuário através de CPF e senha, retorna o token JWT para a autorização no API Gateway. Também permite a geração de token anônimo caso o usuário não queira se identificar.

## Infraestrutura
O provisionamento de infraestrutura é feito via Terraform nos seguintes repositórios:
- kubernetes-terraform: Provisionamento da VPC, Subnets e Cluster EKS.
- dotlanche-database: Provisionamento de bancos de dados.
- dotlanche-authentication: Provisionamento e configuração do API Gateway, Load Balancer, Cognito e as Functions.

# Stack
- .NET
- Kubernetes
- Postgresql
- MongoDB Atlas
- AWS EKS
- AWS Lambda Functions
- AWS Cognito
- AWS Api Gateway
- Terraform
