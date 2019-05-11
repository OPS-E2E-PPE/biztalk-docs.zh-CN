---
title: 教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器接收数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc5a63ec-1897-4c9b-b37f-cdcec151b1c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e8697598b0f4eff86e72fde53747ba0259af8c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399153"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a><span data-ttu-id="f987c-102">教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器接收数据</span><span class="sxs-lookup"><span data-stu-id="f987c-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data</span></span>
<span data-ttu-id="f987c-103">可以使用用于 TIBCO Enterprise Message Service (EMS) 的 BizTalk 适配器从 TIBCO 系统接收数据。</span><span class="sxs-lookup"><span data-stu-id="f987c-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to receive data from a TIBCO system.</span></span> <span data-ttu-id="f987c-104">本演练介绍阐释了这一点的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="f987c-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="f987c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="f987c-105">Prerequisites</span></span>  

- <span data-ttu-id="f987c-106">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器要求将 TIBCO EMS C# API，TIBCO 添加。EMS.dll，到全局程序集缓存 (GAC)。</span><span class="sxs-lookup"><span data-stu-id="f987c-106">BizTalk Adapter for TIBCO Enterprise Message Service requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="f987c-107">有关安装该程序集的详细信息，请参阅[TIBCO Enterprise Message Service 要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。</span><span class="sxs-lookup"><span data-stu-id="f987c-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  

- <span data-ttu-id="f987c-108">安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器上运行才能生成和部署示例。</span><span class="sxs-lookup"><span data-stu-id="f987c-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="f987c-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="f987c-109">What This Sample Does</span></span>  
 <span data-ttu-id="f987c-110">此示例提取一个文件夹中的 XML 文件、 将该文件发送到业务流程，然后使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器从 TIBCO 系统检索数据。</span><span class="sxs-lookup"><span data-stu-id="f987c-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to retrieve data from a TIBCO system.</span></span> <span data-ttu-id="f987c-111">将结果写入到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="f987c-111">The result is written to an XML file.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="f987c-112">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="f987c-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="f987c-113">此示例中，在 Visual Studio 中设计说明使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器，BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="f987c-113">This sample, designed in Visual Studio, illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f987c-114">该示例假定您知道如何从应用程序处理的 TIBCO 发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="f987c-114">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="f987c-115">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="f987c-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="f987c-116">该示例的默认位置是</span><span class="sxs-lookup"><span data-stu-id="f987c-116">The default location for the sample is</span></span>  

 <span data-ttu-id="f987c-117">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span><span class="sxs-lookup"><span data-stu-id="f987c-117">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span></span>  

 <span data-ttu-id="f987c-118">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="f987c-118">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="f987c-119">**Runtime 项目文件名**</span><span class="sxs-lookup"><span data-stu-id="f987c-119">**Runtime Project Filename**</span></span>|<span data-ttu-id="f987c-120">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="f987c-120">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="f987c-121">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="f987c-121">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="f987c-122">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="f987c-122">OneWayReceive.sln</span></span>|<span data-ttu-id="f987c-123">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="f987c-123">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="f987c-124">Schema.xsd，</span><span class="sxs-lookup"><span data-stu-id="f987c-124">Schema.xsd,</span></span>|<span data-ttu-id="f987c-125">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="f987c-125">Schema file for the application.</span></span>|  
|<span data-ttu-id="f987c-126">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="f987c-126">Orchestration.odx</span></span>|<span data-ttu-id="f987c-127">使用应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="f987c-127">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="f987c-128">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="f987c-128">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="f987c-129">强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="f987c-129">The strong naming key file.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="f987c-130">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="f987c-130">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="f987c-131">创建用于 TIBCO EMS 的 BizTalk 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="f987c-131">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  

1. <span data-ttu-id="f987c-132">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f987c-132">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f987c-133">单击**启动**，**程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f987c-133">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f987c-134">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="f987c-134">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="f987c-135">右键单击**适配器**，然后指向**新建**，**适配器**以显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f987c-135">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="f987c-136">输入一个值**名称**字段，例如**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="f987c-136">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  

5. <span data-ttu-id="f987c-137">选择**TIBCO Enterprise Message System**从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f987c-137">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-biztalk-receive-port"></a><span data-ttu-id="f987c-138">创建 BizTalk 接收端口</span><span class="sxs-lookup"><span data-stu-id="f987c-138">Create a BizTalk Receive Port</span></span>  

1. <span data-ttu-id="f987c-139">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="f987c-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="f987c-140">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="f987c-140">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="f987c-141">输入一个值**名称**字段，例如**TIBCOEMSOneWayRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f987c-141">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRP**, and click **OK**.</span></span>  

