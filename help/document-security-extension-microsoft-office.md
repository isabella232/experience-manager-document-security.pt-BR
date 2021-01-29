---
title: Introdução ao AEM Documento Security Extension for Microsoft Office
description: Usando o documento Security Extension for Microsoft Office, você pode aplicar configurações de confidencialidade predefinidas a seus arquivos do Microsoft Office.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
translation-type: tm+mt
source-git-commit: 19de0b62ac493c7507581abb607b008c64f77597
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%

---


# Introdução ao AEM Documento Security Extension for Microsoft Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

O Adobe® Experience Manager Security Extension for Microsoft® Office garante que somente as pessoas autorizadas por você possam usar arquivos do Word, Excel e PowerPoint que contenham sua propriedade intelectual. Ao usar o Documento Security Extension for Microsoft Office, você pode aplicar configurações de confidencialidade predefinidas a seus arquivos.

O Documento Security Extension for Microsoft Office estende o complemento de Rights Management e Segurança de Documentos para Adobe Experience Manager Forms para proteger arquivos do Word, Excel e PowerPoint e para permitir que usuários autorizados que tenham este software instalado possam usar arquivos protegidos por política, de acordo com as configurações de confidencialidade estabelecidas na política.

## Como a Segurança do Documento protege a propriedade intelectual {#how-document-security-protects-intellectual-property}

A Segurança do documento garante que somente as pessoas autorizadas possam usar arquivos que contenham sua propriedade intelectual. Usando o Documento Security, você pode proteger arquivos usando políticas de confidencialidade. Uma *policy* é uma coleção de informações que inclui configurações de confidencialidade e uma lista de usuários autorizados. As configurações especificadas em uma política determinam como um recipient pode usar um arquivo ao qual você aplica a política. Por exemplo, você pode especificar se os recipient podem imprimir ou copiar texto ou salvar alterações.

Administradores e usuários da Segurança do documento criam políticas. Os administradores criam políticas organizacionais que estão disponíveis para todos os usuários autorizados. Os administradores ou coordenadores de definição de política também podem criar grupos de políticas chamados *conjuntos de políticas* que estão disponíveis para um subconjunto de usuários. Os usuários podem criar suas próprias políticas, que só podem usar. Administradores, coordenadores de definição de política e usuários criam políticas usando as páginas da Web do Documento Security.

Embora as políticas sejam armazenadas no Documento Security, você as aplica a arquivos por meio do Word, Excel ou PowerPoint. Quando você aplica uma política a um arquivo, as informações que o arquivo contém são protegidas pelas configurações de confidencialidade especificadas na política. Quando você distribui o arquivo protegido por política, somente os recipient autorizados pela política podem acessar o conteúdo do arquivo.

Usar uma política para proteger um arquivo dá a você controle contínuo sobre esse arquivo, mesmo depois de distribuí-lo. Você pode auditar eventos para rastrear quando e como os recipient estão usando seu arquivo, fazer alterações na política, impedir que os usuários continuem acessando o arquivo e alterar a política anexada ao arquivo.

## Como as políticas funcionam {#how-policies-work}

As políticas contêm informações sobre os usuários autorizados e as configurações de confidencialidade a serem aplicadas à propriedade intelectual. Usuários podem ser qualquer usuário reconhecido pela Segurança do Documento por meio da inclusão em uma lista vinculada do LDAP ou Ative Diretory. Os usuários também podem ser pessoas convidadas a se registrar no Documento Security ou para as quais o administrador criou uma conta.

As configurações de confidencialidade em uma política determinam como os recipient podem usar arquivos protegidos pela política. Por exemplo, as políticas especificam se os recipient podem imprimir arquivos, copiar conteúdo para outros arquivos ou salvar alterações em arquivos protegidos. As políticas também podem especificar configurações de confidencialidade diferentes para vários usuários.

Quando você aplica uma política a um arquivo, as informações que o arquivo contém são protegidas pelas configurações de confidencialidade especificadas na política. Quando você distribui o arquivo, o Documento Security autentica os recipient que tentam abrir o arquivo e autoriza o acesso de acordo com os privilégios especificados na política.

Depois que uma política é aplicada a um arquivo, as configurações de confidencialidade da política podem ser alteradas a qualquer momento, permitindo que você adicione ou remova usuários autorizados ou altere os privilégios para usuários após eles terem recebido o arquivo. A política aplicada ao arquivo pode ser alterada e o acesso ao arquivo pode ser revogado para que qualquer pessoa com uma cópia do arquivo não possa mais abri-lo.

Se a política permitir acesso offline, os recipient também poderão usar arquivos protegidos por política offline (sem uma conexão ativa com a Internet ou a rede) pelo período especificado na política.

