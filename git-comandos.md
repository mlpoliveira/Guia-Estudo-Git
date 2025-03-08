# Comandos Mais Utilizados no Git (com Integração ao GitHub)

Este documento lista os comandos mais comuns do Git para controle de versão, incluindo integração com repositórios remotos no GitHub. Cada comando é acompanhado de uma breve explicação.

## Configuração Inicial

```bash
git config --global user.name "Seu Nome"
```
Define o nome do usuário para todos os repositórios Git no seu sistema. É usado para identificar quem fez os commits.

```bash
git config --global user.email "seu.email@exemplo.com"
```
Define o e-mail do usuário para todos os repositórios Git no seu sistema. Deve corresponder ao e-mail associado à sua conta do GitHub.

```bash
git config --list
```
Lista todas as configurações atuais do Git no seu sistema.

---

## Criando e Clonando Repositórios

```bash
git init
```
Inicializa um novo repositório Git no diretório atual. Cria uma pasta oculta `.git` para rastrear as alterações.

```bash
git clone <URL-do-repositório>
```
Clona (copia) um repositório remoto do GitHub para o seu computador local.

Exemplo:
```bash
git clone https://github.com/usuario/repositorio.git
```

---

## Gerenciamento de Alterações

```bash
git status
```
Mostra o estado atual do repositório, incluindo arquivos modificados, adicionados à área de staging ou prontos para commit.

```bash
git add <arquivo>
```
Adiciona um arquivo específico à área de staging para ser incluído no próximo commit.

Exemplo:
```bash
git add index.html
```

```bash
git add .
```
Adiciona todos os arquivos modificados ou novos na pasta atual à área de staging.

```bash
git commit -m "Mensagem do commit"
```
Cria um commit com as alterações na área de staging. A mensagem deve descrever o que foi alterado.

Exemplo:
```bash
git commit -m "Adiciona página inicial"
```

```bash
git commit -am "Mensagem do commit"
```
Combina `git add .` e `git commit` em um único comando, mas só funciona para arquivos já rastreados pelo Git.

```bash
git restore <arquivo>
```
Descarta alterações em um arquivo que ainda não foi adicionado à área de staging.

```bash
git restore --staged <arquivo>
```
Remove um arquivo da área de staging, mas mantém as alterações no diretório de trabalho.

---

## Histórico e Navegação

```bash
git log
```
Mostra o histórico de commits no repositório, incluindo autor, data e mensagem.

```bash
git log --oneline
```
Mostra o histórico de commits em uma versão resumida, com apenas o hash e a mensagem do commit.

```bash
git diff
```
Mostra as diferenças entre o diretório de trabalho e a área de staging ou o último commit.

```bash
git checkout <hash-do-commit>
```
Move o HEAD para um commit específico, permitindo visualizar o estado do repositório naquele momento.

```bash
git checkout <nome-da-branch>
```
Troca para uma branch específica.

---

## Gerenciamento de Branches

```bash
git branch
```
Lista todas as branches locais no repositório. A branch atual é marcada com um asterisco (`*`).

```bash
git branch <nome-da-branch>
```
Cria uma nova branch com o nome especificado, mas não troca para ela.

```bash
git checkout -b <nome-da-branch>
```
Cria uma nova branch e troca para ela imediatamente.

```bash
git merge <nome-da-branch>
```
Combina a branch especificada com a branch atual. Pode gerar conflitos que precisam ser resolvidos manualmente.

```bash
git branch -d <nome-da-branch>
```
Deleta uma branch local que já foi mesclada.

---

## Integração com GitHub (Repositórios Remotos)

```bash
git remote add origin <URL-do-repositório>
```
Conecta o repositório local a um repositório remoto no GitHub. "origin" é o nome padrão do remoto.

Exemplo:
```bash
git remote add origin https://github.com/usuario/repositorio.git
```

```bash
git remote -v
```
Lista os repositórios remotos associados ao repositório local.

```bash
git push origin <nome-da-branch>
```
Envia os commits da branch local para o repositório remoto no GitHub.

Exemplo:
```bash
git push origin main
```

```bash
git push origin <nome-da-branch> --force
```
Força o envio dos commits, sobrescrevendo o histórico remoto. **Use com cautela.**

```bash
git pull origin <nome-da-branch>
```
Busca e mescla as alterações do repositório remoto na branch local.

Exemplo:
```bash
git pull origin main
```

```bash
git fetch origin
```
Busca as atualizações do repositório remoto sem mesclá-las na branch local. Útil para verificar mudanças antes de mesclar.

---

## Resolução de Problemas

```bash
git reset --soft <hash-do-commit>
```
Move o HEAD para um commit específico, mantendo as alterações no diretório de trabalho e na área de staging.

```bash
git reset --hard <hash-do-commit>
```
Move o HEAD para um commit específico e descarta todas as alterações posteriores no diretório de trabalho e na área de staging.

```bash
git revert <hash-do-commit>
```
Cria um novo commit que desfaz as alterações de um commit específico, preservando o histórico.

```bash
git stash
```
Salva temporariamente as alterações não commitadas para trabalhar em outra tarefa. As alterações são removidas do diretório de trabalho.

```bash
git stash pop
```
Restaura as alterações salvas com `git stash` e as aplica ao diretório de trabalho.

---

## Dicas Finais

- **Documente bem os commits**: Use mensagens claras e descritivas com `git commit -m`.
- **Evite force push em repositórios colaborativos**: Use `git push --force` apenas em repositórios pessoais ou com consentimento da equipe.
- **Atualize frequentemente**: Faça `git pull` regularmente para evitar conflitos ao trabalhar em equipe.
- **Use branches**: Trabalhe em branches separadas para novas funcionalidades ou correções e mescle-as ao `main` com pull requests no GitHub.

---

Este documento cobre os comandos mais usados no Git e no GitHub. Para mais detalhes sobre cada comando, use `git <comando> --help` (exemplo: `git push --help`) ou consulte a documentação oficial do Git.