#### <a name="create-a-biztalk-receive-location"></a><span data-ttu-id="f987c-142">创建 BizTalk 接收位置</span><span class="sxs-lookup"><span data-stu-id="f987c-142">Create a BizTalk Receive Location</span></span>  

1. <span data-ttu-id="f987c-143">右键单击新接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f987c-143">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

2. <span data-ttu-id="f987c-144">输入一个值**名称**字段，例如**TIBCOEMSOneWayRL**。</span><span class="sxs-lookup"><span data-stu-id="f987c-144">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRL**.</span></span>  

3. <span data-ttu-id="f987c-145">从中可用的适配器列表中选择 TIBCO EMS 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f987c-145">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f987c-146">此值是在中创建 TIBCO 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f987c-146">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

4. <span data-ttu-id="f987c-147">输入值**服务器连接定义**:</span><span class="sxs-lookup"><span data-stu-id="f987c-147">Enter values for the **Server Connection definition**:</span></span>  


   | <span data-ttu-id="f987c-148">**属性**</span><span class="sxs-lookup"><span data-stu-id="f987c-148">**Property**</span></span> |                                <span data-ttu-id="f987c-149">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f987c-149">**Value**</span></span>                                |
   |--------------|-------------------------------------------------------------------------|
   | <span data-ttu-id="f987c-150">目标</span><span class="sxs-lookup"><span data-stu-id="f987c-150">Destination</span></span>  |               <span data-ttu-id="f987c-151">服务器目标队列或主题名称。</span><span class="sxs-lookup"><span data-stu-id="f987c-151">The server destination queue or topic name.</span></span>               |
   | <span data-ttu-id="f987c-152">端口号</span><span class="sxs-lookup"><span data-stu-id="f987c-152">Port number</span></span>  | <span data-ttu-id="f987c-153">TIBCO 服务器正在侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="f987c-153">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="f987c-154">默认值为 7222。</span><span class="sxs-lookup"><span data-stu-id="f987c-154">Default value is 7222.</span></span> |
   | <span data-ttu-id="f987c-155">服务器名称</span><span class="sxs-lookup"><span data-stu-id="f987c-155">Server Name</span></span>  |                    <span data-ttu-id="f987c-156">TIBCO EMS 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f987c-156">The name of the TIBCO EMS server.</span></span>                    |


