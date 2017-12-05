---
title: "教程： 使用 TIBCO 企业消息服务的 BizTalk 适配器将数据发送 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1912d594-3839-4e04-bc40-93bd7cc0b309
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2e2dc6fe0c1427ac959ce77d6ff4f46b4f4285
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-send-data"></a><span data-ttu-id="2fd48-102">教程 1：使用适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器来发送数据</span><span class="sxs-lookup"><span data-stu-id="2fd48-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data</span></span>
<span data-ttu-id="2fd48-103">您可以使用用于 TIBCO Enterprise Message Service (EMS) 的 BizTalk 适配器将数据发送至 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="2fd48-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to send data to a TIBCO system.</span></span> <span data-ttu-id="2fd48-104">本演练描述了对此进行说明的一个 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="2fd48-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2fd48-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="2fd48-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="2fd48-106">用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO EMS C# API（即 TIBCO.EMS.dll）添加到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="2fd48-106">BizTalk Adapter for TIBCO EMS requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="2fd48-107">有关安装程序集的详细信息，请参阅[TIBCO 企业消息服务要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd48-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  
  
-   <span data-ttu-id="2fd48-108">为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2fd48-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="2fd48-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="2fd48-109">What This Sample Does</span></span>  
 <span data-ttu-id="2fd48-110">本示例从某文件夹中选择一个 XML 文件，将该文件发送至业务流程，然后使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器在 TIBCO 系统中创建记录。</span><span class="sxs-lookup"><span data-stu-id="2fd48-110">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to create a record in the TIBCO system.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="2fd48-111">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="2fd48-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="2fd48-112">此示例中，在 Visual Studio 中设计演示 BizTalk 适配器用于 TIBCO 企业消息服务与 BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="2fd48-112">This sample, designed in Visual Studio, illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="2fd48-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="2fd48-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="2fd48-114">本示例的默认位置为</span><span class="sxs-lookup"><span data-stu-id="2fd48-114">The default location for the sample is</span></span>  
  
 <span data-ttu-id="2fd48-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span><span class="sxs-lookup"><span data-stu-id="2fd48-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span></span>  
  
 <span data-ttu-id="2fd48-116">下表列出并介绍了示例中的文件。</span><span class="sxs-lookup"><span data-stu-id="2fd48-116">The following table lists and describes the files in the sample.</span></span>  
  
|<span data-ttu-id="2fd48-117">**运行时项目文件名**</span><span class="sxs-lookup"><span data-stu-id="2fd48-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="2fd48-118">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="2fd48-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="2fd48-119">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="2fd48-119">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="2fd48-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="2fd48-120">OneWaySend.sln</span></span>|<span data-ttu-id="2fd48-121">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="2fd48-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="2fd48-122">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="2fd48-122">Schema.xsd</span></span>|<span data-ttu-id="2fd48-123">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="2fd48-123">Schema file for the application.</span></span>|  
|<span data-ttu-id="2fd48-124">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="2fd48-124">Orchestration.odx</span></span>|<span data-ttu-id="2fd48-125">应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2fd48-125">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="2fd48-126">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="2fd48-126">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="2fd48-127">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="2fd48-127">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="2fd48-128">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="2fd48-128">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="2fd48-129">创建用于 TIBCO EMS 的 BizTalk 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="2fd48-129">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  
  
1.  <span data-ttu-id="2fd48-130">启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="2fd48-130">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2fd48-131">单击**启动**，**所有程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-131">Click **Start**, **All Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2fd48-132">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-132">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="2fd48-133">右键单击**适配器**和指向**新建**，**适配器**以显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-133">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="2fd48-134">输入一个值**名称**字段，例如**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-134">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  
  
5.  <span data-ttu-id="2fd48-135">选择**TIBCO 企业消息系统**从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-135">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="2fd48-136">创建 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="2fd48-136">Create a BizTalk Send Port</span></span>  
  
