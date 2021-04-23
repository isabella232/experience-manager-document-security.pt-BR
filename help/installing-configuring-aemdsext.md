---
title: Instalação e configuração do AEM Document Security Extension for Microsoft Office
description: Este documento orienta você na instalação e configuração do Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
translation-type: ht
source-git-commit: a15d49cdd21ccb8e6ec6c770a92bf16cb24ffaa1
workflow-type: ht
source-wordcount: '2796'
ht-degree: 100%

---

# Instalação e configuração do AEM Document Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Este documento orienta você na instalação e configuração do Adobe Experience Manager Document Security Extension for Microsoft Office.

Este documento inclui informações sobre as seguintes tarefas:

* Instalação do Document Security Extension for Microsoft Office
* Pré-configuração do instalador para apontar para o LiveCycle Rights Management ES2 ou posterior, ou para o complemento Segurança de documentos para o AEM 6.0 Forms ou posterior.
* Configuração da aplicação automática da política padrão

## Antes de instalar {#before-you-install}

Antes de instalar o Document Security Extension for Microsoft Office, verifique se:

* Você leu as [Notas de versão](document-security-extension-release-notes.md).
* O Microsoft Office está ativado. A caixa de diálogo de ativação não é exibida ao abrir aplicativos do Microsoft Office.
* Os pacotes de serviços mais recentes do Microsoft Windows e do Microsoft Office estão instalados.
* Se você estiver instalando o Document Security for Microsoft Office para um idioma não compatível, abra o aplicativo do Office pelo menos uma vez.

>[!NOTE]
>
>Não instale o software em uma pasta cujo nome contenha caracteres de byte duplo. Se você fizer isso, o menu do AEM Document Security não será exibido no Microsoft Office.

>[!NOTE]
>
>A instalação de uma versão de 32 bits do Document Security Extension em um sistema operacional de 64 bits é suportada, mas o oposto não é suportado. Não é possível instalar a versão de 64 bits do Document Security Extension for Microsoft Office em um sistema operacional de 32 bits.

### Desative o McAfee VirusScan {#disable-mcafee-virusscan}

Para garantir que os aplicativos do Office sejam inicializados sem problemas em computadores que contenham o Document Security Extension instalado e o McAfee VirusScan com o On-Access Scan ativado, desative a opção Proteção de sobrecarga de buffer, no console do McAfee VirusScan.

### Desinstale plug-ins de terceiros {#uninstall-third-party-plug-ins}

O AEM Document Security Extension for Microsoft Office não é compatível com plug-ins de terceiros para aplicativos do Microsoft Office. Como essa extensão entra em conflito com plug-ins de terceiros, desinstale todos os plug-ins para o Microsoft Office que não sejam da Adobe antes de instalar o Document Security for Microsoft Office. A Adobe não fornece suporte para o Document Security para aplicativos do Microsoft Office com plug-ins de terceiros instalados.

## Requisitos do sistema {#system-requirements}

### Cliente do Document Security Extension {#document-security-extension-client}

Verifique as seguintes configurações mínimas nas quais você deseja instalar o Document Security Extension:

* Versões de 32 ou 64 bits do Microsoft Windows 7 ou Windows 10 em inglês, francês, alemão, japonês, italiano, espanhol, português brasileiro, coreano, chinês simplificado ou chinês tradicional.
   **Observação:** o *Document Security Extension for Microsoft Office também deve funcionar em dispositivos Microsoft Surface.*

* Versões de 32 bits ou 64 bits do Microsoft Office 2013, 2016, 2019 e aplicativos de desktop do Microsoft Office instalados como parte do Office 365 em inglês, francês, alemão, japonês, italiano, espanhol, português brasileiro, coreano, chinês simplificado ou chinês tradicional.

   **Observação**: o *AEM Document Security Extension for Microsoft Office não oferece suporte a plug-ins de terceiros para aplicativos do Microsoft Office. Como essa extensão pode entrar em conflito com plug-ins de terceiros, todos os plug-ins que não sejam da Adobe para aplicativos do Microsoft Office devem ser desinstalados antes da instalação do Document Security Extension for Microsoft Office. A Adobe não fornece suporte para o Document Security Extension para aplicativos do Microsoft Office com plug-ins de terceiros instalados.*

* Processador de 1,3 GHz ou superior
* 2 GB de RAM
* 100 MB de espaço disponível em disco rígido

### Segurança de documentos {#document-security}

