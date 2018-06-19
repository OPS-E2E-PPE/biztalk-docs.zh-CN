---
title: Siebel 适配器支持哪些操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing by using the adapter
ms.assetid: 800cf44b-357f-4850-8878-f49ceb549adf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40bfb247ff0f3af2abeec584c5fd079f392cd18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222349"
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a>Siebel 适配器支持何种操作
适配器客户端可以通过以下任一方法来执行 Siebel 系统上的操作：  
  
-   创建 BizTalk 项目。  
  
-   使用 WCF 通道模型。  
  
-   使用 WCF 服务模型。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。 这些操作都是通过在通道上发送 SOAP 消息中调用。 如果需要响应，它将通过相同的通道返回 SOAP 消息中。 有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 Siebel eBusiness Applications 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。  
  
 本部分提供有关 Siebel 系统使用支持的操作的信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
> [!NOTE]
>  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持从 Siebel 系统接收的入站的调用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 Siebel 的业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [对 Siebel 中的业务服务的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a>另请参阅  
 [为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)