5. <span data-ttu-id="f987c-157">输入值**用户凭据**:</span><span class="sxs-lookup"><span data-stu-id="f987c-157">Enter values for the **User Credentials**:</span></span>  

   |<span data-ttu-id="f987c-158">**属性**</span><span class="sxs-lookup"><span data-stu-id="f987c-158">**Property**</span></span>|<span data-ttu-id="f987c-159">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f987c-159">**Value**</span></span>|  
   |------------------|---------------|  
   |<span data-ttu-id="f987c-160">Password</span><span class="sxs-lookup"><span data-stu-id="f987c-160">Password</span></span>|<span data-ttu-id="f987c-161">TIBCO EMS 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="f987c-161">The password for the TIBCO EMS server.</span></span>|  
   |<span data-ttu-id="f987c-162">“用户名”</span><span class="sxs-lookup"><span data-stu-id="f987c-162">User name</span></span>|<span data-ttu-id="f987c-163">TIBCO EMS 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="f987c-163">The user name for the TIBCO EMS server.</span></span>|  

    <span data-ttu-id="f987c-164">有关属性的详细信息，请参阅[创建 TIBCO Enterprise Message Service 接收处理程序](../core/creating-tibco-enterprise-message-service-receive-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="f987c-164">For more information about the properties, see [Creating TIBCO Enterprise Message Service Receive Handlers](../core/creating-tibco-enterprise-message-service-receive-handlers.md).</span></span>  

6. <span data-ttu-id="f987c-165">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f987c-165">Click **OK**.</span></span>  

7. <span data-ttu-id="f987c-166">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f987c-166">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

8. <span data-ttu-id="f987c-167">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="f987c-167">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="create-a-one-way-file-send-port"></a><span data-ttu-id="f987c-168">创建一个单向 file 发送端口</span><span class="sxs-lookup"><span data-stu-id="f987c-168">Create a one-way file send port</span></span>  

1. <span data-ttu-id="f987c-169">创建发送端口，例如 C:\FilesOut 要使用的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="f987c-169">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  

2. <span data-ttu-id="f987c-170">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="f987c-170">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

3. <span data-ttu-id="f987c-171">右键单击**发送端口**，然后指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f987c-171">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  

4. <span data-ttu-id="f987c-172">输入一个值**名称**字段，例如**TIBCOEMSOneWayFileSP**。</span><span class="sxs-lookup"><span data-stu-id="f987c-172">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileSP**.</span></span>  

5. <span data-ttu-id="f987c-173">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f987c-173">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

6. <span data-ttu-id="f987c-174">有关**目标文件夹**属性中，输入前面创建的文件夹的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f987c-174">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  

7. <span data-ttu-id="f987c-175">选择**XMLTransmit**中的可用管道列表**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f987c-175">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="f987c-176">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="f987c-176">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="f987c-177">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="f987c-177">Build and deploy the project</span></span>  

1. <span data-ttu-id="f987c-178">右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**属性**以启动项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="f987c-178">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  

2. <span data-ttu-id="f987c-179">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f987c-179">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="f987c-180">输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。</span><span class="sxs-lookup"><span data-stu-id="f987c-180">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  

4. <span data-ttu-id="f987c-181">右键单击 OneWayReceive 项目在解决方案资源管理器中的，单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="f987c-181">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="f987c-182">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="f987c-182">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="f987c-183">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="f987c-183">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="f987c-184">单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="f987c-184">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  

3. <span data-ttu-id="f987c-185">双击业务流程以显示**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="f987c-185">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="f987c-186">单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="f987c-186">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="f987c-187">指定适当的值的绑定选项，例如：</span><span class="sxs-lookup"><span data-stu-id="f987c-187">Specify the appropriate values for the binding options, for example:</span></span>  


   |         <span data-ttu-id="f987c-188">**参数**</span><span class="sxs-lookup"><span data-stu-id="f987c-188">**Parameter**</span></span>          |        <span data-ttu-id="f987c-189">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f987c-189">**Value**</span></span>         |
   |--------------------------------|--------------------------|
   |              <span data-ttu-id="f987c-190">主机</span><span class="sxs-lookup"><span data-stu-id="f987c-190">Host</span></span>              | <span data-ttu-id="f987c-191">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="f987c-191">BizTalkServerApplication</span></span> |
   |          <span data-ttu-id="f987c-192">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="f987c-192">FileSendPort</span></span>          |   <span data-ttu-id="f987c-193">TIBCOEMSOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="f987c-193">TIBCOEMSOneWayFileSP</span></span>   |
   | <span data-ttu-id="f987c-194">TibcoEMSOneWayReceiveOperation</span><span class="sxs-lookup"><span data-stu-id="f987c-194">TibcoEMSOneWayReceiveOperation</span></span> |     <span data-ttu-id="f987c-195">TIBCOEMSOneWayRP</span><span class="sxs-lookup"><span data-stu-id="f987c-195">TIBCOEMSOneWayRP</span></span>     |


6. <span data-ttu-id="f987c-196">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f987c-196">Click **OK**.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="f987c-197">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="f987c-197">Start the orchestration</span></span>  

- <span data-ttu-id="f987c-198">在中[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]管理控制台中，右键单击该业务流程，然后单击**启动**以登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="f987c-198">In the [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="verify-that-the-application-receives-a-message"></a><span data-ttu-id="f987c-199">验证应用程序收到一条消息</span><span class="sxs-lookup"><span data-stu-id="f987c-199">Verify that the application receives a message</span></span>  

- <span data-ttu-id="f987c-200">打开文件发送端口配置为将发送到并验证已生成输出文档的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f987c-200">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span> <span data-ttu-id="f987c-201">此文件应包含用于 TIBCO Enterprise Message Service 的 BizTalk 适配器处理查询的结果。</span><span class="sxs-lookup"><span data-stu-id="f987c-201">This file should contain the results of the query that was processed by the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  

  <span data-ttu-id="f987c-202">如果成功处理的文档实例，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="f987c-202">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="f987c-203">TIBCO EMS 适配器从 TIBCO 系统接收消息，并将其发布到 MessageBox 作为 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="f987c-203">The TIBCO EMS adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="f987c-204">业务流程订阅此发布的消息，以便 BizTalk 消息引擎会激活业务流程的实例，并将消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="f987c-204">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="f987c-205">业务流程实例将消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="f987c-205">The orchestration instance publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="f987c-206">File 发送端口订阅此消息，以便 BizTalk 向文件适配器发送的消息。</span><span class="sxs-lookup"><span data-stu-id="f987c-206">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  

5.  <span data-ttu-id="f987c-207">文件适配器写入包含结果集限于指定的输出文件夹的消息。</span><span class="sxs-lookup"><span data-stu-id="f987c-207">The File adapter writes the message containing the result set to the designated output folder.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f987c-208">请参阅</span><span class="sxs-lookup"><span data-stu-id="f987c-208">See Also</span></span>  
 <span data-ttu-id="f987c-209">[教程：使用用于 TIBCO Enterprise Message Service 的 BizTalk 适配器发送数据](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="f987c-209">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span></span>  
 <span data-ttu-id="f987c-210">[教程：使用用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="f987c-210">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="f987c-211">入门</span><span class="sxs-lookup"><span data-stu-id="f987c-211">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)