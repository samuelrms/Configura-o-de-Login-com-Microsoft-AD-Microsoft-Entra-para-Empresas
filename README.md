# Configuração de Login com Microsoft AD / Microsoft Entra para Empresas

## Passo 1: Registro do Aplicativo no Microsoft Entra

1. **Acesse o portal do Microsoft Entra** - Entre no [portal do Azure](https://portal.azure.com) e selecione o serviço "Azure Active Directory".
2. **Registro de Aplicativos** - Na barra lateral, clique em "Registros de aplicativos" e depois em "Novo registro".
3. **Nome do Aplicativo** - Insira um nome para o aplicativo que será fácil de reconhecer.
4. **Tipos de Conta Suportados** - Escolha "Contas nesta organização somente (Microsoft somente - Único inquilino)" para restringir o login a membros da sua empresa.
5. **URI de Redirecionamento** - Você precisará adicionar duas URIs de redirecionamento:
   - Uma para o ambiente de desenvolvimento (ex: `http://localhost:3000/auth/callback`).
   - Outra para o ambiente de produção (ex: `https://yourproductionapp.com/auth/callback`).
   Isso garante que a aplicação possa operar tanto em ambiente local quanto quando for movida para produção.
6. **Clique em Registrar** - Após inserir os detalhes necessários, clique em "Registrar".

## Passo 2: Configuração de Permissões

1. **Permissões de API** - Dentro do registro do seu aplicativo, vá para "Permissões de API" e clique em "Adicionar uma permissão".
2. **Escolha as APIs necessárias** - Selecione as APIs que seu aplicativo precisa acessar. Para a maioria dos aplicativos empresariais, as permissões padrão do Microsoft Graph são suficientes.
3. **Adicionar Permissões** - Escolha as permissões específicas dentro da API selecionada e adicione-as ao aplicativo.

## Passo 3: Geração de Certificados e Segredos

1. **Certificados e segredos** - Na barra lateral, selecione "Certificados e segredos".
2. **Novo Segredo do Cliente** - Clique em "Novo segredo do cliente". Dê um nome ao segredo e selecione a duração. Após criar, certifique-se de copiar o valor do segredo; ele não será mostrado novamente.
3. **Upload de Certificado (opcional)** - Se o seu aplicativo requer um certificado, você pode fazer upload dele nesta seção.

## Passo 4: Configuração do Endereço de Logout (opcional)

- Para configurar um endereço de logout personalizado, acesse "Autenticação" no registro do aplicativo e adicione o URL de logout nas configurações.

## Passo 5: Obtenção dos Detalhes do Aplicativo

- Após a configuração, certifique-se de anotar o "ID do Aplicativo" e o "Diretório (ID do Locatário)" nas informações do aplicativo. Eles serão necessários para configurar o login no seu aplicativo.

## Considerações

- Todas as informações foram retiradas da propria documentação da [Microsoft AD (Entra ID)](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app)
