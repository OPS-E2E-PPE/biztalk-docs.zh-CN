---
title: 删除主机实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35a06480-0962-4bdc-add2-56f979a2f1c9
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 472dac5fe3f4cf71431ad670b87aa3a1958abf9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338792"
---
# <a name="delete-a-host-instance"></a><span data-ttu-id="81ec5-102">删除主机实例</span><span class="sxs-lookup"><span data-stu-id="81ec5-102">Delete a Host Instance</span></span>

## <a name="overview"></a><span data-ttu-id="81ec5-103">概述</span><span class="sxs-lookup"><span data-stu-id="81ec5-103">Overview</span></span>
<span data-ttu-id="81ec5-104">可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 Windows Management Instrumentation (WMI) 来删除主机实例。</span><span class="sxs-lookup"><span data-stu-id="81ec5-104">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or Windows Management Instrumentation (WMI) to delete host instances.</span></span> <span data-ttu-id="81ec5-105">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="81ec5-105">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span> <span data-ttu-id="81ec5-106">有关使用 WMI 删除主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="81ec5-106">For information about using WMI to delete a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="81ec5-107">删除主机实例时，从关联的服务器中删除 BizTalk Server 运行时的实例和更新 BizTalk 管理数据库以从主机中删除该实例。</span><span class="sxs-lookup"><span data-stu-id="81ec5-107">When you delete a host instance, the instance of the BizTalk Server runtime is removed from the associated server and the BizTalk Management database is updated to remove that instance from the host.</span></span>  
  
 <span data-ttu-id="81ec5-108">若要避免在删除主机实例时丢失消息，BizTalk Server 完成所有处理，就该实例实际上会删除。</span><span class="sxs-lookup"><span data-stu-id="81ec5-108">To avoid losing messages when you delete a host instance, BizTalk Server completes all processing before the instance is actually removed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="81ec5-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="81ec5-109">Prerequisites</span></span>  
 <span data-ttu-id="81ec5-110">若要执行此过程，必须以 Administrators 组和 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="81ec5-110">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="81ec5-111">此外，您还必须是 db_securityadmin SQL Server 数据库角色和以下数据库所在的服务器上的 securityadmin SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="81ec5-111">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="81ec5-112">BAM 主导入 (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="81ec5-112">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="81ec5-113">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="81ec5-113">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="81ec5-114">BizTalk MessageBox (BizTalkMsgBoxDb) （全部）</span><span class="sxs-lookup"><span data-stu-id="81ec5-114">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="81ec5-115">BizTalk 跟踪 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="81ec5-115">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="81ec5-116">规则引擎 (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="81ec5-116">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="81ec5-117">我们建议使用 BizTalk Server 管理控制台或 Windows Management Instrumentation (WMI) 脚本更新主机实例的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="81ec5-117">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="81ec5-118">这可确保 BizTalk Server 可以更新 BizTalk Server 数据库中的帐户信息并保持数据库和同步的主机实例之间的安全配置。</span><span class="sxs-lookup"><span data-stu-id="81ec5-118">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="81ec5-119">步骤</span><span class="sxs-lookup"><span data-stu-id="81ec5-119">Steps</span></span>
  
1. <span data-ttu-id="81ec5-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="81ec5-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="81ec5-121">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="81ec5-121">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="81ec5-122">在详细信息窗格中，右键单击你想要删除，然后单击该主机实例**删除**。</span><span class="sxs-lookup"><span data-stu-id="81ec5-122">In the details pane, right-click the host instance you want to delete, and then click **Delete**.</span></span>  
  
4. <span data-ttu-id="81ec5-123">在中**确认删除主机实例**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="81ec5-123">In the **Confirm delete host instance** dialog box, click **Yes**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="81ec5-124">如果 BizTalk Server 无法删除主机实例，则会出现对话框，可以在其中强制删除该主机实例。</span><span class="sxs-lookup"><span data-stu-id="81ec5-124">If BizTalk Server cannot delete the host instance, a dialog box appears in which you can force the deletion of the host instance.</span></span> <span data-ttu-id="81ec5-125">阅读完后提供的信息，请单击**是**以删除该主机实例。</span><span class="sxs-lookup"><span data-stu-id="81ec5-125">After reading the information provided, click **Yes** to delete the host instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ec5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="81ec5-126">See Also</span></span>  
 <span data-ttu-id="81ec5-127">[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="81ec5-127">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="81ec5-128">[如何添加主机实例](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="81ec5-128">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="81ec5-129">[如何启动主机实例](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="81ec5-129">[How to Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="81ec5-130">[如何停止主机实例](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="81ec5-130">[How to Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 [<span data-ttu-id="81ec5-131">如何修改主机实例属性</span><span class="sxs-lookup"><span data-stu-id="81ec5-131">How to Modify Host Instance Properties</span></span>](../core/how-to-modify-host-instance-properties.md)