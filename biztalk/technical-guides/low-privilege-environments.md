---
title: 低特权环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abdc45d0-b63a-4b6c-80c4-1f8e87644cd9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 121655ecb70c084637f2fd481dc6bd2fce7a57cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396295"
---
# <a name="low-privilege-environments"></a><span data-ttu-id="65e91-102">低特权环境</span><span class="sxs-lookup"><span data-stu-id="65e91-102">Low-Privilege Environments</span></span>
<span data-ttu-id="65e91-103">多个工作流所含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包需要提升的权限来执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="65e91-103">Several workflows that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack require elevated permissions to perform certain actions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="65e91-104">管理包，可在低特权环境中执行基本的监视功能。</span><span class="sxs-lookup"><span data-stu-id="65e91-104">Management Pack enables you to perform basic monitoring functionalities in a low privilege environment.</span></span> <span data-ttu-id="65e91-105">有两种管理角色： BizTalk Server 管理器和 BizTalk Server 操作员。</span><span class="sxs-lookup"><span data-stu-id="65e91-105">There are two Administrative Roles: the BizTalk Server Administrator, and the BizTalk Server Operator.</span></span> <span data-ttu-id="65e91-106">BizTalk Server 管理员是高权限角色，有权访问配置数据和跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="65e91-106">The BizTalk Server Administrator is a high privilege role with access to configuration and tracking data.</span></span> <span data-ttu-id="65e91-107">BizTalk Server 管理员可以执行所有密钥管理任务，此类登记和启动项目。</span><span class="sxs-lookup"><span data-stu-id="65e91-107">The BizTalk Server Administrator can perform all key administrative tasks such enlisting and starting artifacts.</span></span> <span data-ttu-id="65e91-108">BizTalk Server 操作员是低权限角色，仅有权监视和故障排除操作。</span><span class="sxs-lookup"><span data-stu-id="65e91-108">The BizTalk Server Operator is a low privilege role with access only to monitoring and troubleshooting actions.</span></span> <span data-ttu-id="65e91-109">有关详细信息，请参阅[最低安全用户权限](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="65e91-109">For more information, see [Minimum Security User Rights](http://technet.microsoft.com/library/aa559845\(BTS.80\).aspx).</span></span>  
  
 <span data-ttu-id="65e91-110">使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包：</span><span class="sxs-lookup"><span data-stu-id="65e91-110">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack:</span></span>  
  
-   <span data-ttu-id="65e91-111">BizTalk Server Operators 组的成员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65e91-111">Members of the BizTalk Server Operators group can do the following:</span></span>  
  
    -   <span data-ttu-id="65e91-112">发生错误，查询挂起的消息 \ 实例，查看配置的监视器 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="65e91-112">Monitor BizTalk Server for errors, query for suspended messages\instances, view configuration.</span></span>  
  
    -   <span data-ttu-id="65e91-113">监视 BizTalk Server 安装和项目。</span><span class="sxs-lookup"><span data-stu-id="65e91-113">Monitor BizTalk Server installations and artifacts.</span></span>  
  
    -   <span data-ttu-id="65e91-114">查看服务状态和消息流。</span><span class="sxs-lookup"><span data-stu-id="65e91-114">View service state and message flow.</span></span>  
  
    -   <span data-ttu-id="65e91-115">启动或停止应用程序和项目，例如业务流程、 发送端口或发送端口组处于登记状态。</span><span class="sxs-lookup"><span data-stu-id="65e91-115">Start or stop applications and artifacts such as orchestrations, send ports or send port groups that are in an enlisted state.</span></span>  
  
    -   <span data-ttu-id="65e91-116">启用或禁用接收位置。</span><span class="sxs-lookup"><span data-stu-id="65e91-116">Enable or disable receive locations.</span></span> <span data-ttu-id="65e91-117">更改不会生效直到下一步的缓存刷新间隔为 60 秒，这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="65e91-117">The changes do not take effect until the next cache refresh interval of 60 seconds, which is the default.</span></span> <span data-ttu-id="65e91-118">在 BizTalk Server 组级别设置缓存刷新间隔。</span><span class="sxs-lookup"><span data-stu-id="65e91-118">The cache refresh interval is set at the BizTalk Server group level.</span></span>  
  
-   <span data-ttu-id="65e91-119">BizTalk Server Operators 组的成员不能执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65e91-119">Members of the BizTalk Server Operators group cannot do the following:</span></span>  
  
    -   <span data-ttu-id="65e91-120">修改 BizTalk Server 的配置。</span><span class="sxs-lookup"><span data-stu-id="65e91-120">Modify the configuration for BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="65e91-121">查看被归类为个人身份信息 (PII) 或消息正文的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="65e91-121">View message context properties classified as Personally Identifiable Information (PII) or message bodies.</span></span>  
  
    -   <span data-ttu-id="65e91-122">修改消息路由，例如删除或将新的订阅添加到正在运行的系统，包括能够将消息发布到 BizTalk Server 运行时的过程。</span><span class="sxs-lookup"><span data-stu-id="65e91-122">Modify the course of message routing, such as removing or adding new subscriptions to the running system, including the ability to publish messages into the BizTalk Server runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65e91-123">若要执行如重新启动 BTSNTSvc.exe 服务的管理包提供的所有监视任务，必须是 BizTalk 服务器上的本地管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="65e91-123">To perform all monitoring tasks provided by the Management Pack such as restarting BTSNTSvc.exe service, you must be a member of the local Administrators group on the BizTalk Servers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65e91-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="65e91-124">In this section</span></span>  
  
-   [<span data-ttu-id="65e91-125">监视</span><span class="sxs-lookup"><span data-stu-id="65e91-125">Monitoring</span></span>](../technical-guides/monitoring.md)  
  
-   [<span data-ttu-id="65e91-126">发现</span><span class="sxs-lookup"><span data-stu-id="65e91-126">Discoveries</span></span>](../technical-guides/discoveries.md)