## Como os arquivos protegidos por política funcionam {#how-policy-protected-files-work}

Para que um usuário abra e use arquivos do Word, Excel e PowerPoint protegidos por política, a política deve incluir o usuário como um recipient ou permitir acesso anônimo, e o usuário deve ter o Documento Security Extension for Microsoft Office instalado. Para fornecer um arquivo protegido por política a alguém que não tenha o Documento Security Extension for Microsoft Office, forneça uma cópia do software ou informe a alguém como baixá-lo do seu site. Se você não tiver o instalador, poderá baixá-lo da [página de download](https://www.adobe.com/products/livecycle/rightsmanagement/extension/downloads.html).

Quando um usuário tenta abrir um arquivo protegido por política, o Documento Security Extension for Microsoft Office conecta-se ao Documento Security para autenticar o usuário. Se a Segurança do Documento estiver configurada para auditar o uso do arquivo, o usuário verá uma notificação indicando que o uso do arquivo está sendo auditado. A Segurança do documento determina quais permissões de arquivo conceder ao usuário, e o usuário poderá então usar o arquivo de acordo com as configurações de política, sob estas condições:

* Para o período de validade especificado na política.
* Até que um administrador ou a pessoa que aplicou a política revogue o acesso ao arquivo ou altere a política.

   Se a pessoa que aplicou a política alterar a política ou revogar o acesso ao arquivo, as permissões do usuário para o arquivo serão alteradas ou removidas mesmo que o usuário já tenha o arquivo. Se o próprio arquivo for revogado, um URL poderá ser fornecido ao usuário para obter uma cópia atualizada.

   Os arquivos protegidos por política podem ser abertos offline (sem uma conexão com a Internet ou com a rede), se a política permitir acesso offline, durante o período de empréstimo offline especificado na política. Quando o período de empréstimo offline terminar, o usuário deverá ficar online e sincronizar com o Documento Security, que start um novo período de empréstimo.

   Se a política permitir que o arquivo seja salvo e um usuário salvar uma cópia do arquivo protegido por política, a política será automaticamente aplicada e imposta para o arquivo salvo. Eventos, como tentativas de abrir o novo arquivo, também são auditados e registrados da mesma forma que o arquivo original.

## Usar o Documento Security para proteger seus arquivos {#using-document-security-to-protect-your-files}

Você pode usar políticas para proteger seus arquivos em várias situações.

Por exemplo, um fabricante está aceitando ofertas de fornecedores que fornecerão peças para um novo produto. O fabricante deve fornecer aos licitantes informações proprietárias de que eles precisam para finalizar suas contribuições. O fabricante usa o Documento Security para proteger os arquivos com uma política que permite aos licitantes abrir os arquivos e visualização as informações. No entanto, os licitantes são impedidos de alterar, imprimir ou copiar os arquivos e qualquer pessoa que não tenha permissão é impedida de abrir os arquivos.

Depois de aceitar uma das ofertas, o fabricante atualiza a política para conceder ao licitante vencedor permissões para imprimir, copiar e salvar alterações localmente, e para remover os licitantes que não têm mais permissão para abrir os arquivos.

Ao trabalhar com o licitante bem-sucedido, os engenheiros do fabricante alteram algumas das especificações de design nos arquivos. Para publicar as novas especificações, o fabricante revoga o acesso a alguns dos arquivos e publica novas versões. Quando os engenheiros do licitante vencedor tentarem abrir o arquivo, verão uma mensagem informando que o acesso ao arquivo foi revogado. A mensagem contém um URL no qual eles podem baixar uma nova versão do arquivo.

## Informações adicionais {#additional-information}

Os recursos nesta tabela podem ajudá-lo a saber mais sobre AEM Segurança do Documento:

<table >
 <tbody>
  <tr>
   <th><p>Para obter informações sobre</p> </th>
   <th><p>Consulte</p> </th>
  </tr>
  <tr>
   <td><p>Ajuda do administrador para formulários AEM</p> </td>
   <td><p><a href="http://www.adobe.com/go/learn_aemforms_admin_65">Na página </a> Ajuda do administrador, clique no link Ajuda nas páginas de administração da Segurança do Documento, no canto superior direito de uma página.</p> </td>
  </tr>
  <tr>
   <td><p>Atualizações de patches, notas técnicas e informações adicionais sobre esta versão do produto</p> </td>
   <td><p><a href="https://helpx.adobe.com/br/marketing-cloud/contact-support.html">Suporte técnico ao Marketing Cloud</a></p> </td>
  </tr>
 </tbody>
</table>

