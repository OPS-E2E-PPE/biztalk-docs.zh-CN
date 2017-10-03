---
title: "消息版本控制 Support1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message versioning, support for
ms.assetid: 650b966e-9fa6-4af8-a061-7852a892717a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a2175ba0a3aafd052e6830439800569cf5f005f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-versioning-support"></a>消息版本控制支持
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过消息操作、 命名空间和的节点 Id 中包含的版本字符串组件的支持版本控制中加以表示的操作。 当前版本为 http://Microsoft.LobServices.Sap/2007/03。 这意味着对于名为"RFC_SAMPLE"RFC，显示适配器 RFC 操作具有以下：  
  
-   节点 ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   消息操作： http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc  
  
> [!NOTE]
>  此功能不提供与早期版本的适配器的向后兼容性。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)