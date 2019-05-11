---
title: 消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构 |Microsoft Docs
description: Siebel 适配器的 BizTalk 适配器包 (BAP) 中使用的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4da884-89b0-4ab1-a728-c5569088a993
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a96682063437bb59c04372a7e8540743b27113
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371295"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-siebel-ebusiness-applications"></a>消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构

## <a name="overview"></a>概述
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。 它公开应用程序可以调用 Siebel 系统的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。  
  
 作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。 本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [基本 Siebel 数据类型](basic-siebel-data-types.md)  
  
-   [业务组件操作的消息架构](message-schemas-for-business-component-operations.md)  
  
-   [业务服务操作的消息架构](message-schemas-for-business-service-operations.md)  
  
-   [选择列表的消息架构](message-schema-for-picklist-operations.md)  
  
-   [消息版本控制支持](message-versioning-support2.md)  
  
