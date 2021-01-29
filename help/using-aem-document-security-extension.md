---
title: Uso do AEM Documento Security Extension for Microsoft Office
description: Você pode controlar como os recipient usam seus arquivos protegidos por política, não importa o quão amplamente você os distribua. O documento explica como proteger arquivos e como trabalhar com arquivos protegidos.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
translation-type: tm+mt
source-git-commit: 21288f7f1c8f786d3c4c363986226038bdb03e26
workflow-type: tm+mt
source-wordcount: '6270'
ht-degree: 0%

---


# Uso do AEM Documento Security Extension for Microsoft Office{#using-aem-document-security-extension-for-microsoft-office}

## Arquivos Protect usando AEM Extensão de Segurança de Documento {#usingaemdocumentsecurityextensiontoprotectfiles}

Você pode controlar como os recipient usam seus arquivos protegidos por política, não importa o quão amplamente você os distribua.

Usando o Documento Security Extension for Microsoft Office, é possível executar estas tarefas:

* Configurar a conexão com a Segurança do Documento
* Aplicar uma política a um arquivo
* Abrir as páginas da Web de Segurança do Documento para criar e gerenciar políticas de usuário
* Remover proteção de política de um arquivo
* Alterar a política aplicada a um arquivo
* Abra as páginas da Web Segurança do Documento para revogar o acesso aos arquivos ou alterar a política do arquivo
* Abra as páginas da Web do Documento Security para visualização do histórico de auditoria do arquivo

### Conectar-se a um servidor de segurança do Documento {#connect-to-a-document-security-server}

Se pretende aplicar políticas a ficheiros, tem de configurar as definições de ligação para a Segurança do Documento. Dependendo de como o Documento Security Extension for Microsoft Office foi instalado, talvez você já tenha configurações de conexão padrão. Você pode adicionar configurações de conexão para uma ou mais instâncias da Segurança do Documento. Você pode obter informações do servidor do administrador de Segurança do Documento.

Você deve definir o servidor que deseja usar para proteger arquivos ou gerenciar seus arquivos protegidos como o servidor padrão. Quando você aplica uma política a um novo arquivo ou abre as páginas da Web do Documento Security, o Documento Security Extension for Microsoft Office conecta-se ao servidor padrão. Se você proteger arquivos usando mais de uma instância do Documento Security, deverá alterar a configuração padrão do servidor ao alternar entre servidores. Você pode abrir arquivos protegidos por qualquer instância do Documento Security, desde que tenha autorização para abrir o arquivo.

Se o servidor de Segurança do Documento utilizar autenticação baseada em certificados, será necessário instalar o certificado recebido na máquina local. Será necessário escolher a autenticação de certificado e fornecer o certificado que deseja usar para autenticação.

Depois de configurar as definições de conexão para uma instância do Documento Security em um aplicativo do Microsoft Office, ele é configurado para todo o Word, Excel e PowerPoint.

#### Instale o certificado do cliente {#install-the-client-side-certificate}

Se for necessário acessar as páginas da Web do Documento Security por meio de autenticação de certificado ou autenticação bidirecional, você receberá o certificado que deve ser instalado em sua máquina local. Você recebe um arquivo de certificado (arquivo .PFX ou .P12) e sua senha.

1. Salve o arquivo de certificado em sua máquina local.
1. Clique no arquivo de certificado com o duplo para abrir o Assistente de importação de certificado e clique em **Next**.
1. Clique em **Próximo** se o arquivo de certificado estiver listado na caixa Nome do arquivo. Clique em **Procurar** se quiser localizar outro certificado.
1. Digite a senha recebida e clique em **Next**.
1. Na caixa de diálogo Repositório de certificados, selecione Colocar todos os certificados no seguinte armazenamento e clique em **Procurar**.
1. Na caixa de diálogo Selecionar armazenamento de certificados, selecione Pessoal, clique em **OK**, clique em **Próximo** e, em seguida, clique em **Concluir**.

#### Definir configurações de conexão {#configure-connection-settings}

1. No Documento Security Extension for Microsoft Office 2010 e Office 2013, na guia **Documento Security**, selecione **Escolher servidor**.
1. Clique em **Novo** para criar novas definições de ligação ou selecione uma ligação existente e clique em **Editar**.
1. Digite um nome para a conexão na caixa **Name**. Você pode usar qualquer nome.
1. Digite o endereço do servidor na caixa **Endereço do servidor**.
1. Digite a porta do servidor na caixa **Porta**.
1. (Opcional) Se quiser lembrar seu nome de usuário e senha, selecione **Lembrar senha neste computador** e digite seu nome de usuário e senha nas caixas apropriadas. É recomendável que você não selecione essa opção se outras pessoas tiverem acesso ao computador.
1. Clique em **Ligar a Este Servidor**. O Documento Security Extension for Microsoft Office tenta se conectar ao servidor especificado. Dependendo do tipo de autenticação especificado, execute um dos procedimentos a seguir:

   **Nome de usuário e senha**

   Digite o nome de usuário e a senha recebidos do administrador do Documento Security.

   **Autenticação de certificado**

   Escolha essa opção para selecionar o certificado recebido e instalado em seu armazenamento de certificados pessoal.

   Se apenas um tipo de autenticação estiver configurado na Segurança do Documento, somente essa opção será exibida.

>[!NOTE]
>
>Se não conseguir se conectar ao servidor, tente abrir as páginas da Web do Documento Security no Internet Explorer. Se você não conseguir se conectar ao servidor usando o Internet Explorer ou se uma caixa de diálogo exibir um aviso sobre o certificado do servidor, o Documento Security Extension for Microsoft Office não poderá se conectar ao servidor. Entre em contato com o administrador do servidor para obter assistência.

>[!NOTE]
>
>Se você não conseguir se conectar ao Documento Security, será exibida uma mensagem informando que &quot;O nome de usuário e a senha estão incorretos, verifique as configurações e tente novamente&quot;. Esta mensagem poderá ser exibida se você não conseguir se conectar por outro motivo. Se você estiver se conectando ao servidor pela primeira vez, verifique se definiu o nome do servidor e a porta corretamente.

