---
title: 教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器发送数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1912d594-3839-4e04-bc40-93bd7cc0b309
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 217abb544fa81faa667ca066d53bc126b88dcc48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266390"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-send-data"></a><span data-ttu-id="3a389-102">教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器发送数据</span><span class="sxs-lookup"><span data-stu-id="3a389-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data</span></span>
<span data-ttu-id="3a389-103">您可以使用 BizTalk 适配器用于 TIBCO Enterprise Message Service (EMS) 将数据发送到 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="3a389-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to send data to a TIBCO system.</span></span> <span data-ttu-id="3a389-104">本演练介绍阐释了这一点的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="3a389-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3a389-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="3a389-105">Prerequisites</span></span>  

- <span data-ttu-id="3a389-106">用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO EMS C# API，TIBCO 添加。EMS.dll，到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="3a389-106">BizTalk Adapter for TIBCO EMS requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="3a389-107">有关安装该程序集的详细信息，请参阅[TIBCO Enterprise Message Service 要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。</span><span class="sxs-lookup"><span data-stu-id="3a389-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  

- <span data-ttu-id="3a389-108">安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器上运行才能生成和部署示例。</span><span class="sxs-lookup"><span data-stu-id="3a389-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="3a389-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="3a389-109">What This Sample Does</span></span>  
 <span data-ttu-id="3a389-110">此示例提取文件文件夹中的 XML 文件，将该文件发送到业务流程，然后使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器在 TIBCO 系统中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="3a389-110">This sample picks up an XML file from a file folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to create a record in the TIBCO system.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="3a389-111">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="3a389-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="3a389-112">此示例中，在 Visual Studio 中设计说明使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器，BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="3a389-112">This sample, designed in Visual Studio, illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="3a389-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="3a389-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="3a389-114">该示例的默认位置是</span><span class="sxs-lookup"><span data-stu-id="3a389-114">The default location for the sample is</span></span>  

 <span data-ttu-id="3a389-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span><span class="sxs-lookup"><span data-stu-id="3a389-115">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWaySend</span></span>  

 <span data-ttu-id="3a389-116">下表列出并介绍了在示例中的文件。</span><span class="sxs-lookup"><span data-stu-id="3a389-116">The following table lists and describes the files in the sample.</span></span>  

|<span data-ttu-id="3a389-117">**Runtime 项目文件名**</span><span class="sxs-lookup"><span data-stu-id="3a389-117">**Runtime Project Filename**</span></span>|<span data-ttu-id="3a389-118">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="3a389-118">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="3a389-119">OneWaySend.btproj</span><span class="sxs-lookup"><span data-stu-id="3a389-119">OneWaySend.btproj</span></span><br /><br /> <span data-ttu-id="3a389-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="3a389-120">OneWaySend.sln</span></span>|<span data-ttu-id="3a389-121">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="3a389-121">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="3a389-122">Schema.xsd</span><span class="sxs-lookup"><span data-stu-id="3a389-122">Schema.xsd</span></span>|<span data-ttu-id="3a389-123">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="3a389-123">Schema file for the application.</span></span>|  
|<span data-ttu-id="3a389-124">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="3a389-124">Orchestration.odx</span></span>|<span data-ttu-id="3a389-125">使用应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="3a389-125">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="3a389-126">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="3a389-126">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="3a389-127">强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="3a389-127">The strong naming key file.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="3a389-128">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="3a389-128">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="3a389-129">创建用于 TIBCO EMS 的 BizTalk 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="3a389-129">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  

1. <span data-ttu-id="3a389-130">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="3a389-130">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="3a389-131">单击**启动**，**所有程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3a389-131">Click **Start**, **All Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3a389-132">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="3a389-132">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="3a389-133">右键单击**适配器**，然后指向**新建**，**适配器**以显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-133">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="3a389-134">输入一个值**名称**字段，例如**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="3a389-134">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  

5. <span data-ttu-id="3a389-135">选择**TIBCO Enterprise Message System**从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3a389-135">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="3a389-136">创建 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="3a389-136">Create a BizTalk Send Port</span></span>  

