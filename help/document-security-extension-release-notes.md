---
title: AEM Document Security for Microsoft Office - Notas de versão
description: Leia as notas de versão antes de instalar o AEM Document Security Extension 6.2 for Microsoft Office.
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
translation-type: ht
source-git-commit: 403b800eab086d131beb65a496836158778954ee
workflow-type: ht
source-wordcount: '1030'
ht-degree: 100%

---


# AEM Document Security for Microsoft Office - Notas de versão {#aem-document-security-for-microsoft-office-release-notes}

## Novidades no AEM Document Security for Microsoft Office {#whats-new-in-aem-document-security-for-microsoft-office}

* **Compatibilidade com o Office 2019**: a extensão Document Security for Microsoft Office agora é compatível com o Microsoft Office 2019. Também deve funcionar com aplicativos de desktop do Microsoft Office 2019 instalados como parte do Office 365.

>[!NOTE]
>
>O documento usa os termos Adobe Experience Manager Document Security for Microsoft Office, Adobe Experience Manager Document Security Extension for Microsoft Office e Document Security Extension for Microsoft Office de modo intercambiável.

## Instalação e configuração do AEM Document Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Esta versão do Document Security Extension for Microsoft Office é compatível com o Adobe LiveCycle Rights Management ES2 e posterior, e com o complemento Segurança de documentos do AEM Forms.

Examine as informações neste documento antes de instalar o AEM Document Security Extension for Microsoft Office. Para obter instruções detalhadas de instalação, consulte o artigo [Instalação e configuração do AEM Document Security Extension for Microsoft Office](installing-configuring-aemdsext.md).

## Problemas corrigidos {#fixed-issues}

