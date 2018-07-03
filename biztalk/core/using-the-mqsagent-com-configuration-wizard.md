---
title: 使用 MQSAgent COM + 配置向导 |Microsoft Docs
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
ms.openlocfilehash: d387229964f95ac5ab5bac0b890c28ce6a6db845
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996670"
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a><span data-ttu-id="171b0-102">使用 MQSAgent COM + 配置向导</span><span class="sxs-lookup"><span data-stu-id="171b0-102">Using the MQSAgent COM+ Configuration Wizard</span></span>
<span data-ttu-id="171b0-103">使用 MQSAgent COM+ 配置向导，可配置适配器的 COM+ 应用程序（MQSeries 组件）部分，即 MQSAgent。</span><span class="sxs-lookup"><span data-stu-id="171b0-103">The MQSAgent COM+ Configuration Wizard configures the MQSAgent, the COM+ application (MQSeries component) part of the adapter.</span></span> <span data-ttu-id="171b0-104">通过此向导可设置该组件的应用程序标识、角色名称和角色中包含的用户。</span><span class="sxs-lookup"><span data-stu-id="171b0-104">The wizard sets the application identity of the component, and the role name and users included in the role.</span></span> <span data-ttu-id="171b0-105">使用 MQSAgent COM + 配置向导创建的 MQSAgent COM + 组件的名称是**MQSAgent2**。</span><span class="sxs-lookup"><span data-stu-id="171b0-105">The name of the MQSAgent COM+ component created with the MQSAgent COM+ Configuration Wizard is **MQSAgent2**.</span></span>  

> [!NOTE]
>  <span data-ttu-id="171b0-106">64 位 Windows Server 支持 MQSAgent COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="171b0-106">The MQSAgent COM+ application is supported on a 64-bit Windows server.</span></span> <span data-ttu-id="171b0-107">该应用程序将以 32 位进程在 WOW64 下运行。</span><span class="sxs-lookup"><span data-stu-id="171b0-107">It will run as a 32-bit process under WOW64.</span></span> <span data-ttu-id="171b0-108">运行在 64 位版本 Windows Server 上的基于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机可以与安装有 MQSAgent 的远程 32 位计算机进行通信。</span><span class="sxs-lookup"><span data-stu-id="171b0-108">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-based computer that is running on a 64-bit version of Windows Server can communicate with a remote 32-bit computer that has the MQSAgent installed.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="171b0-109">MQSeries 代理和 MQSAgent COM + 配置向导可执行文件**MQSConfigWiz.exe**如果从 BizTalk Server 2009 升级到 BizTalk Server 将不会安装。</span><span class="sxs-lookup"><span data-stu-id="171b0-109">The MQSeries Agent and the MQSAgent COM+ Configuration Wizard executable **MQSConfigWiz.exe** are not installed if you upgrade from BizTalk Server 2009 to BizTalk Server.</span></span> <span data-ttu-id="171b0-110">从 BizTalk Server 2009 重新运行安装程序升级到 BizTalk Server，然后选择**修改**选项，然后选择 MQSeries 代理下要安装这些组件的其他软件。</span><span class="sxs-lookup"><span data-stu-id="171b0-110">After upgrading to BizTalk Server from BizTalk Server 2009 re-run setup, select the **Modify** option, and select the MQSeries Agent under the Additional Software to install these components.</span></span>  

## <a name="to-set-the-application-identity"></a><span data-ttu-id="171b0-111">设置应用程序标识</span><span class="sxs-lookup"><span data-stu-id="171b0-111">To set the application identity</span></span>  

-   <span data-ttu-id="171b0-112">使用**应用程序标识**MQSAgent COM + 配置向导，如下所示设置 mqsagent 的应用程序标识的页：</span><span class="sxs-lookup"><span data-stu-id="171b0-112">Use the **Application Identity** page of the MQSAgent COM+ Configuration Wizard to set the application identity for the MQSAgent as follows:</span></span>  

    |<span data-ttu-id="171b0-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="171b0-113">Use this</span></span>|<span data-ttu-id="171b0-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="171b0-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="171b0-115">**交互式用户**</span><span class="sxs-lookup"><span data-stu-id="171b0-115">**Interactive User**</span></span>|<span data-ttu-id="171b0-116">选择此选项可将当前登录帐户用于应用程序标识。</span><span class="sxs-lookup"><span data-stu-id="171b0-116">Select this option to use the current logon account for the application identity.</span></span>|  
    |<span data-ttu-id="171b0-117">**Local Service**</span><span class="sxs-lookup"><span data-stu-id="171b0-117">**Local Service**</span></span>|<span data-ttu-id="171b0-118">将应用程序标识设置为内置服务帐户。</span><span class="sxs-lookup"><span data-stu-id="171b0-118">Set the application identity to a built-in service account.</span></span>|  
    |<span data-ttu-id="171b0-119">**Network Service**</span><span class="sxs-lookup"><span data-stu-id="171b0-119">**Network Service**</span></span>|<span data-ttu-id="171b0-120">将应用程序标识设置为具有网络访问权限的内置帐户。</span><span class="sxs-lookup"><span data-stu-id="171b0-120">Set the application identity to a built-in account with network access.</span></span>|  
    |<span data-ttu-id="171b0-121">**此用户**</span><span class="sxs-lookup"><span data-stu-id="171b0-121">**This user**</span></span>|<span data-ttu-id="171b0-122">将应用程序标识设置为指定的用户名。</span><span class="sxs-lookup"><span data-stu-id="171b0-122">Set the application identity to the indicated user name.</span></span>|  

