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
ms.openlocfilehash: 0f304039d0d6d68d12bfc7605cba69bb01e22ca7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395993"
---
# <a name="using-the-mqsagent-com-configuration-wizard"></a><span data-ttu-id="178da-102">使用 MQSAgent COM + 配置向导</span><span class="sxs-lookup"><span data-stu-id="178da-102">Using the MQSAgent COM+ Configuration Wizard</span></span>
<span data-ttu-id="178da-103">MQSAgent COM + 配置向导配置 MQSAgent COM + 应用程序 （MQSeries 组件） 适配器的部分。</span><span class="sxs-lookup"><span data-stu-id="178da-103">The MQSAgent COM+ Configuration Wizard configures the MQSAgent, the COM+ application (MQSeries component) part of the adapter.</span></span> <span data-ttu-id="178da-104">该向导设置组件的角色名称和用户角色中包含的应用程序标识。</span><span class="sxs-lookup"><span data-stu-id="178da-104">The wizard sets the application identity of the component, and the role name and users included in the role.</span></span> <span data-ttu-id="178da-105">使用 MQSAgent COM + 配置向导创建的 MQSAgent COM + 组件的名称是**MQSAgent2**。</span><span class="sxs-lookup"><span data-stu-id="178da-105">The name of the MQSAgent COM+ component created with the MQSAgent COM+ Configuration Wizard is **MQSAgent2**.</span></span>  

> [!NOTE]
>  <span data-ttu-id="178da-106">64 位 Windows server 支持 MQSAgent COM + 应用程序。</span><span class="sxs-lookup"><span data-stu-id="178da-106">The MQSAgent COM+ application is supported on a 64-bit Windows server.</span></span> <span data-ttu-id="178da-107">它将作为 32 位进程在 WOW64 下运行。</span><span class="sxs-lookup"><span data-stu-id="178da-107">It will run as a 32-bit process under WOW64.</span></span> <span data-ttu-id="178da-108">一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-64 位版本的 Windows Server 运行的基于的计算机可以与安装有 MQSAgent 的远程 32 位计算机进行通信。</span><span class="sxs-lookup"><span data-stu-id="178da-108">A [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-based computer that is running on a 64-bit version of Windows Server can communicate with a remote 32-bit computer that has the MQSAgent installed.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="178da-109">MQSeries 代理和 MQSAgent COM + 配置向导可执行文件**MQSConfigWiz.exe**如果从 BizTalk Server 2009 升级到 BizTalk Server 将不会安装。</span><span class="sxs-lookup"><span data-stu-id="178da-109">The MQSeries Agent and the MQSAgent COM+ Configuration Wizard executable **MQSConfigWiz.exe** are not installed if you upgrade from BizTalk Server 2009 to BizTalk Server.</span></span> <span data-ttu-id="178da-110">从 BizTalk Server 2009 重新运行安装程序升级到 BizTalk Server，然后选择**修改**选项，然后选择 MQSeries 代理下要安装这些组件的其他软件。</span><span class="sxs-lookup"><span data-stu-id="178da-110">After upgrading to BizTalk Server from BizTalk Server 2009 re-run setup, select the **Modify** option, and select the MQSeries Agent under the Additional Software to install these components.</span></span>  

## <a name="to-set-the-application-identity"></a><span data-ttu-id="178da-111">若要设置应用程序标识</span><span class="sxs-lookup"><span data-stu-id="178da-111">To set the application identity</span></span>  

-   <span data-ttu-id="178da-112">使用**应用程序标识**MQSAgent COM + 配置向导，如下所示设置 mqsagent 的应用程序标识的页：</span><span class="sxs-lookup"><span data-stu-id="178da-112">Use the **Application Identity** page of the MQSAgent COM+ Configuration Wizard to set the application identity for the MQSAgent as follows:</span></span>  

    |<span data-ttu-id="178da-113">使用此选项</span><span class="sxs-lookup"><span data-stu-id="178da-113">Use this</span></span>|<span data-ttu-id="178da-114">执行的操作</span><span class="sxs-lookup"><span data-stu-id="178da-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="178da-115">**交互式用户**</span><span class="sxs-lookup"><span data-stu-id="178da-115">**Interactive User**</span></span>|<span data-ttu-id="178da-116">选择此选项可将当前的登录帐户用于应用程序标识。</span><span class="sxs-lookup"><span data-stu-id="178da-116">Select this option to use the current logon account for the application identity.</span></span>|  
    |<span data-ttu-id="178da-117">**Local Service**</span><span class="sxs-lookup"><span data-stu-id="178da-117">**Local Service**</span></span>|<span data-ttu-id="178da-118">设置应用程序标识为内置服务帐户。</span><span class="sxs-lookup"><span data-stu-id="178da-118">Set the application identity to a built-in service account.</span></span>|  
    |<span data-ttu-id="178da-119">**Network Service**</span><span class="sxs-lookup"><span data-stu-id="178da-119">**Network Service**</span></span>|<span data-ttu-id="178da-120">设置应用程序标识为具有网络访问权限的内置帐户。</span><span class="sxs-lookup"><span data-stu-id="178da-120">Set the application identity to a built-in account with network access.</span></span>|  
    |<span data-ttu-id="178da-121">**此用户**</span><span class="sxs-lookup"><span data-stu-id="178da-121">**This user**</span></span>|<span data-ttu-id="178da-122">将应用程序标识设置为指定的用户名。</span><span class="sxs-lookup"><span data-stu-id="178da-122">Set the application identity to the indicated user name.</span></span>|  

> [!NOTE]
>  <span data-ttu-id="178da-123">不建议你使用帐户具有管理权限的应用程序标识。</span><span class="sxs-lookup"><span data-stu-id="178da-123">It is not recommended that you use an account with administrative permissions for the application identity.</span></span> <span data-ttu-id="178da-124">该帐户必须具有所需的最小权限： 读取和写入 MQSeries 队列的权限。</span><span class="sxs-lookup"><span data-stu-id="178da-124">The account must have the minimal rights required: read and write permission for the MQSeries queues.</span></span>  

## <a name="to-name-the-role-and-add-users-to-it"></a><span data-ttu-id="178da-125">若要命名角色并向其添加用户</span><span class="sxs-lookup"><span data-stu-id="178da-125">To name the role and add users to it</span></span>  

- <span data-ttu-id="178da-126">使用**名称的角色**MQSAgent COM + 配置向导，如下所示将名称和用户分配到角色页：</span><span class="sxs-lookup"><span data-stu-id="178da-126">Use the **Name of Role** page of the MQSAgent COM+ Configuration Wizard  to assign a name and users to the role as follows:</span></span>  


  |     <span data-ttu-id="178da-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="178da-127">Use this</span></span>     |                                                                         <span data-ttu-id="178da-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="178da-128">To do this</span></span>                                                                          |
  |------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | <span data-ttu-id="178da-129">**角色的名称**</span><span class="sxs-lookup"><span data-stu-id="178da-129">**Name of role**</span></span> |                                                                 <span data-ttu-id="178da-130">键入角色的名称。</span><span class="sxs-lookup"><span data-stu-id="178da-130">Type the name of the role.</span></span>                                                                  |
  |    <span data-ttu-id="178da-131">**用户**</span><span class="sxs-lookup"><span data-stu-id="178da-131">**Users**</span></span>     |                                                         <span data-ttu-id="178da-132">显示属于该角色的用户。</span><span class="sxs-lookup"><span data-stu-id="178da-132">Display the users that belong to the role.</span></span>                                                          |
  |     <span data-ttu-id="178da-133">**“添加”**</span><span class="sxs-lookup"><span data-stu-id="178da-133">**Add**</span></span>      | <span data-ttu-id="178da-134">将用户添加到角色。</span><span class="sxs-lookup"><span data-stu-id="178da-134">Add users to the role.</span></span> <span data-ttu-id="178da-135">这些是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务帐户使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="178da-135">These are the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] service accounts using the adapter.</span></span> |