Para usar o Document Security Extension, certifique-se de que é possível se conectar ao Adobe LiveCycle Rights Management ES2 e posterior ou ao complemento Segurança de documentos para o AEM 6.0 Forms ou posterior.

## Instalação do Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

Você pode baixar o instalador na [página de download](download-installer.md). Não é possível personalizar o arquivo executável do instalador diretamente, mas ele pode ser instalado interativamente ou no modo silencioso. Para instalar o software, faça logon no Windows como administrador.

Instaladores separados estão disponíveis para versões de 32 bits e 64 bits do Microsoft Office. Para a versão de 32 bits do Microsoft Office, baixe o arquivo DocumentSecurityExtensionforMicrosoftOffice.exe. Para a versão de 64 bits do Microsoft Office, baixe o arquivo DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>Este documento usa o arquivo do instalador de 32 bits (DocumentSecurityExtensionforMicrosoftOffice.exe) para explicar vários comandos e opções. Se você estiver usando a versão de 64 bits do Microsoft Office, use o arquivo do instalador de 64 bits (DocumentSecurityExtensionforMicrosoftOffice64.exe) para executar as operações listadas neste documento.

### Instalação no modo silencioso {#install-in-silent-mode}

Use um utilitário de extração de arquivos, como o WinZip, para extrair `DocumentSecurityExtensionforMicrosoftOffice.exe` do arquivo do instalador. Abra o prompt de comando, vá para a pasta que contém o arquivo de configuração e digite o seguinte texto:

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

O instalador também está disponível como um arquivo MSI, que pode ser usado para personalização.

### Instalação de um arquivo MSI no modo silencioso {#install-an-msi-file-in-silent-mode}

1. Use um utilitário de extração de arquivos, como o WinZip, para extrair o arquivo `DocumentSecurityExtensionforMicrosoftOffice.msi` do arquivo ZIP.

1. Abra o prompt de comando, vá para a pasta que contém o arquivo MSI e digite o seguinte texto:

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Pré-configuração do instalador para conexão com o Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

Você pode pré-configurar o instalador do Document Security Extension for Microsoft Office para apontar para um servidor do LiveCycle ou do AEM para que os usuários que instalarem o Document Security Extension for Microsoft Office possam usar os recursos sem configurar uma conexão. Dessa forma, os usuários podem abrir documentos protegidos sem a necessidade de configuração. No entanto, eles não poderão proteger novos documentos até que configurem o cliente para usar um determinado servidor.

As etapas a seguir descrevem como criar e configurar um arquivo MSI. Este arquivo MSI contém os valores de registro necessários para pré-configurar o instalador do Document Security Extension for Microsoft Office para o servidor do LiveCycle ou do AEM instalado em sua empresa.

### Pré-requisitos para personalizar o instalador {#prerequisites-for-customizing-the-installer}

