
# Azure Cognitive Search: Utilizando AI Search para Indexação e Consulta de Dados

## Problema Proposto
O desafio consiste em implementar um mecanismo de busca integrado a serviços de inteligência artificial para identificar palavras-chave, sentimentos e outros padrões em documentos, utilizando também o serviço de armazenamento do Azure.

---

## Documentação do Processo

### Passo 1: Criar o recurso Azure Cognitive Search
Crie um recurso do *AI Search* no portal Azure para iniciar o processo de indexação.

### Passo 2: Criar o recurso Azure AI Services
Crie o recurso de *Azure AI Services* que será responsável pela análise de sentimentos, extração de entidades e palavras-chave.

### Passo 3: Criar o recurso de Armazenamento (Storage Account)
Configure uma *Storage Account* para armazenar os documentos que serão analisados.

### Passo 4: Permitir acesso anônimo ao Blob Storage
Como se trata de um laboratório didático, é necessário permitir o acesso anônimo ao blob para facilitar o desenvolvimento.  
Acesse o recurso de *Storage*, vá até **Settings > Configuration** e altere o acesso público para os blobs.

### Passo 5: Criar o Container no Storage
Dentro da *Storage Account*, vá em **Data Storage > Containers**, crie um container e adicione os arquivos que serão processados.

### Passo 6: Importar e indexar dados no AI Search
Volte ao recurso *AI Search* e inicie o processo de importação e indexação dos dados armazenados.

Durante esse processo:

- Em **"Attach Cognitive Services"**, selecione o recurso de *Azure AI Services*.

> Obs: Caso ele não apareça, é possível que sua conta gratuita tenha limitações. Siga normalmente para o próximo passo.

- Em **"Add Enrichments"**, configure as opções de análise de texto, sentimento, etc.
- Conclua as etapas até o **Passo 17: Select the indexer name** para verificar detalhes da indexação.

### Passo 7: Consultar o índice (Search Explorer)
Acesse o *Search Explorer* dentro do AI Search para testar as consultas:

```http
search=*&$count=true
```
> Verifica se a indexação ocorreu corretamente e retorna todos os documentos.

```http
search=locations:'Chicago'
```
> Retorna documentos relacionados à localização "Chicago".

```http
search=sentiment:'negative'
```
> Retorna documentos com sentimento negativo.

---

## Considerações Finais
As ferramentas de inteligência artificial do Azure tornam a análise de documentos e feedbacks muito mais eficiente, contribuindo para diagnósticos rápidos e decisões baseadas em dados confiáveis.
