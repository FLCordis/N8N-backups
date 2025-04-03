# N8N Workflow GitHub Sync

Este projeto contém um Workflow desenvolvido no N8N que sincroniza automaticamente os fluxos com um repositório no GitHub. O objetivo é garantir que todas as versões dos fluxos sejam atualizadas e versionadas corretamente caso necessário para uma restauração.

## 📌 Funcionalidades

- Acessa todos os fluxos do N8N e os salva em um arquivo.
- Compara os arquivos salvos com os existentes no repositório GitHub.
- Caso os arquivos sejam idênticos, nenhuma atualização é feita.
- Se houver mudanças, os arquivos são atualizados e uma nova versão é criada.
- Se o arquivo ainda não existir no repositório, ele é criado automaticamente.
- Envio de notificação por e-mail do Status do backup.
- Restauração do Workflow pelo versionamento do código.

## 🗃️ Como usar o Backup
![Backup](https://imgur.com/hHHhzLL.png)
### 1. Pré-requisitos

####  Certifique-se de ter os seguintes itens configurados:
- Uma instância do [N8N](https://n8n.io/) em funcionamento.
- Um repositório no GitHub para armazenar os fluxos.
- Credencial OAuth2.0 do GitHub salvo no N8N.
- Credencial da API do N8N salva no usuário.
- Credencial do Email (caso for usar essa feature).

### 2. Configuração do Workflow

####  1. No campo **Data**, deve ser preenchido com os valores do usuário:
- **Owner**: Nome do usuário do proprietário do repositório.
- **Repo**: Nome do repositório.
- **Path** (opcional): Caso existir uma pasta que os arquivos fiquem dentro (ex: pasta123/ ), sempre colocando a barra após o nome.
####  2. Configure as credenciais do GitHub no N8N.
####  3. Execute o Workflow e verifique se os arquivos são sincronizados corretamente.

## 🚀 Como usar a Restauração
![Restauração](https://imgur.com/6mj4ZQo.png)
### 1. Pré-requisitos

Configurar as credenciais no Workflow igual aos anteriores.

### 2. Uso do Workflow

#### 1. No campo **Data**, deve ser preenchido com os valores do usuário:
- **File**: O caminho completo incluindo as pastas caso exista até o arquivo com sua extensão (ex: pasta123/backup-dHnc23.json)
- **Owner**: Nome do usuário do proprietário do repositório.
- **Repo**: Nome do repositório.
- **Version**: O código SHA do versionamento do histórico. CASO não for preenchido ele pega a última versão do código.
####  2. Executar o fluxograma.

## ⚙️ Tecnologias utilizadas

- [N8N](https://n8n.io/) - Plataforma de automação de workflows.
- [GitHub API](https://docs.github.com/en/rest) - Para controle de versão e armazenamento dos fluxos.

## 📄 Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---
