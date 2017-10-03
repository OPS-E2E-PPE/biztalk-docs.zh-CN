---
title: "开发 SAP 应用程序使用 WCF 通道模型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF channel model, developing applications by using
ms.assetid: 1ce70c8b-5eeb-4585-97af-b0a7b4398dac
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13015cb042d26c946abfa3c99a4f67034b8d9708
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sap-applications-using-the-wcf-channel-model"></a>开发 SAP 应用程序使用 WCF 通道模型
你可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型来使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过直接通过使用 SAP 绑定创建的通道实例发送 XML 消息。  
  
 通过使用的强类型类和 WCF 服务模型公开的方法使用 WCF 通道模型的一个优点是通道模型提供更好地控制细化 SAP 系统执行的操作。 原因是什么？ WCF 通道模型直接控制通过通道发送的消息的内容。  
  
 WCF 通道模型提供了对 WCF 服务模型的另一个关键优势是对数据进行流式处理的更全面支持。 通过使用 WCF 通道模型，你可以执行：  
  
-   你的代码和适配器之间交换的所有消息流式都处理的消息节点。  
  
-   消息节点值 SendIdoc 和 ReceiveIdoc 操作流式处理。  
  
 这是因为在 WCF 通道模型你直接控制如何提供到适配器发送的消息的消息正文，并使用从适配器接收的消息在消息正文的方式。  
  
 与此相反，该适配器未提供对支持流式处理 WCF 服务模型中。 因为在 WCF 服务模型中，WCF 运行时序列化和反序列化其 XML 和托管的代码对象表示形式之间的消息，由与适配器交换每条消息的完整内存中副本。  
  
 本主题中的各节说明如何执行操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 WCF 通道模型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [与 SAP 适配器的 WCF 通道模型概述](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-channel-model-with-the-sap-adapter.md)  
  
-   [创建一个通道，使用 SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)  
  
-   [通过使用 WCF 通道模型调用 SAP 系统上的操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)  
  
-   [接收来自 SAP 系统的入站的操作，通过使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md) 
  
-   [SAP 使用 WCF 通道模型中的流式处理平面文件 Idoc](../../adapters-and-accelerators/adapter-sap/stream-flat-file-idocs-in-sap-using-the-wcf-channel-model.md)