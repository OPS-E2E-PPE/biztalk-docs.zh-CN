---
title: "教程： 使用 TIBCO 会合的 BizTalk 适配器将数据发送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b761ce2d-3465-43e0-bd8d-4d68b523226a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63540402ca8e060d26c8398af010a81eaad0a6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-send-data"></a><span data-ttu-id="83695-102">教程：使用 TIBCO Rendezvous 的 BizTalk 适配器以发送数据</span><span class="sxs-lookup"><span data-stu-id="83695-102">Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Send Data</span></span>
<span data-ttu-id="83695-103">您可以使用用于 TIBCO Rendezvous 的 BizTalk 适配器向 TIBCO 系统发送数据。</span><span class="sxs-lookup"><span data-stu-id="83695-103">You can use the BizTalk Adapter for TIBCO Rendezvous to send data to a TIBCO system.</span></span> <span data-ttu-id="83695-104">本演练描述了对此进行说明的一个 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="83695-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="83695-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="83695-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="83695-106">为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="83695-106">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
-   <span data-ttu-id="83695-107">此示例使用包含消息上下文属性的 DLL: Microsoft.BizTalk.Adapters.TibRV.Properties.dll。</span><span class="sxs-lookup"><span data-stu-id="83695-107">The sample uses a DLL containing message context properties: Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span> <span data-ttu-id="83695-108">您可能需要更新解决方案对此库的引用。</span><span class="sxs-lookup"><span data-stu-id="83695-108">You may need to update the solution's reference to this library.</span></span> <span data-ttu-id="83695-109">有关详细信息，请参阅[BizTalk Server 消息上下文属性 （发送处理程序）](../core/biztalk-server-message-context-properties-send-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="83695-109">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="83695-110">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="83695-110">What This Sample Does</span></span>  
 <span data-ttu-id="83695-111">该示例从一个文件夹选取一个 XML 文件，将该文件发送到业务流程，然后使用用于 TIBCO Rendezvous 的 BizTalk 适配器在 TIBCO 系统中创建一个记录。</span><span class="sxs-lookup"><span data-stu-id="83695-111">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Rendezvous to create a record in the TIBCO system.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="83695-112">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="83695-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="83695-113">本示例是在 [!INCLUDE[vs2010](../includes/vs2010-md.md)] 中设计的，它通过 BizTalk 业务流程中使用用于 TIBCO Rendezvous 的 BizTalk 适配器介绍了一些基本功能。</span><span class="sxs-lookup"><span data-stu-id="83695-113">This sample, designed in [!INCLUDE[vs2010](../includes/vs2010-md.md)], illustrates basic functionality using the BizTalk Adapter for TIBCO Rendezvous with a BizTalk orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="83695-114">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="83695-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="83695-115">本示例的默认位置为</span><span class="sxs-lookup"><span data-stu-id="83695-115">The default location for the sample is</span></span>  
  
 <span data-ttu-id="83695-116">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend</span><span class="sxs-lookup"><span data-stu-id="83695-116">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Rendezvous(r)\Sdk\OneWaySend</span></span>  
  
 <span data-ttu-id="83695-117">下表列出并介绍了示例中的文件。</span><span class="sxs-lookup"><span data-stu-id="83695-117">The following table lists and describes the files in the sample.</span></span>  
  
|<span data-ttu-id="83695-118">**运行时项目文件名**</span><span class="sxs-lookup"><span data-stu-id="83695-118">**Runtime Project Filename**</span></span>|<span data-ttu-id="83695-119">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="83695-119">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="83695-120">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="83695-120">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="83695-121">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="83695-121">OneWaySend.sln</span></span>|<span data-ttu-id="83695-122">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="83695-122">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="83695-123">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="83695-123">Schema.xsd</span></span><br /><br /> <span data-ttu-id="83695-124">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="83695-124">PropertySchema.xsd</span></span>|<span data-ttu-id="83695-125">应用程序的架构和属性架构文件。</span><span class="sxs-lookup"><span data-stu-id="83695-125">Schema and property schema files for the application.</span></span>|  
|<span data-ttu-id="83695-126">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="83695-126">Orchestration.odx</span></span>|<span data-ttu-id="83695-127">应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="83695-127">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="83695-128">TIBCORendezvousOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="83695-128">TIBCORendezvousOneWaySend.snk</span></span>|<span data-ttu-id="83695-129">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="83695-129">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="83695-130">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="83695-130">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="83695-131">创建用于 TIBCO Rendezvous 的 BizTalk 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="83695-131">Create a new instance of the BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
1.  <span data-ttu-id="83695-132">启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="83695-132">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="83695-133">单击**启动**，**程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="83695-133">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="83695-134">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="83695-134">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="83695-135">右键单击**适配器**和指向**新建**，**适配器...**</span><span class="sxs-lookup"><span data-stu-id="83695-135">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="83695-136">若要显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-136">to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="83695-137">输入一个值**名称**字段，例如**TIBCO 会合**。</span><span class="sxs-lookup"><span data-stu-id="83695-137">Enter a value for the **Name** field, for example **TIBCO Rendezvous**.</span></span>  
  
