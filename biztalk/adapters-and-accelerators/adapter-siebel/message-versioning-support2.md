---
title: 消息版本控制 Support2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 5b7b9202-9f45-450e-918f-b26a03711aab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04514a9c55fa29a930b6ba7467177d6a754ff3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-versioning-support"></a><span data-ttu-id="34f1d-102">消息版本控制支持</span><span class="sxs-lookup"><span data-stu-id="34f1d-102">Message Versioning Support</span></span>
<span data-ttu-id="34f1d-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]通过消息操作、 命名空间和的节点 Id 中包含的版本字符串组件的支持版本控制中加以表示的操作。</span><span class="sxs-lookup"><span data-stu-id="34f1d-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="34f1d-104">当前版本为 http://Microsoft.LobServices.Siebel/2007/03。</span><span class="sxs-lookup"><span data-stu-id="34f1d-104">The current version is http://Microsoft.LobServices.Siebel/2007/03.</span></span> <span data-ttu-id="34f1d-105">这意味着 Siebel 存储库中的帐户业务对象上的插入操作，该适配器显示在插入操作具有以下：</span><span class="sxs-lookup"><span data-stu-id="34f1d-105">This means that for an Insert operation on an Account business object in the Siebel repository, the Insert operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="34f1d-106">节点 ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="34f1d-106">Node ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="34f1d-107">消息操作： http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="34f1d-107">Message action: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="34f1d-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span><span class="sxs-lookup"><span data-stu-id="34f1d-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34f1d-109">此功能不提供与早期版本的适配器的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="34f1d-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f1d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34f1d-110">See Also</span></span>  
 [<span data-ttu-id="34f1d-111">消息和用于 Siebel eBusiness Applications 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="34f1d-111">Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)