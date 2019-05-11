---
title: 提交消息通过接收位置和 InfoPath 窗体 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receive locations
- receive locations, messages
- messages, InfoPath forms
- InfoPath forms, messages
ms.assetid: e8676830-3fbc-423f-82f6-03e6a532075f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf95acf08084f7382e166efdace182a4464178c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377010"
---
# <a name="submitting-messages-through-receive-locations-and-infopath-forms"></a>提交消息通过接收位置和 InfoPath 窗体
接收位置接收消息提交到[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]应用程序。 您可以定义接收位置作为物理终结点配置为使用指定的传输协议接收消息。 例如，接收位置可能配置为接收文件拖放到特定的文件系统文件夹，使用文件传输。  
  
 创建接收端口，以逻辑方式分组和管理接收位置的接收位置。 对于每个接收位置指定接收管道，它会在该特定的接收位置接收消息的实际处理 （解码、 拆装、 验证等）。 A4SWIFT 绑定接收位置接收端口的逻辑分组并管理接收位置。  
  
 以将 SWIFT 消息提交到 A4SWIFT 应用程序，通过接收位置，消息必须进行拖放到已配置的接收位置，由接收管道使用 SWIFT 反汇编程序进行处理、 分析并由 SWIFT 反汇编程序、 验证和发布到 MessageBox 数据库。 消息发布到 MessageBox 数据库后，A4SWIFT 应用程序中的其他组件中检索进行其他处理 （使用订阅） 的消息。 例如，可用于发送端口最终路由。  
  
 详细了解创建和配置接收端口和接收位置，请参阅 BizTalk Server 帮助。  
  
 您还可以提交新消息通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，使用消息修复和新提交功能。 若要执行此操作，打开[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体从 MRSR 网站的文件夹中，该消息。 在中的数据填充[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体，它使用证书，请登录，然后将其提交。 消息修复和新提交业务流程处理消息。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for SWIFT 运行时](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)