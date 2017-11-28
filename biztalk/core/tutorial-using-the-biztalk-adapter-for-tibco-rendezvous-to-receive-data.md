---
title: "教程： 使用 TIBCO 会合的 BizTalk 适配器接收数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58e7a739-701d-4085-a840-54f81c55e943
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de436413f10cf4882b5c4e4b21af7bac6a3234c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data"></a><span data-ttu-id="12d68-102">教程：使用适用于 TIBCO Rendezvous 的 BizTalk 适配器来接收数据</span><span class="sxs-lookup"><span data-stu-id="12d68-102">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data</span></span>
<span data-ttu-id="12d68-103">您可以使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收来自 TIBCO 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="12d68-103">You can use the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="12d68-104">本演练描述了对此进行说明的一个 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="12d68-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="12d68-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="12d68-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="12d68-106">为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="12d68-106">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="12d68-107">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="12d68-107">What This Sample Does</span></span>  
 <span data-ttu-id="12d68-108">本示例使用用于 TIBCO Rendezvous 的 BizTalk 适配器接收来自 TIBCO 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="12d68-108">This sample uses the BizTalk Adapter for TIBCO Rendezvous to receive data from a TIBCO system.</span></span> <span data-ttu-id="12d68-109">业务流程处理消息并使用文件适配器将数据编写为指定文件夹中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="12d68-109">An orchestration processes the message and, using the file adapter, writes the data as an XML file in a specified folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="12d68-110">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="12d68-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="12d68-111">本示例在 [!INCLUDE[vs2010](../includes/vs2010-md.md)] 中设计，它使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器以及 BizTalk 业务流程来说明基本功能。</span><span class="sxs-lookup"><span data-stu-id="12d68-111">This sample, designed in [!INCLUDE[vs2010](../includes/vs2010-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12d68-112">本示例假定您知道如何发送来自 TIBCO 的消息以供应用程序处理。</span><span class="sxs-lookup"><span data-stu-id="12d68-112">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="12d68-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="12d68-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="12d68-114">本示例的默认位置为</span><span class="sxs-lookup"><span data-stu-id="12d68-114">The default location for the sample is</span></span>  
  
 <span data-ttu-id="12d68-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive</span><span class="sxs-lookup"><span data-stu-id="12d68-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWayReceive</span></span>  
  
 <span data-ttu-id="12d68-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="12d68-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="12d68-117">**运行时项目文件名**</span><span class="sxs-lookup"><span data-stu-id="12d68-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="12d68-118">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="12d68-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="12d68-119">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="12d68-119">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="12d68-120">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="12d68-120">OneWayReceive.sln</span></span>|<span data-ttu-id="12d68-121">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="12d68-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="12d68-122">PureMessage.xsd，</span><span class="sxs-lookup"><span data-stu-id="12d68-122">PureMessage.xsd,</span></span>|<span data-ttu-id="12d68-123">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="12d68-123">Schema file for the application.</span></span>|  
