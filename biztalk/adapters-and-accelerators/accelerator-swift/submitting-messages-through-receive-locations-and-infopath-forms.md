---
title: "提交通过消息接收位置和 InfoPath 窗体 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6cddeca2eb80fbeb7c9fb5742e2838a860079d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a>通过提交消息接收位置和 InfoPath 窗体
接收位置接收消息提交至[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]应用程序。 你可以定义接收位置作为物理终结点配置为接收使用指定的传输协议的消息。 例如，接收位置可能配置为拖放到特定的文件系统文件夹使用文件传输的接收文件。  
  
 你创建的逻辑分组，并管理的接收端口接收位置接收位置。 对于每个接收位置中，你将指定接收管道，在该特定接收位置接收的消息的实际处理 （解码、 反汇编、 验证和等等） 的作用。 A4SWIFT 绑定接收位置接收逻辑分组，并管理的端口接收位置。  
  
 若要提交到 A4SWIFT 应用程序接收位置通过 SWIFT 消息，消息必须是拖放到配置的接收位置、 通过使用 SWIFT 反汇编程序接收管道处理、 分析和通过 SWIFT 反汇编程序中，验证和发布到 MessageBox 数据库。 消息发布到 MessageBox 数据库之后，你 A4SWIFT 的应用程序中的其他组件以进行其他处理检索 （使用订阅） 的消息。 例如，可用于发送端口最终路由。  
  
 有关创建和配置详细信息接收端口和接收位置，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
 您还可以提交一条新消息通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，使用消息修复和新提交功能。 若要执行此操作，你可以打开[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]该消息从 MRSR 网站的文件夹中的窗体。 在中的数据填充[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体、 使用您的证书，其签名，然后提交它。 消息修复和新提交业务流程处理的消息。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)