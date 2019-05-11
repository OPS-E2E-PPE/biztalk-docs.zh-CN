---
title: 消息版本控制 Support2 |Microsoft Docs
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
ms.openlocfilehash: 181e242334d91b92eeaa2800baf9a56bd936a3eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371323"
---
# <a name="message-versioning-support"></a><span data-ttu-id="22cc3-102">消息版本控制支持</span><span class="sxs-lookup"><span data-stu-id="22cc3-102">Message Versioning Support</span></span>
<span data-ttu-id="22cc3-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]通过消息操作、 命名空间和节点 Id 中包含的版本字符串组件来支持版本控制提供的操作。</span><span class="sxs-lookup"><span data-stu-id="22cc3-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="22cc3-104">当前版本是 http://Microsoft.LobServices.Siebel/2007/03。</span><span class="sxs-lookup"><span data-stu-id="22cc3-104">The current version is http://Microsoft.LobServices.Siebel/2007/03.</span></span> <span data-ttu-id="22cc3-105">这意味着在 Siebel 存储库中帐户业务对象上的插入操作，适配器提供的插入操作具有以下：</span><span class="sxs-lookup"><span data-stu-id="22cc3-105">This means that for an Insert operation on an Account business object in the Siebel repository, the Insert operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="22cc3-106">节点 ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="22cc3-106">Node ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="22cc3-107">消息操作： http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="22cc3-107">Message action: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="22cc3-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span><span class="sxs-lookup"><span data-stu-id="22cc3-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22cc3-109">此功能不提供向后兼容早期版本的适配器。</span><span class="sxs-lookup"><span data-stu-id="22cc3-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22cc3-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="22cc3-110">See Also</span></span>  
 [<span data-ttu-id="22cc3-111">消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构</span><span class="sxs-lookup"><span data-stu-id="22cc3-111">Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)