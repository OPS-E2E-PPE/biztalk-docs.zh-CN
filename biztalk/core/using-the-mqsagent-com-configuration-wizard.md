---
title: 使用 MQSAgent COM + 配置向导 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mqsagent.wizard
helpviewer_keywords:
- MQSeries adapters, MQSAgent COM+ Configuration Wizard
- configuring [MQSeries adapters], MQSAgent COM+ Configuration Wizard
- MQSAgent COM+ Configuration Wizard
ms.assetid: f106700a-7f57-4c83-9344-6525fc10544d
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6e8b625bcc3accbefda193c52459616691c265
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a><span data-ttu-id="6ddcc-102">使用 MQSAgent COM + 配置向导</span><span class="sxs-lookup"><span data-stu-id="6ddcc-102">Using the MQSAgent COM+ Configuration Wizard</span></span>
<span data-ttu-id="6ddcc-103">使用 MQSAgent COM+ 配置向导，可配置适配器的 COM+ 应用程序（MQSeries 组件）部分，即 MQSAgent。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-103">The MQSAgent COM+ Configuration Wizard configures the MQSAgent, the COM+ application (MQSeries component) part of the adapter.</span></span> <span data-ttu-id="6ddcc-104">通过此向导可设置该组件的应用程序标识、角色名称和角色中包含的用户。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-104">The wizard sets the application identity of the component, and the role name and users included in the role.</span></span> <span data-ttu-id="6ddcc-105">使用 MQSAgent COM + 配置向导创建 MQSAgent COM + 组件的名称是**MQSAgent2**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-105">The name of the MQSAgent COM+ component created with the MQSAgent COM+ Configuration Wizard is **MQSAgent2**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ddcc-106">64 位 Windows Server 支持 MQSAgent COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-106">The MQSAgent COM+ application is supported on a 64-bit Windows server.</span></span> <span data-ttu-id="6ddcc-107">该应用程序将以 32 位进程在 WOW64 下运行。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-107">It will run as a 32-bit process under WOW64.</span></span> <span data-ttu-id="6ddcc-108">运行在 64 位版本 Windows Server 上的基于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机可以与安装有 MQSAgent 的远程 32 位计算机进行通信。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-108">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-based computer that is running on a 64-bit version of Windows Server can communicate with a remote 32-bit computer that has the MQSAgent installed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ddcc-109">MQSeries 代理和 MQSAgent COM + 配置向导可执行文件**MQSConfigWiz.exe**未从 BizTalk Server 2009 升级到 BizTalk Server 安装。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-109">The MQSeries Agent and the MQSAgent COM+ Configuration Wizard executable **MQSConfigWiz.exe** are not installed if you upgrade from BizTalk Server 2009 to BizTalk Server.</span></span> <span data-ttu-id="6ddcc-110">从 BizTalk Server 2009 重新运行安装程序，升级到 BizTalk Server 之后, 选择**修改**选项，然后选择要安装这些组件的其他软件下 MQSeries 代理。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-110">After upgrading to BizTalk Server from BizTalk Server 2009 re-run setup, select the **Modify** option, and select the MQSeries Agent under the Additional Software to install these components.</span></span>  
  
## <a name="to-set-the-application-identity"></a><span data-ttu-id="6ddcc-111">设置应用程序标识</span><span class="sxs-lookup"><span data-stu-id="6ddcc-111">To set the application identity</span></span>  
  
