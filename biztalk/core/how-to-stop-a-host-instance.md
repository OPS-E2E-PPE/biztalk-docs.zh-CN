---
title: 停止主机实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1f2e0c1-a387-4182-82ef-e25f49ac509b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b66c89ccafa72c56de00aebd24091915643f44e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972670"
---
# <a name="stop-a-host-instance"></a><span data-ttu-id="3bc8b-102">停止主机实例</span><span class="sxs-lookup"><span data-stu-id="3bc8b-102">Stop a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="3bc8b-103">概述</span><span class="sxs-lookup"><span data-stu-id="3bc8b-103">Overview</span></span>
<span data-ttu-id="3bc8b-104">可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或 Windows 管理规范 (WMI) 来停止主机实例。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to stop host instances.</span></span> <span data-ttu-id="3bc8b-105">必须先停止主机实例才能删除该主机实例或从计算机中删除 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-105">You must stop a host instance before you can delete it or remove BizTalk Server from a computer.</span></span> <span data-ttu-id="3bc8b-106">可以停止已安装和已启动的主机实例。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-106">You can stop a host instance that is installed and started.</span></span> <span data-ttu-id="3bc8b-107">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-107">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="3bc8b-108">有关使用 WMI 停止主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-108">For information about using WMI to stop a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="3bc8b-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="3bc8b-109">Prerequisites</span></span>  
 <span data-ttu-id="3bc8b-110">若要执行此过程，则必须以 Administrators 组和 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-110">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="3bc8b-111">此外，您还必需是以下数据库所在服务器上的 db_securityadmin SQL Server 数据库角色和 securityadmin SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="3bc8b-111">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="3bc8b-112">BAM 主导入 (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="3bc8b-112">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="3bc8b-113">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="3bc8b-113">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="3bc8b-114">BizTalk MessageBox (BizTalkMsgBoxDb)（全部）</span><span class="sxs-lookup"><span data-stu-id="3bc8b-114">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="3bc8b-115">BizTalk 跟踪 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="3bc8b-115">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="3bc8b-116">规则引擎 (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="3bc8b-116">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3bc8b-117">建议使用 BizTalk Server 管理控制台或 Windows 管理规范 (WMI) 脚本来更新主机实例的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-117">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="3bc8b-118">这样可以确保 BizTalk Server 能够更新 BizTalk Server 数据库中的帐户信息，并在数据库与主机实例之间保持安全配置同步。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-118">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="3bc8b-119">步骤</span><span class="sxs-lookup"><span data-stu-id="3bc8b-119">Steps</span></span>
  
1. <span data-ttu-id="3bc8b-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="3bc8b-121">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-121">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="3bc8b-122">在详细信息窗格中，右键单击你想要停止，然后单击该主机实例**停止**。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-122">In the details pane, right-click the host instance you want to stop, and then click **Stop**.</span></span>  
  
    <span data-ttu-id="3bc8b-123">主机实例的状态将变为**已停止**。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-123">The status of the host instance changes to **Stopped**.</span></span>  
  
   <span data-ttu-id="3bc8b-124">在停止主机实例之后，可以启动、删除该主机实例，或从计算机中删除 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-124">After you stop a host instance, you can start it, delete it, or remove BizTalk Server from the computer.</span></span> <span data-ttu-id="3bc8b-125">有关启动主机实例的信息，请参阅[如何启动主机实例](../core/how-to-start-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-125">For information about starting a host instance, see [How to Start a Host Instance](../core/how-to-start-a-host-instance.md).</span></span> <span data-ttu-id="3bc8b-126">有关删除主机实例的信息，请参阅[如何删除主机实例](../core/how-to-delete-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="3bc8b-126">For information about deleting a host instance, see [How to Delete a Host Instance](../core/how-to-delete-a-host-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc8b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bc8b-127">See Also</span></span>  
 <span data-ttu-id="3bc8b-128">[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="3bc8b-128">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="3bc8b-129">[如何添加主机实例](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="3bc8b-129">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="3bc8b-130">[如何启动主机实例](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="3bc8b-130">[How to Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="3bc8b-131">[如何删除主机实例](../core/how-to-delete-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="3bc8b-131">[How to Delete a Host Instance](../core/how-to-delete-a-host-instance.md) </span></span>  
 [<span data-ttu-id="3bc8b-132">如何修改主机实例属性</span><span class="sxs-lookup"><span data-stu-id="3bc8b-132">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)