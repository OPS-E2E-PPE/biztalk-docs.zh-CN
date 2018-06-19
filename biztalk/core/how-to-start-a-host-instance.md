---
title: 启动主机实例 |Microsoft 文档
description: 使用 BizTalk 管理在 BizTalk Server 中启动的主机实例
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
ms.openlocfilehash: dd5cccc48b33dda4b6458f8dfa8f56a84ad3cd62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255813"
---
# <a name="start-a-host-instance"></a><span data-ttu-id="ce24b-103">启动主机实例</span><span class="sxs-lookup"><span data-stu-id="ce24b-103">Start a Host Instance</span></span>
<span data-ttu-id="ce24b-104">可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或 Windows 管理规范 (WMI) 来启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="ce24b-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to start host instances.</span></span> <span data-ttu-id="ce24b-105">在添加或停止主机实例之后，必须启动该实例以便其运行并将消息路由至 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ce24b-105">After you add or stop a host instance, you must start it so that it is running and routing messages to the MessageBox databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce24b-106">为主机实例指定的服务帐户应该是所关联主机的 Windows 组的成员。</span><span class="sxs-lookup"><span data-stu-id="ce24b-106">The service account that you specify for a host instance should be a member of the Windows group for the associated host.</span></span> <span data-ttu-id="ce24b-107">否则，主机实例在运行时可能不具有相应的权限或验证。</span><span class="sxs-lookup"><span data-stu-id="ce24b-107">Otherwise, the host instance may not have the appropriate permissions or authentication at run time.</span></span> <span data-ttu-id="ce24b-108">此外，为安全起见，该帐户应具有最低特权，因为以主机实例为宿主的业务流程可能会执行有恶意的自定义代码。</span><span class="sxs-lookup"><span data-stu-id="ce24b-108">In addition, for security reasons, the account should have minimum privileges because orchestrations hosted by the host instance might execute potentially malicious custom code.</span></span>  
  
 <span data-ttu-id="ce24b-109">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="ce24b-109">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="ce24b-110">有关使用 WMI 来启动主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="ce24b-110">For information about using WMI to start a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="ce24b-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="ce24b-111">Prerequisites</span></span>  
 <span data-ttu-id="ce24b-112">若要执行此过程，则必须以 Administrators 组和 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="ce24b-112">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="ce24b-113">此外，您还必需是以下数据库所在服务器上的 db_securityadmin SQL Server 数据库角色和 securityadmin SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="ce24b-113">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="ce24b-114">BAM 主导入 (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="ce24b-114">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="ce24b-115">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="ce24b-115">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="ce24b-116">BizTalk MessageBox (BizTalkMsgBoxDb)（全部）</span><span class="sxs-lookup"><span data-stu-id="ce24b-116">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="ce24b-117">BizTalk 跟踪 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="ce24b-117">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="ce24b-118">规则引擎 (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="ce24b-118">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ce24b-119">建议使用 BizTalk Server 管理控制台或 Windows 管理规范 (WMI) 脚本来更新主机实例的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="ce24b-119">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="ce24b-120">这样可以确保 BizTalk Server 能够更新 BizTalk Server 数据库中的帐户信息，并在数据库与主机实例之间保持安全配置同步。</span><span class="sxs-lookup"><span data-stu-id="ce24b-120">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="ce24b-121">步骤</span><span class="sxs-lookup"><span data-stu-id="ce24b-121">Steps</span></span>
  
1.  <span data-ttu-id="ce24b-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="ce24b-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="ce24b-123">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="ce24b-123">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="ce24b-124">在详细信息窗格中，右键单击你想要启动，，然后单击该主机实例**启动**。</span><span class="sxs-lookup"><span data-stu-id="ce24b-124">In the details pane, right-click the host instance you want to start, and then click **Start**.</span></span>  
  
     <span data-ttu-id="ce24b-125">主机实例的状态更改为**启动挂起**。</span><span class="sxs-lookup"><span data-stu-id="ce24b-125">The status of the host instance changes to **Start pending**.</span></span> <span data-ttu-id="ce24b-126">主机实例启动后，状态将更改为**运行**。</span><span class="sxs-lookup"><span data-stu-id="ce24b-126">After the host instance initiates, the status changes to **Running**.</span></span>  
  
 <span data-ttu-id="ce24b-127">启动主机实例之后，可以停止它，以防止其将消息路由至 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ce24b-127">After you start a host instance, you can stop it to prevent it from routing messages to the MessageBox database.</span></span> <span data-ttu-id="ce24b-128">必须先停止主机实例才能从给定计算机上删除 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="ce24b-128">You must stop a host instance before you can remove BizTalk Server from a given computer.</span></span> <span data-ttu-id="ce24b-129">要停止的主机实例的信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="ce24b-129">For information about stopping a host instance, see [How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce24b-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce24b-130">See Also</span></span>  
 <span data-ttu-id="ce24b-131">[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="ce24b-131">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="ce24b-132">[添加一个主机实例](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="ce24b-132">[Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="ce24b-133">[停止主机实例](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="ce24b-133">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 <span data-ttu-id="ce24b-134">[删除的主机实例](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="ce24b-134">[Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="ce24b-135">修改主机实例属性</span><span class="sxs-lookup"><span data-stu-id="ce24b-135">Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)