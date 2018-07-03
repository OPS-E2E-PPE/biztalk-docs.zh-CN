---
title: 安装 JMS MQRFH2 组件示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bd855-512f-40a4-8038-ae9b847b1097
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f04067ef6b2e1a057edc05601059d931b7ba7f28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018598"
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a>安装 JMS MQRFH2 组件示例
若要使用此示例与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，还必须安装以下：  
  
- IBM WebSphere MQ 5.3 （带有 CSD12)，WebSphere MQ 6.x 或 WebSphere MQ 7.0  
  
- IBM"RfhUtil"JMS 测试实用程序，用于队列和检索消息  
  
  JMS MQRFH2 组件示例要求要驻留在你的 Microsoft BizTalk Server 安装文件夹和相应的架构在全局程序集缓存中驻留的 PipelineComponents 文件夹中的 JMS MQRFH2 组件。 安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]core 自动复制，并将程序集安装到正确的位置。 但是，如果需要，你可以手动执行这些任务。  
  
  **若要手动安装 JMS MQRFH2 组件和架构**  
  
1. 将程序集 Microsoft.Practices.ESB.JMS.PipelineComponents.dll 复制到 PipelineComponents 文件夹的 BizTalk Server 安装文件夹。  
  
2. 添加架构程序集使用.NET Framework 配置工具在全局程序集缓存到 Microsoft.Practices.ESB.JMS.Schemas.Property.dll 位于中的管理工具部分**启动**菜单。  
  
   本部分介绍 JMS MQRFH2 示例安装到 GlobalBank.JMS BizTalk 应用程序的过程。 在安装此示例之前，如中所述，您必须安装 ESB 工具包内核[安装 BizTalk ESB 工具包 Core](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612))。  
  
   可以从解决方案项目中安装 JMS MQRFH2 组件示例，也可以使用随附的 Windows 安装程序文件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 本节包含下列主题：  
  
-   [使用安装脚本安装 JMS MQRFH2 示例](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [JMS MQRFH2 组件示例安装的程序集和项目](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [测试 JMS MQRFH2 示例安装](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)