1. <span data-ttu-id="3a389-137">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3a389-137">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="3a389-138">右键单击**发送端口**，然后指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-138">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="3a389-139">输入一个值**名称**字段，例如**TIBCOEMSOneWaySP**。</span><span class="sxs-lookup"><span data-stu-id="3a389-139">Enter a value for the **Name** field, for example **TIBCOEMSOneWaySP**.</span></span>  

4. <span data-ttu-id="3a389-140">从中可用的适配器列表中选择 TIBCO EMS 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-140">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3a389-141">此值是在中创建 TIBCO Enterprise Message System 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="3a389-141">This value is the name that was specified when the TIBCO Enterprise Message System adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

5. <span data-ttu-id="3a389-142">输入值**服务器连接定义**:</span><span class="sxs-lookup"><span data-stu-id="3a389-142">Enter values for the **Server Connection definition**:</span></span>  


   | <span data-ttu-id="3a389-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="3a389-143">**Property**</span></span> |                                <span data-ttu-id="3a389-144">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3a389-144">**Value**</span></span>                                |
   |--------------|-------------------------------------------------------------------------|
   | <span data-ttu-id="3a389-145">目标</span><span class="sxs-lookup"><span data-stu-id="3a389-145">Destination</span></span>  |               <span data-ttu-id="3a389-146">服务器目标队列或主题名称。</span><span class="sxs-lookup"><span data-stu-id="3a389-146">The server destination queue or topic name.</span></span>               |
   | <span data-ttu-id="3a389-147">端口号</span><span class="sxs-lookup"><span data-stu-id="3a389-147">Port number</span></span>  | <span data-ttu-id="3a389-148">TIBCO 服务器正在侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="3a389-148">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="3a389-149">默认值为 7222。</span><span class="sxs-lookup"><span data-stu-id="3a389-149">Default value is 7222.</span></span> |
   | <span data-ttu-id="3a389-150">服务器名称</span><span class="sxs-lookup"><span data-stu-id="3a389-150">Server Name</span></span>  |                    <span data-ttu-id="3a389-151">TIBCO EMS 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="3a389-151">The name of the TIBCO EMS server.</span></span>                    |


