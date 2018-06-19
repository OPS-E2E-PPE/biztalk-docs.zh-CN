---
title: 安装 JMS MQRFH2 组件示例 |Microsoft 文档
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
ms.openlocfilehash: 7b522d986524c77a53cf5a847f749a9ce41e2c50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294245"
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a>安装 JMS MQRFH2 组件示例
若要使用此示例与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，你还必须安装以下：  
  
-   IBM WebSphere MQ 5.3 （与 CSD12)，WebSphere MQ 6.x 或 WebSphere MQ 7.0  
  
-   IBM"RfhUtil"JMS 测试实用程序以及队列检索消息  
  
 JMS MQRFH2 组件示例要求要驻留在你的 Microsoft BizTalk Server 安装文件夹以及要驻留在全局程序集缓存中的相应架构 PipelineComponents 文件夹中的 JMS MQRFH2 组件。 安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心自动复制，并将程序集安装到正确的位置。 但是，如果需要，你可以手动执行这些任务。  
  
 **若要手动安装的 JMS MQRFH2 组件和架构**  
  
1.  将程序集 Microsoft.Practices.ESB.JMS.PipelineComponents.dll 复制到你的 BizTalk Server 安装文件夹的 PipelineComponents 文件夹。  
  
2.  添加到全局程序集缓存使用.NET Framework 配置工具的 Microsoft.Practices.ESB.JMS.Schemas.Property.dll 位于的管理工具部分中的架构程序集**启动**菜单。  
  
 本部分介绍将 JMS MQRFH2 示例安装到 GlobalBank.JMS BizTalk 应用程序的过程。 在安装此示例之前，你必须安装 ESB 工具包核心中所述[安装 BizTalk ESB 工具包核心](http://go.microsoft.com/fwlink/?LinkId=187612)([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612))。  
  
 可以从解决方案项目安装 JMS MQRFH2 组件示例，也可以使用随附的 Windows Installer 文件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。 本节包含下列主题：  
  
-   [安装使用安装脚本 JMS MQRFH2 示例](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [程序集和项目安装 JMS MQRFH2 组件示例](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [测试 JMS MQRFH2 示例安装](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)