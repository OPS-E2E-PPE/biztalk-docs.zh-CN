---
title: 开发 SAP 应用程序使用 WCF 通道模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, developing applications by using
ms.assetid: 1ce70c8b-5eeb-4585-97af-b0a7b4398dac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2bce6ad43b6efce111a2801ba7a5b44e73dce1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013126"
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a>开发 SAP 应用程序使用 WCF 通道模型
可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过直接通过使用 SAP 绑定创建通道实例发送 XML 消息。  
  
 通过使用强类型化类和方法，WCF 服务模型公开了使用 WCF 通道模型的一个优点是通道模型提供更精细地控制在 SAP 系统执行的操作。 原因是什么？ WCF 通道模型直接控制在通道上发送的消息的内容。  
  
 WCF 通道模型提供了对 WCF 服务模型的另一个主要优点是对数据进行流式处理的更全面支持。 通过使用 WCF 通道模型，你可以执行：  
  
- 你的代码和适配器之间交换的所有消息流式处理的消息节点。  
  
- 消息节点值 SendIdoc 和 ReceiveIdoc 操作流式处理。  
  
  这是因为 WCF 通道模型中您可以直接控制如何提供向适配器发送的消息的消息正文和如何使用从适配器接收的消息的消息正文。  
  
  与此相反，该适配器不提供支持的 WCF 服务模型中的流式处理。 因为在 WCF 服务模型中，WCF 运行时序列化和反序列化其 XML 和托管的代码对象表示形式之间的消息，由完整的内存中副本的每个适配器与交换的消息。  
  
  本主题中的各节说明如何执行操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SAP 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [创建一个通道，使用 SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [SAP 系统的操作使用调用的 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [通过使用 WCF 通道模型接收来自 SAP 系统的入站的操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [SAP 使用 WCF 通道模型中的流式处理平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)