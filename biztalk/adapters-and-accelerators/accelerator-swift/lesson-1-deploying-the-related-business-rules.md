---
title: 第 1 课： 部署相关的业务规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6228f890e0f508650827f2bb2c3e52b5d29f96f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971102"
---
# <a name="lesson-1-deploying-the-related-business-rules"></a>第 1 课： 部署相关的业务规则
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括在 A4SWIFT 软件开发工具包 (SDK) 调用的业务规则引擎 (BRE) 部署实用程序的程序。 在本课程中，使用此实用程序来检查程序集的部署的架构，确定所需的规则，并部署必要的词汇和策略的每个架构。  
  
 您还可以通过使用 SWIFT 标准发布指南 (SRG) 来确定所需的规则，然后使用业务规则编辑器工具来部署词汇和策略部署规则。  
  
### <a name="to-deploy-the-related-business-rules"></a>若要部署的相关的业务规则  
  
1. 单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。  
  
2. 在 BRE 部署实用工具对话框中，单击**浏览**。  
  
3. 在.NET 全局程序集缓存对话框中，选择**swift 架构**，然后单击**确定**。  
  
   > [!NOTE]
   >  Swift 架构引用的程序集您以前部署。  
  
4. 单击**部署**。  
  
    根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布以用于 BRE。 完成后，BRE 部署实用工具将显示以下消息：  
  
    **部署已完成。有关详细信息中查看日志文件或业务规则编辑器。**  
  
5. 关闭 SWIFT BRE 部署实用工具对话框。  
  
6. 在 Windows 资源管理器，浏览到\<*驱动器*\>: \Documents and Settings\All Users\Application Data 以确认日志文件**BREDeploymentLog.txt**将出现在文件夹。  
  
   > [!NOTE]
   >  您可以打开日志文件使用文本编辑器来确认每个部署步骤。  
  
7. 重新启动规则引擎更新服务。 通过单击**启动**，再单击**运行**，输入**services.msc**，然后单击**确定**。 在中**服务 （本地）** 窗口中，右键单击**规则引擎更新服务**，然后单击**重启**。  
  
   请继续执行[第 2 课： 确认部署使用业务规则编辑器工具](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)。