# Descrição do Projeto Conceitual

Este projeto apresenta o modelo conceitual de um sistema de e-commerce, desenvolvido como parte do curso Formação SQL Database Specialist. O objetivo é estruturar as principais entidades, relacionamentos e regras de negócio envolvidas no processo de venda online, desde o cadastro do cliente até a finalização do pedido e sua entrega.

O design conceitual foi elaborado com foco em boas práticas de modelagem, integridade dos dados e expansão futura. Abaixo estão os principais pontos considerados no desenvolvimento do esquema:

## 1. Cadastro de Clientes (PF e PJ)

O sistema diferencia dois tipos de clientes: Pessoa Física (PF) e Pessoa Jurídica (PJ).
Para evitar atributos nulos e manter a integridade dos dados, foi adotado um modelo com especialização:
- A tabela Cliente armazena informações comuns.
- As tabelas Cliente_PF e Cliente_PJ armazenam atributos específicos de cada tipo, vinculadas ao cliente via chave estrangeira.

## 2. Formas de Pagamento Cadastradas pelo Cliente

O cliente pode registrar suas próprias formas de pagamento, permitindo o uso de múltiplos cartões.
Para isso, foi criada a entidade Forma_pagamento_cliente, que armazena o tipo de pagamento e referencia o cliente.
Pagamentos mais detalhados (como cartão) foram modelados com especialização, permitindo armazenar informações específicas de maneira estruturada e segura.

## 3. Pedidos e Pagamentos

Cada pedido está vinculado ao cliente e à forma de pagamento utilizada no momento da compra.
Esse design permite registrar exatamente qual forma foi usada, mesmo que o cliente a exclua posteriormente do cadastro.

## 4. Informações de Entrega

A entrega do pedido foi modelada como uma entidade separada (Entrega), permitindo registrar dados como transportadora, código de rastreamento, status e datas relevantes.
Essa separação facilita a evolução do sistema e possibilita cenários com múltiplas entregas no futuro.

## 5. Objetivo Geral do Modelo

O esquema conceitual reflete as principais operações de um e-commerce real, garantindo:
- Integridade e consistência dos dados;
- Flexibilidade para diferentes tipos de cliente;
- Segurança no armazenamento de informações sensíveis;
- Evolutividade para futuras funcionalidades;
- Organização clara das relações entre entidades.