1.  <span data-ttu-id="2fd48-137">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-137">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
2.  <span data-ttu-id="2fd48-138">右键单击**发送端口**和指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-138">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="2fd48-139">输入一个值**名称**字段，例如**TIBCOEMSOneWaySP**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-139">Enter a value for the **Name** field, for example **TIBCOEMSOneWaySP**.</span></span>  
  
4.  <span data-ttu-id="2fd48-140">从中的可用适配器的列表中选择 TIBCO EMS 适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-140">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fd48-141">该值是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建 TIBCO Enterprise Message System 适配器时所指定的名称。</span><span class="sxs-lookup"><span data-stu-id="2fd48-141">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
5.  <span data-ttu-id="2fd48-142">输入值**服务器连接定义**:</span><span class="sxs-lookup"><span data-stu-id="2fd48-142">Enter values for the **Server Connection definition**:</span></span>  
  
    |<span data-ttu-id="2fd48-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="2fd48-143">**Property**</span></span>|<span data-ttu-id="2fd48-144">**值**</span><span class="sxs-lookup"><span data-stu-id="2fd48-144">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="2fd48-145">目标</span><span class="sxs-lookup"><span data-stu-id="2fd48-145">Destination</span></span>|<span data-ttu-id="2fd48-146">服务器目标队列或主题名称。</span><span class="sxs-lookup"><span data-stu-id="2fd48-146">The server destination queue or topic name.</span></span>|  
    |<span data-ttu-id="2fd48-147">端口号</span><span class="sxs-lookup"><span data-stu-id="2fd48-147">Port number</span></span>|<span data-ttu-id="2fd48-148">TIBCO 服务器正在侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="2fd48-148">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="2fd48-149">默认值为 7222。</span><span class="sxs-lookup"><span data-stu-id="2fd48-149">Default value is 7222.</span></span>|  
    |<span data-ttu-id="2fd48-150">服务器名称</span><span class="sxs-lookup"><span data-stu-id="2fd48-150">Server Name</span></span>|<span data-ttu-id="2fd48-151">TIBCO EMS 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="2fd48-151">The name of the TIBCO EMS server.</span></span>|  
  
