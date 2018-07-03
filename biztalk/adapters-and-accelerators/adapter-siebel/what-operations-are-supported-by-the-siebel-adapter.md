---
title: Siebel 适配器支持哪些操作 |Microsoft Docs
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
ms.openlocfilehash: f3f080cedb74210d02806681b6c9e20656d3d09e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004774"
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a>Siebel 适配器支持哪些操作
适配器客户端可以通过以下任一方法来执行 Siebel 系统的操作：  
  
- 创建 BizTalk 项目。  
  
- 使用 WCF 通道模型。  
  
- 使用 WCF 服务模型。  
  
  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。 通过通道发送 SOAP 消息来调用这些操作。 如果响应是必需的它通过同一通道返回 SOAP 消息中。 有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。  
  
  本部分提供有关 Siebel 系统使用支持的操作信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
> [!NOTE]
>  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持从 Siebel 系统接收的入站的调用。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 Siebel 业务组件上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [在 Siebel 业务服务上的操作](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a>请参阅  
 [用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)