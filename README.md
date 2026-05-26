# Executando Tarefas Automatizadas com AWS Lambda e S3

Este repositório documenta minha prática no laboratório da DIO sobre **tarefas automatizadas usando AWS Lambda e Amazon S3**.  
O objetivo é registrar, de forma simples e clara, o que foi feito, o que aprendi e como posso reutilizar esse conhecimento em projetos futuros.

---

## 🔧 Visão Geral do Laboratório

Neste desafio, foi construída uma solução onde o **S3** dispara eventos que acionam uma **Lambda Function** para executar uma tarefa automatizada, por exemplo:

- Processar arquivos enviados para um bucket S3;
- Transformar o conteúdo (ex.: ajustar estrutura, filtrar dados, modificar respostas);
- Salvar o resultado em outro bucket ou retornar via S3 Object Lambda.

> Obs.: Ajuste esta seção para refletir exatamente o que você fez no laboratório.

---

## 🧱 Arquitetura da Solução (Resumo)

- **Amazon S3**
  - Bucket de origem para upload dos objetos.
  - Opcional: Bucket de destino para salvar o resultado processado.

- **AWS Lambda**
  - Função ativada automaticamente por eventos do S3 (ex.: `s3:ObjectCreated:*`).
  - Código responsável por ler o objeto, processar e retornar o resultado ou salvar em outro bucket.

- **S3 Object Lambda (opcional, se foi usado)**
  - Camada que permite transformar o objeto “on the fly” usando a Lambda antes de entregar para o cliente.

---

## 📝 Passo a Passo (Resumo do que foi feito)

1. **Criação do bucket S3**
   - Configuração de nome e região.
   - Ajuste de permissões básicas para testes.

2. **Criação da Lambda Function**
   - Definição do runtime (ex.: Node.js, Python, etc.).
   - Implementação do código da função.
   - Configuração de permissões (IAM Role) para acessar o S3.

3. **Configuração do gatilho (trigger)**
   - Associação do bucket S3 com a Lambda Function.
   - Definição do evento (ex.: criação de objeto).

4. **Teste da automação**
   - Upload de arquivos no S3.
   - Verificação da execução da Lambda (logs no CloudWatch).
   - Conferência do resultado (no próprio S3 ou na resposta da função).

## 💡 Principais Conceitos Aprendidos

- Como **integrar S3 com Lambda** usando eventos.
- Como **configurar permissões** para que a Lambda acesse objetos no S3.
- Como **automatizar tarefas** que são disparadas automaticamente sem intervenção manual.
- (Opcional) Como utilizar **S3 Object Lambda** para transformar objetos sob demanda.

## 🚀 Como Reutilizar Esta Ideia em Outros Projetos

- Processar uploads de usuários (imagens, documentos, CSVs, etc.).
- Criar pipelines simples de dados usando apenas S3 + Lambda.
- Implementar validações ou transformações de arquivos antes de serem consumidos por outras aplicações.

---

## 📚 Referências Utilizadas

- Slides do laboratório disponibilizados pela DIO.
- Documentação da AWS sobre **S3 Object Lambda** e **AWS Lambda**.
- Materiais complementares de Git e GitHub indicados no desafio (GitHub Quick Start, GitBook, documentação oficial).

---

## 🔗 Entrega

Este repositório foi criado para:
- Consolidar os conceitos de **Lambda + S3**;
- Praticar a **documentação técnica** em Markdown;
- Utilizar o **GitHub** como portfólio de estudos.
