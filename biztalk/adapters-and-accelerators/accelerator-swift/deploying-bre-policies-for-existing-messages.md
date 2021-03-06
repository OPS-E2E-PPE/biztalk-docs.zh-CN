---
title: 为现有消息部署 BRE 策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 585c903d-ee44-4e92-8798-febb176367e3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe4f95526883f0bc8e79ff0b0c0241aa198747f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377972"
---
# <a name="deploying-bre-policies-for-existing-messages"></a>为现有消息部署 BRE 策略
**若要部署的相关的业务规则：**  
  
1.  单击**启动**，单击**程序**，单击**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。  
  
2.  BRE 部署实用工具中单击**浏览**。  
  
3.  在.NET 全局程序集缓存对话框中，选择**SWIFT MX 架构**，然后单击**确定**。  
  
4.  单击**部署**。  
  
     根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布以用于 BRE。 完成后，BRE 部署实用工具将显示以下消息："部署已完成。 查看日志文件或业务规则编辑器的详细信息。"  
  
5.  关闭 SWIFT BRE 部署实用工具对话框。  
  
6.  在 Windows 资源管理器，浏览到*\<驱动器\>*: \Documents and Settings\All Users\Application Data 以确认日志文件 BREDeploymentLog.txt 显示文件夹中。  
  
7.  单击**启动**，单击**运行**，类型**services.msc**，然后单击**确定**。 在服务 （本地） 窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。