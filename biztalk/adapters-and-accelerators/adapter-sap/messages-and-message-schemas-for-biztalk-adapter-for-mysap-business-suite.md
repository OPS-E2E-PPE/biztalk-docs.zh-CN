---
title: 消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器 |Microsoft Docs
description: 用于 mySAP 适配器通过 BizTalk Server 的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ea5c27-8297-47bf-bcfd-503870349189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 119fe8aea98266e0fcd3b26bff439b6136b3b755
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373221"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite"></a>消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器

## <a name="overview"></a>概述
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 它公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。  
  
 作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。 本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [基本 SAP 数据类型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)  
  
-   [自定义 RFC 的数据类型映射](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)  
  
-   [IDOC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)  
  
-   [用于接收 IDOC 的消息上下文属性](../../adapters-and-accelerators/adapter-sap/message-context-properties-for-receiving-idocs.md)  
  
-   [RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)  
  
-   [tRFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-trfc-operations.md)  
  
-   [BAPI 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-bapi-operations.md)  
  
-   [特殊操作](../../adapters-and-accelerators/adapter-sap/special-operations.md)  
  
-   [消息版本控制支持](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)  
  
