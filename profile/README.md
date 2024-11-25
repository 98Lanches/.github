# 🍔 Projeto Dotlanches - TECH Challenge FIAP 2024 

Este é um projeto desenvolvido para o Tech Challenge curso de Software Architecture da FIAP em 2024. A proposta é um sistema que é construído de maneira incremental ao longo do curso, aplicando tecnologias, metodologias e boas práticas aprendidas ao longo do curso.

# O Dotlanches

O sistema dotlanches é um sistema de controle de pedidos desenvolvido para uma lanchonete em expansão, que permite que a lanchonete possa atender os clientes de maneira eficiente e eficaz, gerenciando seus pedidos e estoques de forma adequada. 
A aplicação oferece as seguintes funcionalidades:
- **Pagamento**: O sistema possui uma opção de pagamento integrada, via QRCode (simulado).
- **Acompanhamento de Pedidos**: Uma vez que os pedidos são confirmados e pagos, eles são enviados para a cozinha para serem preparados. Simultaneamente aparecerem em um monitor para os clientes acompanharem o progresso de seus pedidos
- **Gestão de clientes**: Identificação e autenticação de clientes.
- **Gerenciamento de Produos**: Os produtos dispostos para escolha dos clientes são gerenciados pelo estabelecimento, definindo nome, categoria, preço e descrição.

## Integrantes do grupo 98:
- André Torres Corrêa
- Angelo Costa Neto
- Mauro Tuyoshi Imamura Júnior

# Arquitetura

O sistema foi desenvolvido utilizando uma arquitetura de microsserviços, publicada utilizando em um cluster EKS (Kubernetes) na AWS. Cada microsserviço possui seu próprio banco de dados, variando entre bancos relacionais e não relacionais. Além disto, a aplicação está exposta via API Gateway da AWS, com Lambda Functions realizando a integração com o Cognito para autenticação e autorização dos usuários.

# Stack

# Links

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
