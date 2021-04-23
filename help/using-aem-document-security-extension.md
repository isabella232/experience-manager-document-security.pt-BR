---
title: Uso do AEM Document Security Extension for Microsoft Office
description: Controle como os recipients usam seus arquivos protegidos por políticas, independentemente da abrangência da distribuição de arquivos. O documento explica como proteger arquivos e como trabalhar com arquivos protegidos.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
exl-id: 667a9718-b865-4911-96c2-7c08f75e0732
translation-type: ht
source-git-commit: a15d49cdd21ccb8e6ec6c770a92bf16cb24ffaa1
workflow-type: ht
source-wordcount: '6270'
ht-degree: 100%

---

# Uso do AEM Document Security Extension for Microsoft Office {#using-aem-document-security-extension-for-microsoft-office}

## Proteção de arquivos usando o AEM Document Security Extension {#usingaemdocumentsecurityextensiontoprotectfiles}

Controle como os recipients usam seus arquivos protegidos por políticas, independentemente da abrangência da distribuição de arquivos.

Usando o Document Security Extension for Microsoft Office, é possível executar estas tarefas:

* Configurar a conexão com a Segurança de documentos
* Aplicar uma política a um arquivo
* Abrir as páginas da Web de Segurança de documentos para criar e gerenciar políticas de usuários
* Remover a proteção por política de um arquivo
* Alterar a política aplicada a um arquivo
* Abrir as páginas da Web de Segurança de documentos para revogar o acesso aos arquivos ou alterar a política do arquivo
* Abrir as páginas da Web de Segurança de documentos para visualizar o histórico de auditoria do arquivo

### Conexão com um servidor de Segurança de documentos {#connect-to-a-document-security-server}

Se sua intenção for aplicar políticas a arquivos, é preciso configurar as definições de conexão para a Segurança de documentos. Dependendo de como o Document Security Extension for Microsoft Office foi instalado, talvez você já tenha configurações de conexão padrão. Você pode adicionar configurações de conexão para uma ou mais instâncias da Segurança de documentos. E pode também obter informações do servidor do administrador de Segurança de documentos.

É preciso definir o servidor que deseja usar para proteger arquivos ou gerenciar seus arquivos protegidos como o servidor padrão. Ao aplicar uma política a um novo arquivo ou abrir as páginas da Web de Segurança de documentos, o Document Security Extension for Microsoft Office se conecta ao servidor padrão. Se você proteger arquivos usando mais de uma instância de Segurança de documentos, deverá alterar a configuração padrão do servidor ao alternar entre servidores. É possível abrir arquivos protegidos por qualquer instância de Segurança de documentos, desde que você tenha autorização para abrir o arquivo.

Se o servidor de Segurança de documentos utilizar autenticação baseada em certificados, será necessário instalar o certificado recebido no computador local. Também será necessário escolher a autenticação de certificado e fornecer o certificado que deseja usar para autenticação.

Depois de configurar as definições de conexão para uma instância de Segurança de documentos em um aplicativo do Microsoft Office, ela é configurada para o Word, Excel e PowerPoint.

#### Instalação do certificado do lado do cliente {#install-the-client-side-certificate}

Se for necessário acessar as páginas da Web de Segurança de documentos por meio de autenticação de certificado ou autenticação bidirecional, você receberá o certificado que deve ser instalado em seu computador local. Você receberá um arquivo de certificado (arquivo .PFX ou .P12) e sua senha.

1. Salve o arquivo de certificado em seu computador local.
1. Clique duas vezes no arquivo de certificado para abrir o Assistente de importação de certificado e clique em **Próximo**.
1. Clique em **Próximo** se o arquivo de certificado estiver listado na caixa Nome do arquivo. Clique em **Pesquisar** se quiser localizar outro certificado.
1. Digite a senha recebida e clique em **Próximo**.
1. Na caixa de diálogo Armazenar certificados, selecione Colocar todos os certificados no seguinte armazenamento e clique em **Pesquisar**.
1. Na caixa de diálogo Selecionar armazenamento de certificados, selecione Pessoal, clique em **OK**, clique em **Próximo** e, em seguida, clique em **Concluir**.

#### Configuração de definições de conexão {#configure-connection-settings}

1. No Document Security Extension for Microsoft Office 2010 e Office 2013, na guia **Segurança de documentos**, selecione **Escolher servidor**.
1. Clique em **Novo** para criar novas definições de conexão, ou selecione uma conexão existente, e clique em **Editar**.
1. Digite um nome para a conexão na caixa **Nome**. Você pode usar qualquer nome.
1. Digite o endereço do servidor na caixa **Endereço do servidor**.
1. Digite a porta do servidor na caixa **Porta**.
1. (Opcional) Se quiser lembrar seu nome de usuário e senha, selecione **Lembrar senha neste computador** e digite seu nome de usuário e senha nas caixas apropriadas. É recomendável que você não selecione essa opção se outras pessoas tiverem acesso ao computador.
1. Clique em **Conectar a este servidor**. O Document Security Extension for Microsoft Office tentará se conectar ao servidor especificado. Dependendo do tipo de autenticação especificado, execute um dos procedimentos a seguir:

   **Nome de usuário e senha**

   Digite o nome de usuário e a senha recebidos do administrador da Segurança de documentos.

   **Autenticação de certificados**

   Escolha essa opção para selecionar o certificado recebido e instalado em seu armazenamento de certificados pessoal.

   Se somente um tipo de autenticação estiver configurado na Segurança de documentos, somente essa opção será exibida.

>[!NOTE]
>
>Se não conseguir se conectar ao servidor, tente abrir as páginas da Web de Segurança de documentos no Internet Explorer. Se não conseguir se conectar ao servidor usando o Internet Explorer ou se uma caixa de diálogo exibir um aviso sobre o certificado do servidor, o Document Security Extension for Microsoft Office não poderá se conectar ao servidor. Entre em contato com o administrador do servidor para obter assistência.

>[!NOTE]
>
>Se não conseguir se conectar à Segurança de documentos, será exibida uma mensagem informando que “O nome de usuário e a senha estão incorretos. Verifique as configurações e tente novamente”. Esta mensagem poderá ser exibida se você não conseguir se conectar por outro motivo. Se estiver se conectando ao servidor pela primeira vez, verifique se definiu o nome do servidor e a porta corretamente.

#### Especificação do servidor padrão {#specify-the-default-server}

