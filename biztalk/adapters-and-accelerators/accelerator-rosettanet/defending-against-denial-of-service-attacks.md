---
title: 抵御拒绝服务攻击 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2aa48e126aafc7b2202547fd72806b5d471ef4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976918"
---
# <a name="defending-against-denial-of-service-attacks"></a><span data-ttu-id="1a68c-102">抵御拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="1a68c-102">Defending Against Denial-of-Service Attacks</span></span>
<span data-ttu-id="1a68c-103">有人可能会启动拒绝服务攻击的 Microsoft® 安装[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]通过压力过大 RNIFReceive.aspx 接收页。</span><span class="sxs-lookup"><span data-stu-id="1a68c-103">Someone could start a denial-of-service attack against an installation of Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] by stressing the RNIFReceive.aspx receive page.</span></span> <span data-ttu-id="1a68c-104">这些人可以通过向该页发送大量的空消息来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="1a68c-104">They could do so by sending large numbers of empty messages to that page.</span></span> <span data-ttu-id="1a68c-105">如果状态为不选中，则这种攻击可以使用 ASPX 接收页发布的事件填满事件日志。</span><span class="sxs-lookup"><span data-stu-id="1a68c-105">If left unchecked, such an attack could flood the event log with events published by the ASPX receive page.</span></span>  
  
## <a name="defending-against-an-attack"></a><span data-ttu-id="1a68c-106">抵御攻击</span><span class="sxs-lookup"><span data-stu-id="1a68c-106">Defending Against an Attack</span></span>  
 <span data-ttu-id="1a68c-107">要使服务器抵御拒绝服务攻击，建议您将事件日志保持在一个合理的大小，并采取措施处理过多的事件。</span><span class="sxs-lookup"><span data-stu-id="1a68c-107">To defend your server against denial-of-service attacks, it is recommended that you maintain the event log at a reasonable size and take steps to deal with excessive numbers of events.</span></span> <span data-ttu-id="1a68c-108">可以通过设置最大日志大小、选择覆盖事件的方法或使用 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® 管理规范 (WMI) 管理日志的大小来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="1a68c-108">You can accomplish this by setting the maximum log size, selecting a way of overwriting events, or using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) to manage the size of the log.</span></span> <span data-ttu-id="1a68c-109">有关详细信息，请参阅 microsoft 帮助[!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™。</span><span class="sxs-lookup"><span data-stu-id="1a68c-109">For more information, see Help for Microsoft [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a68c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a68c-110">See Also</span></span>  
 [<span data-ttu-id="1a68c-111">管理配置、证书、数据库和安全性</span><span class="sxs-lookup"><span data-stu-id="1a68c-111">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)