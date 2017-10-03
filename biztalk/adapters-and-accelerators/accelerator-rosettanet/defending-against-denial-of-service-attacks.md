---
title: "防范拒绝服务攻击 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 667b9d321f7703f770297b001ef2a99be2bf4902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="defending-against-denial-of-service-attacks"></a><span data-ttu-id="0c8bf-102">防范拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="0c8bf-102">Defending Against Denial-of-Service Attacks</span></span>
<span data-ttu-id="0c8bf-103">可能会有人通过对 RNIFReceive.aspx 接收页施加压力，开始针对 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 的安装进行拒绝服务的攻击。</span><span class="sxs-lookup"><span data-stu-id="0c8bf-103">Someone could start a denial-of-service attack against an installation of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] by stressing the RNIFReceive.aspx receive page.</span></span> <span data-ttu-id="0c8bf-104">这些人可以通过向该页发送大量的空消息来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="0c8bf-104">They could do so by sending large numbers of empty messages to that page.</span></span> <span data-ttu-id="0c8bf-105">如果状态为不选中，则这种攻击可以使用 ASPX 接收页发布的事件填满事件日志。</span><span class="sxs-lookup"><span data-stu-id="0c8bf-105">If left unchecked, such an attack could flood the event log with events published by the ASPX receive page.</span></span>  
  
## <a name="defending-against-an-attack"></a><span data-ttu-id="0c8bf-106">抵御攻击</span><span class="sxs-lookup"><span data-stu-id="0c8bf-106">Defending Against an Attack</span></span>  
 <span data-ttu-id="0c8bf-107">要使服务器抵御拒绝服务攻击，建议您将事件日志保持在一个合理的大小，并采取措施处理过多的事件。</span><span class="sxs-lookup"><span data-stu-id="0c8bf-107">To defend your server against denial-of-service attacks, it is recommended that you maintain the event log at a reasonable size and take steps to deal with excessive numbers of events.</span></span> <span data-ttu-id="0c8bf-108">可以通过设置最大日志大小、选择覆盖事件的方法或使用 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® 管理规范 (WMI) 管理日志的大小来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="0c8bf-108">You can accomplish this by setting the maximum log size, selecting a way of overwriting events, or using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) to manage the size of the log.</span></span> <span data-ttu-id="0c8bf-109">有关详细信息，请参见帮助[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™。</span><span class="sxs-lookup"><span data-stu-id="0c8bf-109">For more information, see Help for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8bf-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c8bf-110">See Also</span></span>  
 [<span data-ttu-id="0c8bf-111">管理配置、 证书、 数据库和安全</span><span class="sxs-lookup"><span data-stu-id="0c8bf-111">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)