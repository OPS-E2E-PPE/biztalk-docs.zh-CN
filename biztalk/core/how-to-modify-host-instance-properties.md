---
title: 更改主机实例属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a35ca0c8-89b3-483a-b2fc-c8f43a8864d1
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a64257f752e161963539256dcaca3f7f8f1077
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003342"
---
# <a name="update-host-instance-properties"></a><span data-ttu-id="c96e3-102">更新主机实例属性</span><span class="sxs-lookup"><span data-stu-id="c96e3-102">Update Host Instance Properties</span></span>

## <a name="overview"></a><span data-ttu-id="c96e3-103">概述</span><span class="sxs-lookup"><span data-stu-id="c96e3-103">Overview</span></span>
<span data-ttu-id="c96e3-104">可以使用 BizTalk Server 管理控制台或 Windows 管理规范 (WMI) 来修改主机实例。</span><span class="sxs-lookup"><span data-stu-id="c96e3-104">You can use the BizTalk Server Administration Console or Windows Management Instrumentation (WMI) to modify host instances.</span></span> <span data-ttu-id="c96e3-105">可以修改运行主机实例的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="c96e3-105">You can modify the service account running a host instance.</span></span> <span data-ttu-id="c96e3-106">还可以禁用主机实例。</span><span class="sxs-lookup"><span data-stu-id="c96e3-106">You can also disable a host instance.</span></span> <span data-ttu-id="c96e3-107">例如，如果要保留主机实例的设置并且不想启动它，则可以将其禁用。</span><span class="sxs-lookup"><span data-stu-id="c96e3-107">For example, if you want to preserve the settings for a host instance and you do not want it to start, you can disable it.</span></span> <span data-ttu-id="c96e3-108">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="c96e3-108">For more information about host instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="c96e3-109">受信任主机和非信任主机的实例不能使用相同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="c96e3-109">Host instances of trusted hosts and host instances of non-trusted hosts cannot use the same service accounts.</span></span> <span data-ttu-id="c96e3-110">如果希望更改某个主机实例的信任设置，并且该主机实例与其他主机实例使用了相同的服务帐户，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="c96e3-110">If you want to change the trust setting of a host instance and the host instance uses a service account that other host instances use, you can do one of the following:</span></span>  
  
-   <span data-ttu-id="c96e3-111">对于要更改信任设置的主机实例，可以将其服务帐户更改为新的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="c96e3-111">You can change the service account of the host instance for which you want to change the trust settings to a new service account.</span></span>  
  
-   <span data-ttu-id="c96e3-112">可以将主机实例的服务帐户更改为具有相同信任设置的其他主机实例所用的现有服务帐户。</span><span class="sxs-lookup"><span data-stu-id="c96e3-112">You can change the service account of the host instance to an existing service account that other host instances with the same trust setting use.</span></span>  
  
