# Documentação do Projeto
## Visão Geral

Este projeto foi desenvolvido como parte de um teste técnico e consiste em duas aplicações em Python, utilizando o framework Django. O objetivo é criar um serviço contínuo para recepção de dados e geração de relatórios meteorológicos.

## Estrutura do Projeto

O projeto é dividido em dois aplicativos principais:

1. **DataReceiver**: Responsável por receber dados via TCP/IP.
2. **Reports**: Responsável por gerar relatórios e enviá-los por e-mail.

### Tecnologias Utilizadas

- Python
- Django
- Docker
- PostgreSQL
- FPDF (para geração de PDFs)
- Biblioteca de envio de e-mails do Django

## Implementação

### 1. Execução Contínua

A aplicação foi implementada como um serviço contínuo utilizando Django, que roda dentro de um contêiner Docker. O servidor TCP foi configurado para escutar na porta 5784 e processar dados recebidos. A ideia é que, ao receber dados no formato especificado (nome, e-mail, telefone, idade), o servidor valide e armazene essas informações em um banco de dados.

### 2. Armazenamento de Dados

Os dados recebidos são armazenados em um banco de dados PostgreSQL, garantindo a integridade e a persistência das informações. O sistema foi projetado para lidar com erros de integridade, como duplicatas, e retornar mensagens apropriadas ao cliente.

### 3. Geração de Relatórios

A segunda aplicação utiliza um utilitário que gera previsões meteorológicas a partir de um arquivo bruto. A biblioteca FPDF é utilizada para formatar e gerar relatórios em PDF, seguindo um template aprovado. O relatório é estruturado de forma a incluir análises e previsões, com destaque para fenômenos meteorológicos significativos.

### 4. Envio de E-mails

O envio de e-mails é configurado utilizando o SMTP do Gmail. Após a geração do relatório, o sistema verifica uma flag que indica se o relatório deve ser enviado por e-mail. O e-mail enviado contém o título com a data do relatório e o PDF anexado.

## Conclusão

Este projeto demonstra a capacidade de desenvolver aplicações em Python utilizando Django, além de integrar serviços de rede e manipulação de dados. A implementação foi realizada de forma modular e escalável, permitindo futuras expansões e melhorias.

