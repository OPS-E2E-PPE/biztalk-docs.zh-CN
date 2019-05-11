---
title: 配置 FileAct 和 InterAct 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d3876ff-e8e4-47f4-9ca8-d4dad419ed67
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa2cb8756ce5d00109fbb17d042f43ec4a782b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367278"
---
# <a name="configure-the-fileact-and-interact-adapter"></a><span data-ttu-id="f0616-102">配置 FileAct 和 InterAct 适配器</span><span class="sxs-lookup"><span data-stu-id="f0616-102">Configure the FileAct and InterAct Adapter</span></span>
<span data-ttu-id="f0616-103">配置使用的不同项目[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]运行时。</span><span class="sxs-lookup"><span data-stu-id="f0616-103">Configure the different artifacts used by the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] runtime.</span></span> 

  
## <a name="prerequisites"></a><span data-ttu-id="f0616-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="f0616-104">Prerequisites</span></span>  
   
- <span data-ttu-id="f0616-105">安装 [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0616-105">Install the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]</span></span>
  
- <span data-ttu-id="f0616-106">以的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Administrators 组</span><span class="sxs-lookup"><span data-stu-id="f0616-106">Sign in as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators group</span></span>
  
- <span data-ttu-id="f0616-107">确认 SQL Server 正在运行</span><span class="sxs-lookup"><span data-stu-id="f0616-107">Confirm SQL Server is running</span></span>
  
## <a name="step-1-configure-the-fileact-and-interact-adapter"></a><span data-ttu-id="f0616-108">第 1 步：配置 FileAct 和 InterAct 适配器</span><span class="sxs-lookup"><span data-stu-id="f0616-108">Step 1: Configure the FileAct and InterAct adapter</span></span>  
  
1.  <span data-ttu-id="f0616-109">在中**Microsoft BizTalk FileAct 和交互适配器配置**向导中，转到**概述**。</span><span class="sxs-lookup"><span data-stu-id="f0616-109">In the **Microsoft BizTalk FileAct and InterAct Adapter Configuration** wizard, go to **Overview**.</span></span> <span data-ttu-id="f0616-110">在左窗格中，选择**运行时**配置适配器运行时组件。</span><span class="sxs-lookup"><span data-stu-id="f0616-110">In the left pane, select **Runtime** to configure the runtime components of the adapters.</span></span>  
  
2.  <span data-ttu-id="f0616-111">在中**运行时配置**下**帐户**，选择省略号 [...] 输入 COM plus 存储和转发模式配置。</span><span class="sxs-lookup"><span data-stu-id="f0616-111">In **Runtime Configuration**, under **Account**, select the ellipsis […] to enter the COM plus configuration for the Store and Forward mode.</span></span>  
  
3.  <span data-ttu-id="f0616-112">在中**用户凭据**，输入用户名称 (在*域 \ 用户名*格式) 和 COM plus 配置中使用的帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="f0616-112">In **User Credentials**, enter the user name (in the *domain\user name* format) and password for the account used in the COM plus configuration.</span></span> <span data-ttu-id="f0616-113">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="f0616-113">Select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0616-114">一个**用户凭据**如果您输入的帐户有建议的更高权限，将显示警告。</span><span class="sxs-lookup"><span data-stu-id="f0616-114">A **User Credentials** warning appears if the account you entered has higher privileges than are recommended.</span></span> <span data-ttu-id="f0616-115">选择**是**以继续。</span><span class="sxs-lookup"><span data-stu-id="f0616-115">Select **Yes** to continue.</span></span>
  
4.  <span data-ttu-id="f0616-116">选择**应用配置**将 COM plus 配置应用到 FileAct 和交互的适配器。</span><span class="sxs-lookup"><span data-stu-id="f0616-116">Select **Apply configuration** to apply the COM plus configuration to the FileAct and InterAct Adapter.</span></span>  
  
5.  <span data-ttu-id="f0616-117">在中**摘要**，查看，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f0616-117">In the **Summary**, review, and select **Next**.</span></span>  
  
6.  <span data-ttu-id="f0616-118">配置完成后，查看组件的列表。</span><span class="sxs-lookup"><span data-stu-id="f0616-118">When the configuration completes, review the list of components.</span></span> <span data-ttu-id="f0616-119">一个对勾意味着该组件已成功配置。</span><span class="sxs-lookup"><span data-stu-id="f0616-119">A check mark means that the component is configured successfully.</span></span> <span data-ttu-id="f0616-120">"X"意味着该组件的问题。</span><span class="sxs-lookup"><span data-stu-id="f0616-120">An "X" means that there is a problem with that component.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0616-121">使用**日志文件**链接来查看配置事件。</span><span class="sxs-lookup"><span data-stu-id="f0616-121">Use the **Logfile** link to view the configuration events.</span></span>  
  
7.  <span data-ttu-id="f0616-122">选择**完成**以完成配置。</span><span class="sxs-lookup"><span data-stu-id="f0616-122">Select **Finish** to complete the configuration.</span></span> <span data-ttu-id="f0616-123">**概述**显示运行时组件的当前配置状态。</span><span class="sxs-lookup"><span data-stu-id="f0616-123">The **Overview** shows the current configuration status for the Runtime components.</span></span>  

<span data-ttu-id="f0616-124">接下来，创建要运行这些适配器的主机和主机实例。</span><span class="sxs-lookup"><span data-stu-id="f0616-124">Next, create the host and host instances to run these adapters.</span></span>

## <a name="step-2-create-the-host-and-host-instances"></a><span data-ttu-id="f0616-125">第 2 步：创建主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="f0616-125">Step 2: Create the host and host instances</span></span>

<span data-ttu-id="f0616-126">我们建议你创建的专用的主机的 FileAct 适配器和 InterAct 适配器的单独的专用的主机。</span><span class="sxs-lookup"><span data-stu-id="f0616-126">We recommend that you create a dedicated host for the FileAct adapter and a separate dedicated host for the InterAct adapter.</span></span> <span data-ttu-id="f0616-127">对于每个适配器，创建至少一个主机实例。</span><span class="sxs-lookup"><span data-stu-id="f0616-127">For each adapter, create at least one host instance.</span></span>  

<span data-ttu-id="f0616-128">[管理 BizTalk 主机和主机实例](../../core/managing-biztalk-hosts-and-host-instances.md)列出的步骤创建主机和主机实例。</span><span class="sxs-lookup"><span data-stu-id="f0616-128">[Managing BizTalk Hosts and Host Instances](../../core/managing-biztalk-hosts-and-host-instances.md) list the steps to create hosts and host instances.</span></span> 

<span data-ttu-id="f0616-129">创建后下, 一步是添加发送处理程序，并使用客户端消息合作伙伴创建 SWIFT 联盟网关 （压降） 中。</span><span class="sxs-lookup"><span data-stu-id="f0616-129">Once created, the next step is to add the send handler, and use the Client Message Partner you created in the SWIFT Alliance Gateway (SAG).</span></span>

## <a name="step-3-create-the-send-handler"></a><span data-ttu-id="f0616-130">步骤 3：创建发送处理程序</span><span class="sxs-lookup"><span data-stu-id="f0616-130">Step 3: Create the send handler</span></span>

<span data-ttu-id="f0616-131">使用 FileAct 和 InterAct 发送处理程序属性的发送端口配置值，如果在单个 FileAct 上未设置的属性或 InterAct 发送端口。</span><span class="sxs-lookup"><span data-stu-id="f0616-131">You use the FileAct and InterAct send handler properties as the send port configuration values, if the properties are not set on the individual FileAct or InterAct send port.</span></span> 
  
1. <span data-ttu-id="f0616-132">在中**BizTalk Server 管理**控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="f0616-132">In the **BizTalk Server Administration** console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="f0616-133">选择**FileAct**或**InterAct**适配器。</span><span class="sxs-lookup"><span data-stu-id="f0616-133">Select the **FileAct** or **InterAct** adapter.</span></span> <span data-ttu-id="f0616-134">在右窗格中，双击发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="f0616-134">In the right pane, double-click the send handler.</span></span>  
  
3. <span data-ttu-id="f0616-135">在中**主机名**下拉列表中，选择在上一部分中创建的主机。</span><span class="sxs-lookup"><span data-stu-id="f0616-135">In the **Host name** drop-down list, select the host you created in the previous section.</span></span> <span data-ttu-id="f0616-136">然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="f0616-136">Then select **Properties**.</span></span>  
  
4. <span data-ttu-id="f0616-137">在中**传输属性**，选择**自变量**属性，并输入以下参数为：</span><span class="sxs-lookup"><span data-stu-id="f0616-137">In the **Transport Properties**, select the **Argument** property, and enter the following argument as:</span></span>  
  
    `-SagMessagePartner <Client Message Partner created in SAG\>`
  
   > [!NOTE]
   >  <span data-ttu-id="f0616-138">替换 <`Client Message Partner created in SAG`> 客户端消息合作伙伴的名称。</span><span class="sxs-lookup"><span data-stu-id="f0616-138">Replace <`Client Message Partner created in SAG`> with the name of the client message partner.</span></span> <span data-ttu-id="f0616-139">保留默认值为加密模式、 FACrypto 模式和日志消息属性。</span><span class="sxs-lookup"><span data-stu-id="f0616-139">Leave the default values for the Crypto Mode, FACrypto Mode, and LogMessages properties.</span></span>  
  
5. <span data-ttu-id="f0616-140">选择**确定**以保存所做的更改，然后关闭属性窗口。</span><span class="sxs-lookup"><span data-stu-id="f0616-140">Select **OK** to save your changes, and then to close the properties window.</span></span> 
  
6. <span data-ttu-id="f0616-141">下**平台设置**，选择**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="f0616-141">Under **Platform Settings**, select **Host Instances**.</span></span>  
  
7. <span data-ttu-id="f0616-142">重新启动主机实例：</span><span class="sxs-lookup"><span data-stu-id="f0616-142">Restart the host instances:</span></span> 

   - <span data-ttu-id="f0616-143">右键单击 FileAct 主机实例，并**重新启动**</span><span class="sxs-lookup"><span data-stu-id="f0616-143">Right-click the FileAct host instance, and **Restart**</span></span>
   - <span data-ttu-id="f0616-144">右键单击交互主机实例，并**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="f0616-144">Right-click the InterAct host instance, and **Restart**.</span></span>  

<span data-ttu-id="f0616-145">接下来，输入 SWIFTNet paramfile 中的服务器消息合作伙伴，若要启用 FileAct 和 InterAct 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="f0616-145">Next, enter the server message partners in the SWIFTNet paramfile to enable the FileAct and InterAct receive adapters.</span></span>
  
## <a name="step-4-configure-the-swiftnet-param-file"></a><span data-ttu-id="f0616-146">步骤 4：配置 SWIFTNet param 文件</span><span class="sxs-lookup"><span data-stu-id="f0616-146">Step 4: Configure the SWIFTNet param file</span></span>

<span data-ttu-id="f0616-147">若要启用 FileAct 和 InterAct 接收适配器初始化的值，必须在 SWIFTNet paramfile 中输入合作伙伴在压降中创建的服务器消息。</span><span class="sxs-lookup"><span data-stu-id="f0616-147">To enable the FileAct and InterAct receive adapters to initialize with the values, the Server message partners created in SAG must be entered in the SWIFTNet paramfile.</span></span> <span data-ttu-id="f0616-148">Paramfile 通常位于`c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`。</span><span class="sxs-lookup"><span data-stu-id="f0616-148">The paramfile is typically located in `c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`.</span></span> <span data-ttu-id="f0616-149">配置 paramfile 后，开始**SnlReceiver.exe**。</span><span class="sxs-lookup"><span data-stu-id="f0616-149">After you configure the paramfile, start **SnlReceiver.exe**.</span></span>  
  
1. <span data-ttu-id="f0616-150">打开**SWIFTNet paramfile**。</span><span class="sxs-lookup"><span data-stu-id="f0616-150">Open the **SWIFTNet paramfile**.</span></span> <span data-ttu-id="f0616-151">中的位置标记为"\*\*\*"将以下代码添加。</span><span class="sxs-lookup"><span data-stu-id="f0616-151">In the location marked with "\*\*\*" add the following.</span></span> <span data-ttu-id="f0616-152">请注意，`AdapterType`值可以是`Interact`或`Fileact`。</span><span class="sxs-lookup"><span data-stu-id="f0616-152">Note that the `AdapterType` value can be `Interact` or `Fileact`.</span></span>  
  
     ```spawn "snlreceiver -SagMessagePartner <Server MessagePartnerName\> -AdapterMode <AdapterType\>"```  
       
  
   ```  
    username:snlowner  
    subsystem_name:SampleSubsystem  
    #subsystem_group: SampleSubsystem  
    #subsystem_dependency:Support,Swarm  
    subsystem_nature:critical  
    subsystem_start:  
    ***  
    *END  
    subsystem_stop:  
    *KILL9:snlreceiver  
    *END  
    subsystem_status:  
    *NB:1:snlreceiver  
    *END  
    start_event:SNL001:subsystem SampleSubsystem is up  
    stop_event:SNL002:subsystem SampleSubsystem is down  
   ```  
  
> [!NOTE]
>  <span data-ttu-id="f0616-153">在开始 SNLreceiver 之前，启用接收端口的适配器使用 （FileAct 或交互）。</span><span class="sxs-lookup"><span data-stu-id="f0616-153">Before you start SNLreceiver, enable the receive ports for the adapter you are using (FileAct or InterAct).</span></span>  
  
2. <span data-ttu-id="f0616-154">启动和停止 SnlReceiver.exe:</span><span class="sxs-lookup"><span data-stu-id="f0616-154">Start and stop SnlReceiver.exe:</span></span>

    1.  <span data-ttu-id="f0616-155">在桌面上，选择**远程 API**图标以打开远程 API 的命令提示符。</span><span class="sxs-lookup"><span data-stu-id="f0616-155">On the desktop, select the **Remote API** icon to open the Remote API command prompt.</span></span>  
  
    2.  <span data-ttu-id="f0616-156">在命令提示符下键入 `Swiftnet start`。</span><span class="sxs-lookup"><span data-stu-id="f0616-156">At the command prompt, type `Swiftnet start`.</span></span> <span data-ttu-id="f0616-157">选择 enter 键以启动 SnlReceiver.exe。</span><span class="sxs-lookup"><span data-stu-id="f0616-157">Select ENTER to start SnlReceiver.exe.</span></span>  
  
    3.  <span data-ttu-id="f0616-158">在命令提示符下键入 `Swiftnet stop`。</span><span class="sxs-lookup"><span data-stu-id="f0616-158">At the command prompt, type `Swiftnet stop`.</span></span> <span data-ttu-id="f0616-159">选择 ENTER 以停止 SnlReceiver.exe。</span><span class="sxs-lookup"><span data-stu-id="f0616-159">Select ENTER to stop SnlReceiver.exe.</span></span>  

  
<span data-ttu-id="f0616-160">接下来，更新文件**autoexec.bat**来设置环境变量的 SWIFT。</span><span class="sxs-lookup"><span data-stu-id="f0616-160">Next, update the file **autoexec.bat** to set the SWIFT environment variables.</span></span>

## <a name="step-5-update-autoexecbat-to-configure-the-receive-adapters"></a><span data-ttu-id="f0616-161">步骤 5：若要配置的接收适配器的更新 autoexec.bat</span><span class="sxs-lookup"><span data-stu-id="f0616-161">Step 5: Update autoexec.bat to configure the receive adapters</span></span>

<span data-ttu-id="f0616-162">更新**autoexec.bat**文件以将 SWIFT 环境变量设置的计算机上的安装位置[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]接收适配器。</span><span class="sxs-lookup"><span data-stu-id="f0616-162">Update the **autoexec.bat** file to set the SWIFT environment variables on the computer where you installed the [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] receive adapters.</span></span> <span data-ttu-id="f0616-163">从已安装在路径中的接收适配器的系统生成的环境变量`c:\SWIFTAlliance`与名为的接收适配器的实例**Ra1**。</span><span class="sxs-lookup"><span data-stu-id="f0616-163">The environment variables are generated from the system that has the receive adapter installed in the path `c:\SWIFTAlliance` with an instance of the receive adapter named **Ra1**.</span></span> <span data-ttu-id="f0616-164">更新你的配置适当的 SWIFT 环境变量。</span><span class="sxs-lookup"><span data-stu-id="f0616-164">Update the SWIFT environment variables appropriately for your configuration.</span></span>  
  
 <span data-ttu-id="f0616-165">下面是 autoexe.bat 文件的一个示例：</span><span class="sxs-lookup"><span data-stu-id="f0616-165">The following is a sample of the autoexe.bat file:</span></span>
  
```  
SET COMPUTERNAME=<Machine Name>  
SET GENLOG_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET GENUTIL_DIR=C:\SWIFTAlliance\RA\bin  
SET HOMEDRIVE=C:  
SET LOGONSERVER=\\SERVERNAME  
SET OSA_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET OSA_INSTANCE=Ra1  
SET PKIEXECDIR=C:\SWIFTAlliance\RA  
SET SAGRA_HOME=C:\SWIFTAlliance\RA  
SET SESSIONNAME=RDP-Tcp#1  
SET SLP_ENV=DEFAULT  
SET SLP_FILE=server.slp  
SET SNL_DOMAIN_NAME=Ra1  
SET SPK_DATA_DIR=C:\SWIFTAlliance\RA\data\pki  
SET SWNET_BIN_PATH=C:\SWIFTAlliance\RA\Ra1\bin  
SET SWNET_CFG_PATH=C:\SWIFTAlliance\RA\Ra1\cfg  
SET SWNET_HOME=C:\SWIFTAlliance\RA  
SET SWNET_HOST=HOSTNAME  
SET SWNET_INST=Ra1  
SET SWNET_LOG_PATH=C:\SWIFTAlliance\RA\Ra1\log  
SET SWNET_SLP_PATH=C:\SWIFTAlliance\RA\data\  
SET SWNET_VERSION=5.0.20  
SET SWTRACE=C:\SWIFTAlliance\RA\Ra1\log  
SET Path=%PATH%;C:\SWIFTAlliance\RA\bin  
SET Path=%PATH%;C:\SWIFTAlliance\RA\lib  
  
```  
  
## <a name="see-some-examples"></a><span data-ttu-id="f0616-166">查看一些示例</span><span class="sxs-lookup"><span data-stu-id="f0616-166">See some examples</span></span>
<span data-ttu-id="f0616-167">FileAct 和 InterAct 消息的示例，请参阅[示例进行交互和 FileAct 消息](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f0616-167">For examples of FileAct and InterAct messages, see [Sample InterAct and FileAct Messages](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0616-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0616-168">See Also</span></span>  

[<span data-ttu-id="f0616-169">安装 FileAct 和 InterAct 适配器</span><span class="sxs-lookup"><span data-stu-id="f0616-169">Install the FileAct and InterAct Adapter</span></span>](../../adapters-and-accelerators/fileact-interact/install-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="f0616-170">卸载或修复 FileAct 和 InterAct 适配器</span><span class="sxs-lookup"><span data-stu-id="f0616-170">Uninstall or repair the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="f0616-171">阅读安装过程中的已知问题</span><span class="sxs-lookup"><span data-stu-id="f0616-171">Read the installation known issues</span></span>](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
