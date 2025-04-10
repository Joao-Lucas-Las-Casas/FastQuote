# FastQuote - Sistema de Cotação

## SUMÁRIO

- [Dados do Cliente](#dados-do-cliente)
- [Equipe de Desenvolvimento](#equipe-de-desenvolvimento)
- [Introdução](#introdução)
- [Objetivo](#objetivo)
- [Escopo](#escopo)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Fluxo Geral](#fluxo-geral)
- [Arquitetura do Sistema](#arquitetura-do-sistema)
- [Conclusão](#conclusão)

---

## Dados do Cliente

- **Título do Projeto:** FastQuote – Solução rápida em cotações via WebSite.
- **Cliente:** AguiaFix – A Solução Em Fixadores
- **CNPJ/CPF:** 06.886.538/0001-21
- **Contato:** Vinicius Mastrangelo Dias
- **Email do Contato:** Vendas2@aguiafix.com.br

---

## Equipe de Desenvolvimento

| Nome Completo             | Curso                                     | Disciplina                      |
|---------------------------|-------------------------------------------|---------------------------------|
| Vinicius Mastrangelo Dias  | Análise e Desenvolvimento de Sistemas     | Programação Orientada a Objetos |
| João Lucas Las Casas       | Análise e Desenvolvimento de Sistemas     | Programação Orientada a Objetos |

---

## Introdução

A área de vendas da AguiaFix enfrenta desafios no processo de recebimento e processamento de cotações enviadas por clientes online. Atualmente, os clientes enviam manualmente a lista de itens desejados via WhatsApp, o que exige uma interação inicial extensa entre vendedores e clientes para coletar todas as informações necessárias. Isso torna o processo demorado e pode impactar negativamente a conversão de vendas.

O projeto **FastQuote** busca solucionar esse problema ao introduzir uma ferramenta digital no site da empresa, proporcionando maior agilidade e eficiência na geração de cotações.

---

## Objetivo

Desenvolver uma aba no site da AguiaFix para permitir que os clientes preencham suas solicitações de cotação de forma estruturada, otimizando o tempo de resposta da equipe de vendas e aumentando a conversão de vendas.

---

## Escopo

1. **Visão Geral:**  
   O **FastQuote** é uma funcionalidade que será implementada no site da AguiaFix para agilizar o processo de cotação de produtos. Atualmente, os clientes enviam pedidos de forma manual pelo WhatsApp, resultando em trocas demoradas de mensagens. O **FastQuote** permitirá que os clientes preencham suas solicitações diretamente no site, otimizando o fluxo de trabalho dos vendedores e aumentando a conversão de vendas.

2. **Objetivos do Projeto:**
    - Criar uma aba específica no site da AguiaFix para receber cotações de forma estruturada.
    - Reduzir o tempo de resposta entre a solicitação do cliente e o retorno do vendedor.
    - Melhorar a organização das cotações, eliminando a necessidade de interações manuais extensas.
    - Aumentar a taxa de conversão de cotações para vendas, facilitando o fechamento do negócio.

3. **Escopo Funcional:**
    - **Funcionalidades para os Clientes:**
        - Acesso a uma aba exclusiva para cotação no site.
        - Formulário estruturado para preenchimento com os seguintes campos:
            - Itens desejados (pronta entrega e encomenda).
            - Quantidade de cada item.
            - Prazo máximo que o cliente pode aguardar.
            - Informações adicionais relevantes.
        - Indicação da disponibilidade dos itens em estoque e prazos de entrega estimados.
        - Revisão da cotação antes do envio.
        - Envio automático da cotação via WhatsApp para o setor de vendas.

    - **Funcionalidades para os Vendedores:**
        - Recebimento automático da cotação com todas as informações preenchidas pelo cliente.
        - Acesso a um painel de controle (caso necessário) para organizar e priorizar cotações.

---

## Tecnologias Utilizadas

- **Frontend:**
    - HTML, CSS, JavaScript
    - Tailwind CSS (Estilização responsiva e moderna)
    - Choices.js (Para dropdowns de seleção)
    - Flatpickr (Para seleção de datas)

- **Backend:**
    - Java 17+
    - Spring Boot (Framework principal do backend)
    - Apache POI (Para ler planilhas .xlsx com os dados de estoque)
    - OpenPDF (Para gerar arquivos PDF com o status da cotação)
    - MySQL (Para armazenar logs, históricos ou informações de usuários)

---

## Fluxo Geral

1. O **usuário** acessa a interface web e preenche o formulário de cotação no frontend.
2. Ao clicar no botão "Enviar", os dados são validados no frontend.
3. Se os dados forem válidos, uma requisição **POST** é enviada ao backend.
4. O backend processa os dados, gera um PDF e envia via WhatsApp.
5. O usuário é redirecionado para a tela de confirmação com a mensagem de sucesso.

---

## Arquitetura do Sistema

### Camada de Apresentação (Frontend):
- **Responsabilidades:**
    - Interface onde o cliente preenche o formulário de cotação.
    - Validação dos dados antes de enviá-los ao backend.
    - Exibição das respostas do servidor.

### Camada de Lógica de Negócio (Backend):
- **Responsabilidades:**
    - Receber e processar requisições HTTP do frontend.
    - Implementar a lógica para comparar os dados com a planilha de estoque.
    - Gerar PDFs e enviar via WhatsApp.

### Camada de Persistência (Banco de Dados):
- **Responsabilidades:**
    - Armazenar registros das cotações.
    - Manter logs e históricos de cotações feitas.

### Integração com API:
- **WhatsApp Business API**: Envio de mensagens com o PDF em anexo.

---

### **Componentes da Arquitetura**

- **Frontend**: Formulário interativo para entrada de dados.
- **Backend**: Controladores (Controllers), Serviços (Services), Repositórios (Repositories).
- **Integração com API**: Comunicação com a API do WhatsApp Business.

---

## Conclusão

O projeto **FastQuote** tem como objetivo automatizar o processo de cotação, proporcionando maior eficiência na interação entre clientes e vendedores da AguiaFix. Com isso, busca-se uma melhoria significativa no tempo de resposta e na taxa de conversão de cotações em vendas.