-   <span data-ttu-id="6ddcc-112">使用**应用程序标识**MQSAgent COM + 配置向导页面，如下所示为 MQSAgent 设置应用程序标识：</span><span class="sxs-lookup"><span data-stu-id="6ddcc-112">Use the **Application Identity** page of the MQSAgent COM+ Configuration Wizard to set the application identity for the MQSAgent as follows:</span></span>  
  
    |<span data-ttu-id="6ddcc-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6ddcc-113">Use this</span></span>|<span data-ttu-id="6ddcc-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6ddcc-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ddcc-115">**交互式用户**</span><span class="sxs-lookup"><span data-stu-id="6ddcc-115">**Interactive User**</span></span>|<span data-ttu-id="6ddcc-116">选择此选项可将当前登录帐户用于应用程序标识。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-116">Select this option to use the current logon account for the application identity.</span></span>|  
    |<span data-ttu-id="6ddcc-117">**Local Service**</span><span class="sxs-lookup"><span data-stu-id="6ddcc-117">**Local Service**</span></span>|<span data-ttu-id="6ddcc-118">将应用程序标识设置为内置服务帐户。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-118">Set the application identity to a built-in service account.</span></span>|  
    |<span data-ttu-id="6ddcc-119">**Network Service**</span><span class="sxs-lookup"><span data-stu-id="6ddcc-119">**Network Service**</span></span>|<span data-ttu-id="6ddcc-120">将应用程序标识设置为具有网络访问权限的内置帐户。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-120">Set the application identity to a built-in account with network access.</span></span>|  
    |<span data-ttu-id="6ddcc-121">**此用户**</span><span class="sxs-lookup"><span data-stu-id="6ddcc-121">**This user**</span></span>|<span data-ttu-id="6ddcc-122">将应用程序标识设置为指定的用户名。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-122">Set the application identity to the indicated user name.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6ddcc-123">建议你不要将具有管理权限的帐户用于应用程序标识。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-123">It is not recommended that you use an account with administrative permissions for the application identity.</span></span> <span data-ttu-id="6ddcc-124">帐户必须具有所需的最小权限： 读取和写入 MQSeries 队列的权限。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-124">The account must have the minimal rights required: read and write permission for the MQSeries queues.</span></span>  
  
## <a name="to-name-the-role-and-add-users-to-it"></a><span data-ttu-id="6ddcc-125">对角色进行命名并向其添加用户</span><span class="sxs-lookup"><span data-stu-id="6ddcc-125">To name the role and add users to it</span></span>  
  
-   <span data-ttu-id="6ddcc-126">使用**名称的角色**MQSAgent COM + 配置向导页面，如下所示将名称和用户分配给角色：</span><span class="sxs-lookup"><span data-stu-id="6ddcc-126">Use the **Name of Role** page of the MQSAgent COM+ Configuration Wizard  to assign a name and users to the role as follows:</span></span>  
  
    |<span data-ttu-id="6ddcc-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6ddcc-127">Use this</span></span>|<span data-ttu-id="6ddcc-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6ddcc-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6ddcc-129">**角色名称**</span><span class="sxs-lookup"><span data-stu-id="6ddcc-129">**Name of role**</span></span>|<span data-ttu-id="6ddcc-130">键入角色的名称。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-130">Type the name of the role.</span></span>|  
    |<span data-ttu-id="6ddcc-131">**用户**</span><span class="sxs-lookup"><span data-stu-id="6ddcc-131">**Users**</span></span>|<span data-ttu-id="6ddcc-132">显示属于该角色的用户。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-132">Display the users that belong to the role.</span></span>|  
    |<span data-ttu-id="6ddcc-133">**添加**</span><span class="sxs-lookup"><span data-stu-id="6ddcc-133">**Add**</span></span>|<span data-ttu-id="6ddcc-134">向该角色添加用户。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-134">Add users to the role.</span></span> <span data-ttu-id="6ddcc-135">这些用户都是使用适配器的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-135">These are the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service accounts using the adapter.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="6ddcc-136">仅向该角色添加需要访问适配器的帐户。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-136">Add to the role only accounts requiring access to the adapter.</span></span>  
  
## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a><span data-ttu-id="6ddcc-137">将 Windows Server 2008 计算机上的 MSDTC 安全配置设置为“不要求进行验证”</span><span class="sxs-lookup"><span data-stu-id="6ddcc-137">To set the MSDTC Security configuration on the Windows Server 2008 computer to No Authentication Required</span></span>  
 <span data-ttu-id="6ddcc-138">如果 MQSAgent COM + 应用程序安装在[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]上安装了计算机和将 MQSeries 适配器 （已安装与 BizTalk Server）[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机、 上的 MSDTC 安全配置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机必须设置为**不要求进行验证**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-138">If the MQSAgent COM+ application is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computer and the MQSeries Adapter (which is installed with BizTalk Server) is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer, the MSDTC Security configuration on the [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer must be set to **No Authentication Required**.</span></span> <span data-ttu-id="6ddcc-139">若要将 MSDTC 安全配置设置为“不要求进行验证”，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="6ddcc-139">Follow these steps to set the MSDTC security configuration to No Authentication Required:</span></span>  
  
1.  <span data-ttu-id="6ddcc-140">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-140">Click **Start** and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="6ddcc-141">双击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-141">Double-click **Administrative Tools**.</span></span>  
  
3.  <span data-ttu-id="6ddcc-142">双击**组件服务**以启动**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-142">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  
  
4.  <span data-ttu-id="6ddcc-143">展开**组件服务**，展开**计算机**，然后展开**我的电脑**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-143">Expand **Component Services**, expand **Computers**, and then expand **My Computer**.</span></span>  
  
5.  <span data-ttu-id="6ddcc-144">右键单击**我的电脑**单击**属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-144">Right-click **My Computer** and click the **Properties** menu item.</span></span>  
  
6.  <span data-ttu-id="6ddcc-145">在**我的电脑**对话框中，单击**MSDTC**选项卡，然后单击**安全配置**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-145">In the **My Computer** dialog box, click the **MSDTC** tab and then click **Security Configuration**.</span></span>  
  
7.  <span data-ttu-id="6ddcc-146">在**安全配置**对话框中，在**事务管理器通信**部分中，选择**不要求进行验证**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-146">In the **Security Configuration** dialog box, in the **Transaction Manager Communication** section, select **No Authentication Required**.</span></span> <span data-ttu-id="6ddcc-147">如果系统提示您对话框中，单击**是**重新启动 MS DTC 服务。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-147">If you are prompted with a dialog box, click **Yes** to restart the MS DTC Service.</span></span>  
  
8.  <span data-ttu-id="6ddcc-148">重新启动 MS DTC 服务后，单击**确定**单击**确定**以关闭**我的电脑**对话框。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-148">After the MS DTC service has restarted, click **OK** and click **OK** again to close the **My Computer** dialog box.</span></span>  
  
9. <span data-ttu-id="6ddcc-149">关闭**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-149">Close the **Component Services** management interface.</span></span>  
  
## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a><span data-ttu-id="6ddcc-150">将 MQSAgent 运行时组件配置为在一组替代凭据下运行</span><span class="sxs-lookup"><span data-stu-id="6ddcc-150">To configure the MQSAgent runtime components to run under an alternative set of credentials</span></span>  
 <span data-ttu-id="6ddcc-151">MQSAgent COM+ 应用程序包括管理组件和运行时组件。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-151">The MQSAgent COM+ application includes components for both administration and runtime.</span></span> <span data-ttu-id="6ddcc-152">如果出于安全目的想将此功能分隔到不同的 COM+ 应用程序中，请在安装 MQSAgent COM+ 应用程序的计算机上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6ddcc-152">If you want to separate this functionality into different COM+ applications for security purposes, follow these steps on the computer that the MQSAgent COM+ application is installed on:</span></span>  
  
1.  <span data-ttu-id="6ddcc-153">启用 MQSAgent COM+ 组件的更改。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-153">Enable changes for the MQSAgent COM+ component.</span></span>  
  
    -   <span data-ttu-id="6ddcc-154">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-154">Click **Start** and then click **Control Panel**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-155">双击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-155">Double-click **Administrative Tools**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-156">双击**组件服务**以启动**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-156">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  
  
    -   <span data-ttu-id="6ddcc-157">展开**组件服务**，展开**我的电脑**，展开**COM + 应用程序**，右键单击**MQSAgent2** COM + 应用程序然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-157">Expand **Component Services**, expand **My Computer**, expand **COM+ Applications**, right-click the **MQSAgent2** COM+ application and then click **Properties**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-158">单击**高级**选项卡上，并取消选中**禁用更改**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-158">Click the **Advanced** tab and uncheck **Disable changes**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-159">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-159">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="6ddcc-160">为 MQSAgent 运行时组件创建新 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-160">Create a new COM+ application for the MQSAgent runtime components.</span></span>  
  
    -   <span data-ttu-id="6ddcc-161">右键单击**COM + 应用程序**，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-161">Right-click **COM+ Applications**, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-162">单击**创建空的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-162">Click **Create an empty application**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-163">输入的名称**MQSAgent2RunTime**，保留默认选项为**服务器应用程序**启用和单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-163">Enter the name **MQSAgent2RunTime**, leave the default option for **Server application** enabled and click **Next**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-164">选择的选项**此用户**，输入合适的帐户信息，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-164">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6ddcc-165">此帐户应具有**连接**和**放**和/或**获取**上适当的 IBM WebSphere MQ Windows 队列的权限。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-165">This account should have **connect** and **put** and/or **get** permissions on the appropriate IBM WebSphere MQ for Windows queues.</span></span> <span data-ttu-id="6ddcc-166">你可以设置与此帐户的适当权限**setmqaut**适用于 IBM WebSphere MQ 命令。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-166">You can set the appropriate permissions for this account with the **setmqaut** command available with the IBM WebSphere MQ.</span></span> <span data-ttu-id="6ddcc-167">有关详细信息**setmqaut**命令，请参阅 IBM WebSphere MQ 文档。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-167">For more information about the **setmqaut** command see the IBM WebSphere MQ documentation.</span></span>  
  
    -   <span data-ttu-id="6ddcc-168">单击**下一步**上**添加应用程序角色**对话框。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-168">Click **Next** on the **Add Application Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="6ddcc-169">单击**下一步**上**向角色添加用户**对话框。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-169">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  
  
    -   <span data-ttu-id="6ddcc-170">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-170">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="6ddcc-171">将运行时组件移至新的 COM+ 应用程序</span><span class="sxs-lookup"><span data-stu-id="6ddcc-171">Move the runtime components to the new COM+ application</span></span>  
  
    -   <span data-ttu-id="6ddcc-172">展开**MQSAgent2** COM + 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-172">Expand the **MQSAgent2** COM+ application.</span></span>  
  
    -   <span data-ttu-id="6ddcc-173">展开**组件**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-173">Expand **Components**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-174">右键单击**MQSAgent2.MQSAgent.1**组件，并单击**移动**以显示**移动组件 (s)**对话框。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-174">Right-click the **MQSAgent2.MQSAgent.1** component and click **Move** to display the **Move components(s)** dialog box.</span></span>  
  
    -   <span data-ttu-id="6ddcc-175">选择**MQSAgent2RunTime**下**请选择一个目标**单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-175">Select **MQSAgent2RunTime** under **Please select a destination** and click **OK**.</span></span>  
  
    -   <span data-ttu-id="6ddcc-176">重复上述步骤**MQSAgent2.MQSBroker.1**和**MQSAgent2.MQSProxy.1**组件。</span><span class="sxs-lookup"><span data-stu-id="6ddcc-176">Repeat these steps for the **MQSAgent2.MQSBroker.1** and **MQSAgent2.MQSProxy.1** components.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ddcc-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ddcc-177">See Also</span></span>  
 <span data-ttu-id="6ddcc-178">[如何配置 MQSeries 适配器发送和接收处理程序](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="6ddcc-178">[How to Configure MQSeries Adapter Send and Receive Handlers](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span></span>  
 [<span data-ttu-id="6ddcc-179">配置 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="6ddcc-179">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)