-   <span data-ttu-id="c96e3-113">可以删除主机实例，然后使用不同的信任设置和服务帐户重新进行创建。</span><span class="sxs-lookup"><span data-stu-id="c96e3-113">You can delete the host instance, and re-create it with a different trust setting and service account.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c96e3-114">必须通过更新主机实例的属性来更改主机实例的凭据。</span><span class="sxs-lookup"><span data-stu-id="c96e3-114">You must change the credentials for a host instance by updating the properties of the host instance.</span></span> <span data-ttu-id="c96e3-115">如果更改相应服务的凭据，则为主机实例指定的服务帐户必须是主机上的组的成员。</span><span class="sxs-lookup"><span data-stu-id="c96e3-115">If you change the credentials of the corresponding service, the service account you specify for the host instance must be a member of the group on the host.</span></span> <span data-ttu-id="c96e3-116">不要使用服务管理单元或计算机管理控制台来更改主机实例的凭据，否则，主机实例可能无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="c96e3-116">Do not use the Services snap-in or the Computer Management console to change the credentials of host instance, otherwise the host instance may not function properly.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c96e3-117">如果更改主机实例的凭据，则还必须更改相应的 SQL Server 凭据。</span><span class="sxs-lookup"><span data-stu-id="c96e3-117">If you change the credentials of a host instance, you must also change the corresponding SQL Server credentials.</span></span> <span data-ttu-id="c96e3-118">如果不更新 SQL Server 凭据，则主机实例将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="c96e3-118">If you do not update the SQL Server credentials, the host instance will not function properly.</span></span>  
  
 <span data-ttu-id="c96e3-119">有关使用 WMI 修改主机实例的信息，请参阅**MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="c96e3-119">For information about using WMI to modify a host instance, see **MSBTS_HostInstance (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="c96e3-120">必要條件</span><span class="sxs-lookup"><span data-stu-id="c96e3-120">Prerequisites</span></span>  
 <span data-ttu-id="c96e3-121">若要执行此过程，则必须以 Administrators 组和 BizTalk Server Administrators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="c96e3-121">To perform this procedure, you must be logged on as a member of the Administrators group and the BizTalk Server Administrators group.</span></span>  
  
 <span data-ttu-id="c96e3-122">此外，您还必需是以下数据库所在服务器上的 db_securityadmin SQL Server 数据库角色和 securityadmin SQL Server 角色的成员：</span><span class="sxs-lookup"><span data-stu-id="c96e3-122">In addition, you must also be a member of the db_securityadmin SQL Server Database role and the securityadmin SQL Server Role on the server(s) where the following databases are:</span></span>  
  
-   <span data-ttu-id="c96e3-123">BAM 主导入 (BAMPrimaryImport)</span><span class="sxs-lookup"><span data-stu-id="c96e3-123">BAM Primary Import (BAMPrimaryImport)</span></span>  
  
-   <span data-ttu-id="c96e3-124">BizTalk 管理 (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="c96e3-124">BizTalk Management (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="c96e3-125">BizTalk MessageBox (BizTalkMsgBoxDb)（全部）</span><span class="sxs-lookup"><span data-stu-id="c96e3-125">BizTalk MessageBox (BizTalkMsgBoxDb) (all)</span></span>  
  
-   <span data-ttu-id="c96e3-126">BizTalk 跟踪 (BizTalk DTADb)</span><span class="sxs-lookup"><span data-stu-id="c96e3-126">BizTalk Tracking (BizTalk DTADb)</span></span>  
  
-   <span data-ttu-id="c96e3-127">规则引擎 (BizTalkRuleEngineDb)</span><span class="sxs-lookup"><span data-stu-id="c96e3-127">Rule Engine (BizTalkRuleEngineDb)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c96e3-128">建议使用 BizTalk Server 管理控制台或 Windows 管理规范 (WMI) 脚本来更新主机实例的帐户信息。</span><span class="sxs-lookup"><span data-stu-id="c96e3-128">We recommend that you update account information for host instances by using the BizTalk Server Administration Console or a Windows Management Instrumentation (WMI) script.</span></span> <span data-ttu-id="c96e3-129">这样可以确保 BizTalk Server 能够更新 BizTalk Server 数据库中的帐户信息，并在数据库与主机实例之间保持安全配置同步。</span><span class="sxs-lookup"><span data-stu-id="c96e3-129">This ensures that BizTalk Server can update the account information in the BizTalk Server databases and keep the security configuration between the databases and host instance synchronized.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="c96e3-130">步骤</span><span class="sxs-lookup"><span data-stu-id="c96e3-130">Steps</span></span>
  
1. <span data-ttu-id="c96e3-131">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="c96e3-131">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c96e3-132">在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，单击**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="c96e3-132">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, click **Platform Settings**, and then click **Host Instances**.</span></span>  
  
3. <span data-ttu-id="c96e3-133">在详细信息窗格中，右键单击你想要修改，然后单击该主机实例**属性**。</span><span class="sxs-lookup"><span data-stu-id="c96e3-133">In the details pane, right-click the host instance you want to modify, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="c96e3-134">在中**主机实例属性**对话框中，单击**配置**若要修改的服务帐户信息。</span><span class="sxs-lookup"><span data-stu-id="c96e3-134">In the **Host Instance Properties** dialog box, click **Configure** to modify the service account information.</span></span>  
  
5. <span data-ttu-id="c96e3-135">在中**登录凭据**对话框框中，输入帐户名和密码的帐户的主机实例将在其下运行，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="c96e3-135">In the **Logon Credentials** dialog box, enter the account name and password of the account under which the host instance will run, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="c96e3-136">在中**主机实例属性**对话框中，执行以下操作，然后依次**确定**:</span><span class="sxs-lookup"><span data-stu-id="c96e3-136">In the **Host Instance Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="c96e3-137">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c96e3-137">Use this</span></span>|<span data-ttu-id="c96e3-138">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c96e3-138">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="c96e3-139">**主机名**</span><span class="sxs-lookup"><span data-stu-id="c96e3-139">**Host name**</span></span>|<span data-ttu-id="c96e3-140">显示与所选服务器关联的主机名称。</span><span class="sxs-lookup"><span data-stu-id="c96e3-140">Displays the name of the host associated with the selected server.</span></span>|  
   |<span data-ttu-id="c96e3-141">**Server**</span><span class="sxs-lookup"><span data-stu-id="c96e3-141">**Server**</span></span>|<span data-ttu-id="c96e3-142">显示与所选主机关联的服务器。</span><span class="sxs-lookup"><span data-stu-id="c96e3-142">Displays the server associated with the selected host.</span></span>|  
   |<span data-ttu-id="c96e3-143">**登录**</span><span class="sxs-lookup"><span data-stu-id="c96e3-143">**Logon**</span></span>|<span data-ttu-id="c96e3-144">显示用于运行主机实例的新服务帐户的帐户名。</span><span class="sxs-lookup"><span data-stu-id="c96e3-144">Displays the account name of the new service account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="c96e3-145">**配置**</span><span class="sxs-lookup"><span data-stu-id="c96e3-145">**Configure**</span></span>|<span data-ttu-id="c96e3-146">单击此项可显示**登录凭据**对话框框中，您可以在其中输入帐户名称和主机实例将运行的帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="c96e3-146">Click to display the **Logon Credentials** dialog box, where you can enter the account name and password of the account under which the host instance will run.</span></span>|  
   |<span data-ttu-id="c96e3-147">**禁止主机实例启动**</span><span class="sxs-lookup"><span data-stu-id="c96e3-147">**Disable host instance from starting**</span></span>|<span data-ttu-id="c96e3-148">选中此复选框可将所选主机的状态从“已启用”改为“已禁用”。</span><span class="sxs-lookup"><span data-stu-id="c96e3-148">Select this check box to change the status of the selected host from enabled to disabled.</span></span> <span data-ttu-id="c96e3-149">如果不希望启动主机实例，但还要保留其设置，禁用主机实例就十分有用。</span><span class="sxs-lookup"><span data-stu-id="c96e3-149">Disabling a host instance is useful if you do not want the host instance to start, but you do want to preserve its settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c96e3-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="c96e3-150">See Also</span></span>  
 <span data-ttu-id="c96e3-151">[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="c96e3-151">[Managing BizTalk Hosts and Host Instances](../core/managing-biztalk-hosts-and-host-instances.md) </span></span>  
 <span data-ttu-id="c96e3-152">[添加主机实例](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c96e3-152">[Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 <span data-ttu-id="c96e3-153">[启动主机实例](../core/how-to-start-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c96e3-153">[Start a Host Instance](../core/how-to-start-a-host-instance.md) </span></span>  
 <span data-ttu-id="c96e3-154">[停止主机实例](../core/how-to-stop-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c96e3-154">[Stop a Host Instance](../core/how-to-stop-a-host-instance.md) </span></span>  
 [<span data-ttu-id="c96e3-155">删除主机实例</span><span class="sxs-lookup"><span data-stu-id="c96e3-155">Delete a Host Instance</span></span>](../core/how-to-delete-a-host-instance.md)