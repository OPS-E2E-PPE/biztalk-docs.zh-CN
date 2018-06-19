---
title: 安全摘要 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security
ms.assetid: 357ebf63-a35e-4ce4-a754-be880946f9fc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d327de93941278b9b1dcecc9378183c6a2f77a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213973"
---
# <a name="security-summary"></a><span data-ttu-id="9cef6-102">安全摘要</span><span class="sxs-lookup"><span data-stu-id="9cef6-102">Security Summary</span></span>
## <a name="overview"></a><span data-ttu-id="9cef6-103">概述</span><span class="sxs-lookup"><span data-stu-id="9cef6-103">Overview</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="9cef6-104">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供开发和运行时组件以便于 BizTalk 应用程序提供 SWIFT 消息传送和自动化功能。</span><span class="sxs-lookup"><span data-stu-id="9cef6-104"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides development and runtime components to facilitate BizTalk applications that provide SWIFT messaging and automation functionality.</span></span> <span data-ttu-id="9cef6-105">通过使用开发的应用程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]是 BizTalk 应用程序，保护的本机[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]， [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]， [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，和 IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]安全功能。</span><span class="sxs-lookup"><span data-stu-id="9cef6-105">Applications developed by using [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] are BizTalk applications and are secured by native [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], and IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] security features.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9cef6-106">通过使用事实上加密的 Internet 通信标准和协议保护隐私系统元素。</span><span class="sxs-lookup"><span data-stu-id="9cef6-106"> protects privacy of system elements by using de facto Internet encrypted communications standards and protocols.</span></span> <span data-ttu-id="9cef6-107">通信参与者、 过程和信息保护的使用签名证书，[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证和企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="9cef6-107">Communication participants, processes, and information are secured by using signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9cef6-108">此外强制实施授权的资源使用情况与机制如[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]角色和[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，并且 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9cef6-108"> also enforces authorization of resource usage with mechanisms such as [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and the MessageBox database.</span></span>  
  
 <span data-ttu-id="9cef6-109">除了本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能，[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]定义并强制执行创建、 修复、 批准和提交的 SWIFT 消息业务用户的安全语义。</span><span class="sxs-lookup"><span data-stu-id="9cef6-109">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] defines and enforces security semantics for the creation, repair, approval, and submission of SWIFT messages by business users.</span></span> <span data-ttu-id="9cef6-110">此用户级安全进行强制要求使用[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]进行数字签名上的用户工作站和证书和数据完整性验证的技术[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]服务器上的运行时服务。</span><span class="sxs-lookup"><span data-stu-id="9cef6-110">This user-level security is enforced by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies on the user workstation, and certificate and data integrity verification by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] runtime services on the server.</span></span>  
  
 <span data-ttu-id="9cef6-111">在一起，[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]设计、 开发和执行安全 SWIFT 消息传递和工作流自动化系统提供的平台、 基础结构和工具。</span><span class="sxs-lookup"><span data-stu-id="9cef6-111">Together, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="9cef6-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="9cef6-112">More information</span></span>  
 <span data-ttu-id="9cef6-113">有关安全最佳做法的信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="9cef6-113">For information about security best practices, see the following:</span></span>  
  
-   <span data-ttu-id="9cef6-114">TechNet 安全资源中心：</span><span class="sxs-lookup"><span data-stu-id="9cef6-114">TechNet Security Resource Center:</span></span>  
  
     [<span data-ttu-id="9cef6-115">http://go.microsoft.com/fwlink/p/?LinkId=27741</span><span class="sxs-lookup"><span data-stu-id="9cef6-115">http://go.microsoft.com/fwlink/p/?LinkId=27741</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=27741)  
  

-   <span data-ttu-id="9cef6-116">显示如何使用其工具来实施中所述的最佳做法的 Symantec 安全指南[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]安全操作指南[!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9cef6-116">Symantec security guide showing how to use their tools to implement the best practices described in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Security Operations Guide for [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span></span>  
  
     [<span data-ttu-id="9cef6-117">http://go.microsoft.com/fwlink/p/?LinkId=28274</span><span class="sxs-lookup"><span data-stu-id="9cef6-117">http://go.microsoft.com/fwlink/p/?LinkId=28274</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=28274)  

  
-   <span data-ttu-id="9cef6-118">有关信息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]安全通知服务：</span><span class="sxs-lookup"><span data-stu-id="9cef6-118">Information about the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Security Notification Service:</span></span>  
  
     [<span data-ttu-id="9cef6-119">http://go.microsoft.com/fwlink/p/?LinkId=27744</span><span class="sxs-lookup"><span data-stu-id="9cef6-119">http://go.microsoft.com/fwlink/p/?LinkId=27744</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=27744)  
  
  
## <a name="see-also"></a><span data-ttu-id="9cef6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cef6-120">See Also</span></span>  
[<span data-ttu-id="9cef6-121">运行时、 消息修复、 FIN 响应和消息传送</span><span class="sxs-lookup"><span data-stu-id="9cef6-121">Runtime, message repair, FIN response, and messaging</span></span>](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)