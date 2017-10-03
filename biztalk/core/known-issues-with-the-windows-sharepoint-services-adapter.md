---
title: "Windows SharePoint Services Adapter 的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c20eda7-643d-484c-bf5d-59ff69604cea
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09369108d5e122bb8243ac94d2748db7bc1e06f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services 适配器的已知问题
本部分包含可帮助你避免出现错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="wss-adapter-fails-to-start-a-workflow-attached-to-a-doc-librarysharepoint-list"></a>WSS 适配器无法启动附加到“文档库/Sharepoint 列表”的工作流  
 从 BizTalk 使用 WSS 适配器将文档或列表项目提交到“文档库/Sharepoint 列表”时，无法启动附加到该列表的工作流。 解决方法是将以下 XML 代码复制到 \Program Files\Microsoft BizTalk Server 20xx\Business Activity Services\BTSharePointV3AdapterWS\web.config 文件中。  以下 XML 代码必须插入内\<配置 > 元素。  
  
```  
<configSections>  
    <sectionGroup name="System.Workflow.ComponentModel.WorkflowCompiler" type="System.Workflow.ComponentModel.Compiler.WorkflowCompilerConfigurationSectionGroup, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">  
      <section name="authorizedTypes" type="System.Workflow.ComponentModel.Compiler.AuthorizedTypesSectionHandler, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
    </sectionGroup>  
  </configSections>  
  <System.Workflow.ComponentModel.WorkflowCompiler>  
    <authorizedTypes>  
      <authorizedType Assembly="System.Workflow.Activities, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Namespace="System.Workflow.*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Namespace="System.Workflow.*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System.Workflow.Runtime, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Namespace="System.Workflow.*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.Workflow" TypeName="SPWorkflowActivationProperties" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.Workflow" TypeName="SPWorkflowTaskProperties" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.Workflow" TypeName="SPWorkflowHistoryEventType" Authorized="True" />  
      <authorizedType Assembly="Microsoft.SharePoint.WorkflowActions, Version=12.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" Namespace="Microsoft.SharePoint.WorkflowActions" TypeName="*" Authorized="True" />  
    </authorizedTypes>  
  </System.Workflow.ComponentModel.WorkflowCompiler>  
  
```