6. <span data-ttu-id="3a389-152">输入值**用户凭据**:</span><span class="sxs-lookup"><span data-stu-id="3a389-152">Enter values for the **User Credentials**:</span></span>  

   |<span data-ttu-id="3a389-153">**属性**</span><span class="sxs-lookup"><span data-stu-id="3a389-153">**Property**</span></span>|<span data-ttu-id="3a389-154">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3a389-154">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="3a389-155">Password</span><span class="sxs-lookup"><span data-stu-id="3a389-155">Password</span></span>|<span data-ttu-id="3a389-156">TIBCO EMS 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="3a389-156">The password for the TIBCO EMS server.</span></span>|  
   |<span data-ttu-id="3a389-157">“用户名”</span><span class="sxs-lookup"><span data-stu-id="3a389-157">User name</span></span>|<span data-ttu-id="3a389-158">TIBCO EMS 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="3a389-158">The user name for the TIBCO EMS server.</span></span>|  

    <span data-ttu-id="3a389-159">有关属性的详细信息，请参阅[创建 TIBCO Enterprise Message Service 发送处理程序](../core/creating-tibco-enterprise-message-service-send-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="3a389-159">For more information about the properties, see [Creating  TIBCO Enterprise Message Service Send Handlers](../core/creating-tibco-enterprise-message-service-send-handlers.md).</span></span>  

7. <span data-ttu-id="3a389-160">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3a389-160">Click **OK**.</span></span>  

8. <span data-ttu-id="3a389-161">选择**XML 传输**中的可用管道列表**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3a389-161">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

9. <span data-ttu-id="3a389-162">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="3a389-162">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="3a389-163">创建文件接收端口</span><span class="sxs-lookup"><span data-stu-id="3a389-163">Create a file receive port</span></span>  

1. <span data-ttu-id="3a389-164">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="3a389-164">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="3a389-165">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-165">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="3a389-166">输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3a389-166">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="3a389-167">创建文件接收位置</span><span class="sxs-lookup"><span data-stu-id="3a389-167">Create a file receive location</span></span>  

1.  <span data-ttu-id="3a389-168">创建一个文件夹，文件接收位置监视，例如 C:\Filesource。</span><span class="sxs-lookup"><span data-stu-id="3a389-168">Create a folder for the file receive location to monitor, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="3a389-169">右键单击新接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-169">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="3a389-170">输入一个值**名称**字段，例如**TIBCOEMSOneWayFileRL**。</span><span class="sxs-lookup"><span data-stu-id="3a389-170">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="3a389-171">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-171">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="3a389-172">输入您为前面创建的文件夹的位置**接收文件夹**属性，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3a389-172">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="3a389-173">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3a389-173">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="3a389-174">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="3a389-174">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="3a389-175">从适配器架构生成文档实例</span><span class="sxs-lookup"><span data-stu-id="3a389-175">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="3a389-176">右键单击 Schema.xsd 在解决方案资源管理器中的，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3a389-176">Right-click Schema.xsd in Solution Explorer and click **Properties**.</span></span>  

2.  <span data-ttu-id="3a389-177">在属性窗口中，单击以选中**输出实例文件名**下**常规**类别。</span><span class="sxs-lookup"><span data-stu-id="3a389-177">In the Properties window, click to select the **Output Instance Filename** option under the **General** category.</span></span>  

3.  <span data-ttu-id="3a389-178">单击省略号按钮 （...） 以显示**选择输出文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-178">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

4.  <span data-ttu-id="3a389-179">指定的文件夹和输出文件实例名称，例如**C:\instance.xml**然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="3a389-179">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="3a389-180">未指定为 file 接收位置在此处指定的文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="3a389-180">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

5.  <span data-ttu-id="3a389-181">右键单击 Schema.xsd 在解决方案资源管理器中的，单击**生成实例**以在指定位置生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="3a389-181">Right-click Schema.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="3a389-182">修改生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="3a389-182">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="3a389-183">在诸如记事本之类的文本编辑器中打开生成的文档实例，并编辑文档实例，以确保数据将在 TIBCO 系统中生成唯一的记录的内容。</span><span class="sxs-lookup"><span data-stu-id="3a389-183">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data will generate a unique record in the TIBCO system.</span></span> <span data-ttu-id="3a389-184">例如，下面的代码显示了数据文件的第一部分：</span><span class="sxs-lookup"><span data-stu-id="3a389-184">For example the code below shows the first part of the data file:</span></span>  

    ```  
    <ns0:Root xmlns:ns0="http://TibcoEMSOne_WaySend.TibcoEMSOneWaySendSchema">  
      <Name>Punya Palit</Name>  
      <MailAddress>Prose Ware, Inc.</MailAddress>  
    </ns0:Root>  
    ```  

2.  <span data-ttu-id="3a389-185">保存修改后的文档实例。</span><span class="sxs-lookup"><span data-stu-id="3a389-185">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="3a389-186">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="3a389-186">Build and deploy the project</span></span>  

1. <span data-ttu-id="3a389-187">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**属性**以启动项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="3a389-187">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="3a389-188">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3a389-188">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="3a389-189">输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。</span><span class="sxs-lookup"><span data-stu-id="3a389-189">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  

4. <span data-ttu-id="3a389-190">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="3a389-190">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="3a389-191">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="3a389-191">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="3a389-192">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="3a389-192">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="3a389-193">单击**刷新**按钮在 MMC 工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="3a389-193">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="3a389-194">双击业务流程以显示**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3a389-194">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="3a389-195">单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="3a389-195">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="3a389-196">指定适当的值的绑定选项，例如：</span><span class="sxs-lookup"><span data-stu-id="3a389-196">Specify the appropriate values for the binding options, for example:</span></span>  


   |     <span data-ttu-id="3a389-197">**参数**</span><span class="sxs-lookup"><span data-stu-id="3a389-197">**Parameter**</span></span>      |        <span data-ttu-id="3a389-198">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3a389-198">**Value**</span></span>         |
   |------------------------|--------------------------|
   |          <span data-ttu-id="3a389-199">主机</span><span class="sxs-lookup"><span data-stu-id="3a389-199">Host</span></span>          | <span data-ttu-id="3a389-200">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="3a389-200">BizTalkServerApplication</span></span> |
   |    <span data-ttu-id="3a389-201">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="3a389-201">FileReceivePort</span></span>     |   <span data-ttu-id="3a389-202">TIBCOEMSOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="3a389-202">TIBCOEMSOneWayFileRP</span></span>   |
   | <span data-ttu-id="3a389-203">TibcoEMSOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="3a389-203">TibcoEMSOneWaySendPort</span></span> |     <span data-ttu-id="3a389-204">TIBCOEMSOneWaySP</span><span class="sxs-lookup"><span data-stu-id="3a389-204">TIBCOEMSOneWaySP</span></span>     |


6. <span data-ttu-id="3a389-205">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="3a389-205">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="3a389-206">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="3a389-206">Start the orchestration</span></span>  

- <span data-ttu-id="3a389-207">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该业务流程，然后单击**启动**以登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="3a389-207">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="3a389-208">拖放到该文件所监视的文件夹的文档实例接收位置</span><span class="sxs-lookup"><span data-stu-id="3a389-208">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="3a389-209">复制到文件之前创建的文档实例接收文件夹应用程序监视器。</span><span class="sxs-lookup"><span data-stu-id="3a389-209">Copy the document instance that was created earlier to the file receive folder the application monitors.</span></span>  

#### <a name="verify-that-the-tibco-system-is-updated"></a><span data-ttu-id="3a389-210">验证 TIBCO 系统已更新</span><span class="sxs-lookup"><span data-stu-id="3a389-210">Verify that the TIBCO system is updated</span></span>  

- <span data-ttu-id="3a389-211">使用 TIBCO web 界面验证记录已创建从 XML 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="3a389-211">Use the TIBCO web interface to verify that the record was created from the data in the XML file.</span></span>  

  <span data-ttu-id="3a389-212">如果成功处理的文档实例，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="3a389-212">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="3a389-213">文件适配器从文件夹中检索该文件，并将其发布到 MessageBox 作为 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="3a389-213">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="3a389-214">业务流程订阅此发布的消息，以便 BizTalk 消息引擎将激活业务流程的实例并将消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="3a389-214">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="3a389-215">业务流程实例处理使用业务流程中指定的逻辑消息，并将消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="3a389-215">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="3a389-216">TIBCO 发送端口订阅此发布消息，因此 BizTalk 消息引擎将消息发送到 TIBCO 发送端口。</span><span class="sxs-lookup"><span data-stu-id="3a389-216">The TIBCO send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the TIBCO send port.</span></span>  

5.  <span data-ttu-id="3a389-217">发送端口将消息传 TIBCO Enterprise Message Service 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="3a389-217">The send port hands the message to the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  

6.  <span data-ttu-id="3a389-218">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将消息发送到 TIBCO 系统。</span><span class="sxs-lookup"><span data-stu-id="3a389-218">The BizTalk Adapter for TIBCO Enterprise Message Service sends the message to the TIBCO system.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3a389-219">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a389-219">See Also</span></span>  
 <span data-ttu-id="3a389-220">[教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器接收数据](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span><span class="sxs-lookup"><span data-stu-id="3a389-220">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data](../core/tutorial-us-the-biztalk-adapter-for-tibco-message-service-to-receive-data.md) </span></span>  
 <span data-ttu-id="3a389-221">[教程：使用用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="3a389-221">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="3a389-222">入门</span><span class="sxs-lookup"><span data-stu-id="3a389-222">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)