6.  <span data-ttu-id="2fd48-152">输入值**用户凭据**:</span><span class="sxs-lookup"><span data-stu-id="2fd48-152">Enter values for the **User Credentials**:</span></span>  
  
    |<span data-ttu-id="2fd48-153">**属性**</span><span class="sxs-lookup"><span data-stu-id="2fd48-153">**Property**</span></span>|<span data-ttu-id="2fd48-154">**值**</span><span class="sxs-lookup"><span data-stu-id="2fd48-154">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="2fd48-155">密码</span><span class="sxs-lookup"><span data-stu-id="2fd48-155">Password</span></span>|<span data-ttu-id="2fd48-156">TIBCO EMS 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="2fd48-156">The password for the TIBCO EMS server.</span></span>|  
    |<span data-ttu-id="2fd48-157">用户名</span><span class="sxs-lookup"><span data-stu-id="2fd48-157">User name</span></span>|<span data-ttu-id="2fd48-158">TIBCO EMS 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="2fd48-158">The user name for the TIBCO EMS server.</span></span>|  
  
     <span data-ttu-id="2fd48-159">有关属性的详细信息，请参阅[创建 TIBCO 企业消息服务发送处理程序](../core/creating-tibco-enterprise-message-service-send-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd48-159">For more information about the properties, see [Creating  TIBCO Enterprise Message Service Send Handlers](../core/creating-tibco-enterprise-message-service-send-handlers.md).</span></span>  
  
7.  <span data-ttu-id="2fd48-160">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-160">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="2fd48-161">选择**XML 传输**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-161">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
9. <span data-ttu-id="2fd48-162">右键单击发送端口，然后单击**启动**登记和启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="2fd48-162">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="create-a-file-receive-port"></a><span data-ttu-id="2fd48-163">创建文件接收端口</span><span class="sxs-lookup"><span data-stu-id="2fd48-163">Create a file receive port</span></span>  
  
1.  <span data-ttu-id="2fd48-164">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-164">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="2fd48-165">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**以显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-165">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="2fd48-166">输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-166">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-file-receive-location"></a><span data-ttu-id="2fd48-167">创建文件接收位置</span><span class="sxs-lookup"><span data-stu-id="2fd48-167">Create a file receive location</span></span>  
  
1.  <span data-ttu-id="2fd48-168">为要监视的文件接收位置创建文件夹，例如 C:\Filesource。</span><span class="sxs-lookup"><span data-stu-id="2fd48-168">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  
  
2.  <span data-ttu-id="2fd48-169">右键单击新的接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-169">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  
  
3.  <span data-ttu-id="2fd48-170">输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRL**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-170">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRL**.</span></span>  
  
4.  <span data-ttu-id="2fd48-171">选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-171">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="2fd48-172">输入以前为创建的文件夹的位置**接收文件夹**属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-172">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  
  
6.  <span data-ttu-id="2fd48-173">选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-173">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="2fd48-174">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-174">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="2fd48-175">从适配器架构生成文档实例</span><span class="sxs-lookup"><span data-stu-id="2fd48-175">Generate a document instance from the Adapter schema</span></span>  
  
1.  <span data-ttu-id="2fd48-176">右击 Schema.xsd 在解决方案资源管理器中的，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-176">Right-click Schema.xsd in Solution Explorer and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="2fd48-177">在属性窗口中，单击以选中**输出实例文件名**选项下**常规**类别。</span><span class="sxs-lookup"><span data-stu-id="2fd48-177">In the Properties window, click to select the **Output Instance Filename** option under the **General** category.</span></span>  
  
3.  <span data-ttu-id="2fd48-178">单击省略号按钮 （…） 以显示**选择输出文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-178">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  
  
4.  <span data-ttu-id="2fd48-179">指定的文件夹和输出文件实例的名称，例如**C:\instance.xml**单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-179">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fd48-180">请勿指定为此处的文件接收位置指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="2fd48-180">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  
  
5.  <span data-ttu-id="2fd48-181">右击 Schema.xsd 在解决方案资源管理器中的，单击**生成实例**在指定的位置生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="2fd48-181">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  
  
#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="2fd48-182">修改生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="2fd48-182">Modify the generated document instance</span></span>  
  
1.  <span data-ttu-id="2fd48-183">在文本编辑器（如记事本）中打开生成的文档实例，并编辑文档实例的内容以确保此数据将在 TIBCO 系统中生成唯一的记录。</span><span class="sxs-lookup"><span data-stu-id="2fd48-183">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="2fd48-184">例如，下面的代码显示了此数据文件的第一部分：</span><span class="sxs-lookup"><span data-stu-id="2fd48-184">For example the code below shows the first part of the data file:</span></span>  
  
    ```  
    <ns0:Root xmlns:ns0="http://TibcoEMSOne_WaySend.TibcoEMSOneWaySendSchema">  
      <Name>Punya Palit</Name>  
      <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  
  
2.  <span data-ttu-id="2fd48-185">保存修改后的文档实例。</span><span class="sxs-lookup"><span data-stu-id="2fd48-185">Save the modified document instance.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="2fd48-186">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="2fd48-186">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="2fd48-187">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="2fd48-187">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="2fd48-188">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2fd48-188">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="2fd48-189">输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。</span><span class="sxs-lookup"><span data-stu-id="2fd48-189">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="2fd48-190">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="2fd48-190">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="2fd48-191">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="2fd48-191">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="2fd48-192">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="2fd48-192">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="2fd48-193">单击**刷新**中 MMC 工具栏或按按钮**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="2fd48-193">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="2fd48-194">双击要显示的业务流程**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="2fd48-194">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="2fd48-195">单击**绑定**显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="2fd48-195">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="2fd48-196">指定绑定选项的适当值，例如：</span><span class="sxs-lookup"><span data-stu-id="2fd48-196">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="2fd48-197">**参数**</span><span class="sxs-lookup"><span data-stu-id="2fd48-197">**Parameter**</span></span>|<span data-ttu-id="2fd48-198">**值**</span><span class="sxs-lookup"><span data-stu-id="2fd48-198">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="2fd48-199">主机</span><span class="sxs-lookup"><span data-stu-id="2fd48-199">Host</span></span>|<span data-ttu-id="2fd48-200">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="2fd48-200">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="2fd48-201">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="2fd48-201">FileReceivePort</span></span>|<span data-ttu-id="2fd48-202">TIBCOEMSOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="2fd48-202">TIBCOEMSOneWayFileRP</span></span>|  
    |<span data-ttu-id="2fd48-203">TibcoEMSOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="2fd48-203">TibcoEMSOneWaySendPort</span></span>|<span data-ttu-id="2fd48-204">TIBCOEMSOneWaySP</span><span class="sxs-lookup"><span data-stu-id="2fd48-204">TIBCOEMSOneWaySP</span></span>|  
  
6.  <span data-ttu-id="2fd48-205">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="2fd48-205">Click OK.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="2fd48-206">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="2fd48-206">Start the orchestration</span></span>  
  
-   <span data-ttu-id="2fd48-207">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击业务流程，然后单击**启动**登记和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="2fd48-207">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="2fd48-208">将文档实例拖到由文件接收位置监视的文件夹</span><span class="sxs-lookup"><span data-stu-id="2fd48-208">Drop a document instance into the folder monitored by the file receive location</span></span>  
  
-   <span data-ttu-id="2fd48-209">将早期创建的文档实例复制到应用程序监视的文件接收文件夹。</span><span class="sxs-lookup"><span data-stu-id="2fd48-209">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  
  
#### <a name="verify-that-the-tibco-system-is-updated"></a><span data-ttu-id="2fd48-210">验证 TIBCO 系统是否已更新</span><span class="sxs-lookup"><span data-stu-id="2fd48-210">Verify that the TIBCO system is updated</span></span>  
  
-   <span data-ttu-id="2fd48-211">使用 TIBCO Web 界面验证是否已从 XML 文件中的数据创建记录。</span><span class="sxs-lookup"><span data-stu-id="2fd48-211">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  
  
 <span data-ttu-id="2fd48-212">成功处理文档实例后，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="2fd48-212">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="2fd48-213">文件适配器从文件夹中检索文件，并作为 BizTalk 消息将其发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="2fd48-213">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="2fd48-214">业务流程订阅此发布消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将该消息发送到该业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="2fd48-214">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="2fd48-215">业务流程实例使用业务流程中指定的逻辑处理该消息，并将该消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="2fd48-215">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="2fd48-216">TIBCO 发送端口订阅此发布消息，以便 BizTalk 消息引擎将消息发送到 TIBCO 发送端口。</span><span class="sxs-lookup"><span data-stu-id="2fd48-216">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  
  
5.  <span data-ttu-id="2fd48-217">发送端口将消息传递给用于 TIBCO Enterprise Message Service 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="2fd48-217">The send port hands the message to the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
6.  <span data-ttu-id="2fd48-218">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将消息发送到 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="2fd48-218">The BizTalk Adapter for TIBCO Enterprise Message Service sends the message to the TIBCO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd48-219">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fd48-219">See Also</span></span>  
 <span data-ttu-id="2fd48-220">[教程： 使用 BizTalk Adapter for TIBCO 企业消息服务接收数据](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="2fd48-220">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span></span>  
 <span data-ttu-id="2fd48-221">[教程： 使用 Microsoft BizTalk Adapter for TIBCO 企业消息服务](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="2fd48-221">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="2fd48-222">入门</span><span class="sxs-lookup"><span data-stu-id="2fd48-222">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)