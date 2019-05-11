---
title: 启动主机实例 |Microsoft Docs
description: 使用 BizTalk 管理 BizTalk Server 中启动主机实例
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96a4362-2147-4b8e-a270-bf9a17477ba3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dc17eec6a1782a1b607be812003978793d49c6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383838"
---
# <a name="start-a-host-instance"></a><span data-ttu-id="cc800-103">启动主机实例</span><span class="sxs-lookup"><span data-stu-id="cc800-103">Start a Host Instance</span></span>
<span data-ttu-id="cc800-104">可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="cc800-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to start host instances.</span></span> <span data-ttu-id="cc800-105">添加或停止主机实例后，您必须启动它，以便它正在运行，并且将消息路由到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="cc800-105">After you add or stop a host instance, you must start it so that it is running and routing messages to the MessageBox databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc800-106">为主机实例指定的服务帐户应是关联的主机的 Windows 组的成员。</span><span class="sxs-lookup"><span data-stu-id="cc800-106">The service account that you specify for a host instance should be a member of the Windows group for the associated host.</span></span> <span data-ttu-id="cc800-107">否则，主机实例可能没有适当的权限或在运行时的身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc800-107">Otherwise, the host instance may not have the appropriate permissions or authentication at run time.</span></span> <span data-ttu-id="cc800-108">此外，出于安全原因，该帐户应具有最小特权因为业务流程主机实例所承载的可能执行潜在的恶意的自定义代码。</span><span class="sxs-lookup"><span data-stu-id="cc800-108">In addition, for security reasons, the account should have minimum privileges because orchestrations hosted by the host instance might execute potentially malicious custom code.</span></span>  
  
 <span data-ttu-id="cc800-109">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="cc800-109">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="cc800-110">有关使用 WMI 启动主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="cc800-110">For information about using WMI to start a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="cc800-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="cc800-111">Prerequisites</span></span>  
 <span data-ttu-id="cc800-112">若要执行此过程，必须以 Administrators 组和 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cc800-112">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="cc800-113">此外，您还必须是 db_securityadmin SQL Server 数据库角色和以下数据库所在的服务器上的 securityadmin SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="cc800-113">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="cc800-114">BAM 主导入 (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="cc800-114">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="cc800-115">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="cc800-115">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="cc800-116">BizTalk MessageBox (BizTalkMsgBoxDb) （全部）</span><span class="sxs-lookup"><span data-stu-id="cc800-116">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="cc800-117">BizTalk 跟踪 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="cc800-117">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="cc800-118">规则引擎 (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="cc800-118">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="cc800-119">我们建议使用 BizTalk Server 管理控制台或 Windows Management Instrumentation (WMI) 脚本更新主机实例的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="cc800-119">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="cc800-120">这可确保 BizTalk Server 可以更新 BizTalk Server 数据库中的帐户信息并保持数据库和同步的主机实例之间的安全配置。</span><span class="sxs-lookup"><span data-stu-id="cc800-120">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="cc800-121">步骤</span><span class="sxs-lookup"><span data-stu-id="cc800-121">Steps</span></span>
  
1. <span data-ttu-id="cc800-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cc800-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cc800-123">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="cc800-123">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="cc800-124">在详细信息窗格中，右键单击你想要开始，然后单击该主机实例**启动**。</span><span class="sxs-lookup"><span data-stu-id="cc800-124">In the details pane, right-click the host instance you want to start, and then click **Start**.</span></span>  
  
    <span data-ttu-id="cc800-125">主机实例的状态将变为**启动挂起**。</span><span class="sxs-lookup"><span data-stu-id="cc800-125">The status of the host instance changes to **Start pending**.</span></span> <span data-ttu-id="cc800-126">主机实例启动后，状态将更改为**运行**。</span><span class="sxs-lookup"><span data-stu-id="cc800-126">After the host instance initiates, the status changes to **Running**.</span></span>  
  
   <span data-ttu-id="cc800-127">启动主机实例后，可以停止它以防止它将消息路由到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="cc800-127">After you start a host instance, you can stop it to prevent it from routing messages to the MessageBox database.</span></span> <span data-ttu-id="cc800-128">可以从给定计算机上删除 BizTalk Server 之前，必须停止主机实例。</span><span class="sxs-lookup"><span data-stu-id="cc800-128">You must stop a host instance before you can remove BizTalk Server from a given computer.</span></span> <span data-ttu-id="cc800-129">有关停止主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="cc800-129">For information about stopping a host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc800-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc800-130">See Also</span></span>  
 <span data-ttu-id="cc800-131">[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="cc800-131">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="cc800-132">[添加主机实例](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="cc800-132">[Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="cc800-133">[停止主机实例](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="cc800-133">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 <span data-ttu-id="cc800-134">[删除主机实例](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="cc800-134">[Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="cc800-135">修改主机实例属性</span><span class="sxs-lookup"><span data-stu-id="cc800-135">Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)