|<span data-ttu-id="12d68-124">TIBCORvOWR.odx</span><span class="sxs-lookup"><span data-stu-id="12d68-124">TIBCORvOWR.odx</span></span>|<span data-ttu-id="12d68-125">应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="12d68-125">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="12d68-126">TIBCORv.snk</span><span class="sxs-lookup"><span data-stu-id="12d68-126">TIBCORv.snk</span></span>|<span data-ttu-id="12d68-127">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="12d68-127">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="12d68-128">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="12d68-128">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="12d68-129">创建用于 TIBCO Rendezvous 的 BizTalk 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="12d68-129">Create a new instance of the BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
1.  <span data-ttu-id="12d68-130">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="12d68-130">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="12d68-131">单击**启动**，**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]， [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="12d68-131">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="12d68-132">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="12d68-132">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="12d68-133">右键单击**适配器**和指向**新建**，**适配器...**</span><span class="sxs-lookup"><span data-stu-id="12d68-133">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="12d68-134">若要显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12d68-134">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="12d68-135">输入一个值**名称**字段，例如**TIBCO 会合**。</span><span class="sxs-lookup"><span data-stu-id="12d68-135">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="12d68-136">选择**TIBCO(r) Rendezvous(r)**从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12d68-136">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-port"></a><span data-ttu-id="12d68-137">创建 BizTalk 接收端口</span><span class="sxs-lookup"><span data-stu-id="12d68-137">Create a BizTalk Receive Port</span></span>  
  
1.  <span data-ttu-id="12d68-138">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="12d68-138">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="12d68-139">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...**以显示**接收端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12d68-139">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the **Receive Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="12d68-140">输入一个值**名称**字段，例如**TIBCORvOneWayRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12d68-140">Enter a value for the **Name** field, for example **TIBCORvOneWayRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-location"></a><span data-ttu-id="12d68-141">创建 BizTalk 接收位置</span><span class="sxs-lookup"><span data-stu-id="12d68-141">Create a BizTalk Receive Location</span></span>  
  
1.  <span data-ttu-id="12d68-142">右键单击新的接收端口，然后单击**新建**，**接收位置...**</span><span class="sxs-lookup"><span data-stu-id="12d68-142">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="12d68-143">若要显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12d68-143">to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="12d68-144">输入一个值**名称**字段，例如**TIBCORvOneWayRL**。</span><span class="sxs-lookup"><span data-stu-id="12d68-144">Enter a value for the **Name** field, for example **TIBCORvOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="12d68-145">从中的可用适配器的列表中选择 TIBCO 会合适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12d68-145">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12d68-146">该值是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建 TIBCO 适配器时指定的名称。</span><span class="sxs-lookup"><span data-stu-id="12d68-146">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="12d68-147">输入一个值**RendezvousSubjectName**下**AdapterRequiredProperties**。</span><span class="sxs-lookup"><span data-stu-id="12d68-147">Enter a value for the **RendezvousSubjectName** under the **AdapterRequiredProperties**.</span></span>  
  
5.  <span data-ttu-id="12d68-148">输入值**认证侦听程序属性**:</span><span class="sxs-lookup"><span data-stu-id="12d68-148">Enter values for the **Certified Listener Properties**:</span></span>  
  
    |<span data-ttu-id="12d68-149">**属性**</span><span class="sxs-lookup"><span data-stu-id="12d68-149">**Property**</span></span>|<span data-ttu-id="12d68-150">**值**</span><span class="sxs-lookup"><span data-stu-id="12d68-150">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="12d68-151">分类帐文件名称</span><span class="sxs-lookup"><span data-stu-id="12d68-151">Ledger file name</span></span>|<span data-ttu-id="12d68-152">用于持久性认证消息传递的分类帐文件名。</span><span class="sxs-lookup"><span data-stu-id="12d68-152">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="12d68-153">可重复使用的名称</span><span class="sxs-lookup"><span data-stu-id="12d68-153">Reusable name</span></span>|<span data-ttu-id="12d68-154">用于已验证消息传递的可重用的通信名称。</span><span class="sxs-lookup"><span data-stu-id="12d68-154">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="12d68-155">在网络上所有已验证消息通信名称中，该名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="12d68-155">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="12d68-156">输入值**凭据**:</span><span class="sxs-lookup"><span data-stu-id="12d68-156">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="12d68-157">**属性**</span><span class="sxs-lookup"><span data-stu-id="12d68-157">**Property**</span></span>|<span data-ttu-id="12d68-158">**值**</span><span class="sxs-lookup"><span data-stu-id="12d68-158">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="12d68-159">密码</span><span class="sxs-lookup"><span data-stu-id="12d68-159">Password</span></span>|<span data-ttu-id="12d68-160">TIBCO Rendezvous 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="12d68-160">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="12d68-161">用户名</span><span class="sxs-lookup"><span data-stu-id="12d68-161">User name</span></span>|<span data-ttu-id="12d68-162">TIBCO Rendezvous 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="12d68-162">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="12d68-163">输入值**RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="12d68-163">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="12d68-164">**属性**</span><span class="sxs-lookup"><span data-stu-id="12d68-164">**Property**</span></span>|<span data-ttu-id="12d68-165">**值**</span><span class="sxs-lookup"><span data-stu-id="12d68-165">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="12d68-166">后台程序</span><span class="sxs-lookup"><span data-stu-id="12d68-166">Daemon</span></span>|<span data-ttu-id="12d68-167">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="12d68-167">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="12d68-168">Network</span><span class="sxs-lookup"><span data-stu-id="12d68-168">Network</span></span>|<span data-ttu-id="12d68-169">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="12d68-169">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="12d68-170">服务</span><span class="sxs-lookup"><span data-stu-id="12d68-170">Service</span></span>|<span data-ttu-id="12d68-171">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="12d68-171">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="12d68-172">有关属性的详细信息，请参阅[设置 TIBCO 会合接收传输属性](../core/setting-tibco-rendezvous-receive-transport-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="12d68-172">For more information about the properties, see [Setting TIBCO Rendezvous Receive Transport Properties](../core/setting-tibco-rendezvous-receive-transport-properties.md).</span></span>  
  
8.  <span data-ttu-id="12d68-173">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="12d68-173">Click **OK**.</span></span>  
  
9. <span data-ttu-id="12d68-174">选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12d68-174">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
10. <span data-ttu-id="12d68-175">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="12d68-175">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="create-a-one-way-file-send-port"></a><span data-ttu-id="12d68-176">创建单向文件发送端口</span><span class="sxs-lookup"><span data-stu-id="12d68-176">Create a one-way file send port</span></span>  
  
1.  <span data-ttu-id="12d68-177">创建发送端口要使用的目标文件夹，例如 C:\FilesOut。</span><span class="sxs-lookup"><span data-stu-id="12d68-177">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="12d68-178">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="12d68-178">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="12d68-179">右键单击**发送端口**和指向**新建**，**静态单向发送端口...**</span><span class="sxs-lookup"><span data-stu-id="12d68-179">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="12d68-180">若要显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12d68-180">to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="12d68-181">输入一个值**名称**字段，例如**TIBCORvOneWayFileSP**。</span><span class="sxs-lookup"><span data-stu-id="12d68-181">Enter a value for the **Name** field, for example **TIBCORvOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="12d68-182">选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12d68-182">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="12d68-183">有关**目标文件夹**属性，输入前面创建的文件夹的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12d68-183">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="12d68-184">选择**XMLTransmit**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="12d68-184">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="12d68-185">右键单击发送端口，然后单击**启动**登记和启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="12d68-185">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="12d68-186">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="12d68-186">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="12d68-187">右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="12d68-187">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="12d68-188">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="12d68-188">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="12d68-189">输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。</span><span class="sxs-lookup"><span data-stu-id="12d68-189">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="12d68-190">右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="12d68-190">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="12d68-191">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="12d68-191">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="12d68-192">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="12d68-192">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="12d68-193">单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="12d68-193">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="12d68-194">双击要显示的业务流程**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="12d68-194">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="12d68-195">单击**绑定**显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="12d68-195">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="12d68-196">指定绑定选项的适当值，例如：</span><span class="sxs-lookup"><span data-stu-id="12d68-196">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="12d68-197">**参数**</span><span class="sxs-lookup"><span data-stu-id="12d68-197">**Parameter**</span></span>|<span data-ttu-id="12d68-198">**值**</span><span class="sxs-lookup"><span data-stu-id="12d68-198">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="12d68-199">主机</span><span class="sxs-lookup"><span data-stu-id="12d68-199">Host</span></span>|<span data-ttu-id="12d68-200">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="12d68-200">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="12d68-201">发送端口</span><span class="sxs-lookup"><span data-stu-id="12d68-201">SendPort</span></span>|<span data-ttu-id="12d68-202">TIBCORvOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="12d68-202">TIBCORvOneWayFileSP</span></span>|  
    |<span data-ttu-id="12d68-203">接收端口</span><span class="sxs-lookup"><span data-stu-id="12d68-203">ReceivePort</span></span>|<span data-ttu-id="12d68-204">TIBCORvOneWayRP</span><span class="sxs-lookup"><span data-stu-id="12d68-204">TIBCORvOneWayRP</span></span>|  
  
6.  <span data-ttu-id="12d68-205">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="12d68-205">Click **OK**.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="12d68-206">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="12d68-206">Start the orchestration</span></span>  
  
-   <span data-ttu-id="12d68-207">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击业务流程，然后单击**启动**登记和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="12d68-207">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="verify-that-the-application-receives-a-message"></a><span data-ttu-id="12d68-208">验证应用程序是否收到消息</span><span class="sxs-lookup"><span data-stu-id="12d68-208">Verify that the application receives a message</span></span>  
  
-   <span data-ttu-id="12d68-209">打开将文件发送端口配置为发送到的目标文件夹，并验证是否已生成输出文档。</span><span class="sxs-lookup"><span data-stu-id="12d68-209">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span>  
  
 <span data-ttu-id="12d68-210">成功处理文档实例后，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="12d68-210">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="12d68-211">TIBCO Rendezvous 适配器接收来自 TIBCO 系统的消息并将其作为 BizTalk 消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="12d68-211">The TIBCO Rendezvous adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="12d68-212">业务流程会订阅此发布的消息，以便 BizTalk 消息引擎能够激活业务流程的实例，并将该消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="12d68-212">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="12d68-213">业务流程实例将此消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="12d68-213">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="12d68-214">文件发送端口会订阅此消息，以便 BizTalk 能够将消息发送到文件适配器。</span><span class="sxs-lookup"><span data-stu-id="12d68-214">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="12d68-215">文件适配器将包含结果集的消息写入到指定的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="12d68-215">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d68-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12d68-216">See Also</span></span>  
 <span data-ttu-id="12d68-217">[教程： 使用 TIBCO 会合的 BizTalk 适配器将数据发送](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="12d68-217">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data.md) </span></span>  
 <span data-ttu-id="12d68-218">[教程： 使用 Microsoft BizTalk Adapter for TIBCO 会合](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="12d68-218">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="12d68-219">入门</span><span class="sxs-lookup"><span data-stu-id="12d68-219">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)