Use o editor de banco de dados Orca para personalizar o instalador. As etapas a seguir descrevem como criar um arquivo MSI personalizado modificando uma cópia do arquivo de instalação MSI usando o editor de banco de dados Orca. O Orca está disponível como parte do Windows SDK para Windows Server 2008 e do .NET Framework 3.5. Para obter mais informações sobre como editar arquivos do Microsoft Windows® Installer usando o Orca, consulte [Suporte da Microsoft](http://support.microsoft.com/kb/255905/EN-US/).

>[!NOTE]
>
>É recomendável fazer um backup completo de todos os arquivos do instalador antes de criar o arquivo MSI personalizado.

#### Instalar o Orca {#install-orca}

1. Baixe o Windows SDK para Windows Server 2008 e o .NET Framework 3.5 do [Centro de downloads da Microsoft](http://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=11310).
1. Clique duas vezes no arquivo Orca.msi na pasta \Microsoft SDK\bin.

   Você também precisa da variante MSI do arquivo instalador. Entre em contato com o suporte da Adobe para receber a versão mais recente do instalador MSI.

   >[!NOTE]
   >
   >Sempre feche o arquivo DocumentSecurityExtensionforMicrosoftOffice.msi antes de executar o instalador. Não é possível executar o instalador se o Orca estiver usando o arquivo MSI.

### Criação e configuração do arquivo MSI {#create-and-configure-the-msi-file}

1. Clique em **[!UICONTROL Iniciar > Programas > Orca]**.

1. Clique em **[!UICONTROL Arquivo > Abrir]** e navegue até o arquivo `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Selecione Propriedade na lista de tabelas (no lado esquerdo).

1. Edite os seguintes valores de nome de chave, conforme aplicável à instalação do Rights Management ou do Document Security em sua empresa.

<table>
 <tbody>
  <tr>
   <td><p><strong>N</strong><strong>ome</strong><strong>da chave</strong></p> </td>
   <td><p><strong>Descrição</strong></p> </td>
   <td><p><strong>V</strong><strong>alor</strong><strong>padrão da chave</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>Nome de exibição.</p> </td>
   <td><p>Servidor padrão</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>URL do servidor do host.</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. Selecione Registro na lista de tabelas (no lado esquerdo).

1. Edite o seguinte valor de nome de chave.

   | **Nome da chave** | **Descrição** | **Valor padrão da chave** |
   |---|---|---|
   | `IsDefault` | O servidor APS padrão. | Servidor padrão |

1. Salve o arquivo modificado no mesmo diretório que contém o instalador MSI original.

   >[!NOTE]
   >
   >Uma prática comum é usar o mesmo nome de arquivo MSI original (por exemplo, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Configuração da aplicação automática de uma política padrão {#configuring-automatic-application-of-a-default-policy}

Como parte da configuração, você pode configurar a aplicação automática de uma política padrão para que o Document Security Extension for Microsoft Office proteja todos os documentos salvos.

É possível especificar uma das seguintes opções:

* Proteger todos os documentos com uma política padrão.
* Permitir que os usuários salvem opcionalmente um arquivo em um formato desprotegido quando não puderem se conectar ao servidor. Esta flexibilidade permite que você considere casos em que os usuários estão criando documentos enquanto estão desconectados da rede (por exemplo, enquanto estiverem em um avião).

Depois de ativar o recurso de aplicação automática de política, o documento é protegido com a política padrão nos seguintes casos:

* O usuário edita e salva um documento recém-criado
* O usuário edita e salva um documento desprotegido
* O usuário abre um aplicativo que abre com um documento padrão, edita e salva o documento

### Configuração do recurso de aplicação automática de política no arquivo MSI {#configure-the-auto-apply-policy-feature-in-the-msi-file}

Antes de começar, pré-configure o instalador para apontar para o seu servidor do LiveCycle ou do AEM Forms, conforme descrito anteriormente neste artigo.

1. Clique em **[!UICONTROL Iniciar > Programas > Orca]**.

1. Clique em **[!UICONTROL Arquivo > Abrir]** e navegue até o arquivo `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Selecione Propriedade na lista de tabelas (no lado esquerdo).

1. Edite os seguintes valores de nome de chave, conforme aplicável à instalação do Rights Management ou do Document Security em sua empresa.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nome da chave</strong></p> </td>
   <td><p><strong>Descrição</strong></p> </td>
   <td><p><strong>V</strong><strong>alor</strong><strong>padrão da chave</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>Ative ou desative o recurso de aplicação automática de política.</p> <p><code>1</code>: Ativar</p> <p>0: Desativar</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>O GUID da política a ser usado quando novos documentos forem salvos. Aplica-se ao recurso de aplicação automática de política.</p> </td>
   <td><p>ID de política hexadecimal conforme visível no servidor RM</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>URL do servidor.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>Número da porta do servidor.</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>Determina se os documentos podem ser criados sem a proteção de Segurança de documentos, se o cliente não conseguir entrar em contato com o servidor para proteger o documento na primeira vez que for salvo.</p> <p>1: Permitir salvamentos desprotegidos </p> <p>0: Impedir a criação de novos documentos quando o cliente não puder entrar em contato com o servidor para salvar o documento.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>A opção `AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` é útil quando você deseja lembrar os clientes de proteger todos os documentos sem forçá-los a fazê-lo. Também é útil quando você sabe que os usuários criam documentos enquanto estão desconectados da rede. Você não deseja impedir que eles criem e salvem documentos.

1. Salve o arquivo modificado no mesmo diretório que contém o arquivo MSI original.

   >[!NOTE]
   >
   >Uma prática comum é usar o mesmo nome de arquivo MSI original (por exemplo, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Habilitação de proteção automática de novos documentos {#enabling-automatic-protection-of-new-documents}

O administrador pode habilitar a capacidade de proteger automaticamente qualquer documento salvo por um usuário. O administrador configura o recurso de Aplicação automática de política no programa de instalação do Document Security Extension for Microsoft Office.

Se a Aplicação automática de política estiver ativada, todos os documentos salvos pelo usuário serão protegidos com a política padrão. Esta ação se aplica nas seguintes situações:

* Quando um usuário cria um novo documento, o edita e o salva.
* Quando um usuário abre um documento desprotegido, o edita e o salva.

Para obter informações sobre como configurar a Aplicação automática de política, consulte [Configurar uma aplicação automática de política padrão](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p).

## Habilitar a interface sem faixa de opções {#enable-ribbon-less-user-interface}

Você pode ativar/desativar a interface sem faixa de opções modificando as configurações no Registro do Windows. Execute as seguintes etapas para atualizar o Registro e ativar a interface sem faixa de opções:

1. Faça backup do Registro do Windows antes de fazer alterações. Para obter instruções detalhadas, consulte [Como modificar o Registro do Windows](https://support.microsoft.com/pt-BR/kb/136393).
1. No Editor de Registro, navegue até HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 ou HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Crie um novo valor Dword (32 bits) chamado **HidePluginUI**.

1. Defina o valor da propriedade **HidePluginUI** como 1 para ativar a interface sem faixa de opções.

1. Feche o Editor de Registro.

## Habilitação de marca d&#39;água para impressão no Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}

Você pode alterar as configurações de registro do Windows para fazer com que a marca d&#39;água dinâmica coexista com os cabeçalhos e rodapés existentes. As configurações do Registro disponibilizam a marca d&#39;água somente durante a impressão. Execute as seguintes etapas para atualizar o Registro e ativar as marcas d&#39;água durante a impressão:

1. Faça backup do Registro do Windows antes de fazer alterações. Para obter instruções detalhadas, consulte [Como modificar o Registro do Windows](https://support.microsoft.com/pt-BR/kb/136393).
1. No Editor de Registro, navegue até HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 ou HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Crie uma nova chave de Registro **WatermarkMode**.
1. Na chave de registro WatermarkMode, crie um DWORD **WatermarkMode** e defina o valor de DWORD **WatermarkMode** para **1**.

1. Feche o editor de Registro.

>[!NOTE]
>
>No Windows Explorer, você pode usar o menu Arquivo ou o menu de contexto para criar um Documento do Microsoft Excel. Para os documentos criados com métodos indicados, a data de impressão não pode ser recuperada ou alterada. É uma limitação do Microsoft Excel. As marcas d&#39;água da Segurança de documentos do AEM dependem da data de impressão do documento. Assim, para esses documentos, a marca d&#39;água é revertida para uma data anterior. Além disso, os cabeçalhos e rodapés também não são retidos.

## Inclusão de uma página de capa personalizada a um documento {#coverpage}

Um usuário pode tentar abrir o documento protegido em um computador que não tenha um plug-in AEM Document Security for Microsoft Office instalado. Esses computadores não podem abrir o documento. Mas é possível exibir uma página de capa contendo instruções para baixar o plug-in do AEM Document Security for Microsoft Office e outras informações.

### Antes de configurar uma página de capa {#before-you-configure-a-cover-page}

* Faça backup do arquivo CommonResources.dll. O caminho padrão é:

   * **(Para Office de 32 bits em computador de 32 bits)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(Para Office de 32 bits em computador de 64 bits)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(Para Office de 64 bits em computador de 64 bits)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Verifique se o Microsoft Visual Studio 2008 ou posterior está instalado. Você também pode usar qualquer outro utilitário para editar os arquivos DLL.
* Extraia o arquivo template.zip. O arquivo contém modelos .xlsx, .docx e .pptx para a página de capa. Use apenas os modelos fornecidos para os tipos de arquivo .xlsx, .docx e .pptx. É possível criar seus próprios modelos para outros tipos de arquivos. Personalize modelos para incluir mensagens e instruções personalizadas. O template.zip está disponível em:

[Obter arquivo](assets/templates.zip)

### Estrutura do arquivo CommonResources.dll {#structure-of-the-commonresources-dll-file}

O arquivo CommonResources.dll contém informações sobre os modelos de recursos. Ele contém dois identificadores de nome: TEMPLATE_FILE e RT_MANIFEST. Para ativar uma página de capa personalizada, o identificador de nome TEMPLATE_FILE é modificado. O identificador de nome TEMPLATE_FILE tem seis recursos:

<table>
 <tbody>
  <tr>
   <td><p><strong>Recurso</strong></p> </td>
   <td><p><strong>Representa </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### Configure o modelo como uma página de capa {#configure-the-template-as-a-cover-page}

1. Abra o Microsoft Visual Studio. Pesquise e abra o arquivo CommonResources.dll para edição.

   >[!NOTE]
   >
   >Se o arquivo não aparecer na janela do Solution Explorer, abra-o novamente usando a opção Abrir com. Selecione o Editor de recursos como editor.

1. Na janela Solution Explorer, expanda o diretório TEMPLATE_FILE e exclua os recursos 101.

1. Adicione os recursos:

   1. Com um projeto selecionado no Solution Explorer, no menu Projeto, clique em Propriedades.
   1. Selecione a guia Recursos.
   1. Na barra de ferramentas do Designer de recursos, aponte para Adicionar recurso e clique na seta. Para o tipo de recurso, selecione TEMPLATE_FILE e clique em Importar.
   1. Na caixa de diálogo Adicionar arquivo existente aos recursos, navegue até o arquivo Resource.xlsx e clique em Abrir. O arquivo é adicionado ao diretório TEMPLATE_FILE.

   >[!NOTE]
   >
   >Verifique se as configurações de idioma estão corretas. Exclua o recurso com um idioma neutro.

1. Repita as etapas 2 e 3 para todos os tipos de recursos.

   >[!NOTE]
   >
   >Não exclua e adicione tipos de recursos em ordem aleatória. Depois do 101, configure o 102 e assim por diante.

### Criar pacote personalizado do arquivo CommonResources.dll com o instalador do AEM Document Security Extension for Microsoft Office {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

É possível personalizar o arquivo CommonResources.dll para incluir a adição de uma página de capa personalizada. Depois de personalizar o arquivo, você pode substituir manualmente o arquivo original pelo arquivo personalizado em todas as estações de trabalho ou escolher um método automatizado para substituir o arquivo.

Em um ambiente amplo, é difícil e tedioso substituir manualmente o `CommonResources.dll file` padrão por um arquivo personalizado `CommonResources.dll`. Use uma ferramenta de autoextração e empacotamento (por exemplo, WinZip Self-Extrator) para criar o pacote do arquivo personalizado CommonResources.dll com o instalador do AEM Document Security Extension for Microsoft Office. Posteriormente, é possível distribuir o instalador personalizado para toda a estação de trabalho. Este método reduz o tempo necessário para substituir o arquivo padrão `CommonResources.dll` por um arquivo personalizado. Ele também garante que toda a estação de trabalho tenha o arquivo CommonResources.dll necessário. A ferramenta de autoextração e empacotamento é somente um dos muitos métodos possíveis para substituir automaticamente um arquivo. Escolha qualquer método que seja adequado ao seu ambiente.

Execute as seguintes etapas para criar o pacote do arquivo personalizado `CommonResources.dll` com o instalador do AEM Document Security Extension for Microsoft Office:

1. Instale uma ferramenta de autoextração e empacotamento. Por exemplo, WinZip Self-Extrator.
1. Crie uma nova pasta. Por exemplo, YOUR_FOLDER_NAME
1. Coloque o instalador original do AEM Document Security Extension e o arquivo personalizado CommonResources.dll na pasta recém-criada.
1. Crie um arquivo de lote na pasta. Por exemplo, YOUR_FOLDER_NAME\Installer.bat
1. Abra o arquivo de lote para edição e adicione o seguinte código ao arquivo de lote:

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   Se você estiver usando qualquer outra versão do LiveCycle ou do AEM Forms no JEE, além do LiveCycle Rights Management ES4 e da versão 11.0.0, substitua o caminho da chave do registro conforme a seguir:

   * (LiveCycle Rights Management ES2 e versão 9.0): *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (Livecycle Rights Management ES3 e versão 10.0)
   * (Livecycle Rights Management ES4 e versão 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0 Forms no JEE e versões posteriores) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. No código acima, substitua todas as instâncias de YOUR_FOLDER_NAME pelo nome da pasta que você criou na etapa 2.
1. **(Para o instalador do AEM Document Security Extension for Microsoft Office somente com extensão .exe)** Substitua a seguinte linha de código:

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
com

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. Salve e feche o arquivo de lote.
1. Use uma ferramenta de autoextração e empacotamento para criar um pacote da pasta que contém o arquivo personalizado CommonResources.dll, o instalador original do AEM Document Security Extension for Microsoft Office e o arquivo de lote.

   >[!NOTE]
   >
   >Verifique se o pacote de autoextração está definido para ser executado como um administrador e
   >executar automaticamente o arquivo de lote ao concluir a extração.

Agora, o instalador de autoextração do AEM Document Security Extension for Microsoft Office criará o pacote do arquivo personalizado CommonResources.dll e estará pronto para distribuição.