* As cadeias de caracteres são exibidas verticalmente e as quebras de linha incorretas são adicionadas ao conteúdo. (Ref# CQ-4201054)

## Problemas conhecidos {#known-issues}

### Incompatibilidade com plug-ins de terceiros {#third-party-plug-ins-not-supported}

O AEM Document Security Extension for Microsoft Office não funciona com plug-ins de terceiros. Desinstale todos os plug-ins de terceiros do Microsoft Office antes de instalar o Document Security Extension for Microsoft Office.

### Opções de menu desativadas no Microsoft Word, Excel e PowerPoint {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

O AEM Document Security Extension for Microsoft Office usa recursos de proteção incorporados para proteger documentos, planilhas e apresentações. Ele desativa algumas opções de menu do Excel, Word e PowerPoint.

### Restrições para o Microsoft Office 2013, 2016 e 2019 {#restrictions-for-microsoft-office}

No Microsoft Office, as seguintes opções estão indisponíveis durante uma sessão protegida:

* Microsoft Office 2016 ou Microsoft Office 2019

   * Arquivo > Salvar como
   * Arquivo > Histórico
   * Arquivo > Compartilhar
   * Arquivo > Exportar
   * Arquivo > Publicar
   * Arquivo > Conta
   * Arquivo > Informações > Proteger Documento/Pasta de trabalho/Apresentação > Criptografar com senha
   * Arquivo > Informações > Proteger documento > Adicionar uma assinatura digital
   * Arquivo > Informações > Proteger documento > Marcar como final
   * Opção Compartilhar na parte superior direita

* Microsoft Office 2013

   * Arquivo > Salvar como
   * Arquivo > Compartilhar
   * Arquivo > Exportar
   * Arquivo > Conta
   * Arquivo > Informações > Proteger Documento/Pasta de trabalho/Apresentação > Criptografar com senha
   * Arquivo > Informações > Proteger documento > Adicionar uma assinatura digital
   * Arquivo > Informações > Proteger documento > Marcar como final

### Erro ao abrir um documento protegido do SharePoint Server {#opening-a-protected-document-from-sharepoint-server}

Erro ao abrir o documento protegido: se tentar abrir um documento protegido do SharePoint Server no Document Security Extension for Microsoft Office sem abrir primeiro o programa do Microsoft Office associado ao tipo de arquivo, como Microsoft Word, Microsoft Excel ou Microsoft PowerPoint, o documento pode não abrir. Uma mensagem de erro é exibida indicando que você deve instalar o plug-in aplicável. Portanto, é recomendável abrir o programa associado do Microsoft Office antes de abrir um documento protegido do SharePoint Server no Document Security Extension for Microsoft Office.

(Opcional) É recomendável limpar a pasta de cache antes de abrir um documento protegido do SharePoint Server no Document Security Extension for Microsoft Office.

Ao abrir um documento protegido do SharePoint Server, todas as permissões do documento são desativadas, independentemente da política aplicada.

### Erro ao aplicar uma política com uma marca d&#39;água dinâmica a um arquivo do Microsoft Excel 2013, Microsoft Excel 2016 e Microsoft Excel 2019 sem impressora instalada {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

Ao aplicar uma política com marca d&#39;água dinâmica a um arquivo do Microsoft Excel 2013, Microsoft Excel 2016 e Microsoft Excel 2019 em um computador sem impressora instalada, e depois salvar o arquivo, o seguinte erro é exibido: &quot;Erro interno ao aplicar a marca d&#39;água dinâmica.&quot; Esse erro também aparece ao reabrir o arquivo protegido. A marca d&#39;água não é aplicada e não é visível em Visualização > Layout da página.

### Desabilitação da Prevenção de Execução de Dados do Windows para aplicativos compatíveis do Office {#disable-windows-data-execution-prevention-for-supported-office-applications}

É recomendável desativar a configuração DEP (Prevenção de Execução de Dados) do Windows ao usar o Document Security Extension para aplicativos do Microsoft Office.

### Falta de proteção aos arquivos compartilhados do Microsoft Office usando o Document Security Extension {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

Um erro ocorre ao proteger qualquer arquivo compartilhado do Microsoft Office usando o Document Security Extension, e o arquivo compartilhado não é protegido.

### Erro ao iniciar aplicativos do Office em computadores que contenham o Document Security Extension for Microsoft Office e McAfee VirusScan {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Para garantir que os aplicativos do Office sejam inicializados sem problemas em um computador que contenha o Document Security instalado e o McAfee VirusScan com o On-Access Scan ativado, desative a opção Proteção de sobrecarga de buffer, no console do McAfee VirusScan.

### Erro na instalação do Document Security Extension for Microsoft Office em computadores com um idioma não compatível do Microsoft Office {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

Antes de instalar o Document Security Extension for Microsoft Office em um computador que tenha um aplicativo do Microsoft Office com um idioma não compatível, abra o aplicativo do Office pelo menos uma vez.

### Ativação do botão Sincronizar offline mesmo quando um usuário não tem permissões offline {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

O botão Sincronizar offline está disponível mesmo se o usuário não tiver permissões offline para o documento. No entanto, selecionar o botão não faz nada.

### Falta de suporte para versões de avaliação do Microsoft Office {#no-support-for-trial-versions-of-microsoft-office}

O Document Security Extension for Microsoft Office não suporta versões de avaliação do Microsoft Office. Antes de instalar a extensão, verifique se você instalou uma cópia licenciada do Microsoft Office e se ela está ativada.

### Erro ao abrir arquivos protegidos do Microsoft Office {#unable-to-open-a-protected-microsoft-office-files}

Se a visualização protegida do Microsoft Office estiver ativada, a extensão do Rights Management não poderá abrir arquivos protegidos do Microsoft Excel (XLS, XLSX) e do Microsoft PowerPoint (PPT) de um local remoto.

### Células com uma imagem ou uma cor de plano de fundo de um documento do Microsoft Excel aparecem na parte superior da marca d&#39;água {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Se uma célula de um documento do Microsoft Excel tiver uma imagem ou estiver preenchida com a cor do plano de fundo, e uma política de marca d&#39;água dinâmica for aplicada ao documento, a imagem ou a cor do plano de fundo preenchida na célula aparecerão na parte superior da marca d&#39;água e cobrirão a marca d&#39;água.

### Problema de usabilidade com vários certificados {#usability-issue-with-multiple-certificates}

Se houver vários certificados no computador do cliente e o usuário cancelar a caixa de diálogo de seleção de certificado, a caixa de diálogo será exibida novamente e o usuário terá de cancelar a caixa de diálogo duas vezes.

### Permissão de edição de documentos protegidos no Microsoft PowerPoint {#microsoft-powerpoint-allows-editing-protected-documents}

Ao tentar editar um documento protegido, o Microsoft PowerPoint exibe a mensagem: &quot;Você não tem permissão para modificar esse documento. Você não poderá salvar as alterações.&quot; Após fechar a mensagem, os usuários podem continuar a adicionar texto ou editar o documento. Mas as mudanças feitas nos documentos protegidos não são salvas.

O comportamento mencionado acima ocorre PowerPoint 2013, PowerPoint 2016 e PowerPoint 2019.
