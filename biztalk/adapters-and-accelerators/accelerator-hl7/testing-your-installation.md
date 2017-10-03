---
title: "测试安装 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing installation
- installing, testing installation
ms.assetid: db27a75c-db7f-46ff-b8ef-2624ff18dcc8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a813634f2fe03d427ef5d0b14688ecca977f571
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="testing-your-installation"></a>测试安装
你可以将设置你[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]测试通过手动运行完成端到端教程或执行端到端教程程序的安装。 若要执行程序，可单击**启动教程**按钮在安装过程中或在 C:\Program Files\Microsoft BizTalk 中执行 EndToEndTutorial.exe\<版本 > HL7\SDK\End 端到端教程中的快捷键（后运行安装和配置） 的文件夹。 这两种自动操作将执行相同的安装步骤通过运行完成教程将会手动执行。 端到端教程程序执行以下任务：  
  
-   部署 MSH 和 ACK 架构  
  
-   部署版本 2.3.1 通用架构  
  
-   部署 ADT 架构  
  
-   创建 Tutorial_1WayReceive 接收端口  
  
-   创建 Tutorial_MLLPReceive 接收位置  
  
-   创建 Tutorial_BTAHL7PickUp 接收端口  
  
-   创建 Tutorial_FileReceiveLoc 接收位置  
  
-   创建 Tutorial_sendAck_ADT 发送端口  
  
-   创建 Tutorial_sendMsg_RX 发送端口  
  
-   创建 Tutorial_BTAHL7Drop 发送端口  
  
-   创建 Tutorial_MLLPSend 发送端口  
  
-   创建 Tutorial_ADTSystem 方  
  
-   创建 Tutorial_RXSystem 方  
  
-   创建 Tutorial_HISystem 方  
  
-   重新启动 BizTalk 服务  
  
 如果已执行端到端教程程序，则可以为 HL7 预定义的文件夹中删除的测试实例。 接收管道与该文件夹关联选取该消息并处理它。 根据筛选器，发送管道将文档路由到目标文件夹。 此简单的"往返"练习的基本构建基块[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 引擎，并确认你的安装。  
  
### <a name="to-test-your-installation"></a>若要测试你的安装  
  
1.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\End 端到端教程文件夹。  
  
2.  右键单击**TutorialSampleInstance.txt**文件，，然后单击**复制**。  
  
3.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7PickUp 文件夹。  
  
4.  右键单击文件夹，并依次**粘贴**。  
  
5.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7Drop 文件夹。  
  
     你可以验证你的安装是否成功，如果已处理的实例出现在**Tutorial_BTAHL7Drop**文件夹作为\< *Guid*>.txt。  
  
 继续执行下一步，[准备使用本教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)。