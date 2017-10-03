---
title: "低特权环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d43f363bd96dd8e3109a8ce21b9565fb43e5f9bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="low-privilege-environments"></a><span data-ttu-id="65f94-102">低特权环境</span><span class="sxs-lookup"><span data-stu-id="65f94-102">Low-Privilege Environments</span></span>
<span data-ttu-id="65f94-103">附带的多个工作流[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包需要提升的权限才能执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="65f94-103">Several workflows that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack require elevated permissions to perform certain actions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="65f94-104">管理包，可在低特权环境中执行基本的监视功能。</span><span class="sxs-lookup"><span data-stu-id="65f94-104"> Management Pack enables you to perform basic monitoring functionalities in a low privilege environment.</span></span> <span data-ttu-id="65f94-105">有两个管理角色： BizTalk 服务器管理员和 BizTalk Server 运算符。</span><span class="sxs-lookup"><span data-stu-id="65f94-105">There are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="65f94-106">BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="65f94-106">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="65f94-107">BizTalk 服务器管理员可以执行所有关键管理任务，此类登记和启动项目。</span><span class="sxs-lookup"><span data-stu-id="65f94-107">The BizTalk Server Administrator can perform all key administrative tasks such enlisting and starting artifacts.</span></span> <span data-ttu-id="65f94-108">BizTalk Server 操作员是低权限角色，仅有权执行监视操作和排除故障操作。</span><span class="sxs-lookup"><span data-stu-id="65f94-108">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="65f94-109">有关详细信息，请参阅[最低安全用户权限](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="65f94-109">For more information, see [Minimum Security User Rights](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx).</span></span>  
  
 <span data-ttu-id="65f94-110">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包：</span><span class="sxs-lookup"><span data-stu-id="65f94-110">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack:</span></span>  
  
-   <span data-ttu-id="65f94-111">BizTalk Server Operators 组的成员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65f94-111">Members of the BizTalk Server Operators group can do the following:</span></span>  
  
    -   <span data-ttu-id="65f94-112">监视 BizTalk Server 以查找错误，挂起 messages\instances，查看配置的查询。</span><span class="sxs-lookup"><span data-stu-id="65f94-112">Monitor BizTalk Server for errors, query for suspended messages\instances, view configuration.</span></span>  
  
    -   <span data-ttu-id="65f94-113">监视 BizTalk Server 安装和项目。</span><span class="sxs-lookup"><span data-stu-id="65f94-113">Monitor BizTalk Server installations and artifacts.</span></span>  
  
    -   <span data-ttu-id="65f94-114">查看服务状态和消息流。</span><span class="sxs-lookup"><span data-stu-id="65f94-114">View service state and message flow.</span></span>  
  
    -   <span data-ttu-id="65f94-115">启动或停止应用程序和项目比如业务流程、 发送端口或发送处于登记状态的端口组。</span><span class="sxs-lookup"><span data-stu-id="65f94-115">Start or stop applications and artifacts such as orchestrations, send ports or send port groups that are in an enlisted state.</span></span>  
  
    -   <span data-ttu-id="65f94-116">启用或禁用接收位置。</span><span class="sxs-lookup"><span data-stu-id="65f94-116">Enable or disable receive locations.</span></span> <span data-ttu-id="65f94-117">在默认为 60 秒的下一缓存刷新间隔之前，更改不会生效。</span><span class="sxs-lookup"><span data-stu-id="65f94-117">The changes do not take effect until the next cache refresh interval of 60 seconds, which is the default.</span></span> <span data-ttu-id="65f94-118">缓存刷新间隔是在 BizTalk Server 组级别进行设置的。</span><span class="sxs-lookup"><span data-stu-id="65f94-118">The cache refresh interval is set at the BizTalk Server group level.</span></span>  
  
-   <span data-ttu-id="65f94-119">BizTalk Server Operators 组的成员不能执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65f94-119">Members of the BizTalk Server Operators group cannot do the following:</span></span>  
  
    -   <span data-ttu-id="65f94-120">修改 BizTalk Server 的配置。</span><span class="sxs-lookup"><span data-stu-id="65f94-120">Modify the configuration for BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="65f94-121">查看分类为个人身份信息 (PII) 的消息上下文属性或消息正文。</span><span class="sxs-lookup"><span data-stu-id="65f94-121">View message context properties classified as Personally Identifiable Information (PII) or message bodies.</span></span>  
  
    -   <span data-ttu-id="65f94-122">修改消息路由的过程（例如向正在运行的系统添加新的订阅或从中删除订阅），包括将消息发布到 BizTalk Server 运行时的能力。</span><span class="sxs-lookup"><span data-stu-id="65f94-122">Modify the course of message routing, such as removing or adding new subscriptions to the running system, including the ability to publish messages into the BizTalk Server runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65f94-123">若要执行的管理包，如重新启动 BTSNTSvc.exe 服务提供的所有监视任务，你必须是 BizTalk 服务器上的本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="65f94-123">To perform all monitoring tasks provided by the Management Pack such as restarting BTSNTSvc.exe service, you must be a member of the local Administrators group on the BizTalk Servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65f94-124">在本节中</span><span class="sxs-lookup"><span data-stu-id="65f94-124">In this section</span></span>  
  
-   [<span data-ttu-id="65f94-125">监视</span><span class="sxs-lookup"><span data-stu-id="65f94-125">Monitoring</span></span>](../technical-guides/monitoring.md)  
  
-   [<span data-ttu-id="65f94-126">发现</span><span class="sxs-lookup"><span data-stu-id="65f94-126">Discoveries</span></span>](../technical-guides/discoveries.md)