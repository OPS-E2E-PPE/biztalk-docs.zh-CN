---
title: "第 1 课： 部署相关的业务规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e52712730546847a821d53a5f8013fff4d553501
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-1-deploying-the-related-business-rules"></a>第 1 课： 部署相关的业务规则
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括在 A4SWIFT 软件开发工具包 (SDK) 调用业务规则引擎 (BRE) 部署实用工具的程序。 在本课程中，你可以使用此实用程序来检查程序集的已部署架构，确定所需的规则，并将必要的词汇和每个架构的策略部署。  
  
 您还可以通过使用 SWIFT 标准版本指南 (SRG) 来识别所需的规则，然后使用业务规则编辑器工具部署的词汇和策略部署规则。  
  
### <a name="to-deploy-the-related-business-rules"></a>若要部署的相关的业务规则  
  
1.  单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本 > Accelerator for SWIFT**，然后单击**BRE部署实用工具**。  
  
2.  在 BRE 部署实用工具的对话框中，单击**浏览**。  
  
3.  在.NET 全局程序集缓存对话框中，选择**SWIFTSchemas**，然后单击**确定**。  
  
    > [!NOTE]
    >  对程序集的 SWIFTSchemas 引用你以前部署。  
  
4.  单击**部署**。  
  
     根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布与 BRE 一起使用。 完成后，BRE 部署实用程序显示以下消息：  
  
     **部署已完成。有关详细信息中查看日志文件或业务规则编辑器。**  
  
5.  关闭 SWIFT BRE 部署实用工具的对话框。  
  
6.  在 Windows 资源管理器，浏览到\<*驱动器*>: \Documents and Settings\All Users\Application 数据，以确认日志文件**BREDeploymentLog.txt**出现在文件夹。  
  
    > [!NOTE]
    >  你可以打开日志文件使用文本编辑器以确认每个部署步骤。  
  
7.  重新启动的规则引擎更新服务。 通过单击来做到**启动**、 单击**运行**、 输入**services.msc**，并单击**确定**。 在**服务 （本地）**窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。  
  
 继续执行[第 2 课： 确认使用业务规则 Composer 工具部署](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)。