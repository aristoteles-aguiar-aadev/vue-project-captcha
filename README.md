# Autor do Projeto 
Aristóteles Aguiar

# vue-project-recaptcha

Este template deve ajudá-lo a começar a desenvolver com Vue 3 no Vite.

## Configuração de IDE Recomendada

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (e desativar o Vetur).

## Personalizar Configuração

Veja [Referência de Configuração do Vite](https://vitejs.dev/config/).

## Configuração do Projeto

```sh
npm install
```

### Compilar e Hot-Reload para Desenvolvimento

```sh
npm run dev
```

### Compilar e Minificar para Produção

```sh
npm run build
```

### Executar Testes de Componentes com Interface com [Cypress Component Testing](https://on.cypress.io/component)

```sh
npm run test:unit:dev # ou `npm run test:unit` para testes sem interface
```

### Executar Testes de Ponta a Ponta com [Cypress](https://www.cypress.io/)

```sh
npm run test:e2e:dev
```

Isso executa os testes de ponta a ponta contra o servidor de desenvolvimento do Vite.
É muito mais rápido do que a build de produção.

Mas ainda é recomendado testar a build de produção com `test:e2e` antes de implantar (por exemplo, em ambientes de CI):

```sh
npm run build
npm run test:e2e
```

### Este comando instala o pacote serve globalmente na sua máquina
```sh
npm install -g serve
serve -s dist
```

Detalhes Técnicos:
- **npm install -g serve**: Este comando instala o pacote serve globalmente na sua máquina. O serve é um servidor HTTP estático de linha de comando, simples e sem configuração, que pode ser usado para servir seus arquivos estáticos, como os arquivos gerados pelo seu processo de build.
- **serve -s dist**: Este comando usa o serve para servir o conteúdo do diretório dist (que contém a sua build de produção) em modo de aplicação de página única (SPA). A flag -s habilita o modo SPA, o que significa que qualquer solicitação que não corresponda a um arquivo será servida pelo index.html. Isso é útil para roteamento no lado do cliente.
# Erro ao executar 'serve -s dist'

1. **Se tentar executar o comando abaixo:**
```sh 
serve -s dist
```

2. **Retornar o erro abaixo:**
serve : O arquivo C:\usuarios\seu_usuario\AppData\Roaming\npm\serve.ps1 não pode ser carregado porque a execução de scripts foi desabilitada neste sistema. 
Para obter mais informações, consulte about_Execution_Policies em https://go.microsoft.com/fwlink/?LinkID=135170.
No linha:1 caractere:1
+ serve -s dist
+ ~~~~~
    + CategoryInfo          : ErrodeSegurança: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

# Solução do Erro 'serve -s dist'

O erro que você está encontrando ocorre porque a execução de scripts PowerShell está desabilitada no seu sistema. Para resolver isso, você pode alterar a política de execução para permitir a execução de scripts. Siga os passos abaixo:

1. **Abra o PowerShell como Administrador:**
   - Clique com o botão direito do mouse no ícone do PowerShell e selecione "Executar como administrador".

2. **Verifique a política de execução atual:**
   - Execute o comando:
     ```powershell
     Get-ExecutionPolicy
     ```

3. **Altere a política de execução para "RemoteSigned" (ou outra que seja adequada para seu ambiente):**
   - Execute o comando:
     ```powershell
     Set-ExecutionPolicy RemoteSigned
     ```
   - Isso permitirá a execução de scripts locais sem assinatura e scripts baixados da Internet que são assinados por um editor confiável.

4. **Confirme a alteração:**
   - Quando solicitado, digite "Y" (Yes) ou, "S" (Sim) para confirmar a alteração.

5. **Tente novamente executar o comando serve:**
   - Navegue até o diretório do seu projeto, ou, no console da sua IDE execute o comando novamente:
     ```powershell
     serve -s dist
     ```

**Nota:** Alterar a política de execução pode ter implicações de segurança. Certifique-se de entender as consequências e ajuste as políticas conforme necessário para seu ambiente específico.

Se precisar de mais ajuda ou tiver outras dúvidas, fique à vontade para perguntar!