1. Faça o seguinte:

   * Em Document Security Extension for Microsoft Office 2010 e Office 2013, na guia **Segurança de documentos**, selecione **Escolher servidor**.

1. Selecione um servidor para especificar como padrão e clique em **Definir padrão**. Uma estrela é exibida ao lado do servidor padrão.

### Uso de provedores de autenticação de terceiros {#using-third-party-authentication-providers}

É possível usar provedores de autenticação de terceiros com a Segurança de documentos do AEM Forms. Esses provedores de autenticação ajudam você a adicionar uma camada de acesso extra aos documentos protegidos. A Segurança de documentos do AEM Forms é compatível com os seguintes fluxos de trabalho de autenticação estendida:

* Autenticação estendida usando o URL padrão do AEM Forms
* Autenticação estendida usando um URL personalizado
* Fluxo de trabalho padrão de autenticação estendida com provedores de identidade de terceiros configurados no servidor do AEM Forms no JEE
* Fluxo de trabalho personalizado de autenticação estendida com provedores de identidade de terceiros configurados no servidor do AEM Forms no JEE
* Autenticação estendida usando página personalizada para listar Autenticações SAML

#### Autenticação estendida usando o URL padrão do AEM Forms {#extended-authentication-using-default-aem-forms-url}

É possível usar o URL padrão do AEM Forms para autenticação estendida. A página de aterrissagem padrão contém a marca Adobe. Além disso, as configurações padrão do AEM Forms são usadas ao usar o URL padrão do AEM Forms para autenticação estendida.

Execute as seguintes etapas para habilitar a autenticação estendida com o URL padrão de aterrissagem da Adobe:

1. Abra a interface do Administrador do AEM Forms.
1. Navegue até Serviços > Segurança de documentos > Configuração > Configuração do servidor.
1. Ative a opção Permitir autenticação estendida.
1. Especifique o URL padrão URL de Aterrissagem da Autenticação Estendida. O URL padrão é http://localhost:8080/edc/extendedauthentication/welcome.jsp.

   Clique em **[!UICONTROL Salvar]**.

   >[!NOTE]
   >
   >Use um nome de host totalmente qualificado no URL. É recomendável usar o protocolo HTTPS.

   Agora, a Segurança de documentos do AEM Forms está configurada para usar autenticação estendida com o URL padrão de aterrissagem do AEM Forms.

   ![](assets/third-party-authentication.png)

#### Autenticação estendida com um URL de aterrissagem personalizado {#extended-authentication-with-a-custom-landing-url}

É possível usar um URL personalizado para autenticação estendida. Ele oferece a flexibilidade para exibir uma página de autenticação personalizada com marca personalizada. Por exemplo, a marca para a sua organização.

Você pode criar um pacote da página de autenticação personalizada em um arquivo WAR e implantar o arquivo WAR no servidor do AEM Forms. O arquivo WAR contém uma lógica completa para aceitar credenciais de usuário e autenticar no servidor do AEM Forms. A Segurança de documentos do AEM Forms tem os seguintes requisitos para a página de autenticação personalizada:

* A página de autenticação deve enviar o nome de usuário como j_username e a senha como j_password. A página também deve enviar o source_url e o login_url como parâmetros ocultos.
* Na autenticação bem-sucedida, a página deve fechar automaticamente.

Execute as seguintes etapas para habilitar a autenticação estendida com um URL de aterrissagem personalizado:

