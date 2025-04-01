# Projeto Conceitual de Banco de Dados – E-COMMERCE

## Descrição do Projeto

Este projeto visa desenvolver um **Banco de Dados para E-Commerce**, focado na gestão eficiente de clientes, pagamentos e entregas. O esquema conceitual foi refinado para atender a requisitos específicos que garantem a integridade dos dados e a flexibilidade nas operações comerciais.

## Objetivos

- **Gestão de Clientes (Pessoa Física e Jurídica)**: Permitir que cada conta no sistema seja associada exclusivamente a uma **Pessoa Física (PF)** ou a uma **Pessoa Jurídica (PJ)**, evitando a mistura de informações entre os dois tipos de cliente.
- **Gestão de Pagamentos**: Possibilitar que cada cliente cadastre múltiplas formas de pagamento, proporcionando maior flexibilidade nas transações.
- **Gestão de Entregas**: Implementar um sistema de acompanhamento de entregas com status atualizados e códigos de rastreamento únicos.

## Funcionalidades Principais

### 1. Gestão de Clientes (PF e PJ)

- **Conta Exclusiva**: Cada conta no sistema deve estar vinculada exclusivamente a uma **Pessoa Física (PF)** ou a uma **Pessoa Jurídica (PJ)**.
  
  **Informações da Pessoa Física (PF):**
  - Nome Completo
  - CPF
  - Endereço Residencial
  - Contato (Telefone e Email)

  **Informações da Pessoa Jurídica (PJ):**
  - Razão Social
  - CNPJ
  - Endereço Comercial
  - Contato (Telefone e Email)

### 2. Gestão de Pagamentos

- **Múltiplas Formas de Pagamento**: Cada cliente pode cadastrar diversas formas de pagamento, como:
  - Cartão de Crédito
  - Boleto Bancário
  - Transferência Bancária
  - PayPal
  - Carteiras Digitais (ex.: Apple Pay, Google Pay)

- **Detalhes do Pagamento:**
  - Tipo de Pagamento
  - Número da Conta ou Cartão
  - Data de Validade (quando aplicável)
  - Nome do Titular
  - Preferência de Pagamento

### 3. Gestão de Entregas

- **Status da Entrega**: Cada entrega possui um status que reflete sua atual etapa no processo logístico. Os status incluem:
  - Pendente
  - Processando
  - Em Transporte
  - Entregue
  - Cancelada

- **Código de Rastreamento**: Cada entrega é associada a um código de rastreamento único, permitindo que o cliente acompanhe o progresso da entrega em tempo real.

## Modelo Conceitual

O modelo conceitual do sistema está estruturado com as seguintes entidades e relacionamentos:

- **Cliente**
  - **Conta** (Associação Exclusiva com PF ou PJ)
    - **Pessoa Física (PF)**
    - **Pessoa Jurídica (PJ)**
  - **Formas de Pagamento** (Relacionamento 1:N com Conta)
    - Tipo de Pagamento
    - Detalhes do Pagamento

- **Produto**
  - ID do Produto
  - Nome
  - Descrição
  - Preço
  - Estoque

- **Pedido**
  - ID do Pedido
  - Data do Pedido
  - Status do Pedido
  - Cliente (Relacionamento N:1 com Conta)
  - Itens do Pedido (Relacionamento 1:N com Itens)
  - Pagamento (Relacionamento 1:N com Formas de Pagamento)
  - Entrega (Relacionamento 1:1 com Entrega)

- **Entrega**
  - ID da Entrega
  - Status da Entrega
  - Código de Rastreamento
  - Endereço de Entrega

- **Pagamento**
  - ID do Pagamento
  - Tipo de Pagamento
  - Detalhes do Pagamento
  - Pedido (Relacionamento N:1 com Pedido)
