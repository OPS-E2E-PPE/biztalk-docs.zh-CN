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
# <a name="message-versioning-support"></a><span data-ttu-id="a0c7d-102">消息版本控制支持</span><span class="sxs-lookup"><span data-stu-id="a0c7d-102">Message Versioning Support</span></span>
<span data-ttu-id="a0c7d-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过消息操作、 命名空间和的节点 Id 中包含的版本字符串组件的支持版本控制中加以表示的操作。</span><span class="sxs-lookup"><span data-stu-id="a0c7d-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="a0c7d-104">当前版本为 http://Microsoft.LobServices.Sap/2007/03。</span><span class="sxs-lookup"><span data-stu-id="a0c7d-104">The current version is http://Microsoft.LobServices.Sap/2007/03.</span></span> <span data-ttu-id="a0c7d-105">这意味着对于名为"RFC_SAMPLE"RFC，显示适配器 RFC 操作具有以下：</span><span class="sxs-lookup"><span data-stu-id="a0c7d-105">This means that for an RFC named "RFC_SAMPLE", the RFC operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="a0c7d-106">节点 ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="a0c7d-106">Node ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="a0c7d-107">消息操作： http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="a0c7d-107">Message action: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="a0c7d-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span><span class="sxs-lookup"><span data-stu-id="a0c7d-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0c7d-109">此功能不提供与早期版本的适配器的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="a0c7d-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c7d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0c7d-110">See Also</span></span>  
 [<span data-ttu-id="a0c7d-111">消息和用于 mySAP Business Suite 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="a0c7d-111">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)