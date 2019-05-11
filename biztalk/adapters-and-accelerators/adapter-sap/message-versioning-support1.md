---
title: 消息版本控制 Support1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 650b966e-9fa6-4af8-a061-7852a892717a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc6a5d1d8bf6d9969deeca33110b1d05d20413ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373203"
---
# <a name="message-versioning-support"></a><span data-ttu-id="f93de-102">消息版本控制支持</span><span class="sxs-lookup"><span data-stu-id="f93de-102">Message Versioning Support</span></span>
<span data-ttu-id="f93de-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过消息操作、 命名空间和节点 Id 中包含的版本字符串组件来支持版本控制提供的操作。</span><span class="sxs-lookup"><span data-stu-id="f93de-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="f93de-104">当前版本是 http://Microsoft.LobServices.Sap/2007/03。</span><span class="sxs-lookup"><span data-stu-id="f93de-104">The current version is http://Microsoft.LobServices.Sap/2007/03.</span></span> <span data-ttu-id="f93de-105">这意味着对于名为"RFC_SAMPLE"RFC 和 RFC 操作由适配器具有以下：</span><span class="sxs-lookup"><span data-stu-id="f93de-105">This means that for an RFC named "RFC_SAMPLE", the RFC operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="f93de-106">节点 ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="f93de-106">Node ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="f93de-107">消息操作： http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="f93de-107">Message action: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="f93de-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span><span class="sxs-lookup"><span data-stu-id="f93de-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f93de-109">此功能不提供向后兼容早期版本的适配器。</span><span class="sxs-lookup"><span data-stu-id="f93de-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f93de-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f93de-110">See Also</span></span>  
 [<span data-ttu-id="f93de-111">消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="f93de-111">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)