1. Implante o arquivo WAR de autenticação personalizada no servidor do AEM Forms.
1. Abra a interface do Administrador do AEM Forms.
1. Navegue até Serviços > Segurança de documentos > Configuração > Configuração do servidor.
1. Ative a opção Permitir autenticação estendida e especifique o URL de aterrissagem personalizado da autenticação estendida.
1. Adicione as seguintes entradas ao arquivo config.xml sob o nó SSO após a entrada *&lt;node name=“AllowedUrls“>*:

   >[!NOTE]
   >
   >&lt;entry key=”sso-l” value=”/ sample_/login.jsp”/>!!discoiqbr!!&lt;entry key=”sso-s” value=”/ sample_/welcome.jsp”>!!discoiqbr!!&lt;entry key=”sso-o” value=”/ sample_/logout.jsp”/>!!discoiqbr!!

   Para obter informações detalhadas sobre a atualização do arquivo config.xml, consulte [Editar manualmente o arquivo de configuração de segurança de documentos](https://helpx.adobe.com/br/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file).

   Agora, a Segurança de documentos do AEM Forms está configurada para usar autenticação estendida com um URL de aterrissagem personalizado

#### Fluxo de trabalho padrão de autenticação estendida com provedores de identidade de terceiros configurados no servidor do AEM Forms {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

A autenticação estendida pode usar diferentes tipos de autenticação disponíveis no servidor do AEM Forms. Por exemplo, SAML, [Quais são os outros exemplos].

Observação: se os provedores SAML estiverem configurados no servidor do AEM Forms, antes de exibir o URL de aterrissagem, uma página contendo todos os provedores de identidade configurados para autenticações SAML será exibida.

A tela a seguir é exibida quando um documento protegido é aberto no Acrobat.

#### Fluxo de trabalho personalizado de autenticação estendida quando provedores SAML são configurados no servidor do AEM Forms {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Se os provedores SAML estiverem configurados no servidor do AEM Forms, antes de exibir o URL de aterrissagem, uma página contendo todos os provedores de identidade configurados para autenticações SAML será exibida.

Os pré-requisitos para configurar um fluxo de trabalho de autenticação estendida personalizado quando os provedores SAML são configurados no servidor do AEM Forms são:

* As autenticações SAML estão configuradas no servidor do AEM Forms
* O WAR personalizado, contendo uma página de autenticação personalizada e uma lógica completa para aceitar credenciais de usuário e autenticar no servidor do AEM Forms, é implantado no servidor do AEM Forms.

#### Uso de página personalizada para listar autenticações SAML {#using-custom-page-for-listing-saml-authentications}

É possível também exibir uma página personalizada para incluir todos os provedores de autenticação configurados no servidor do AEM Forms. Execute as seguintes etapas para criar uma página como essa:

1. Crie um pacote da página de autenticação personalizada em um arquivo WAR e implante o arquivo no servidor do AEM Forms. O arquivo WAR contém uma lógica completa para aceitar credenciais de usuário e autenticar no servidor do AEM Forms.
1. Abra a interface do Administrador do AEM Forms e navegue até **[!UICONTROL Definições]** > **[!UICONTROL Gerenciamento de usuários]** > **[!UICONTROL Configuração]** > **[!UICONTROL Configurações do Provedor de serviço SAML]**.
1. Adicione o seguinte ao campo Propriedades personalizadas e clique em **[!UICONTROL Salvar]**.

   *saml.sp.discovery.url=/demoJSP/saml_discovery.jsp*

   Agora, a Segurança de documentos do AEM Forms está configurada para exibir uma página personalizada contendo todos os provedores de autenticação configurados.

### Obtenção de uma conta de usuário {#obtaining-a-user-account}

Se você ainda não tiver uma conta de Segurança de documentos, a Segurança de documentos poderá iniciar o processo de registro quando estes eventos ocorrerem:

* Um usuário da Segurança de documentos que deseja enviar a você um arquivo protegido por política o adiciona a uma política.
* O administrador da Segurança de documentos cria uma conta para você.

Após registrar e ativar sua conta, você pode usar arquivos protegidos por política para os quais recebeu autorização para uso por meio de uma política.

>[!NOTE]
Se você receber um arquivo protegido por política e não tiver uma conta de Segurança de documentos, ou se receber um convite para se registrar, entre em contato com a pessoa que enviou o arquivo para obter assistência.

Se você receber um convite de registro por email da Segurança de documentos, poderá se registrar usando o URL no email para abrir a página de registro online. Depois de se registrar, você receberá um segundo aviso sobre como ativar sua conta.

#### Obtenção de uma conta de usuário externo {#obtain-an-external-user-account}

1. Abra o email de registro de Segurança de documentos. O URL que a mensagem contém é um link para a página Registro de usuários externos da Segurança de documentos. Se você não receber uma mensagem de registro, entre em contato com a pessoa que enviou o arquivo para obter ajuda.
1. Clique no URL ou copie-o e cole-o no navegador.
1. Digite seu nome, organização e senha nas caixas apropriadas. Sua senha pode ser qualquer combinação de oito caracteres.

   >[!NOTE]
   Escolha uma senha fácil de lembrar. Não há nenhum método disponível para encontrar senhas esquecidas.

1. Clique em **Registrar**. Será exibida uma mensagem informando para verificar se há uma mensagem de email de ativação.
1. Abra o email de confirmação de registro da Segurança de documentos.
1. Clique no URL que aparece na mensagem.
1. Clique no link para a página de Logon.
1. Na caixa **Nome de usuário**, digite o endereço de email em que você se registrou com a Segurança de documentos. Esse endereço de email é o nome de usuário padrão da Segurança de documentos.
1. Na caixa **Senha**, digite a senha que você criou ao se registrar.
1. Clique em **Logon**.

### Criação e gerenciamento de políticas {#creating-and-managing-policies}

Se você tiver permissão do administrador da Segurança de documentos, poderá criar políticas para aplicar aos seus próprios arquivos na página Políticas, das páginas da Web de Segurança de documentos.

Algumas das configurações de política disponíveis para criar políticas nas páginas da Web de Segurança de documentos não são compatíveis com arquivos do Word, Excel e PowerPoint. As tabelas a seguir descrevem como as permissões de política são mapeadas para os recursos do Word, Excel e PowerPoint.

<table>
 <thead>
  <tr>
   <th><p>Permissões</p></th>
   <th><p>Suporte para Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Imprimir &gt; Não permitido</p></td>
   <td><p>Não é permitido imprimir o arquivo.</p></td>
  </tr>
  <tr>
   <td><p>Imprimir &gt; Permitido</p></td>
   <td><p>A impressão do arquivo é permitida.</p><p><strong>Observação</strong>: <i>Se uma política conceder a permissão Copiar, mas não a permissão Imprimir, o conteúdo copiado para outro arquivo poderá ser impresso.</i></p></td>
  </tr>
  <tr>
   <td><p>Imprimir &gt; Somente Baixa res.</p></td>
   <td><p>Não aplicável.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Qualquer um</p></td>
   <td><p>O arquivo pode ser alterado.</p><p>Quando essa permissão não é fornecida, não é possível modificar arquivos protegidos do Word e Excel. Você pode modificar arquivos do PowerPoint, mas não pode salvar as alterações ou visualizar apresentações de slides para arquivos modificados.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Não permitido</p></td>
   <td><p>Os usuários não podem modificar arquivos protegidos.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Alterar páginas</p></td>
   <td><p>Não aplicável.</p><p>Inclui inserção, exclusão e rotação de páginas.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Preencher e Assinar</p></td>
   <td><p>Não aplicável.</p></td>
  </tr>
  <tr>
   <td><p>Offline</p></td>
   <td><p>O arquivo pode ser aberto offline.</p></td>
  </tr>
  <tr>
   <td><p>Copiar</p></td>
   <td><p>Conteúdos do arquivo podem ser copiados para outros arquivos.</p></td>
  </tr>
  <tr>
   <td><p>Leitor de tela </p></td>
   <td><p>Os leitores de tela (dispositivos para usuários portadores de deficiências visuais) podem ler o conteúdo do arquivo.</p></td>
  </tr>
  <tr>
   <td><p>Validade da permissão</p></td>
   <td><p>Compatível.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Configurações gerais</p></th>
   <th><p>Suporte para Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Período de validade</p></td>
   <td><p>Compatível.</p></td>
  </tr>
  <tr>
   <td><p>Documento de auditoria</p></td>
   <td><p>Compatível.</p></td>
  </tr>
  <tr>
   <td><p>Período de concessão offline automático</p></td>
   <td><p>Compatível.</p></td>
  </tr>
  <tr>
   <td><p>Provedores de autorização externos</p></td>
   <td><p>Compatível.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Configurações avançadas</p></th>
   <th><p>Suporte para Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Marcas d'água dinâmicas</p></td>
   <td><p>Compatível.</p></td>
  </tr>
  <tr>
   <td><p>Plug-ins de certificação</p></td>
   <td><p>Não aplicável.</p></td>
  </tr>
  <tr>
   <td><p>Algoritmo de criptografia e comprimento da chave </p></td>
   <td><p>Todas as opções são compatíveis.</p></td>
  </tr>
  <tr>
   <td><p>Restrição de documentos</p></td>
   <td><p>Todo o conteúdo do arquivo é sempre criptografado independentemente da configuração na política.</p></td>
  </tr>
  <tr>
   <td><p>Mensagem de erro de acesso negado</p></td>
   <td><p>Compatível.</p></td>
  </tr>
 </tbody>
</table>

Para obter mais informações sobre como criar e gerenciar políticas, consulte [Ajuda ao usuário final de Segurança de documentos](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

### Aplicação de políticas {#applying-policies}

É possível aplicar qualquer política disponível a um arquivo, incluindo políticas que você criou e as que fazem parte dos conjuntos de políticas aos quais você tem acesso. Antes de aplicar uma política, é preciso salvar o arquivo.

Depois de aplicar uma política, ela é adicionada à lista Recentemente usada no menu Segurança de documentos do AEM para facilitar a aplicação das políticas usadas com mais frequência. Se você usar mais de uma instância de Segurança de documentos. A lista Recentemente usada exibirá as políticas somente para o servidor ao qual você está conectado no momento ou para o servidor padrão se você ainda não tiver feito logon em uma instância de Segurança de documentos.

>[!NOTE]
Você pode aplicar políticas somente a arquivos de documentos do Word (.doc, também .docx e .docm no Microsoft Office 2010 e 2013), arquivos de pastas de trabalho do Excel (.xls, também .xlsx e .xlsm no Microsoft Office 2010 e 2013) e arquivos de apresentação do PowerPoint (.ppt, também .pptx e .pptm no Microsoft Office 2010 e 2013). Não é possível aplicar políticas a arquivos de modelo do Word (.dot), arquivos de modelo do Excel (.xlt) e arquivos de modelo de design do PowerPoint (.pot).

#### Aplicação de uma política {#apply-a-policy}

1. Em Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, selecione **Proteger > Escolher política**.

   Se você escolher o nome de usuário e a senha como método de autenticação no servidor e ainda não tiver fornecido informações de logon para a Segurança de documentos, uma caixa de diálogo solicitará seu nome de usuário e sua senha.

1. Selecione uma política na lista e clique em **Aplicar**.
1. Salve o arquivo.

#### Aplicação de uma política usada recentemente {#apply-a-recently-used-policy}

1. Em Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, selecione **Proteger** > *[Nome da política]*.
1. Salve o arquivo.

## Trabalho com os arquivos protegidos por política {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

Arquivos protegidos por política contêm propriedade intelectual pertencente ao editor do arquivo e protegida pela Segurança de documentos.

É possível usar arquivos protegidos por política seja você interno ou externo à organização do editor de arquivos. Para abrir arquivos protegidos por política, você deve ser reconhecido pela Segurança de documentos, seja por meio da inclusão em uma lista vinculada do LDAP ou de Diretório ativo, sendo adicionado como um usuário local para o LiveCycle ou o AEM Forms no JEE, ou por meio de registro na Segurança de documentos após ser convidado como usuário.

Se você receber um arquivo protegido por política e não tiver uma conta de Segurança de documentos, ou se receber um convite para se registrar, entre em contato com a pessoa que enviou o arquivo para obter assistência.

### Trabalhar com arquivos protegidos por política no Microsoft Office {#working-with-policy-protected-files-in-microsoft-office}

O Document Security Extension for Microsoft Office restringe determinadas funcionalidades do Word, Excel e PowerPoint para proteger a propriedade intelectual do editor de arquivos. Se você não tiver permissão para alterar o arquivo, não poderá salvar modificações nele.

Se estiver trabalhando com um arquivo protegido por política, alguns recursos do produto podem não estar disponíveis ou podem não funcionar normalmente. Se você também tiver um arquivo desprotegido aberto, a maioria dos recursos será ativada para o arquivo desprotegido, exceto aqueles que permitem importar ou copiar conteúdo de um arquivo protegido por política para o qual você não tem permissões de cópia ou exportação.

>[!NOTE]
Ao usar aplicativos do Office compatíveis com o Document Security Extension, é recomendado desativar a configuração do DEP do Windows. Além disso, para garantir que os aplicativos do Office sejam inicializados sem problemas em um computador com o Document Security Extension instalado e o McAfee VirusScan com o On-Access Scan ativado, desative a opção Proteção de sobrecarga de buffer no console do McAfee VirusScan.

Se um recurso não estiver disponível, o nome do comando no menu e o botão da barra de ferramentas relacionado não estarão disponíveis. No Document Security Extension for Microsoft Office, ao passar o ponteiro do mouse sobre o comando ou botão, uma dica de ferramenta indica que a Segurança de documentos não disponibiliza o comando.

### Acesso a arquivos protegidos por política {#opening-policy-protected-files}

É possível abrir arquivos protegidos por política usando os mesmos métodos usados para abrir qualquer outro arquivo. Se você ainda não tiver feito logon na Segurança de documentos, será solicitado a fazê-lo, a menos que não esteja conectado à Internet e possa abrir o arquivo offline. Se você cancelar o processo de logon, o acesso será negado.

Se você não tiver permissão para abrir o arquivo, será informado de que o acesso é negado. Se os privilégios de acesso a arquivos tiverem sido revogados, você também poderá ser direcionado para uma versão atualizada do arquivo, se disponível. Para obter ajuda adicional caso não consiga abrir um arquivo protegido por política, entre em contato com o editor do arquivo.

Quando um arquivo protegido é aberto, o texto na barra de título que segue o nome do arquivo indica que o arquivo está protegido pela Segurança de documentos do AEM.

Ao abrir um documento protegido do SharePoint Server no Document Security Extension for Microsoft Office, verifique se o programa do Microsoft Office associado ao tipo de arquivo, como Microsoft Word, Microsoft Excel ou Microsoft PowerPoint, está aberto. Se você tentar abrir o arquivo sem abrir o aplicativo associado, o documento pode não abrir e uma mensagem de erro indicando que você deve instalar o plug-in aplicável é exibida. Além de abrir o aplicativo necessário, recomenda-se que você limpe a pasta de cache antes de abrir um documento protegido do SharePoint Server no Document Security Extension for Microsoft Office. Além disso, ao abrir um documento protegido do SharePoint Server, todas as permissões do documento são desativadas, independentemente da política aplicada.

Dependendo do método de autenticação implementado na Segurança de documentos, talvez seja solicitado que você escolha o método de autenticação ao abrir um documento protegido. Se a Segurança de documentos for compatível com mais de um método de autenticação, as opções de autenticação serão apresentadas a você. Por exemplo, se o servidor de Segurança de documentos fornecer autenticação de nome de usuário/senha e certificado, você poderá escolher o método de autenticação apropriado. Se a autenticação baseada em certificado estiver ativada, você será solicitado a usar o certificado recebido e instalado.

A experiência do usuário ao abrir arquivos protegidos depende da configuração de autenticação mútua no servidor. Se somente um certificado de cliente válido estiver instalado, nenhuma caixa de diálogo de autenticação será exibida e os arquivos serão abertos com êxito. No entanto, se vários certificados de cliente estiverem instalados em um computador, uma caixa de diálogo de autenticação será exibida. O usuário deve escolher um certificado válido para abrir o arquivo protegido.

### Remoção da proteção por política de um arquivo {#removing-policy-protection-from-a-file}

Se você tiver permissão, poderá remover a proteção por política dos arquivos protegidos. Ao fazer isso, o arquivo não estará mais protegido pela Segurança de documentos.

1. Em Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, selecione **Remover**.

   Caso você ainda não tenha fornecido informações de logon para a Segurança de documentos, uma caixa de diálogo solicitará seu nome de usuário e senha.

>[!NOTE]
Se não conseguir remover uma política de um arquivo protegido, entre em contato com um administrador da Segurança de documentos.

### Exibição de configurações de segurança {#viewing-security-settings}

Você pode visualizar as permissões que tem para o arquivo atual para impressão, cópia, alteração e acesso offline, juntamente com o período de validade do arquivo.

No Document Security Extension for Microsoft Office 2010, o grupo Status de segurança, na guia Segurança de documentos, exibe suas permissões para o arquivo.

Faça o seguinte:

* Em Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, no grupo **Status de segurança**, clique em qualquer item.

### Salvamento de documentos quando a Aplicação automática de política estiver ativada {#saving-documents-when-auto-apply-policy-is-enabled}

Se o administrador tiver ativado a funcionalidade de Aplicação automática de política, qualquer documento que você criar ou editar será automaticamente protegido ao ser salvo.

Se a Aplicação automática de política estiver ativada, o Document Security Extension for Microsoft Office solicitará que você efetue logon no servidor da Segurança de documentos. Será necessário fornecer seu Nome de usuário e senha para ser autenticado pelo servidor. Se você tiver fornecido as credenciais de logon corretas, o documento será salvo e protegido.

>[!NOTE]
Caso não consiga fazer logon na Segurança de documentos, o documento poderá ou não poderá ser salvo. Isso depende de como o administrador configurou a Aplicação automática de política. Consulte o administrador para saber como os documentos são tratados nessa situação.

### Sincronização para acesso offline {#synchronizing-for-offline-access}

As políticas podem permitir que você abra arquivos enquanto estiver offline e não estiver conectado à Segurança de documentos. Você deve ter feito logon anteriormente na Segurança de documentos para estabelecer suas credenciais com o servidor antes de poder trabalhar offline. Se você planeja trabalhar com arquivos offline, é recomendável sincronizar com a Segurança de documentos antes de se desconectar, para garantir que as configurações de política para os seus arquivos estejam atualizadas com o servidor. É recomendável também abrir o arquivo online uma vez antes de abri-lo offline. Se você não abrir o arquivo online uma vez ou não sincronizá-lo com o servidor, ainda poderá usar arquivos protegidos por política offline. No entanto, o período de concessão offline não deve ter expirado e as configurações de política do arquivo não devem ter sido alteradas desde a última sincronização manual ou automática com o servidor.

Faça o seguinte:

* Em Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, selecione **Sincronizar offline**.

   ***Observação**: o botão Sincronizar offline está disponível mesmo se o usuário não tiver permissão offline para o documento. No entanto, selecionar o botão não faz nada. *

### Trabalho com marcas d&#39;água dinâmicas {#working-with-dynamic-watermarks}

O Document Security Extension for Microsoft Office oferece suporte à inclusão de marcas d&#39;água dinâmicas baseadas em texto em documentos protegidos por política. Uma marca d&#39;água dinâmica pode incluir informações que podem mudar, como data, hora, nome de usuário ou nome da política. Se um usuário imprimir um arquivo protegido por política e esse arquivo contiver uma marca d&#39;água dinâmica e a permissão para imprimir, a marca d&#39;água aparecerá na saída.

O Document Security Extension não é compatível com recursos avançados de marca d&#39;água, como marcas d&#39;água baseadas em PDFs, vários elementos em uma marca d&#39;água, opções de formatação de texto e intervalo de páginas.

Crie uma marca d&#39;água dinâmica usando as páginas da Web de Segurança de documentos. Para obter mais informações sobre como criar e incluir marcas d&#39;água dinâmicas em um documento protegido por política, consulte [Ajuda ao usuário final de Segurança de documentos](http://www.adobe.com/go/learn_lc_euRightsMgmt_11_br).

O Document Security Extension for Microsoft Office é compatível com estes recursos de marca d&#39;água:

<table>
 <thead>
  <tr>
   <th><p>Opções de marca d'água da Segurança de documentos</p></th>
   <th><p>Suporte para Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Nome da política</p></td>
   <td><p>Compatível.</p></td>
  </tr>
  <tr>
   <td><p>Nome da marca d'água</p></td>
   <td><p>Compatível.</p></td>
  </tr>
  <tr>
   <td><p>Usar como plano de fundo</p></td>
   <td><p>O comportamento de exibição de uma marca d'água dinâmica é o mesmo, independentemente de você selecionar Usar como plano de fundo.</p><p>Para o Word 2010 e 2013, a marca d'água dinâmica aparece somente no Layout de impressão e visualização de Pré-visualização de impressão. </p><p>No Excel 2010 e 2013 também, ela é exibida nas visualizações de Pré-visualização de impressão e Layout de página.</p></td>
  </tr>
  <tr>
   <td><p>Posição vertical</p></td>
   <td><p>Compatível</p></td>
  </tr>
  <tr>
   <td><p>Posição horizontal</p></td>
   <td><p>Compatível</p><p>Para o Excel 2010 e 2013, o posicionamento horizontal das marcas d'água usando pontos não funciona.</p></td>
  </tr>
  <tr>
   <td><p>Escala</p></td>
   <td><p>Compatível</p></td>
  </tr>
  <tr>
   <td><p>Posição</p></td>
   <td><p>Compatível</p></td>
  </tr>
  <tr>
   <td><p>Opacidade</p></td>
   <td><p>Compatível</p></td>
  </tr>
 </tbody>
</table>

### Acesso às páginas da Web da Segurança de documentos {#opening-the-document-security-web-pages}

É possível abrir as páginas da Web de Segurança de documentos para criar e atualizar suas políticas de usuário, e para exibir o status e as informações de auditoria sobre seus arquivos protegidos por política. Você também pode usar as páginas da Web de Segurança de documentos para alterar políticas ou revogar o acesso de um arquivo protegido por política.

Para abrir as páginas da Web de Segurança de documentos, no Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, selecione **Criar e Gerenciar Políticas**. Caso ainda não tenha fornecido as informações de logon, o navegador será aberto na página de logon do servidor.

### Alteração de políticas {#changing-policies}

Se você tiver permissões, normalmente como administrador de Segurança de documentos ou editor de arquivos, poderá aplicar uma política diferente a um arquivo ou alterar as configurações da política aplicada no momento.

Para alterar as configurações de uma política, use as páginas da Web de Segurança de documentos.

1. Faça o seguinte:

   * Em Document Security Extension for Microsoft Office 2010 ou 2013, na guia **Segurança de documentos**, selecione **Proteger > Alterar segurança**.

1. Selecione uma política na lista e clique em **Aplicar**.

### Revogação de privilégios de acesso a arquivos {#revoking-file-access-privileges}

É possível revogar a capacidade de abrir arquivos protegidos. Ao revogar os privilégios de acesso de um arquivo, você também pode especificar a mensagem que aparece para qualquer pessoa que tenta abrir o arquivo e o URL para uma versão atualizada do arquivo, se estiver substituindo-o por uma cópia revisada.

1. Faça o seguinte:

   * Em Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, selecione **Revogar**.

   As páginas da Web de Segurança de documentos abrem a página Revogar documentos.

1. Especifique uma mensagem para exibir e, se disponível, um URL para a versão atualizada, e clique em **OK**.

Para obter mais informações sobre revogar privilégios de acesso a arquivos, consulte [Ajuda ao usuário final de Segurança de documentos](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

Os privilégios de acesso podem ser reativados pelas páginas da Web de segurança de documentos.

### Exibição do histórico de auditoria de arquivos {#viewing-the-file-audit-history}

A Segurança de documentos pode salvar o histórico de auditoria de arquivos protegidos por política para que você possa auditar as ações que os usuários executam em seus arquivos.

Os eventos auditados para arquivos do Word, Excel e PowerPoint incluem:

**Proteger uma nova política** de documento aplicada a um arquivo

**Visualizar arquivo de documento** aberto

**Fechar arquivo de documento** fechado

**Revogar privilégios** de acesso a documentos removidos do arquivo

**Cancelar revogação de privilégios** de acesso a documentos retornados ao arquivo

**Modificar arquivos de documento** alterados e salvos localmente

**Imprimir arquivo de alta resolução** impresso

**Alterar proteção de política** de manipulador de segurança removida do arquivo

**Alternar a política no documento** Nova política aplicada ao arquivo das páginas da web de Segurança de documentos

### Visualização do histórico de auditoria de um arquivo {#view-the-audit-history-for-a-file}

Em Document Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança de documentos**, selecione **Histórico de auditoria**.

As páginas da Web de Segurança de documentos abrem a página Eventos, que exibe eventos auditados para o arquivo atual.

### Recursos restritos do Microsoft Office {#microsoft-office-restricted-features}

Para proteger sua propriedade intelectual, alguns recursos do Microsoft Office ficam indisponíveis quando um arquivo protegido por política é aberto. A lista de recursos indisponíveis depende das permissões concedidas ao usuário atual. Alguns recursos estão indisponíveis somente para um arquivo protegido, e outros estão indisponíveis para todos os arquivos quando você está em uma sessão protegida. Geralmente, você está em uma sessão protegida a partir do momento em que abre um arquivo protegido por política até que feche o aplicativo ou a sessão expire.

A maioria das políticas concede permissões totais ao editor do arquivo. Outros usuários podem notar restrições adicionais de recursos.

Se um comando não estiver disponível, o nome do comando no menu e o botão da barra de ferramentas relacionado ficam esmaecidos.

>[!NOTE]
Aplicar uma política a um arquivo que contenha um link para um arquivo incorporado não aplica a política ao arquivo vinculado. O Document Security for Microsoft Office não estende a proteção a arquivos vinculados.

* Arquivos do Word, Excel e PowerPoint protegidos por política estão impedidos de abrir em uma janela do navegador Internet Explorer.
* Os usuários aos quais foi concedida somente a permissão Alterar não podem copiar o conteúdo para um arquivo de outro aplicativo usando a Área de transferência do Windows. Os usuários podem copiar o conteúdo para arquivos ativando a opção Área de transferência do Microsoft Office.
* Abrir um arquivo protegido por política no Microsoft Office torna a tecla Print Screen indisponível até que você feche o aplicativo ou a sessão expire.
* O Document Security for Microsoft Office não é compatível com Distributed Authoring and Versioning (WebDAV) baseado na Web. Na maioria dos casos, não é possível abrir um arquivo protegido por política de uma pasta WebDAV. Se você puder abrir um arquivo protegido por política, não terá permissões para salvar, imprimir, alterar ou copiar do arquivo.

A segurança geral que se aplica aos arquivos protegidos por política inclui as seguintes restrições:

Muitos recursos comuns podem ser restritos no Word, Excel e PowerPoint durante uma sessão protegida.

Se um arquivo protegido por política que não permite que o usuário faça alterações for aberto, os comandos que alteram o arquivo de alguma forma não estarão disponíveis. Somente os comandos que abrem ou criam novos documentos e alteram as preferências do aplicativo estão disponíveis.

#### Limitações do Word 2010 e do Word 2013 {#word-2010-and-word-2013-restrictions}

A abertura de um arquivo protegido por política no Word torna indisponível salvar as informações de recuperação automática de arquivo até que você feche e reinicie o Word. Além disso, os recursos listados abaixo são limitados nas situações descritas:

**Arquivo > Novo > Novo a partir de existente** Disponível, mas os arquivos criados usando esse comando enquanto qualquer arquivo protegido por política estiver aberto não poderão ser salvos. O conteúdo no novo arquivo não pode ser copiado para outro arquivo.

**Arquivo > Salvar** Restrito pela permissão Alterar.

**Arquivo > Salvar como** Todas as opções restritas pela permissão Alterar.

**Arquivo > Imprimir** Todas as opções restritas pela permissão Imprimir. Indisponível, a menos que a política permita a impressão em alta resolução.

**Arquivo > Salvar e Enviar** Todas as opções indisponíveis durante uma sessão protegida.

**Arquivo > Informações > Proteger documento > Criptografar com senha, Adicionar assinatura digital, Marcar como final, Restringir permissão por pessoas** Indisponíveis durante uma sessão protegida.

**Arquivo > Fluxos de trabalho** Indisponível durante uma sessão protegida.

***Observação **: a capacidade de inicializar um fluxo de trabalho das versões 2010 do sistema Microsoft Office do Word, Excel e PowerPoint está disponível somente nos pacotes Office Professional Plus 2010, Office Enterprise 2010 e Office Ultimate 2010, bem como nas versões independentes desses programas do Office 2010.*

**Postagem de blog > Publicar** Indisponível durante uma sessão protegida.

**Arquivo > Servidor > Menu tarefas do servidor de arquivos** Indisponível durante uma sessão protegida.

**Início > Área de transferência > Copiar** Restrito pela permissão Copiar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado em nenhum outro arquivo ou na Área de transferência do Office. O conteúdo pode ser copiado dentro do arquivo protegido se o usuário tiver a permissão Alterar.

**Início > Área de transferência > Colar** Limitado pela permissão Alterar.

**Início > Área de transferência > Colar especial** Limitado pela permissão Alterar.

**Inserir > Texto > Objeto** Indisponível durante uma sessão protegida. Arquivos protegidos por política não podem ser inseridos a qualquer momento.

**Endereçamentos** A maioria das opções nesta guia não estão disponíveis durante uma sessão protegida.

**Revisar > Revisão > Pesquisa** Restrito pela permissão Copiar. Indisponível se copiar não for permitido.

**Revisar > Revisão > Thesaurus** Restrito pela permissão Copiar. Indisponível se copiar não for permitido.

**Revisar > Idioma > Traduzir > Traduzir documento** Habilitado com a permissão Copiar.

**Revisar > Idioma > Traduzir > Traduzir texto selecionado** Habilitado com a permissão Copiar.

**Revisar > Idioma > Traduzir > Minitradutor** Habilitado com a permissão Copiar.

**Revisar > Comparar > Comparar** Indisponível durante uma sessão protegida. Arquivos protegidos por política não podem ser comparados a qualquer momento.

**Revisar > Proteger > Bloquear autores** Indisponível durante uma sessão protegida.

**Revisar > Proteger > Restringir edição** Indisponível durante uma sessão protegida.

**Visualização > Macros** Algumas macros são restritas pela permissão Copiar e ficam indisponíveis, a menos que copiar seja permitido.

**Suplementos** Não é possível adicionar ou remover suplementos durante uma sessão protegida.

**Colaboração online** Indisponível durante uma sessão protegida.

**Principais e subdocumentos** Os subdocumentos são regidos pela política de documentos principais quando abertos dentro do documento principal. Se abertos separadamente, os subdocumentos não poderão ser impressos, copiados ou modificados.

**Resumir** Indisponível durante uma sessão protegida.

**Quadros (e todos os comandos relacionados)** Indisponíveis durante uma sessão protegida.

**Painel do documento** Indisponível durante uma sessão protegida.

**Desenvolvedor > Modelo de documento** Indisponível durante uma sessão protegida. Para acessar esse comando, selecione Arquivo > Opções > Personalizar > Guia desenvolvedor > Modelos > Modelo de documento.

**Contorno > Documento principal > Criar subdocumento, Inserir subdocumento** Não disponível durante uma sessão protegida.

#### Limitações do Excel 2010 e Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Os recursos listados abaixo são limitados nas situações descritas:

**Arquivo > Novo > Novo a partir de existente** Disponível, mas os arquivos criados usando esse comando durante uma sessão protegida não podem ser salvos. O conteúdo no novo arquivo não pode ser copiado para outro arquivo.

**Arquivo > Salvar, Salvar como** Restrito pela permissão Alterar.

**Arquivo > Salvar como > PDF** Indisponível durante uma sessão protegida.

**Arquivo > Imprimir** Restrito pela permissão Imprimir. Indisponível, a menos que a política permita a impressão em alta resolução.

**Arquivo > Informações > Proteger documento** Indisponível durante uma sessão protegida.

**Arquivo > Informações > Proteger pasta de trabalho** Indisponível durante uma sessão protegida.

**Arquivo > Salvar e enviar** Indisponível durante uma sessão protegida.

**Arquivo > Opções > Suplementos** Não pode ser adicionado ou removido durante uma sessão protegida.

**Arquivo > Fluxos de trabalho** Indisponível durante uma sessão protegida.

***Observação **: a capacidade de inicializar um fluxo de trabalho das versões 2010 do sistema Microsoft Office do Word, Excel e PowerPoint está disponível somente nos pacotes Office Professional Plus 2010, Office Enterprise 2010 e Office Ultimate 2010, bem como nas versões independentes desses programas do Office 2010.*

**Arquivo > Servidor > Menu tarefas do servidor de arquivos** Indisponível durante uma sessão protegida.

**Início > Área de transferência > Copiar** Restrito pela permissão Copiar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado em nenhum outro arquivo ou na Área de transferência do Microsoft Office. O conteúdo pode ser copiado dentro do arquivo protegido se o usuário tiver a permissão Alterar.

**Início > Área de transferência > Colar** Limitado pela permissão Alterar.

**Início > Área de transferência > Colar especial** Limitado pela permissão Alterar.

**Início > Células > Formatar > Mover ou Copiar planilha** Indisponível durante uma sessão protegida.

**Início > Células > Inserir > Inserir planilha** Indisponível durante uma sessão protegida.

**Início > Células > Excluir > Excluir planilha** Indisponível durante uma sessão protegida.

**Início > Editar > Preencher > Entre planilhas** Limitado pela permissão Alterar.

**Inserir > Tabelas > Tabela** Limitada pela permissão Alterar.

**Inserir > Tabelas > Tabela dinâmica** Arquivos protegidos por política não podem ser selecionados no Assistente de criação.

**Inserir > Texto > Objeto** Indisponível durante uma sessão protegida. Arquivos protegidos por política não podem ser inseridos a qualquer momento.

**Inserir> Texto > Cabeçalho e rodapé** Limitado pela permissão Alterar. Indisponível para um documento protegido por política.

**Dados > Obter dados externos** Não é possível importar dados de arquivos protegidos por política.

**Dados > Contorno > Subtotais** Limitado pela permissão Alterar.

**Dados > Ferramentas de dados > Validação de dados** Limitado pela permissão Alterar.

**Revisar > Revisão > Pesquisa** Restrito pela permissão Copiar.

**Revisar > Revisão > Thesaurus** Restrito pela permissão Copiar.

**Revisar > Idioma > Traduzir** Restrito pela permissão Copiar.

**Revisar > Alterações > Proteger planilha** Indisponível durante uma sessão protegida.

**Revisar > Alterações > Proteger pasta de trabalho** Indisponível durante uma sessão protegida.

**Revisar > Alterações > Compartilhar pasta de trabalho** Indisponível durante uma sessão protegida.

**Revisar > Alterações > Proteger e compartilhar pasta de trabalho** Indisponível durante uma sessão protegida.

**Revisar > Alterações > Permitir que os usuários editem intervalos** Indisponível durante uma sessão protegida.

**Revisar > Alterações > Controlar alterações > Realçar alterações** Indisponível para um arquivo protegido por política que contém uma marca d&#39;água dinâmica.

**Visualização > Macros** Limitado pela permissão Alterar.

**Visualização > Salvar espaço de trabalho** O comando não funciona.

**Desenvolvedor > XML > Pacotes de expansão** Algumas macros são restritas pela permissão Copiar e estão indisponíveis, a menos que copiar seja permitido.

**Fórmulas > Auditoria de fórmulas > Verificação de erros** Restrito pela permissão Alterar. Indisponível, a menos que a alteração seja permitida.

**Colaboração online** Indisponível durante uma sessão protegida.

**Salvar informações de recuperação automática** Indisponível durante uma sessão protegida.

***Observação **: Se você tentar alterar uma célula em um arquivo protegido por política para o qual você não tem permissão para fazer alterações, o Excel exibirá uma mensagem de aviso incorreta indicando que você deve remover a proteção do arquivo usando o comando Desproteger planilha. O uso do comando Desproteger planilha não remove a proteção por política do arquivo.*

#### Restrições do PowerPoint 2010 e PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Os recursos listados abaixo são limitados nas situações descritas:

**Arquivo > Novo > Novo a partir de existente** Disponível, mas os arquivos criados usando esse comando durante uma sessão protegida não podem ser salvos. O conteúdo no novo arquivo não pode ser copiado para outro arquivo.

**Arquivo > Salvar** Restrito pela permissão Alterar.

**Arquivo > Salvar como** Todas as opções restritas pela permissão Alterar.

**Arquivo > Imprimir** Todas as opções restritas pela permissão Imprimir. Indisponível, a menos que a política permita a impressão em alta resolução.

**Arquivo > Salvar e Enviar** Indisponível durante uma sessão protegida.

**Arquivo > Informações > Proteger apresentação > Criptografar com senha, Adicionar uma assinatura digital, Marcar como final, Restringir permissão por pessoas** Indisponível durante uma sessão protegida.

**Arquivo > Opções do PowerPoint > Salvar informações de recuperação automática** Indisponível durante uma sessão protegida.

**Arquivo > Servidor > Menu tarefas do servidor de arquivos** Indisponível durante uma sessão protegida.

**Início > Área de transferência > Copiar** Restrito pela permissão Copiar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado dentro do documento, em qualquer outro arquivo ou na Área de transferência do Office. O conteúdo pode ser copiado dentro do arquivo protegido se o usuário tiver a permissão Alterar.

**Início > Área de transferência > Colar** Limitado pela permissão Alterar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado dentro do documento.

**Início > Área de transferência > Colar especial** Limitado pela permissão Alterar.

**Início > Slides > Novos slides > Slides do Contorno, Reutilizar slides** Indisponível durante uma sessão protegida.

**Inserir > Texto > Objeto** Indisponível durante uma sessão protegida. Arquivos protegidos por política não podem ser inseridos a qualquer momento.

**Design > Plano de fundo > Estilos de plano de fundo, Ocultar gráficos de plano de fundo, Formatar plano de fundo** Indisponível para um arquivo protegido por política que contém uma marca d&#39;água dinâmica.

**Apresentação de slides > Configuração > Gravar apresentação de slides** Restrito por permissão de alteração.

**Revisar > Revisão > Thesaurus** Restrito pela permissão Copiar.

**Revisar > Idioma > Traduzir** Restrito pela permissão Copiar.

**Revisar > Idioma > Traduzir > Minitradutor** Habilitado com a permissão Copiar.

**Visualização > Visualizações de apresentação > Apresentação de slides** Restrito pela permissão Alterar. Se as alterações não forem permitidas, as apresentações de slides não poderão ser exibidas se o arquivo tiver sido modificado.

**Visualização > Macros** Algumas macros são restritas pela permissão Copiar e ficam indisponíveis, a menos que copiar seja permitido.

**Suplementos** Não é possível adicionar ou remover suplementos durante uma sessão protegida.

**Colaboração online** Indisponível durante uma sessão protegida.

## Uso de provedores de autenticação de terceiros {#use-third-party-authentication-providers}

É possível usar provedores de autenticação de terceiros com a Segurança de documentos do AEM Forms. Esses provedores de autenticação ajudam você a adicionar uma camada de acesso extra aos documentos protegidos. A Segurança de documentos do AEM Forms é compatível com os seguintes fluxos de trabalho de autenticação estendida:

* Autenticação estendida usando o URL padrão do AEM Forms
* Autenticação estendida usando um URL personalizado
* Fluxo de trabalho padrão de autenticação estendida com provedores de identidade de terceiros configurados no servidor do AEM Forms no JEE
* Fluxo de trabalho personalizado de autenticação estendida com provedores de identidade de terceiros configurados no servidor do AEM Forms no JEE
* Autenticação estendida usando página personalizada para listar Autenticações SAML

Para obter as etapas detalhadas para configurar workflows de autenticação estendida, consulte o artigo [Cenários de autenticação estendida](http://blogs.adobe.com/livecycle/2011/12/extended-authentication-scenarios.html)

## Glossário {#glossary}

Para obter informações sobre o LiveCycle e o AEM Form no JEE, consulte [Glossário](http://www.adobe.com/go/learn_aemforms_designer_65).
