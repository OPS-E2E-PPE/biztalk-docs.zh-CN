---
title: "部署的现有消息 BRE 策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 585c903d-ee44-4e92-8798-febb176367e3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b03f6f3319e90d4782e1e9e5fd7e2a7e2a27b527
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bre-policies-for-existing-messages"></a>将 BRE 策略部署的现有消息
**部署相关的业务规则：**  
  
1.  单击**启动**，单击**程序**，单击**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。  
  
2.  在 BRE 部署实用程序，单击**浏览**。  
  
3.  在.NET 全局程序集缓存对话框中，选择**SWIFT MX 架构**，然后单击**确定**。  
  
4.  单击**部署**。  
  
     根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布与 BRE 一起使用。 完成后，BRE 部署实用工具，则显示以下消息:"部署已完成。 查看日志文件或业务规则编辑器的详细信息。"  
  
5.  关闭 SWIFT BRE 部署实用工具的对话框。  
  
6.  在 Windows 资源管理器，浏览到*\<驱动器 >*: \Documents and Settings\All Users\Application 数据，以确认日志文件 BREDeploymentLog.txt 显示在文件夹中。  
  
7.  单击**启动**，单击**运行**，类型**services.msc**，然后单击**确定**。 在服务 （本地） 窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。