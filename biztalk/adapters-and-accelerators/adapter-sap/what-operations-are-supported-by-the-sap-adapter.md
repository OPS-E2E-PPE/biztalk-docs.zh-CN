---
title: SAP 适配器支持哪些操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, performing operations
ms.assetid: 4b676336-526d-42b9-9ff2-1a4f27df1a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee217572e0bf56e7a4f7e4810421befeb08bfc3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-sap-adapter"></a>SAP 适配器支持何种操作
创建 BizTalk 项目、 使用 WCF 通道模型，或使用 WCF 服务模型，适配器客户端可以执行 SAP 系统上的操作。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。 这些操作都是通过在通道上发送 SOAP 消息中调用。 如果需要响应，它将通过相同的通道返回 SOAP 消息中。 有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 mySAP Business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。  
  
 本部分提供有关 SAP 系统使用支持的操作的信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SAP 中的 Rfc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)  
  
-   [对 tRFCs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)  
  
-   [对 BAPIs SAP 中的操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)  
  
-   [SAP 中的 Idoc 上的操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)