#### Especifique o servidor padrão {#specify-the-default-server}

1. Faça o seguinte:

   * No Documento Security Extension for Microsoft Office 2010 e Office 2013 na guia **Documento Security**, selecione **Escolher servidor**.

1. Selecione um servidor para especificar como padrão e clique em **Definir padrão**. Uma estrela é exibida ao lado do servidor padrão.

### Uso de provedores de autenticação de terceiros {#using-third-party-authentication-providers}

Você pode usar provedores de autenticação de terceiros com o AEM Forms Documento Security. Esses provedores de autenticação ajudam você a adicionar uma camada de acesso adicional aos documentos protegidos. O AEM Forms Documento Security suporta os seguintes workflows de autenticação estendida:

* Autenticação estendida usando o URL AEM Forms padrão
* Autenticação estendida usando um URL personalizado
* Fluxo de trabalho padrão de autenticação estendida com provedores de identidade de terceiros configurados no AEM Forms no servidor JEE
* Fluxo de trabalho personalizado de autenticação estendida com provedores de identidade de terceiros configurado no AEM Forms no servidor JEE
* Autenticação estendida usando página personalizada para listar Autenticações SAML

#### Autenticação estendida usando o URL padrão do AEM Forms {#extended-authentication-using-default-aem-forms-url}

Você pode usar o URL padrão do AEM Forms para autenticação estendida. A landing page padrão contém a marca Adobe. Além disso, as configurações padrão do AEM Forms são usadas ao usar o URL padrão do AEM Forms para autenticação estendida.

Execute as seguintes etapas para habilitar a autenticação estendida com o URL de aterrissagem de Adobe padrão:

1. Abra a AEM Forms Admin UI.
1. Navegue até Serviços > Segurança do Documento > Configuração > Configuração do servidor.
1. Ative a opção Permitir autenticação estendida.
1. Especifique o URL padrão de Aterrissagem da Autenticação Estendida do URL. O URL padrão é http://localhost:8080/edc/extendedauthentication/welcome.jsp.

   Clique em **[!UICONTROL Salvar]**.

   >[!NOTE]
   >
   >Use um nome de host totalmente qualificado no URL. É recomendável usar o protocolo HTTPS.

   Agora, a segurança do documento AEM Forms está configurada para usar autenticação estendida com o URL inicial padrão do AEM Forms.

   ![](assets/third-party-authentication.png)

#### Autenticação estendida com um URL inicial personalizado {#extended-authentication-with-a-custom-landing-url}

Você pode usar um URL personalizado para autenticação estendida. Ele oferece a flexibilidade para exibir uma página de autenticação personalizada com marca personalizada. Por exemplo, marca para sua organização.

Você pode disponibilizar a página de autenticação personalizada em um arquivo de guerra e implantar o arquivo de guerra no servidor AEM Forms. O arquivo de guerra contém uma lógica completa para aceitar credenciais de usuário e autenticar no servidor AEM Forms. O AEM Forms Documento Security tem os seguintes requisitos para a página de autenticação personalizada:

* A página de autenticação deve enviar o nome de usuário como j_username e a senha como j_password. A página também deve enviar o source_url e o login_url como parâmetros ocultos.
* Na autenticação bem-sucedida, a página deve fechar automaticamente.

Execute as seguintes etapas para habilitar a autenticação estendida com um URL de aterrissagem personalizado:

