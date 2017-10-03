---
title: "消息和消息架构用于 mySAP Business Suite 的 BizTalk Adapter |Microsoft 文档"
description: "MySAP 适配器用于 BizTalk Server 的消息和数据类型的 XML 结构"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75ea5c27-8297-47bf-bcfd-503870349189
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db6ec6b0fbea7ce5c8f90158126d52cbc7530ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite"></a>消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构

## <a name="overview"></a>概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 它公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。 这些操作都是通过在通道上发送 SOAP 消息中调用。 如果需要响应，它将通过相同的通道返回 SOAP 消息中。  
  
 作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。 本主题中的各节描述了消息的 XML 结构和数据类型，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [基本 SAP 数据类型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)  
  
-   [自定义的 Rfc 的数据类型映射](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)  
  
-   [IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)  
  
-   [用于接收到的 Idoc 的消息上下文属性](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)  
  
-   [RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)  
  
-   [Trfc 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)  
  
-   [BAPI 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)  
  
-   [特殊的操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)  
  
-   [消息版本控制支持](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)  
  
