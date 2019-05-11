---
title: 安全摘要 |Microsoft Docs
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
ms.openlocfilehash: 41d4c26782d91a93a1514067dc4c50a5bc9784c1
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530030"
---
# <a name="security-summary"></a><span data-ttu-id="a24d1-102">安全摘要</span><span class="sxs-lookup"><span data-stu-id="a24d1-102">Security Summary</span></span>
## <a name="overview"></a><span data-ttu-id="a24d1-103">概述</span><span class="sxs-lookup"><span data-stu-id="a24d1-103">Overview</span></span>
<span data-ttu-id="a24d1-104">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供开发和运行时组件，以便提供消息传送和自动化功能的 SWIFT 的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a24d1-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides development and runtime components to facilitate BizTalk applications that provide SWIFT messaging and automation functionality.</span></span> <span data-ttu-id="a24d1-105">通过使用开发的应用程序[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]是 BizTalk 应用程序和受保护的本机[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]， [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]， [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，和 IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]安全功能。</span><span class="sxs-lookup"><span data-stu-id="a24d1-105">Applications developed by using [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] are BizTalk applications and are secured by native [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], and IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] security features.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a24d1-106">使用实际加密的 Internet 通信标准和协议来保护隐私的系统元素。</span><span class="sxs-lookup"><span data-stu-id="a24d1-106">protects privacy of system elements by using de facto Internet encrypted communications standards and protocols.</span></span> <span data-ttu-id="a24d1-107">通过使用签名证书保护通信的参与者、 过程和信息[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证和企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="a24d1-107">Communication participants, processes, and information are secured by using signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a24d1-108">此外强制实施的资源使用情况的授权机制如[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]角色和[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，并且 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="a24d1-108">also enforces authorization of resource usage with mechanisms such as [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and the MessageBox database.</span></span>  
  
 <span data-ttu-id="a24d1-109">除了本机[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]定义并强制执行安全创建、 修复、 批准和 SWIFT 消息的业务用户提交的语义。</span><span class="sxs-lookup"><span data-stu-id="a24d1-109">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] defines and enforces security semantics for the creation, repair, approval, and submission of SWIFT messages by business users.</span></span> <span data-ttu-id="a24d1-110">通过强制实施此用户级安全[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]数字签名技术上的用户工作站和证书和数据完整性验证[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]服务器上的运行时服务。</span><span class="sxs-lookup"><span data-stu-id="a24d1-110">This user-level security is enforced by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies on the user workstation, and certificate and data integrity verification by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] runtime services on the server.</span></span>  
  
 <span data-ttu-id="a24d1-111">共同[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]为设计、 开发和执行安全 SWIFT 消息传送和工作流自动化系统提供的平台、 基础结构和工具。</span><span class="sxs-lookup"><span data-stu-id="a24d1-111">Together, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="a24d1-112">详细信息</span><span class="sxs-lookup"><span data-stu-id="a24d1-112">More information</span></span>  
 <span data-ttu-id="a24d1-113">有关安全最佳做法的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a24d1-113">For information about security best practices, see the following:</span></span>  
  
- <span data-ttu-id="a24d1-114">TechNet 安全资源中心：</span><span class="sxs-lookup"><span data-stu-id="a24d1-114">TechNet Security Resource Center:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27741](http://go.microsoft.com/fwlink/p/?LinkId=27741)  
  

- <span data-ttu-id="a24d1-115">Symantec 安全指南显示了如何使用其工具来实现 Microsoft 安全性操作指南中描述的最佳实践[!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a24d1-115">Symantec security guide showing how to use their tools to implement the best practices described in Microsoft Security Operations Guide for [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=28274](http://go.microsoft.com/fwlink/p/?LinkId=28274)  

  
- <span data-ttu-id="a24d1-116">Microsoft 安全通知服务有关的信息：</span><span class="sxs-lookup"><span data-stu-id="a24d1-116">Information about the Microsoft Security Notification Service:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27744](http://go.microsoft.com/fwlink/p/?LinkId=27744)  
  
  
## <a name="see-also"></a><span data-ttu-id="a24d1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a24d1-117">See Also</span></span>  
[<span data-ttu-id="a24d1-118">运行时、消息修复、FIN 响应和消息传递</span><span class="sxs-lookup"><span data-stu-id="a24d1-118">Runtime, message repair, FIN response, and messaging</span></span>](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)