1. Implante o arquivo de guerra de autenticação personalizada no servidor AEM Forms.
1. Abra a AEM Forms Admin UI.
1. Navegue até Serviços > Segurança do Documento > Configuração > Configuração do servidor.
1. Ative a opção Permitir autenticação estendida e especifique o URL de aterrissagem personalizado da autenticação estendida.
1. Adicione as seguintes entradas ao arquivo config.xml sob o nó SSO após a entrada *&lt;nome do nó=&quot;AllowedUrls&quot;>*:

   >[!NOTE]
   >
   >&lt;entry>! !discoiqbr!&lt;entry>! !discoiqbr!&lt;entry>! !discoiqbr!

   Para obter informações passo a passo sobre a atualização do arquivo config.xml, consulte [Editar manualmente o arquivo de configuração de segurança do documento](https://helpx.adobe.com/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file).

   Agora, a segurança do documento AEM Forms está configurada para usar autenticação estendida com um URL de aterrissagem personalizado

#### Fluxo de trabalho padrão de autenticação estendida com provedores de identidade de terceiros configurados no servidor AEM Forms {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

A autenticação estendida pode usar diferentes tipos de autenticação disponíveis no servidor AEM Forms. Por exemplo, SAML, [Quais são mais exemplos].

Observação: Se os provedores SAML estiverem configurados no servidor AEM Forms, antes de exibir o URL de aterrissagem, uma página contendo todos os provedores de identidade configurados para autenticações SAML será exibida.

A tela a seguir é exibida quando um documento protegido é aberto no Acrobat.

#### Fluxo de trabalho personalizado de autenticação estendida quando provedores SAML são configurados no servidor AEM Forms {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Se os provedores SAML estiverem configurados no servidor AEM Forms, antes de exibir o URL de aterrissagem, uma página contendo todos os provedores de identidade configurados para autenticações SAML será exibida.

Os pré-requisitos para configurar um fluxo de trabalho de autenticação estendida personalizado quando os provedores SAML são configurados no servidor AEM Forms:

* As autenticações SAML estão configuradas no servidor AEM Forms
* A guerra personalizada, que contém uma página de autenticação personalizada e uma lógica completa para aceitar credenciais de usuário e autenticar no servidor AEM Forms, é implantada no servidor AEM Forms.

#### Usar página personalizada para listar autenticações SAML {#using-custom-page-for-listing-saml-authentications}

Você também pode exibir uma página personalizada para incluir todos os provedores de autenticação configurados no servidor AEM Forms. Execute as seguintes etapas para criar uma página como essa:

1. Compacte a página de autenticação personalizada em um arquivo de guerra e implante o arquivo de guerra no servidor AEM Forms. O arquivo de guerra contém uma lógica completa para aceitar credenciais de usuário e autenticar no servidor AEM Forms.
1. Abra a interface do usuário do AEM Forms Admin e navegue até **[!UICONTROL Settings]** **[!UICONTROL Gerenciamento de usuários]** > **[!UICONTROL Configuração]** > **[!UICONTROL Configurações do Provedor de serviço SAML]**.
1. Adicione o seguinte ao campo Propriedades personalizadas e clique em **[!UICONTROL Salvar]**.

   *saml.sp.disrecovery.url=/demoJSP/saml_discovery.jsp*

   Agora, a segurança do documento AEM Forms está configurada para exibir uma página personalizada contendo todos os provedores de autenticação configurados.

### Obter uma conta de usuário {#obtaining-a-user-account}

Se você ainda não tiver uma conta de Segurança do Documento, a Segurança do Documento poderá iniciar o processo de registro quando esses eventos ocorrerem:

* Um usuário do Documento Security que deseja enviar um arquivo protegido por política o adiciona a uma política.
* O administrador da Segurança do Documento cria uma conta para você.

Depois de registrar e ativar sua conta, você pode usar arquivos protegidos por política que recebeu autorização para uso por meio de uma política.

>[!NOTE]
Se você receber um arquivo protegido por política e não tiver uma conta de Segurança do Documento, ou se receber um convite para se registrar, entre em contato com a pessoa que enviou o arquivo para obter assistência.

Se você receber um convite de registro por e-mail do Documento Security, poderá se registrar usando o URL no e-mail para abrir a página de registro online. Depois de se registrar, você receberá um segundo aviso sobre como ativar sua conta.

#### Obter uma conta de usuário externo {#obtain-an-external-user-account}

1. Abra o e-mail de registro do Documento Security. O URL que a mensagem contém é um link para a página Registro de usuários externos do Documento Security. Se você não receber uma mensagem de registro, entre em contato com a pessoa que enviou o arquivo para obter ajuda.
1. Clique no URL ou copie-o e cole-o no navegador.
1. Digite seu nome, organização e senha nas caixas apropriadas. Sua senha pode ser qualquer combinação de oito caracteres.

   >[!NOTE]
   Escolha uma senha fácil de lembrar; nenhum método está disponível para encontrar senhas esquecidas.

1. Clique em **Register**. Será exibida uma mensagem informando para verificar se há uma mensagem de e-mail de ativação em seu e-mail.
1. Abra o e-mail de confirmação de registro do Documento Security.
1. Clique no URL que aparece na mensagem.
1. Clique no link para a página Login.
1. Na caixa **Nome de usuário**, digite o endereço de email em que você se registrou com o Documento Security. Esse endereço de email é o nome de usuário padrão da Segurança do Documento.
1. Na caixa **Senha**, digite a senha que você criou ao se registrar.
1. Clique em **Logon**.

### Criar e gerenciar políticas {#creating-and-managing-policies}

Se você tiver permissão do administrador do Documento Security, poderá criar políticas para aplicar aos seus próprios arquivos na página Políticas das páginas da Web do Documento Security.

Algumas das configurações de política disponíveis para criar políticas nas páginas da Web do Documento Security não são suportadas para arquivos do Word, Excel e PowerPoint. As tabelas a seguir descrevem como as permissões de política são mapeadas para os recursos do Word, Excel e PowerPoint.

<table>
 <thead>
  <tr>
   <th><p>Permissões </p></th>
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
   <td><p>A impressão do arquivo é permitida.</p><p><strong>Observação</strong>:  <i>Se uma política conceder a permissão Copiar, mas não a permissão Imprimir, o conteúdo copiado para outro arquivo poderá ser impresso.</i></p></td>
  </tr>
  <tr>
   <td><p>Imprimir &gt; Baixa res. Somente</p></td>
   <td><p>Não aplicável.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Qualquer</p></td>
   <td><p>O arquivo pode ser alterado.</p><p>Quando essa permissão não é fornecida, não é possível modificar arquivos do Word e Excel protegidos. Você pode modificar arquivos do PowerPoint, mas não pode salvar as alterações ou apresentações de slides de visualização para arquivos modificados.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Não permitido</p></td>
   <td><p>Os usuários não podem modificar arquivos protegidos.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Alterar páginas</p></td>
   <td><p>Não aplicável.</p><p>Inclui inserir, excluir e girar páginas.</p></td>
  </tr>
  <tr>
   <td><p>Alterar &gt; Fill &amp; Sign</p></td>
   <td><p>Não aplicável.</p></td>
  </tr>
  <tr>
   <td><p>Offline</p></td>
   <td><p>O arquivo pode ser aberto offline.</p></td>
  </tr>
  <tr>
   <td><p>Copiar</p></td>
   <td><p>O conteúdo do arquivo pode ser copiado para outros arquivos.</p></td>
  </tr>
  <tr>
   <td><p>Reader de tela </p></td>
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
   <td><p>Período de empréstimo off-line automático</p></td>
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
   <td><p>Todas as opções são suportadas.</p></td>
  </tr>
  <tr>
   <td><p>restrição de documento</p></td>
   <td><p>Todo o conteúdo do arquivo é sempre criptografado independentemente da configuração na política.</p></td>
  </tr>
  <tr>
   <td><p>Mensagem de erro de acesso negado</p></td>
   <td><p>Compatível.</p></td>
  </tr>
 </tbody>
</table>

Para obter mais informações sobre como criar e gerenciar políticas, consulte [Ajuda do usuário final do Documento Security](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

### Aplicar políticas {#applying-policies}

É possível aplicar qualquer política disponível a um arquivo, incluindo políticas que você criou e as que fazem parte dos conjuntos de políticas aos quais você tem acesso. Antes de aplicar uma política, você deve salvar o arquivo.

Depois de aplicar uma política, ela é adicionada à lista Recentemente usada no menu Segurança do Documento AEM para facilitar a aplicação das políticas usadas com mais frequência. Se você usar mais de uma instância da Segurança do Documento, a lista Recentemente Usada exibirá as políticas somente para o servidor ao qual você está conectado no momento ou para o servidor padrão se você ainda não tiver feito logon em uma instância da Segurança do Documento.

>[!NOTE]
Você pode aplicar políticas somente a arquivos de documento do Word (.doc, também.docx e .docm no Microsoft Office 2010 e 2013), arquivos de pasta de trabalho do Excel (.xls, também .xlsx e .xlsm no Microsoft Office 2010 e 2013) e arquivos de apresentação do PowerPoint (.ppt, também .pptx e .pptm no Microsoft Office 2010 e 2013). Não é possível aplicar políticas a arquivos de modelo do Word (.dot), arquivos de modelo do Excel (.xlt) e arquivos de modelo do PowerPoint (.pot).

#### Aplicar uma política {#apply-a-policy}

1. No Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Documento Security**, selecione **Proteger > Escolher política**.

   Se você escolher o nome de usuário e a senha como método de autenticação no servidor e ainda não tiver fornecido informações de logon para a Segurança do Documento, uma caixa de diálogo solicitará seu nome de usuário e sua senha.

1. Selecione uma política na lista e clique em **Aplicar**.
1. Salve o arquivo.

#### Aplicar uma política usada recentemente {#apply-a-recently-used-policy}

1. No Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Documento Security**, selecione **Seguro > ***[Nome da política]*.
1. Salve o arquivo.

## Trabalhar com os arquivos protegidos por política {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

Os arquivos protegidos por política contêm propriedade intelectual pertencente ao editor do arquivo e protegida pelo Documento Security.

Você pode usar arquivos protegidos por política se for interno ou externo à organização do editor de arquivos. Para abrir arquivos protegidos por política, você deve ser reconhecido pela Segurança do Documento, seja por meio da inclusão em uma lista vinculada do LDAP ou Ative Diretory, sendo adicionado como um usuário local para formulários do LiveCycle ou AEM no JEE, ou por meio de registro na Segurança do Documento após ser convidado como um usuário.

Se você receber um arquivo protegido por política e não tiver uma conta de Segurança do Documento, ou se receber um convite para se registrar, entre em contato com a pessoa que enviou o arquivo para obter assistência.

### Trabalhar com arquivos protegidos por política no Microsoft Office {#working-with-policy-protected-files-in-microsoft-office}

O Documento Security Extension for Microsoft Office restringe determinadas funcionalidades do Word, Excel e PowerPoint para proteger a propriedade intelectual do editor de arquivos. Se você não tiver permissão para alterar o arquivo, não poderá salvar modificações nele.

Se você estiver trabalhando com um arquivo protegido por política, alguns recursos do produto podem não estar disponíveis ou podem não funcionar como de costume. Se você também tiver um arquivo desprotegido aberto, a maioria dos recursos será ativada para o arquivo desprotegido, exceto aqueles que permitem importar ou copiar conteúdo de um arquivo protegido por política para o qual você não tem permissões de cópia ou exportação.

>[!NOTE]
Ao usar aplicativos do Office compatíveis com o Documento Security Extension, recomenda-se desativar a configuração do DEP do Windows. Além disso, para garantir que os aplicativos do Office sejam start sem problemas em uma máquina com o Documento Security Extension instalado e o McAfee VirusScan com o On-Access Scan ativado, desative a opção Proteção de estouro de buffer no console do McAfee VirusScan.

Se um recurso não estiver disponível, o nome do comando no menu e o botão da barra de ferramentas relacionado não estarão disponíveis. No Documento Security Extension for Microsoft Office, ao passar o ponteiro do mouse sobre o comando ou botão, uma dica de ferramenta indica que o Documento Security não disponibiliza o comando.

### Abrindo arquivos protegidos por política {#opening-policy-protected-files}

É possível abrir arquivos protegidos por política usando os mesmos métodos usados para abrir qualquer outro arquivo. Se você ainda não estiver conectado ao Documento Security, será solicitado a fazê-lo, a menos que não esteja conectado à Internet e possa abrir o arquivo offline. Se você cancelar o processo de logon, o acesso será negado.

Se você não tiver permissão para abrir o arquivo, será informado de que o acesso é negado. Se os privilégios de acesso a arquivos tiverem sido revogados, você também poderá ser direcionado para uma versão atualizada do arquivo, se disponível. Para obter ajuda adicional se não conseguir abrir um arquivo protegido por política, entre em contato com o editor do arquivo.

Quando um arquivo protegido é aberto, o texto na barra de título que segue o nome do arquivo indica que o arquivo está protegido pelo AEM Segurança do Documento.

Ao abrir um documento protegido no Documento Security Extension for Microsoft Office a partir do SharePoint Server, verifique se o programa do Microsoft Office associado ao tipo de arquivo, como Microsoft Word, Microsoft Excel ou Microsoft PowerPoint, está aberto. Se você tentar abrir o arquivo sem abrir o aplicativo associado, o documento pode não abrir e uma mensagem de erro indicando que você deve instalar o plug-in aplicável é exibida. Além de abrir o aplicativo necessário, recomenda-se que você limpe a pasta de cache antes de abrir um documento protegido no Documento Security Extension for Microsoft Office a partir do SharePoint Server. Além disso, quando você abre um documento protegido do SharePoint Server, todas as permissões do documento são desativadas, independentemente da política aplicada.

Dependendo do método de autenticação implementado na Segurança do Documento, talvez seja solicitado que você escolha o método de autenticação ao abrir um documento protegido. Se o Documento Security suportar mais de um método de autenticação, as opções de autenticação serão apresentadas a você. Por exemplo, se o servidor de Segurança do Documento fornecer autenticação de nome de usuário/senha e certificado, você poderá escolher o método de autenticação apropriado. Se a autenticação baseada em certificado estiver ativada, você será solicitado a usar o certificado recebido e instalado.

A experiência do usuário ao abrir arquivos protegidos depende da configuração de autenticação mútua no servidor. Se apenas um certificado de cliente válido estiver instalado, nenhuma caixa de diálogo de autenticação será exibida e os arquivos serão abertos com êxito. No entanto, se vários certificados de cliente estiverem instalados em uma máquina, uma caixa de diálogo de autenticação será exibida. O usuário deve escolher um certificado válido para abrir o arquivo protegido.

### Removendo a proteção de política de um arquivo {#removing-policy-protection-from-a-file}

Se você tiver permissão, poderá remover a proteção por política dos arquivos protegidos. Se você fizer isso, o arquivo não será mais protegido pelo Documento Security.

1. No Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Documento Security**, selecione **Remover**.

   Se você ainda não tiver fornecido informações de logon para a Segurança do Documento, uma caixa de diálogo solicitará seu nome de usuário e senha.

>[!NOTE]
Se não conseguir remover uma política de um arquivo protegido, entre em contato com um administrador do Documento Security.

### Exibindo configurações de segurança {#viewing-security-settings}

Você pode visualização as permissões que tem para o arquivo atual para impressão, cópia, alteração e acesso offline, juntamente com o período de validade do arquivo.

No Documento Security Extension for Microsoft Office 2010, o grupo Status de segurança na guia Segurança do Documento exibe suas permissões para o arquivo.

Faça o seguinte:

* No Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Segurança do Documento**, no grupo **Status de Segurança**, clique em qualquer item.

### Salvar documentos quando a aplicação automática de política estiver ativada {#saving-documents-when-auto-apply-policy-is-enabled}

Se o administrador tiver ativado a funcionalidade de aplicação automática de política, qualquer documento que você criar ou editar será automaticamente protegido ao salvar o documento.

Se a aplicação automática de política estiver ativada, o Documento Security Extension for Microsoft Office solicitará que você efetue logon no servidor Documento Security. Você precisará fornecer seu nome de usuário e sua senha para ser autenticado pelo servidor. Se você forneceu as credenciais de logon corretas, o documento será salvo e protegido.

>[!NOTE]
Se você não conseguir fazer logon no Documento Security, o documento poderá ou não ser salvo. Isso depende de como o administrador configurou a política de aplicação automática. Consulte o administrador para saber como os documentos são tratados nessa situação.

### Sincronização para acesso offline {#synchronizing-for-offline-access}

As políticas podem permitir que você abra arquivos enquanto estiver offline e não estiver conectado à Segurança do Documento. Você deve ter feito logon anteriormente no Documento Security para estabelecer suas credenciais com o servidor antes de poder trabalhar offline. Se você planeja trabalhar com arquivos offline, é recomendável sincronizar com a Segurança do Documento antes de desconectar para garantir que as configurações de política para seus arquivos estejam atualizadas com o servidor. É recomendável que você também abra o arquivo on-line uma vez antes de abri-lo off-line. Se você não abrir o arquivo uma vez on-line ou sincronizar com o servidor, ainda poderá usar arquivos protegidos por política offline. No entanto, o período de empréstimo offline não deve ter expirado e as configurações de política do arquivo não devem ter sido alteradas desde a última sincronização manual ou automática com o servidor.

Faça o seguinte:

* No Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Documento Security**, selecione **Sincronizar offline**.

   ***nota**: O botão Sincronizar off-line está disponível mesmo se o usuário não tiver permissão offline para o documento. No entanto, selecionar o botão não faz nada. *

### Trabalhar com marcas d&#39;água dinâmicas {#working-with-dynamic-watermarks}

O Documento Security Extension for Microsoft Office oferece suporte à inclusão de marcas d&#39;água dinâmicas baseadas em texto em documentos protegidos por política. Uma marca d&#39;água dinâmica pode incluir informações que podem mudar, como data, hora, nome de usuário ou nome da política. Se um usuário imprimir um arquivo protegido por política e esse arquivo contiver uma marca d&#39;água dinâmica e a permissão para imprimir, a marca d&#39;água aparecerá na saída.

A Extensão de segurança do documento não oferece suporte a recursos avançados de marca d&#39;água, como marcas d&#39;água baseadas em PDF, vários elementos em uma marca d&#39;água, opções de formatação de texto e intervalo de páginas.

Você cria uma marca d&#39;água dinâmica usando as páginas da Web do Documento Security. Para obter mais informações sobre como criar e incluir marcas d&#39;água dinâmicas em um documento protegido por política, consulte [Ajuda do usuário final do Documento Security](http://www.adobe.com/go/learn_lc_euRightsMgmt_11).

O Documento Security Extension for Microsoft Office oferece suporte para estes recursos de marca d&#39;água:

<table>
 <thead>
  <tr>
   <th><p>Opções de marca d'água do Documento Security</p></th>
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
   <td><p>O comportamento de exibição de uma marca d'água dinâmica é o mesmo, independentemente de você selecionar Usar como plano de fundo.</p><p>Para o Word 2010 e 2013, a marca d'água dinâmica aparece somente em Layout de impressão e visualização de Pré-visualização de impressão. </p><p>No Excel 2010 e 2013 também, ele é exibido nas visualizações Pré-visualização de impressão e Layout de página.</p></td>
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

### Abrir as páginas da Web do Documento Security {#opening-the-document-security-web-pages}

Você pode abrir as páginas da Web do Documento Security para criar e atualizar suas políticas de usuário, bem como para o status da visualização e as informações de auditoria sobre seus arquivos protegidos por política. Você também pode usar as páginas da Web Segurança do Documento para alterar políticas ou revogar o acesso de um arquivo protegido por política.

Para abrir as páginas da Web do Documento Security, no Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Documento Security**, selecione **Criar e Gerenciar Políticas**. Se você ainda não tiver fornecido as informações de logon, o navegador será aberto na página de logon do servidor.

### Alteração de políticas {#changing-policies}

Se você tiver permissões, normalmente como administrador de Segurança do Documento ou editor de arquivos, poderá aplicar uma política diferente a um arquivo ou alterar as configurações da política aplicada no momento.

Para alterar as configurações de uma política, use as páginas da Web do Documento Security.

1. Faça o seguinte:

   * No Documento Security Extension for Microsoft Office 2010 ou 2013, na guia **Documento Security**, selecione **Proteger > Alterar segurança**.

1. Selecione uma política na lista e clique em **Aplicar**.

### Revogando privilégios de acesso a arquivos {#revoking-file-access-privileges}

Você pode revogar a capacidade de abrir arquivos protegidos. Ao revogar os privilégios de acesso de um arquivo, você também pode especificar a mensagem que aparece para qualquer pessoa que tenta abrir o arquivo e o URL para uma versão atualizada do arquivo, se estiver substituindo-o por uma cópia revisada.

1. Faça o seguinte:

   * No Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Documento Security**, selecione **Revogar**.

   As páginas da Web Segurança do Documento abrem a página Revogar Documentos.

1. Especifique uma mensagem para exibir e, se disponível, um URL para a versão atualizada, e clique em **OK**.

Para obter mais informações sobre revogar privilégios de acesso a arquivos, consulte [Ajuda do usuário final do Documento Security](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

Os privilégios de acesso podem ser reativados pelas páginas da Web do Documento Security.

### Exibindo o histórico de auditoria de arquivos {#viewing-the-file-audit-history}

O Documento Security pode salvar o histórico de auditoria de arquivos protegidos por política para que você possa auditar as ações que os usuários executam em seus arquivos.

Os eventos auditados para arquivos do Word, Excel e PowerPoint incluem:

**Proteger uma nova** DocumentPolicy aplicada a um arquivo

**Visualização** DocumentFile aberta

**Fechar** DocumentFile fechado

**Revogar privilégios** do DocumentAccess removidos do arquivo

**Cancelar revogação dos privilégios** DocumentAccess retornados ao arquivo

**Modificar** DocumentFile alterado e salvo localmente

**Imprimir arquivo de alta** resolução impresso

**Alterar a proteção** HandlerPolicy removida do ficheiro

**Alternar política no** documentoNova política aplicada ao arquivo das páginas da Web do Documento Security

### Visualização do histórico de auditoria de um arquivo {#view-the-audit-history-for-a-file}

No Documento Security Extension for Microsoft Office 2010 e 2013, na guia **Documento Security**, selecione **Histórico de auditoria**.

As páginas da Web Segurança do Documento abrem a página Eventos, que exibe eventos auditados para o arquivo atual.

### Recursos restritos do Microsoft Office {#microsoft-office-restricted-features}

Para proteger sua propriedade intelectual, alguns recursos do Microsoft Office ficam indisponíveis quando um arquivo protegido por política é aberto. A lista de recursos indisponíveis depende das permissões concedidas ao usuário atual. Alguns recursos estão indisponíveis somente para um arquivo protegido, e outros estão indisponíveis para todos os arquivos quando você está em uma sessão protegida. Geralmente, você está em uma sessão protegida a partir do momento em que abre um arquivo protegido por política até que feche o aplicativo ou a sessão expire.

A maioria das políticas concede permissões completas ao editor do arquivo. Outros usuários podem notar restrições adicionais de recursos.

Se um comando não estiver disponível, o nome do comando no menu e o botão da barra de ferramentas relacionado ficam esmaecidos.

>[!NOTE]
Aplicar uma política a um arquivo que contenha um link para um arquivo incorporado não aplica a política ao arquivo vinculado. O Documento Security for Microsoft Office não estende a proteção a arquivos vinculados.

* Arquivos do Word, Excel e PowerPoint protegidos por política estão impedidos de abrir em uma janela do navegador Internet Explorer.
* Os usuários aos quais foi concedida somente a permissão Alterar não podem copiar o conteúdo para um arquivo de outro aplicativo usando a Área de transferência do Windows. Os usuários podem copiar o conteúdo para arquivos ativando a opção Área de transferência do Microsoft Office.
* Abrir um arquivo protegido por política no Microsoft Office torna a tecla Print Screen indisponível até que você feche o aplicativo ou a sessão expire.
* O Documento Security for Microsoft Office não suporta Distributed Authoring and Versioning (WebDAV) baseado na Web. Na maioria dos casos, não é possível abrir um arquivo protegido por política a partir de uma pasta WebDAV. Se você puder abrir um arquivo protegido por política, não terá permissões para salvar, imprimir, alterar ou copiar do arquivo.

A segurança geral que se aplica aos arquivos protegidos por política inclui as seguintes restrições:

Muitos recursos comuns podem ser restritos no Word, Excel e PowerPoint durante uma sessão protegida.

Se um arquivo protegido por política que não permite que o usuário faça alterações for aberto, os comandos que alteram o arquivo de alguma forma não estarão disponíveis. Somente os comandos que abrem ou criam novos documentos e alteram as preferências do aplicativo estão disponíveis.

#### Limitações do Word 2010 e do Word 2013 {#word-2010-and-word-2013-restrictions}

A abertura de um arquivo protegido por política no Word torna indisponível salvar as informações de recuperação automática de arquivo até que você feche e reinicie o Word. Além disso, os recursos listados abaixo são limitados nas situações descritas:

**Arquivo > Novo > Novo com base em** existenteDisponível, mas os arquivos criados usando esse comando enquanto qualquer arquivo protegido por política estiver aberto não poderão ser salvos. O conteúdo no novo arquivo não pode ser copiado para outro arquivo.

**Arquivo >** SalvarRestrito pela permissão Alterar.

**Opções Arquivo > Salvar** como tudo restritas pela permissão Alterar.

**Arquivo >** ImprimirTodas as opções restritas pela permissão Imprimir. Indisponível, a menos que a política permita a impressão em alta resolução.

**Arquivo > Salvar e** enviarTodas as opções indisponíveis durante uma sessão protegida.

**Arquivo > Informações > Documento Protect > Criptografar com senha, Adicionar assinatura digital, Marcar como final, Restringir permissão por** pessoas indisponíveis durante uma sessão protegida.

**Arquivo >** Fluxos de trabalhoIndisponível durante uma sessão protegida.

***observação **: A capacidade de start de um fluxo de trabalho das versões 2010 do sistema Microsoft Office do Word, Excel e PowerPoint está disponível somente no Office Professional Plus 2010, Office Enterprise 2010 e Office Ultimate 2010, bem como nas versões autônomas desses programas do Office 2010.*

**Postagem do blog >** PublicarIndisponível durante uma sessão protegida.

**Arquivo > Servidor >** Menu Tarefa do Servidor de ArquivosIndisponível durante uma sessão protegida.

**Home > Área de transferência >** CopiarRestrito pela permissão Copiar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado em nenhum outro arquivo ou na Área de transferência do Office. O conteúdo pode ser copiado dentro do arquivo protegido se o usuário tiver a permissão Alterar.

**Home > Área de transferência >** ColarLimitado pela permissão Alterar.

**Home > Área de transferência > Colar** especialLimitado pela permissão Alterar.

**Inserir > Texto >** ObjetoIndisponível durante uma sessão protegida. Arquivos protegidos por política não podem ser inseridos a qualquer momento.

**** CorreçõesA maioria das opções nesta guia não estão disponíveis durante uma sessão protegida.

**Revisar > Revisão >** PesquisaRestrito pela permissão Copiar. Indisponível se copiar não for permitido.

**Revisar > Revisão >** Dicionário de sinônimosRestrito pela permissão Copiar. Indisponível se copiar não for permitido.

**Revisar > Idioma > Traduzir > Traduzir** documentoEnabled com a permissão Copiar.

**Revisar > Idioma > Traduzir > Traduzir** texto selecionadoAtivado com a permissão Copiar.

**Revisar > Idioma > Traduzir > Minitradutor** ativado com a permissão Copiar.

**Revisar > Comparar >** CompararNão disponível durante uma sessão protegida. Arquivos protegidos por política não podem ser comparados a qualquer momento.

**Revisar > Protect > Bloquear** autoresIndisponível durante uma sessão protegida.

**Revisar > Protect > Restringir** ediçãoIndisponível durante uma sessão protegida.

**Visualização >** MacrosAlgumas macros são restritas pela permissão Copiar e ficam indisponíveis, a menos que copiar seja permitido.

**SuplementosNão é possível adicionar ou remover** suplementos durante uma sessão protegida.

**Colaboração** onlineIndisponível durante uma sessão protegida.

**Principais e** subdocumentosOs subdocumentos são regidos pela política de documentos principais quando abertos dentro do documento principal. Se abertos separadamente, os subdocumentos não poderão ser impressos, copiados ou modificados.

**** ResumirIndisponível durante uma sessão protegida.

**Quadros (e todos os comandos relacionados)** Indisponíveis durante uma sessão protegida.

**Painel** do documentoIndisponível durante uma sessão protegida.

**Desenvolvedor >** Modelo de DocumentoIndisponível durante uma sessão protegida. Para acessar esse comando, selecione Arquivo > Opções > Personalizar > Guia Desenvolvedor > Modelos > Modelo de Documento.

**Contorno > Documento Principal > Criar subdocumento, Inserir** subdocumentoNão disponível durante uma sessão protegida.

#### Limitações do Excel 2010 e Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Os recursos listados abaixo são limitados nas situações descritas:

**Arquivo > Novo > Novo com base em** existente disponível, mas os arquivos criados usando esse comando durante uma sessão protegida não podem ser salvos. O conteúdo no novo arquivo não pode ser copiado para outro arquivo.

**Arquivo > Salvar, Salvar** como Restrito pela permissão Alterar.

**Arquivo > Salvar como >** PDFUndisponível durante uma sessão protegida.

**Arquivo >** ImprimirRestrito pela permissão Imprimir. Indisponível, a menos que a política permita a impressão em alta resolução.

**Arquivo > Informações > Protect** DocumentUnavailable durante uma sessão protegida.

**Arquivo > Informações > Protect** WorkbookIndisponível durante uma sessão protegida.

**Arquivo > Salvar e** Enviar indisponível durante uma sessão protegida.

**Arquivo > Opções > SuplementosNão pode ser adicionado ou removido** durante uma sessão protegida.

**Arquivo >** Fluxos de trabalhoIndisponível durante uma sessão protegida.

***observação **: A capacidade de start de um fluxo de trabalho das versões 2010 do sistema Microsoft Office do Word, Excel e PowerPoint está disponível somente no Office Professional Plus 2010, Office Enterprise 2010 e Office Ultimate 2010, bem como nas versões autônomas desses programas do Office 2010.*

**Arquivo > Servidor >** Menu Tarefa do Servidor de ArquivosIndisponível durante uma sessão protegida.

**Home > Área de transferência >** CopiarRestrito pela permissão Copiar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado em nenhum outro arquivo ou na Área de transferência do Microsoft Office. O conteúdo pode ser copiado dentro do arquivo protegido se o usuário tiver a permissão Alterar.

**Home > Área de transferência >** ColarLimitado pela permissão Alterar.

**Home > Área de transferência > Colar** especialLimitado pela permissão Alterar.

**Início > Células > Formato > Mover ou Copiar** planilhaIndisponível durante uma sessão protegida.

**Início > Células > Inserir > Inserir** planilhaIndisponível durante uma sessão protegida.

**Início > Células > Excluir > Excluir** planilhaIndisponível durante uma sessão protegida.

**Home > Edição > Preencher > Entre** planilhasLimitado pela permissão Alterar.

**Inserir > Tabelas >** TabelaLimitada pela permissão Alterar.

**Não é possível selecionar Inserir > Tabelas > Arquivos protegidos por** tabela dinâmicaArquivos protegidos por política no Assistente de criação.

**Inserir > Texto >** ObjetoIndisponível durante uma sessão protegida. Arquivos protegidos por política não podem ser inseridos a qualquer momento.

**Inserir > Texto > Cabeçalho e** rodapéLimitado pela permissão Alterar. Indisponível para um documento protegido por política.

**Não é possível importar dados > Obter** dados externos de arquivos protegidos por política.

**Dados > Contorno >** SubtotaisLimitado pela permissão Alterar.

**Dados > Ferramentas de dados >** Validação de dadosLimitado pela permissão Alterar.

**Revisar > Revisão >** PesquisaRestrito pela permissão Copiar.

**Revisar > Revisão >** Dicionário de sinônimosRestrito pela permissão Copiar.

**Revisar > Idioma >** TraduzirRestrito pela permissão Copiar.

**Revisar > Alterações > Protect** SheetUnavailable durante uma sessão protegida.

**Revisar > Alterações >** Pasta de trabalho do Protect Indisponível durante uma sessão protegida.

**Revisar > Alterações > Compartilhar** pasta de trabalhoIndisponível durante uma sessão protegida.

**Revisar > Alterações > Protect e compartilhar** pasta de trabalhoIndisponível durante uma sessão protegida.

**Revisar > Alterações > Permitir que os usuários editem** intervalos indisponíveis durante uma sessão protegida.

**Revisar > Alterações > Controlar alterações > Realçar** alteraçõesNão disponível para um arquivo protegido por política que contém uma marca d&#39;água dinâmica.

**Visualização >** MacrosLimitado pela permissão Alterar.

**Visualização > Salvar** WorkspaceCommand não funciona.

**Desenvolvedor > XML >** Pacotes de expansãoAlgumas macros são restritas pela permissão Copiar e ficam indisponíveis, a menos que copiar seja permitido.

**Fórmulas > Auditoria de fórmulas >** Verificação de errosRestrito pela permissão Alterar. Indisponível, a menos que a alteração seja permitida.

**Colaboração** onlineIndisponível durante uma sessão protegida.

**Salvar** informações de recuperação automática indisponíveis durante uma sessão protegida.

***Observação **: Se você tentar alterar uma célula em um arquivo protegido por política para o qual você não tem permissão para fazer alterações, o Excel exibirá uma mensagem de aviso incorreta indicando que você deve remover a proteção do arquivo usando o comando Desproteger planilha. O uso do comando Desproteger planilha não remove a proteção por política do arquivo.*

#### Restrições do PowerPoint 2010 e PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Os recursos listados abaixo são limitados nas situações descritas:

**Arquivo > Novo > Novo com base em** existente disponível, mas os arquivos criados usando esse comando durante uma sessão protegida não podem ser salvos. O conteúdo no novo arquivo não pode ser copiado para outro arquivo.

**Arquivo >** SalvarRestrito pela permissão Alterar.

**Opções Arquivo > Salvar** como tudo restritas pela permissão Alterar.

**Arquivo >** ImprimirTodas as opções restritas pela permissão Imprimir. Indisponível, a menos que a política permita a impressão em alta resolução.

**Arquivo > Salvar e** Enviar indisponível durante uma sessão protegida.

**Arquivo > Informações > Apresentação do Protect > Criptografar com senha, Adicionar uma assinatura digital, Marcar como final, Restringir permissão por** pessoas indisponíveis durante uma sessão protegida.

**Arquivo > Opções do PowerPoint > Salvar** informações de recuperação automática indisponíveis durante uma sessão protegida.

**Arquivo > Servidor >** Menu Tarefa do Servidor de ArquivosIndisponível durante uma sessão protegida.

**Home > Área de transferência >** CopiarRestrito pela permissão Copiar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado dentro do documento, em qualquer outro arquivo ou na Área de transferência do Office. O conteúdo pode ser copiado dentro do arquivo protegido se o usuário tiver a permissão Alterar.

**Home > Área de transferência >** ColarLimitado pela permissão Alterar. Se copiar não for permitido, o conteúdo copiado não poderá ser colado dentro do documento.

**Home > Área de transferência > Colar** especialLimitado pela permissão Alterar.

**Início > Slides > Novos slides > Slides do Contorno, Reutilizar** slidesIndisponível durante uma sessão protegida.

**Inserir > Texto >** ObjetoIndisponível durante uma sessão protegida. Arquivos protegidos por política não podem ser inseridos a qualquer momento.

**Design > Plano de fundo > Estilos de plano de fundo, Ocultar gráficos de plano de fundo, Formatar** plano de fundoIndisponível para um arquivo protegido por política que contém uma marca d&#39;água dinâmica.

**Apresentação de slides > Configuração > Gravar** apresentação de slides Restrito por permissão de alteração.

**Revisar > Revisão >** Dicionário de sinônimosRestrito pela permissão Copiar.

**Revisar > Idioma >** TraduzirRestrito pela permissão Copiar.

**Revisar > Idioma > Traduzir > Minitradutor** ativado com a permissão Copiar.

**Visualização > Visualizações de apresentação >** Apresentação de slides restrita pela permissão Alterar. Se as alterações não forem permitidas, as apresentações de slides não poderão ser exibidas se o arquivo tiver sido modificado.

**Visualização >** MacrosAlgumas macros são restritas pela permissão Copiar e ficam indisponíveis, a menos que copiar seja permitido.

**SuplementosNão é possível adicionar ou remover** suplementos durante uma sessão protegida.

**Colaboração** onlineIndisponível durante uma sessão protegida.

## Usar provedores de autenticação de terceiros {#use-third-party-authentication-providers}

Você pode usar provedores de autenticação de terceiros com o AEM Forms Documento Security. Esses provedores de autenticação ajudam você a adicionar uma camada de acesso adicional aos documentos protegidos. O AEM Forms Documento Security suporta os seguintes workflows de autenticação estendida:

* Autenticação estendida usando o URL AEM Forms padrão
* Autenticação estendida usando um URL personalizado
* Fluxo de trabalho padrão de autenticação estendida com provedores de identidade de terceiros configurados no AEM Forms no servidor JEE
* Fluxo de trabalho personalizado de autenticação estendida com provedores de identidade de terceiros configurado no AEM Forms no servidor JEE
* Autenticação estendida usando página personalizada para listar Autenticações SAML

Para obter etapas detalhadas para configurar workflows de autenticação estendida, consulte o artigo [Cenários de Autenticação Estendida](http://blogs.adobe.com/livecycle/2011/12/extended-authentication-scenarios.html)

## Glossário {#glossary}

Para obter informações sobre formulários de LiveCycle e AEM na terminologia JEE, consulte [Glossário](http://www.adobe.com/go/learn_aemforms_designer_65).