5.  <span data-ttu-id="83695-138">选择**TIBCO(r) Rendezvous(r)**从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="83695-138">Select **TIBCO(r) Rendezvous(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="83695-139">创建 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="83695-139">Create a BizTalk Send Port</span></span>  
  
1.  <span data-ttu-id="83695-140">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="83695-140">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="83695-141">右键单击**发送端口**和指向**新建**，**静态单向发送端口...**</span><span class="sxs-lookup"><span data-stu-id="83695-141">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port…**</span></span> <span data-ttu-id="83695-142">若要显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-142">to display the **Send Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="83695-143">输入一个值**名称**字段，例如**TIBCORndOneWaySP**。</span><span class="sxs-lookup"><span data-stu-id="83695-143">Enter a value for the **Name** field, for example **TIBCORndOneWaySP**.</span></span>  
  
4.  <span data-ttu-id="83695-144">从中的可用适配器的列表中选择 TIBCO 会合适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-144">Select the TIBCO Rendezvous adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83695-145">此值是 TIBCO 企业消息系统适配器在创建时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="83695-145">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5.  <span data-ttu-id="83695-146">输入值**认证发件人属性**:</span><span class="sxs-lookup"><span data-stu-id="83695-146">Enter values for the **Certified Sender Properties**:</span></span>  
  
    |<span data-ttu-id="83695-147">**属性**</span><span class="sxs-lookup"><span data-stu-id="83695-147">**Property**</span></span>|<span data-ttu-id="83695-148">**值**</span><span class="sxs-lookup"><span data-stu-id="83695-148">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="83695-149">分类帐文件名称</span><span class="sxs-lookup"><span data-stu-id="83695-149">Ledger file name</span></span>|<span data-ttu-id="83695-150">用于持久性认证消息传递的分类帐文件名。</span><span class="sxs-lookup"><span data-stu-id="83695-150">Ledger file name to use for persistent certified message delivery.</span></span>|  
    |<span data-ttu-id="83695-151">可重复使用的名称</span><span class="sxs-lookup"><span data-stu-id="83695-151">Reusable name</span></span>|<span data-ttu-id="83695-152">用于已验证消息传递的可重用的通信名称。</span><span class="sxs-lookup"><span data-stu-id="83695-152">Reusable correspondent name to use for certified message delivery.</span></span> <span data-ttu-id="83695-153">在网络上所有已验证消息通信名称中，该名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="83695-153">The name must be unique among all certified message correspondent names on the network.</span></span>|  
  
6.  <span data-ttu-id="83695-154">输入值**凭据**:</span><span class="sxs-lookup"><span data-stu-id="83695-154">Enter values for the **Credentials**:</span></span>  
  
    |<span data-ttu-id="83695-155">**属性**</span><span class="sxs-lookup"><span data-stu-id="83695-155">**Property**</span></span>|<span data-ttu-id="83695-156">**值**</span><span class="sxs-lookup"><span data-stu-id="83695-156">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="83695-157">密码</span><span class="sxs-lookup"><span data-stu-id="83695-157">Password</span></span>|<span data-ttu-id="83695-158">TIBCO Rendezvous 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="83695-158">The password for the TIBCO Rendezvous server.</span></span>|  
    |<span data-ttu-id="83695-159">用户名</span><span class="sxs-lookup"><span data-stu-id="83695-159">User name</span></span>|<span data-ttu-id="83695-160">TIBCO Rendezvous 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="83695-160">The user name for the TIBCO Rendezvous server.</span></span>|  
  
7.  <span data-ttu-id="83695-161">输入值**RendezvousTransport**:</span><span class="sxs-lookup"><span data-stu-id="83695-161">Enter values for the **RendezvousTransport**:</span></span>  
  
    |<span data-ttu-id="83695-162">**属性**</span><span class="sxs-lookup"><span data-stu-id="83695-162">**Property**</span></span>|<span data-ttu-id="83695-163">**值**</span><span class="sxs-lookup"><span data-stu-id="83695-163">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="83695-164">后台程序</span><span class="sxs-lookup"><span data-stu-id="83695-164">Daemon</span></span>|<span data-ttu-id="83695-165">Rendezvous 传输后台程序参数。</span><span class="sxs-lookup"><span data-stu-id="83695-165">Rendezvous Transport Daemon parameter.</span></span>|  
    |<span data-ttu-id="83695-166">Network</span><span class="sxs-lookup"><span data-stu-id="83695-166">Network</span></span>|<span data-ttu-id="83695-167">Rendezvous 传输网络参数。</span><span class="sxs-lookup"><span data-stu-id="83695-167">Rendezvous Transport Network parameter.</span></span>|  
    |<span data-ttu-id="83695-168">服务</span><span class="sxs-lookup"><span data-stu-id="83695-168">Service</span></span>|<span data-ttu-id="83695-169">Rendezvous 传输服务参数。</span><span class="sxs-lookup"><span data-stu-id="83695-169">Rendezvous Transport Service parameter.</span></span>|  
  
     <span data-ttu-id="83695-170">有关属性的详细信息，请参阅[如何设置 TIBCO 会合传输属性](../core/how-to-set-tibco-rendezvous-transport-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="83695-170">For more information about the properties, see [How to Set TIBCO Rendezvous Transport Properties](../core/how-to-set-tibco-rendezvous-transport-properties.md).</span></span>  
  
8.  <span data-ttu-id="83695-171">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="83695-171">Click **OK**.</span></span>  
  
9. <span data-ttu-id="83695-172">选择**XML 传输**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="83695-172">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
10. <span data-ttu-id="83695-173">右键单击发送端口，然后单击**启动**登记和启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="83695-173">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="create-a-file-receive-port"></a><span data-ttu-id="83695-174">创建文件接收端口</span><span class="sxs-lookup"><span data-stu-id="83695-174">Create a file receive port</span></span>  
  
1.  <span data-ttu-id="83695-175">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="83695-175">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="83695-176">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口...**以显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-176">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port...** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="83695-177">输入一个值**名称**字段，例如**TIBCORndOneWayFileRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="83695-177">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-file-receive-location"></a><span data-ttu-id="83695-178">创建文件接收位置</span><span class="sxs-lookup"><span data-stu-id="83695-178">Create a file receive location</span></span>  
  
1.  <span data-ttu-id="83695-179">为要监视的文件接收位置创建文件夹，例如 C:\Filesource。</span><span class="sxs-lookup"><span data-stu-id="83695-179">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  
  
2.  <span data-ttu-id="83695-180">右键单击新的接收端口，然后单击**新建**，**接收位置...**</span><span class="sxs-lookup"><span data-stu-id="83695-180">Right-click the new receive port and then click **New**, **Receive Location…**</span></span> <span data-ttu-id="83695-181">若要显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-181">to display the **Receive Location Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="83695-182">输入一个值**名称**字段，例如**TIBCORndOneWayFileRL**。</span><span class="sxs-lookup"><span data-stu-id="83695-182">Enter a value for the **Name** field, for example **TIBCORndOneWayFileRL**.</span></span>  
  
4.  <span data-ttu-id="83695-183">选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-183">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="83695-184">输入以前为创建的文件夹的位置**接收文件夹**属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="83695-184">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  
  
6.  <span data-ttu-id="83695-185">选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="83695-185">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="83695-186">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="83695-186">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="generate-a-document-instance-from-the-schema"></a><span data-ttu-id="83695-187">从架构生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="83695-187">Generate a document instance from the schema</span></span>  
  
1.  <span data-ttu-id="83695-188">右击 Schema.xsd 在解决方案资源管理器中的，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="83695-188">Right-click Schema.xsd in Solution Explorer and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="83695-189">在属性窗口中，单击以选中**输出实例文件名**选项下**常规**部分。</span><span class="sxs-lookup"><span data-stu-id="83695-189">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  
  
3.  <span data-ttu-id="83695-190">单击省略号按钮 （…） 以显示**选择输出文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-190">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  
  
4.  <span data-ttu-id="83695-191">指定的文件夹和输出文件实例的名称，例如**C:\instance.xml**单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="83695-191">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83695-192">请勿指定为此处的文件接收位置指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="83695-192">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  
  
5.  <span data-ttu-id="83695-193">右击 Schema.xsd 在解决方案资源管理器中的，单击**生成实例**在指定的位置生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="83695-193">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  
  
#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="83695-194">修改生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="83695-194">Modify the generated document instance</span></span>  
  
1.  <span data-ttu-id="83695-195">在文本编辑器（如记事本）中打开生成的文档实例，并编辑文档实例的内容以确保此数据将在 TIBCO 系统中生成唯一的记录。</span><span class="sxs-lookup"><span data-stu-id="83695-195">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="83695-196">例如，下面的代码显示了此数据文件的第一部分：</span><span class="sxs-lookup"><span data-stu-id="83695-196">For example the code below shows the first part of the data file:</span></span>  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoRendezvousOneWaySend.TibcoRendezvousOneWaySendSchema">  
        <Name>Punya Palit</Name>  
        <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  <span data-ttu-id="83695-197">保存修改后的文档实例。</span><span class="sxs-lookup"><span data-stu-id="83695-197">Save the modified document instance.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="83695-198">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="83695-198">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="83695-199">右键单击**OneWaySend**项目在解决方案资源管理器，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="83695-199">Right-click the **OneWaySend** project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="83695-200">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="83695-200">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="83695-201">输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="83695-201">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  
  
4.  <span data-ttu-id="83695-202">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="83695-202">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="83695-203">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="83695-203">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="83695-204">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="83695-204">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="83695-205">单击**刷新**中 MMC 工具栏或按按钮**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="83695-205">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="83695-206">双击要显示的业务流程**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="83695-206">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="83695-207">单击**绑定**显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="83695-207">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="83695-208">指定绑定选项的适当值，例如：</span><span class="sxs-lookup"><span data-stu-id="83695-208">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="83695-209">**参数**</span><span class="sxs-lookup"><span data-stu-id="83695-209">**Parameter**</span></span>|<span data-ttu-id="83695-210">**值**</span><span class="sxs-lookup"><span data-stu-id="83695-210">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="83695-211">主机</span><span class="sxs-lookup"><span data-stu-id="83695-211">Host</span></span>|<span data-ttu-id="83695-212">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="83695-212">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="83695-213">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="83695-213">FileReceivePort</span></span>|<span data-ttu-id="83695-214">TIBCORndOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="83695-214">TIBCORndOneWayFileRP</span></span>|  
    |<span data-ttu-id="83695-215">TibcoRendezvousSend</span><span class="sxs-lookup"><span data-stu-id="83695-215">TibcoRendezvousSend</span></span>|<span data-ttu-id="83695-216">TIBCORndOneWaySP</span><span class="sxs-lookup"><span data-stu-id="83695-216">TIBCORndOneWaySP</span></span>|  
  
6.  <span data-ttu-id="83695-217">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="83695-217">Click OK.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="83695-218">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="83695-218">Start the orchestration</span></span>  
  
-   <span data-ttu-id="83695-219">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击业务流程，然后单击**启动**登记和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="83695-219">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="83695-220">将文档实例拖到由文件接收位置监视的文件夹</span><span class="sxs-lookup"><span data-stu-id="83695-220">Drop a document instance into the folder monitored by the file receive location</span></span>  
  
-   <span data-ttu-id="83695-221">将早期创建的文档实例复制到应用程序监视的文件接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="83695-221">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  
  
#### <a name="verify-that-the-tibco-system-is-updated"></a><span data-ttu-id="83695-222">验证 TIBCO 系统是否已更新</span><span class="sxs-lookup"><span data-stu-id="83695-222">Verify that the TIBCO system is updated</span></span>  
  
-   <span data-ttu-id="83695-223">使用 TIBCO Web 界面验证是否已从 XML 文件中的数据创建记录。</span><span class="sxs-lookup"><span data-stu-id="83695-223">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  
  
 <span data-ttu-id="83695-224">成功处理文档实例后，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="83695-224">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="83695-225">文件适配器从文件夹中检索文件，并作为 BizTalk 消息将其发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="83695-225">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="83695-226">业务流程订阅此发布消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将该消息发送到该业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="83695-226">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="83695-227">业务流程实例使用业务流程中指定的逻辑处理该消息，并将该消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="83695-227">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="83695-228">TIBCO 发送端口订阅此发布消息，以便 BizTalk 消息引擎将消息发送到 TIBCO 发送端口。</span><span class="sxs-lookup"><span data-stu-id="83695-228">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  
  
5.  <span data-ttu-id="83695-229">发送端口将消息传给用于 TIBCO Rendezvous 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="83695-229">The send port hands the message to the BizTalk Adapter for TIBCO Rendezvous.</span></span>  
  
6.  <span data-ttu-id="83695-230">用于 TIBCO Rendezvous 的 BizTalk 适配器将消息发送给 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="83695-230">The BizTalk Adapter for TIBCO Rendezvous sends the message to the TIBCO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83695-231">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83695-231">See Also</span></span>  
 <span data-ttu-id="83695-232">[教程： 使用 TIBCO 会合的 BizTalk 适配器接收数据](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="83695-232">[Tutorial: Using the BizTalk Adapter for TIBCO Rendezvous to Receive Data](../core/tutorial-using-the-biztalk-adapter-for-tibco-rendezvous-to-receive-data.md) </span></span>  
 <span data-ttu-id="83695-233">[教程： 使用 Microsoft BizTalk Adapter for TIBCO 会合](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="83695-233">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="83695-234">入门</span><span class="sxs-lookup"><span data-stu-id="83695-234">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)