---
title: Solução de problemas AEM Documento Security Extension for Microsoft Office
description: Se tiver problemas ao instalar, configurar ou usar o AEM Documento Security Extension for Microsoft Office, siga as instruções listadas neste documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
translation-type: tm+mt
source-git-commit: ac26ec61f62d7a3db2429c8a9d3f68b82ba8f77a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# Solução de problemas AEM Extensão de Segurança do Documento para Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Solução de problemas de instalação e configuração {#troubleshootinginstallationandconfiguration}

Se tiver problemas ao instalar e configurar AEM Documento Security Extension for Microsoft Office, siga cuidadosamente as instruções listadas na seção - antes de instalar - do artigo [installation](installing-configuring-aemdsext.md).

Se você instalou e configurou tudo de acordo com a documentação, analise as seções a seguir em busca de problemas semelhantes aos que você está enfrentando.

### Falha ao carregar o Documento Security Extension para aplicativos do Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

A propriedade LoadBehavior no Registro do Windows especifica o comportamento de tempo de execução do plug-in de segurança do documento. Se a propriedade LoadBehavior estiver definida como 3, todos os plug-ins serão carregados automaticamente. Antes de instalar o Documento Security Extension for Microsoft Office, verifique se o valor da propriedade LoadBehavior está definido como 3.

1. Faça um backup do Registro do Windows antes de fazer alterações. Para obter instruções detalhadas, consulte [Como modificar o Registro do Windows](https://support.microsoft.com/en-us/kb/136393).
1. No Editor do Registro, navegue toHKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin ou HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Defina o valor da propriedade **LoadBehavior** como 3.

1. Feche o Editor do Registro.

Para obter informações detalhadas sobre LoadBehavior, consulte o artigo [Entradas de registro para suplementos VSTO](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior).

## Solução de problemas de tarefas administrativas {#admintasks}

Esta seção discute possíveis problemas com a sua extensão de segurança do Documento AEM instalada.

### Os aplicativos do Microsoft Office não são start sem problemas ao instalar o Documento Security Extension {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Para garantir que os aplicativos do Office sejam start sem problemas em computadores com o Documento Security Extension instalado e o McAfee VirusScan com o On-Access Scan ativado, desative a opção Proteção de estouro de buffer no console do McAfee VirusScan.