> [!NOTE]
>  <span data-ttu-id="171b0-123">建议你不要将具有管理权限的帐户用于应用程序标识。</span><span class="sxs-lookup"><span data-stu-id="171b0-123">It is not recommended that you use an account with administrative permissions for the application identity.</span></span> <span data-ttu-id="171b0-124">该帐户必须具有所需的最小权限： 读取和写入 MQSeries 队列的权限。</span><span class="sxs-lookup"><span data-stu-id="171b0-124">The account must have the minimal rights required: read and write permission for the MQSeries queues.</span></span>  

## <a name="to-name-the-role-and-add-users-to-it"></a><span data-ttu-id="171b0-125">对角色进行命名并向其添加用户</span><span class="sxs-lookup"><span data-stu-id="171b0-125">To name the role and add users to it</span></span>  

- <span data-ttu-id="171b0-126">使用**名称的角色**MQSAgent COM + 配置向导，如下所示将名称和用户分配到角色页：</span><span class="sxs-lookup"><span data-stu-id="171b0-126">Use the **Name of Role** page of the MQSAgent COM+ Configuration Wizard  to assign a name and users to the role as follows:</span></span>  


  |     <span data-ttu-id="171b0-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="171b0-127">Use this</span></span>     |                                                                         <span data-ttu-id="171b0-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="171b0-128">To do this</span></span>                                                                          |
  |------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | <span data-ttu-id="171b0-129">**角色的名称**</span><span class="sxs-lookup"><span data-stu-id="171b0-129">**Name of role**</span></span> |                                                                 <span data-ttu-id="171b0-130">键入角色的名称。</span><span class="sxs-lookup"><span data-stu-id="171b0-130">Type the name of the role.</span></span>                                                                  |
  |    <span data-ttu-id="171b0-131">**用户**</span><span class="sxs-lookup"><span data-stu-id="171b0-131">**Users**</span></span>     |                                                         <span data-ttu-id="171b0-132">显示属于该角色的用户。</span><span class="sxs-lookup"><span data-stu-id="171b0-132">Display the users that belong to the role.</span></span>                                                          |
  |     <span data-ttu-id="171b0-133">**“添加”**</span><span class="sxs-lookup"><span data-stu-id="171b0-133">**Add**</span></span>      | <span data-ttu-id="171b0-134">向该角色添加用户。</span><span class="sxs-lookup"><span data-stu-id="171b0-134">Add users to the role.</span></span> <span data-ttu-id="171b0-135">这些用户都是使用适配器的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务帐户。</span><span class="sxs-lookup"><span data-stu-id="171b0-135">These are the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service accounts using the adapter.</span></span> |

> [!NOTE]
>  <span data-ttu-id="171b0-136">仅向该角色添加需要访问适配器的帐户。</span><span class="sxs-lookup"><span data-stu-id="171b0-136">Add to the role only accounts requiring access to the adapter.</span></span>  

## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a><span data-ttu-id="171b0-137">将 Windows Server 2008 计算机上的 MSDTC 安全配置设置为“不要求进行验证”</span><span class="sxs-lookup"><span data-stu-id="171b0-137">To set the MSDTC Security configuration on the Windows Server 2008 computer to No Authentication Required</span></span>  
 <span data-ttu-id="171b0-138">如果在安装了 MQSAgent COM + 应用程序[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]上安装了计算机和 MQSeries 适配器 （这与 BizTalk Server 一起安装）[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机、 上的 MSDTC 安全配置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机必须设置为**不要求进行身份验证**。</span><span class="sxs-lookup"><span data-stu-id="171b0-138">If the MQSAgent COM+ application is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computer and the MQSeries Adapter (which is installed with BizTalk Server) is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer, the MSDTC Security configuration on the [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer must be set to **No Authentication Required**.</span></span> <span data-ttu-id="171b0-139">若要将 MSDTC 安全配置设置为“不要求进行验证”，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="171b0-139">Follow these steps to set the MSDTC security configuration to No Authentication Required:</span></span>  

1.  <span data-ttu-id="171b0-140">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="171b0-140">Click **Start** and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="171b0-141">双击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="171b0-141">Double-click **Administrative Tools**.</span></span>  

3.  <span data-ttu-id="171b0-142">双击**组件服务**以启动**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="171b0-142">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  

4.  <span data-ttu-id="171b0-143">展开**组件服务**，展开**计算机**，然后展开**我的电脑**。</span><span class="sxs-lookup"><span data-stu-id="171b0-143">Expand **Component Services**, expand **Computers**, and then expand **My Computer**.</span></span>  

5.  <span data-ttu-id="171b0-144">右键单击**我的电脑**然后单击**属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="171b0-144">Right-click **My Computer** and click the **Properties** menu item.</span></span>  

6.  <span data-ttu-id="171b0-145">在中**我的电脑**对话框中，单击**MSDTC**选项卡，然后单击**安全配置**。</span><span class="sxs-lookup"><span data-stu-id="171b0-145">In the **My Computer** dialog box, click the **MSDTC** tab and then click **Security Configuration**.</span></span>  

7.  <span data-ttu-id="171b0-146">在中**的安全配置**对话框中**事务管理器通信**部分中，选择**不要求进行身份验证**。</span><span class="sxs-lookup"><span data-stu-id="171b0-146">In the **Security Configuration** dialog box, in the **Transaction Manager Communication** section, select **No Authentication Required**.</span></span> <span data-ttu-id="171b0-147">如果系统提示您在对话框中，单击**是**以重新启动 MS DTC 服务。</span><span class="sxs-lookup"><span data-stu-id="171b0-147">If you are prompted with a dialog box, click **Yes** to restart the MS DTC Service.</span></span>  

8.  <span data-ttu-id="171b0-148">重新启动 MS DTC 服务后，单击**确定**然后单击**确定**以关闭**我的电脑**对话框。</span><span class="sxs-lookup"><span data-stu-id="171b0-148">After the MS DTC service has restarted, click **OK** and click **OK** again to close the **My Computer** dialog box.</span></span>  

9. <span data-ttu-id="171b0-149">关闭**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="171b0-149">Close the **Component Services** management interface.</span></span>  

## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a><span data-ttu-id="171b0-150">将 MQSAgent 运行时组件配置为在一组替代凭据下运行</span><span class="sxs-lookup"><span data-stu-id="171b0-150">To configure the MQSAgent runtime components to run under an alternative set of credentials</span></span>  
 <span data-ttu-id="171b0-151">MQSAgent COM+ 应用程序包括管理组件和运行时组件。</span><span class="sxs-lookup"><span data-stu-id="171b0-151">The MQSAgent COM+ application includes components for both administration and runtime.</span></span> <span data-ttu-id="171b0-152">如果出于安全目的想将此功能分隔到不同的 COM+ 应用程序中，请在安装 MQSAgent COM+ 应用程序的计算机上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="171b0-152">If you want to separate this functionality into different COM+ applications for security purposes, follow these steps on the computer that the MQSAgent COM+ application is installed on:</span></span>  

1.  <span data-ttu-id="171b0-153">启用 MQSAgent COM+ 组件的更改。</span><span class="sxs-lookup"><span data-stu-id="171b0-153">Enable changes for the MQSAgent COM+ component.</span></span>  

    -   <span data-ttu-id="171b0-154">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="171b0-154">Click **Start** and then click **Control Panel**.</span></span>  

    -   <span data-ttu-id="171b0-155">双击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="171b0-155">Double-click **Administrative Tools**.</span></span>  

    -   <span data-ttu-id="171b0-156">双击**组件服务**以启动**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="171b0-156">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  

    -   <span data-ttu-id="171b0-157">展开**组件服务**，展开**我的电脑**，展开**COM + 应用程序**，右键单击**MQSAgent2** COM + 应用程序然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="171b0-157">Expand **Component Services**, expand **My Computer**, expand **COM+ Applications**, right-click the **MQSAgent2** COM+ application and then click **Properties**.</span></span>  

    -   <span data-ttu-id="171b0-158">单击**高级**选项卡上，取消选中**禁用更改**。</span><span class="sxs-lookup"><span data-stu-id="171b0-158">Click the **Advanced** tab and uncheck **Disable changes**.</span></span>  

    -   <span data-ttu-id="171b0-159">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="171b0-159">Click **OK**.</span></span>  

2.  <span data-ttu-id="171b0-160">为 MQSAgent 运行时组件创建新 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="171b0-160">Create a new COM+ application for the MQSAgent runtime components.</span></span>  

    -   <span data-ttu-id="171b0-161">右键单击**COM + 应用程序**，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="171b0-161">Right-click **COM+ Applications**, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  

    -   <span data-ttu-id="171b0-162">单击**创建一个空应用程序**。</span><span class="sxs-lookup"><span data-stu-id="171b0-162">Click **Create an empty application**.</span></span>  

    -   <span data-ttu-id="171b0-163">输入的名称**MQSAgent2RunTime**，请保留为默认选项**服务器应用程序**启用，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="171b0-163">Enter the name **MQSAgent2RunTime**, leave the default option for **Server application** enabled and click **Next**.</span></span>  

    -   <span data-ttu-id="171b0-164">选择的选项**此用户**，输入相应的帐户信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="171b0-164">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  

        > [!NOTE]
        >  <span data-ttu-id="171b0-165">此帐户应具有**连接**并**放置**和/或**获取**上相应的 IBM WebSphere MQ Windows 队列的权限。</span><span class="sxs-lookup"><span data-stu-id="171b0-165">This account should have **connect** and **put** and/or **get** permissions on the appropriate IBM WebSphere MQ for Windows queues.</span></span> <span data-ttu-id="171b0-166">可以设置此帐户具有适当的权限**setmqaut**与 IBM WebSphere MQ 可用命令。</span><span class="sxs-lookup"><span data-stu-id="171b0-166">You can set the appropriate permissions for this account with the **setmqaut** command available with the IBM WebSphere MQ.</span></span> <span data-ttu-id="171b0-167">有关详细信息**setmqaut**命令，请参阅 IBM WebSphere MQ 文档。</span><span class="sxs-lookup"><span data-stu-id="171b0-167">For more information about the **setmqaut** command see the IBM WebSphere MQ documentation.</span></span>  

    -   <span data-ttu-id="171b0-168">单击**下一步**上**添加应用程序角色**对话框。</span><span class="sxs-lookup"><span data-stu-id="171b0-168">Click **Next** on the **Add Application Roles** dialog box.</span></span>  

    -   <span data-ttu-id="171b0-169">单击**下一步**上**向角色添加用户**对话框。</span><span class="sxs-lookup"><span data-stu-id="171b0-169">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  

    -   <span data-ttu-id="171b0-170">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="171b0-170">Click **Finish**.</span></span>  

3.  <span data-ttu-id="171b0-171">将运行时组件移至新的 COM+ 应用程序</span><span class="sxs-lookup"><span data-stu-id="171b0-171">Move the runtime components to the new COM+ application</span></span>  

    -   <span data-ttu-id="171b0-172">展开**MQSAgent2** COM + 应用程序。</span><span class="sxs-lookup"><span data-stu-id="171b0-172">Expand the **MQSAgent2** COM+ application.</span></span>  

    -   <span data-ttu-id="171b0-173">展开**组件**。</span><span class="sxs-lookup"><span data-stu-id="171b0-173">Expand **Components**.</span></span>  

    -   <span data-ttu-id="171b0-174">右键单击**MQSAgent2.MQSAgent.1**组件，然后单击**移动**以显示**移动组件 (s)** 对话框。</span><span class="sxs-lookup"><span data-stu-id="171b0-174">Right-click the **MQSAgent2.MQSAgent.1** component and click **Move** to display the **Move components(s)** dialog box.</span></span>  

    -   <span data-ttu-id="171b0-175">选择**MQSAgent2RunTime**下**请选择一个目标**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="171b0-175">Select **MQSAgent2RunTime** under **Please select a destination** and click **OK**.</span></span>  

    -   <span data-ttu-id="171b0-176">重复这些步骤**MQSAgent2.MQSBroker.1**并**MQSAgent2.MQSProxy.1**组件。</span><span class="sxs-lookup"><span data-stu-id="171b0-176">Repeat these steps for the **MQSAgent2.MQSBroker.1** and **MQSAgent2.MQSProxy.1** components.</span></span>  

## <a name="see-also"></a><span data-ttu-id="171b0-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="171b0-177">See Also</span></span>  
 <span data-ttu-id="171b0-178">[如何配置 MQSeries 适配器发送和接收处理程序](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="171b0-178">[How to Configure MQSeries Adapter Send and Receive Handlers](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span></span>  
 [<span data-ttu-id="171b0-179">配置 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="171b0-179">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)