> [!NOTE]
>  <span data-ttu-id="178da-136">将添加到需要访问适配器的角色唯一帐户。</span><span class="sxs-lookup"><span data-stu-id="178da-136">Add to the role only accounts requiring access to the adapter.</span></span>  

## <a name="to-set-the-msdtc-security-configuration-on-the-windows-server-2008-computer-to-no-authentication-required"></a><span data-ttu-id="178da-137">若要在不要求进行身份验证的 Windows Server 2008 计算机上设置的 MSDTC 安全配置</span><span class="sxs-lookup"><span data-stu-id="178da-137">To set the MSDTC Security configuration on the Windows Server 2008 computer to No Authentication Required</span></span>  
 <span data-ttu-id="178da-138">如果在安装了 MQSAgent COM + 应用程序[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]上安装了计算机和 MQSeries 适配器 （这与 BizTalk Server 一起安装）[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机、 上的 MSDTC 安全配置[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]计算机必须设置为**不要求进行身份验证**。</span><span class="sxs-lookup"><span data-stu-id="178da-138">If the MQSAgent COM+ application is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computer and the MQSeries Adapter (which is installed with BizTalk Server) is installed on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer, the MSDTC Security configuration on the [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computer must be set to **No Authentication Required**.</span></span> <span data-ttu-id="178da-139">请按照下列步骤将 MSDTC 安全配置设置为不要求进行验证：</span><span class="sxs-lookup"><span data-stu-id="178da-139">Follow these steps to set the MSDTC security configuration to No Authentication Required:</span></span>  

1.  <span data-ttu-id="178da-140">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="178da-140">Click **Start** and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="178da-141">双击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="178da-141">Double-click **Administrative Tools**.</span></span>  

3.  <span data-ttu-id="178da-142">双击**组件服务**以启动**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="178da-142">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  

4.  <span data-ttu-id="178da-143">展开**组件服务**，展开**计算机**，然后展开**我的电脑**。</span><span class="sxs-lookup"><span data-stu-id="178da-143">Expand **Component Services**, expand **Computers**, and then expand **My Computer**.</span></span>  

5.  <span data-ttu-id="178da-144">右键单击**我的电脑**然后单击**属性**菜单项。</span><span class="sxs-lookup"><span data-stu-id="178da-144">Right-click **My Computer** and click the **Properties** menu item.</span></span>  

6.  <span data-ttu-id="178da-145">在中**我的电脑**对话框中，单击**MSDTC**选项卡，然后单击**安全配置**。</span><span class="sxs-lookup"><span data-stu-id="178da-145">In the **My Computer** dialog box, click the **MSDTC** tab and then click **Security Configuration**.</span></span>  

7.  <span data-ttu-id="178da-146">在中**的安全配置**对话框中**事务管理器通信**部分中，选择**不要求进行身份验证**。</span><span class="sxs-lookup"><span data-stu-id="178da-146">In the **Security Configuration** dialog box, in the **Transaction Manager Communication** section, select **No Authentication Required**.</span></span> <span data-ttu-id="178da-147">如果系统提示您在对话框中，单击**是**以重新启动 MS DTC 服务。</span><span class="sxs-lookup"><span data-stu-id="178da-147">If you are prompted with a dialog box, click **Yes** to restart the MS DTC Service.</span></span>  

8.  <span data-ttu-id="178da-148">重新启动 MS DTC 服务后，单击**确定**然后单击**确定**以关闭**我的电脑**对话框。</span><span class="sxs-lookup"><span data-stu-id="178da-148">After the MS DTC service has restarted, click **OK** and click **OK** again to close the **My Computer** dialog box.</span></span>  

9. <span data-ttu-id="178da-149">关闭**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="178da-149">Close the **Component Services** management interface.</span></span>  

## <a name="to-configure-the-mqsagent-runtime-components-to-run-under-an-alternative-set-of-credentials"></a><span data-ttu-id="178da-150">若要配置 MQSAgent 运行时组件，另一组凭据下运行</span><span class="sxs-lookup"><span data-stu-id="178da-150">To configure the MQSAgent runtime components to run under an alternative set of credentials</span></span>  
 <span data-ttu-id="178da-151">MQSAgent COM + 应用程序包括用于管理和运行时组件。</span><span class="sxs-lookup"><span data-stu-id="178da-151">The MQSAgent COM+ application includes components for both administration and runtime.</span></span> <span data-ttu-id="178da-152">如果你想要此功能分隔到不同 COM + 应用程序出于安全目的，在安装了 MQSAgent COM + 应用程序的计算机上执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="178da-152">If you want to separate this functionality into different COM+ applications for security purposes, follow these steps on the computer that the MQSAgent COM+ application is installed on:</span></span>  

1.  <span data-ttu-id="178da-153">启用 MQSAgent COM + 组件的更改。</span><span class="sxs-lookup"><span data-stu-id="178da-153">Enable changes for the MQSAgent COM+ component.</span></span>  

    -   <span data-ttu-id="178da-154">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="178da-154">Click **Start** and then click **Control Panel**.</span></span>  

    -   <span data-ttu-id="178da-155">双击**管理工具**。</span><span class="sxs-lookup"><span data-stu-id="178da-155">Double-click **Administrative Tools**.</span></span>  

    -   <span data-ttu-id="178da-156">双击**组件服务**以启动**组件服务**管理界面。</span><span class="sxs-lookup"><span data-stu-id="178da-156">Double-click **Component Services** to launch the **Component Services** management interface.</span></span>  

    -   <span data-ttu-id="178da-157">展开**组件服务**，展开**我的电脑**，展开**COM + 应用程序**，右键单击**MQSAgent2** COM + 应用程序然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="178da-157">Expand **Component Services**, expand **My Computer**, expand **COM+ Applications**, right-click the **MQSAgent2** COM+ application and then click **Properties**.</span></span>  

    -   <span data-ttu-id="178da-158">单击**高级**选项卡上，取消选中**禁用更改**。</span><span class="sxs-lookup"><span data-stu-id="178da-158">Click the **Advanced** tab and uncheck **Disable changes**.</span></span>  

    -   <span data-ttu-id="178da-159">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="178da-159">Click **OK**.</span></span>  

2.  <span data-ttu-id="178da-160">创建一个新 COM + 应用程序为 MQSAgent 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="178da-160">Create a new COM+ application for the MQSAgent runtime components.</span></span>  

    -   <span data-ttu-id="178da-161">右键单击**COM + 应用程序**，单击**新建**，**应用程序**以显示**COM + 应用程序安装向导**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="178da-161">Right-click **COM+ Applications**, click **New**, **Application** to display the **COM+ Application Install Wizard** and click **Next**.</span></span>  

    -   <span data-ttu-id="178da-162">单击**创建一个空应用程序**。</span><span class="sxs-lookup"><span data-stu-id="178da-162">Click **Create an empty application**.</span></span>  

    -   <span data-ttu-id="178da-163">输入的名称**MQSAgent2RunTime**，请保留为默认选项**服务器应用程序**启用，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="178da-163">Enter the name **MQSAgent2RunTime**, leave the default option for **Server application** enabled and click **Next**.</span></span>  

    -   <span data-ttu-id="178da-164">选择的选项**此用户**，输入相应的帐户信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="178da-164">Select the option for **This user**, enter the appropriate account information and click **Next**.</span></span>  

        > [!NOTE]
        >  <span data-ttu-id="178da-165">此帐户应具有**连接**并**放置**和/或**获取**上相应的 IBM WebSphere MQ Windows 队列的权限。</span><span class="sxs-lookup"><span data-stu-id="178da-165">This account should have **connect** and **put** and/or **get** permissions on the appropriate IBM WebSphere MQ for Windows queues.</span></span> <span data-ttu-id="178da-166">可以设置此帐户具有适当的权限**setmqaut**与 IBM WebSphere MQ 可用命令。</span><span class="sxs-lookup"><span data-stu-id="178da-166">You can set the appropriate permissions for this account with the **setmqaut** command available with the IBM WebSphere MQ.</span></span> <span data-ttu-id="178da-167">有关详细信息**setmqaut**命令，请参阅 IBM WebSphere MQ 文档。</span><span class="sxs-lookup"><span data-stu-id="178da-167">For more information about the **setmqaut** command see the IBM WebSphere MQ documentation.</span></span>  

    -   <span data-ttu-id="178da-168">单击**下一步**上**添加应用程序角色**对话框。</span><span class="sxs-lookup"><span data-stu-id="178da-168">Click **Next** on the **Add Application Roles** dialog box.</span></span>  

    -   <span data-ttu-id="178da-169">单击**下一步**上**向角色添加用户**对话框。</span><span class="sxs-lookup"><span data-stu-id="178da-169">Click **Next** on the **Add Users to Roles** dialog box.</span></span>  

    -   <span data-ttu-id="178da-170">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="178da-170">Click **Finish**.</span></span>  

3.  <span data-ttu-id="178da-171">将运行时组件移至新的 COM + 应用程序</span><span class="sxs-lookup"><span data-stu-id="178da-171">Move the runtime components to the new COM+ application</span></span>  

    -   <span data-ttu-id="178da-172">展开**MQSAgent2** COM + 应用程序。</span><span class="sxs-lookup"><span data-stu-id="178da-172">Expand the **MQSAgent2** COM+ application.</span></span>  

    -   <span data-ttu-id="178da-173">展开**组件**。</span><span class="sxs-lookup"><span data-stu-id="178da-173">Expand **Components**.</span></span>  

    -   <span data-ttu-id="178da-174">右键单击**MQSAgent2.MQSAgent.1**组件，然后单击**移动**以显示**移动组件 (s)** 对话框。</span><span class="sxs-lookup"><span data-stu-id="178da-174">Right-click the **MQSAgent2.MQSAgent.1** component and click **Move** to display the **Move components(s)** dialog box.</span></span>  

    -   <span data-ttu-id="178da-175">选择**MQSAgent2RunTime**下**请选择一个目标**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="178da-175">Select **MQSAgent2RunTime** under **Please select a destination** and click **OK**.</span></span>  

    -   <span data-ttu-id="178da-176">重复这些步骤**MQSAgent2.MQSBroker.1**并**MQSAgent2.MQSProxy.1**组件。</span><span class="sxs-lookup"><span data-stu-id="178da-176">Repeat these steps for the **MQSAgent2.MQSBroker.1** and **MQSAgent2.MQSProxy.1** components.</span></span>  

## <a name="see-also"></a><span data-ttu-id="178da-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="178da-177">See Also</span></span>  
 <span data-ttu-id="178da-178">[如何配置 MQSeries 适配器发送和接收处理程序](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="178da-178">[How to Configure MQSeries Adapter Send and Receive Handlers](../core/how-to-configure-mqseries-adapter-send-and-receive-handlers.md) </span></span>  
 [<span data-ttu-id="178da-179">配置 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="178da-179">Configuring the MQSeries Adapter</span></span>](../core/configuring-the-mqseries-adapter.md)