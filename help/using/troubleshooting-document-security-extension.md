---
title: Solução de problemas do AEM Document Security Extension for Microsoft Office
description: Se você tiver problemas ao instalar, configurar ou usar o AEM Document Security Extension for Microsoft Office, siga as instruções listadas neste documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---

# Solução de problemas do AEM Document Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Solução de problemas de instalação e configuração {#troubleshootinginstallationandconfiguration}

Se tiver problemas ao instalar e configurar o AEM Document Security Extension for Microsoft Office, verifique se você seguiu cuidadosamente as instruções - antes de instalar - listadas no artigo de [instalação](installing-configuring-aemdsext.md).

Se você instalou e configurou tudo de acordo com a documentação, analise as seções a seguir para ver problemas semelhantes aos que você está enfrentando.

### Falha ao carregar o Document Security Extension para aplicativos do Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

A propriedade LoadBehavior no Registro do Windows especifica o comportamento de tempo de execução do plug-in de segurança do documento. Se a propriedade LoadBehavior estiver definida como 3, todos os plug-ins serão carregados automaticamente. Antes de instalar o Document Security Extension for Microsoft Office, verifique se o valor da propriedade LoadBehavior está definido como 3.

1. Faça backup do Registro do Windows antes de fazer alterações. Para obter instruções detalhadas, consulte [Como modificar o Registro do Windows](https://support.microsoft.com/pt-BR/kb/136393).
1. No Editor de Registro, vá para HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin ou HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Defina o valor da propriedade **LoadBehavior** como 3.

1. Feche o Editor de Registro.

Para obter informações detalhadas sobre LoadBehavior, consulte o artigo [Entradas de registro para suplementos VSTO](https://msdn.microsoft.com/pt-BR/library/bb386106.aspx#LoadBehavior).

## Solução de problemas de tarefas administrativas {#admintasks}

Esta seção discute possíveis problemas com o AEM Document Security Extension instalado.

### Os aplicativos do Microsoft Office não são inicializados sem problemas ao instalar o Document Security Extension {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Para garantir que os aplicativos do Office sejam inicializados sem problemas em computadores que contenham o Document Security Extension instalado e o McAfee VirusScan com o On-Access Scan ativado, desative a opção Proteção de sobrecarga de buffer, no console do McAfee VirusScan.
