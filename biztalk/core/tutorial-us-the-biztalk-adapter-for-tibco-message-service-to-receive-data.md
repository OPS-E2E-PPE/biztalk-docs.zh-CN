---
title: 教程： 使用 BizTalk Adapter for TIBCO 企业消息服务接收数据 |Microsoft 文档
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
ms.openlocfilehash: 7ee9994861772be8fabe04a04e9bb30111cc1bc4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008574"
---
# <a name="tutorial-using-the-biztalk-adapter-for-tibco-enterprise-message-service-to-receive-data"></a><span data-ttu-id="20df9-102">教程：使用 TIBCO Enterprise Message Service 的 BizTalk 适配器以接收数据</span><span class="sxs-lookup"><span data-stu-id="20df9-102">Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Receive Data</span></span>
<span data-ttu-id="20df9-103">您可以使用适用于 TIBCO Enterprise Message Service (EMS) 的 BizTalk 适配器从 TIBCO 系统接收数据。</span><span class="sxs-lookup"><span data-stu-id="20df9-103">You can use the BizTalk Adapter for TIBCO Enterprise Message Service (EMS) to receive data from a TIBCO system.</span></span> <span data-ttu-id="20df9-104">本演练描述了对此进行说明的一个 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="20df9-104">This walkthrough describes an SDK sample that illustrates this.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20df9-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="20df9-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="20df9-106">适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器要求您向全局程序集缓存 (GAC) 中添加 TIBCO EMS C# API 和 TIBCO.EMS.dll。</span><span class="sxs-lookup"><span data-stu-id="20df9-106">BizTalk Adapter for TIBCO Enterprise Message Service requires that you add the TIBCO EMS C# API, TIBCO.EMS.dll, to the global assembly cache (GAC).</span></span> <span data-ttu-id="20df9-107">有关安装程序集的详细信息，请参阅[TIBCO 企业消息服务要求和限制](../core/tibco-enterprise-message-service-requirements-and-limitations.md)。</span><span class="sxs-lookup"><span data-stu-id="20df9-107">For more information about installing the assembly, see [TIBCO Enterprise Message Service Requirements and Limitations](../core/tibco-enterprise-message-service-requirements-and-limitations.md).</span></span>  
  
-   <span data-ttu-id="20df9-108">为了生成并部署该示例，请在运行此适配器的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="20df9-108">Install [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the adapter is running on in order to build and deploy the sample.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="20df9-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="20df9-109">What This Sample Does</span></span>  
 <span data-ttu-id="20df9-110">本示例从文件夹提取 XML 文件，将该文件发送到业务流程，然后使用适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器从 TIBCO 系统检索数据。</span><span class="sxs-lookup"><span data-stu-id="20df9-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for TIBCO Enterprise Message Service to retrieve data from a TIBCO system.</span></span> <span data-ttu-id="20df9-111">结果将写入一个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="20df9-111">The result is written to an XML file.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="20df9-112">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="20df9-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="20df9-113">此示例中，在 Visual Studio 中设计演示 BizTalk 适配器用于 TIBCO 企业消息服务与 BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="20df9-113">This sample, designed in Visual Studio, illustrates basic functionality using the BizTalk Adapter for TIBCO Enterprise Message Service with a BizTalk orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20df9-114">本示例假定您知道如何发送来自 TIBCO 的消息以供应用程序处理。</span><span class="sxs-lookup"><span data-stu-id="20df9-114">The sample assumes that you know how to send a message from TIBCO for the application to process.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="20df9-115">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="20df9-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="20df9-116">本示例的默认位置为</span><span class="sxs-lookup"><span data-stu-id="20df9-116">The default location for the sample is</span></span>  
  
 <span data-ttu-id="20df9-117">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span><span class="sxs-lookup"><span data-stu-id="20df9-117">C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)\Sdk\OneWayReceive</span></span>  
  
 <span data-ttu-id="20df9-118">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="20df9-118">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="20df9-119">**运行时项目文件名**</span><span class="sxs-lookup"><span data-stu-id="20df9-119">**Runtime Project Filename**</span></span>|<span data-ttu-id="20df9-120">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="20df9-120">**Runtime Project File Description**</span></span>|  
|----------------------------------|------------------------------------------|  
|<span data-ttu-id="20df9-121">OneWayReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="20df9-121">OneWayReceive.btproj,</span></span><br /><br /> <span data-ttu-id="20df9-122">OneWayReceive.sln</span><span class="sxs-lookup"><span data-stu-id="20df9-122">OneWayReceive.sln</span></span>|<span data-ttu-id="20df9-123">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="20df9-123">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="20df9-124">Schema.xsd,</span><span class="sxs-lookup"><span data-stu-id="20df9-124">Schema.xsd,</span></span>|<span data-ttu-id="20df9-125">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="20df9-125">Schema file for the application.</span></span>|  
|<span data-ttu-id="20df9-126">Orchestration.odx</span><span class="sxs-lookup"><span data-stu-id="20df9-126">Orchestration.odx</span></span>|<span data-ttu-id="20df9-127">应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="20df9-127">The orchestration used by the application.</span></span>|  
|<span data-ttu-id="20df9-128">TIBCOEMSOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="20df9-128">TIBCOEMSOneWaySend.snk</span></span>|<span data-ttu-id="20df9-129">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="20df9-129">The strong naming key file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="20df9-130">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="20df9-130">How to Use This Sample</span></span>  
  
#### <a name="create-a-new-instance-of-the-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="20df9-131">创建用于 TIBCO EMS 的 BizTalk 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="20df9-131">Create a new instance of the BizTalk Adapter for TIBCO EMS</span></span>  
  
1.  <span data-ttu-id="20df9-132">启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="20df9-132">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="20df9-133">单击**启动**，**程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="20df9-133">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="20df9-134">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="20df9-134">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="20df9-135">右键单击**适配器**和指向**新建**，**适配器**以显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="20df9-135">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="20df9-136">输入一个值**名称**字段，例如**TIBCO EMS**。</span><span class="sxs-lookup"><span data-stu-id="20df9-136">Enter a value for the **Name** field, for example **TIBCO EMS**.</span></span>  
  
5.  <span data-ttu-id="20df9-137">选择**TIBCO 企业消息系统**从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20df9-137">Select **TIBCO Enterprise Message System** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-port"></a><span data-ttu-id="20df9-138">创建 BizTalk 接收端口</span><span class="sxs-lookup"><span data-stu-id="20df9-138">Create a BizTalk Receive Port</span></span>  
  
1.  <span data-ttu-id="20df9-139">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="20df9-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="20df9-140">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**以显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="20df9-140">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port** to display the Receive Port Properties dialog.</span></span>  
  
3.  <span data-ttu-id="20df9-141">输入一个值**名称**字段，例如**TIBCOEMSOneWayRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20df9-141">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRP**, and click **OK**.</span></span>  
  
#### <a name="create-a-biztalk-receive-location"></a><span data-ttu-id="20df9-142">创建 BizTalk 接收位置</span><span class="sxs-lookup"><span data-stu-id="20df9-142">Create a BizTalk Receive Location</span></span>  
  
1.  <span data-ttu-id="20df9-143">右键单击新的接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="20df9-143">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="20df9-144">输入一个值**名称**字段，例如**TIBCOEMSOneWayRL**。</span><span class="sxs-lookup"><span data-stu-id="20df9-144">Enter a value for the **Name** field, for example **TIBCOEMSOneWayRL**.</span></span>  
  
3.  <span data-ttu-id="20df9-145">从中的可用适配器的列表中选择 TIBCO EMS 适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="20df9-145">Select the TIBCO EMS adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20df9-146">该值是在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建 TIBCO 适配器时指定的名称。</span><span class="sxs-lookup"><span data-stu-id="20df9-146">This value is the name that was specified when the TIBCO adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="20df9-147">输入值**服务器连接定义**:</span><span class="sxs-lookup"><span data-stu-id="20df9-147">Enter values for the **Server Connection definition**:</span></span>  
  
    |<span data-ttu-id="20df9-148">**属性**</span><span class="sxs-lookup"><span data-stu-id="20df9-148">**Property**</span></span>|<span data-ttu-id="20df9-149">**值**</span><span class="sxs-lookup"><span data-stu-id="20df9-149">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="20df9-150">目标</span><span class="sxs-lookup"><span data-stu-id="20df9-150">Destination</span></span>|<span data-ttu-id="20df9-151">服务器目标队列或主题名称。</span><span class="sxs-lookup"><span data-stu-id="20df9-151">The server destination queue or topic name.</span></span>|  
    |<span data-ttu-id="20df9-152">端口号</span><span class="sxs-lookup"><span data-stu-id="20df9-152">Port number</span></span>|<span data-ttu-id="20df9-153">TIBCO 服务器正在侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="20df9-153">The port on which the TIBCO server is listening.</span></span> <span data-ttu-id="20df9-154">默认值为 7222。</span><span class="sxs-lookup"><span data-stu-id="20df9-154">Default value is 7222.</span></span>|  
    |<span data-ttu-id="20df9-155">服务器名称</span><span class="sxs-lookup"><span data-stu-id="20df9-155">Server Name</span></span>|<span data-ttu-id="20df9-156">TIBCO EMS 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="20df9-156">The name of the TIBCO EMS server.</span></span>|  
  
5.  <span data-ttu-id="20df9-157">输入值**用户凭据**:</span><span class="sxs-lookup"><span data-stu-id="20df9-157">Enter values for the **User Credentials**:</span></span>  
  
    |<span data-ttu-id="20df9-158">**属性**</span><span class="sxs-lookup"><span data-stu-id="20df9-158">**Property**</span></span>|<span data-ttu-id="20df9-159">**值**</span><span class="sxs-lookup"><span data-stu-id="20df9-159">**Value**</span></span>|  
    |------------------|---------------|  
    |<span data-ttu-id="20df9-160">密码</span><span class="sxs-lookup"><span data-stu-id="20df9-160">Password</span></span>|<span data-ttu-id="20df9-161">TIBCO EMS 服务器的密码。</span><span class="sxs-lookup"><span data-stu-id="20df9-161">The password for the TIBCO EMS server.</span></span>|  
    |<span data-ttu-id="20df9-162">用户名</span><span class="sxs-lookup"><span data-stu-id="20df9-162">User name</span></span>|<span data-ttu-id="20df9-163">TIBCO EMS 服务器的用户名。</span><span class="sxs-lookup"><span data-stu-id="20df9-163">The user name for the TIBCO EMS server.</span></span>|  
  
     <span data-ttu-id="20df9-164">有关属性的详细信息，请参阅[创建 TIBCO 企业消息服务接收处理程序](../core/creating-tibco-enterprise-message-service-receive-handlers.md)。</span><span class="sxs-lookup"><span data-stu-id="20df9-164">For more information about the properties, see [Creating TIBCO Enterprise Message Service Receive Handlers](../core/creating-tibco-enterprise-message-service-receive-handlers.md).</span></span>  
  
6.  <span data-ttu-id="20df9-165">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="20df9-165">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="20df9-166">选择**XMLReceive**从列表中的可用管道**接收管道**下拉列表框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20df9-166">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  
  
8.  <span data-ttu-id="20df9-167">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="20df9-167">Right-click the receive location and click **Enable**.</span></span>  
  
#### <a name="create-a-one-way-file-send-port"></a><span data-ttu-id="20df9-168">创建单向文件发送端口</span><span class="sxs-lookup"><span data-stu-id="20df9-168">Create a one-way file send port</span></span>  
  
1.  <span data-ttu-id="20df9-169">创建发送端口要使用的目标文件夹，例如 C:\FilesOut。</span><span class="sxs-lookup"><span data-stu-id="20df9-169">Create a target folder to be used by the send port, for example C:\FilesOut.</span></span>  
  
2.  <span data-ttu-id="20df9-170">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="20df9-170">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="20df9-171">右键单击**发送端口**和指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="20df9-171">Right-click **Send Ports** and point to **New**, **Static One-way Send Port** to display the **Send Port Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="20df9-172">输入一个值**名称**字段，例如**TIBCOEMSOneWayFileSP**。</span><span class="sxs-lookup"><span data-stu-id="20df9-172">Enter a value for the **Name** field, for example **TIBCOEMSOneWayFileSP**.</span></span>  
  
5.  <span data-ttu-id="20df9-173">选择**文件**从列表中的可用适配器**类型**下拉列表框中，单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="20df9-173">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  
  
6.  <span data-ttu-id="20df9-174">有关**目标文件夹**属性，输入前面创建的文件夹的位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20df9-174">For the **Destination Folder** property, enter the location of the folder that you created earlier and click **OK**.</span></span>  
  
7.  <span data-ttu-id="20df9-175">选择**XMLTransmit**从管道中提供的列表的管道**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20df9-175">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  
  
8.  <span data-ttu-id="20df9-176">右键单击发送端口，然后单击**启动**登记和启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="20df9-176">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  
  
#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="20df9-177">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="20df9-177">Build and deploy the project</span></span>  
  
1.  <span data-ttu-id="20df9-178">右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**属性**以启动项目设计器中为该项目。</span><span class="sxs-lookup"><span data-stu-id="20df9-178">Right-click the OneWayReceive project in Solution Explorer and click **Properties** to launch the Project Designer for the project.</span></span>  
  
2.  <span data-ttu-id="20df9-179">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="20df9-179">Click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="20df9-180">输入适当的值为**服务器**属性和**配置数据库**下的属性**BizTalk 组**类别。</span><span class="sxs-lookup"><span data-stu-id="20df9-180">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group** category.</span></span>  
  
4.  <span data-ttu-id="20df9-181">右键单击解决方案资源管理器中的 OneWayReceive 项目，然后单击**部署**以生成项目并将其部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="20df9-181">Right-click the OneWayReceive project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  
  
#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="20df9-182">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="20df9-182">Bind and Enlist the orchestration</span></span>  
  
1.  <span data-ttu-id="20df9-183">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk 应用程序 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="20df9-183">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="20df9-184">单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**密钥刷新你键盘上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="20df9-184">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console view.</span></span>  
  
3.  <span data-ttu-id="20df9-185">双击要显示的业务流程**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="20df9-185">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  
  
4.  <span data-ttu-id="20df9-186">单击**绑定**显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="20df9-186">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  
  
5.  <span data-ttu-id="20df9-187">指定绑定选项的适当值，例如：</span><span class="sxs-lookup"><span data-stu-id="20df9-187">Specify the appropriate values for the binding options, for example:</span></span>  
  
    |<span data-ttu-id="20df9-188">**参数**</span><span class="sxs-lookup"><span data-stu-id="20df9-188">**Parameter**</span></span>|<span data-ttu-id="20df9-189">**值**</span><span class="sxs-lookup"><span data-stu-id="20df9-189">**Value**</span></span>|  
    |-------------------|---------------|  
    |<span data-ttu-id="20df9-190">主机</span><span class="sxs-lookup"><span data-stu-id="20df9-190">Host</span></span>|<span data-ttu-id="20df9-191">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="20df9-191">BizTalkServerApplication</span></span>|  
    |<span data-ttu-id="20df9-192">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="20df9-192">FileSendPort</span></span>|<span data-ttu-id="20df9-193">TIBCOEMSOneWayFileSP</span><span class="sxs-lookup"><span data-stu-id="20df9-193">TIBCOEMSOneWayFileSP</span></span>|  
    |<span data-ttu-id="20df9-194">TibcoEMSOneWayReceiveOperation</span><span class="sxs-lookup"><span data-stu-id="20df9-194">TibcoEMSOneWayReceiveOperation</span></span>|<span data-ttu-id="20df9-195">TIBCOEMSOneWayRP</span><span class="sxs-lookup"><span data-stu-id="20df9-195">TIBCOEMSOneWayRP</span></span>|  
  
6.  <span data-ttu-id="20df9-196">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="20df9-196">Click **OK**.</span></span>  
  
#### <a name="start-the-orchestration"></a><span data-ttu-id="20df9-197">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="20df9-197">Start the orchestration</span></span>  
  
-   <span data-ttu-id="20df9-198">在[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]管理控制台中，右键单击业务流程，然后单击**启动**登记和启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="20df9-198">In the [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] Administration console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  
  
#### <a name="verify-that-the-application-receives-a-message"></a><span data-ttu-id="20df9-199">验证应用程序是否收到消息</span><span class="sxs-lookup"><span data-stu-id="20df9-199">Verify that the application receives a message</span></span>  
  
-   <span data-ttu-id="20df9-200">打开将文件发送端口配置为发送到的目标文件夹，并验证是否已生成输出文档。</span><span class="sxs-lookup"><span data-stu-id="20df9-200">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span> <span data-ttu-id="20df9-201">此文件应包含适用于 TIBCO Enterprise Message Service 的 BizTalk 适配器处理的查询结果。</span><span class="sxs-lookup"><span data-stu-id="20df9-201">This file should contain the results of the query that was processed by the BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="20df9-202">成功处理文档实例后，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="20df9-202">The following sequence of events occurs if the document instance is processed successfully:</span></span>  
  
1.  <span data-ttu-id="20df9-203">TIBCO EMS 适配器从 TIBCO 系统接收消息，并将其作为 BizTalk 消息发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="20df9-203">The TIBCO EMS adapter receives a message from TIBCO system and publishes it to the MessageBox as a BizTalk message.</span></span>  
  
2.  <span data-ttu-id="20df9-204">业务流程会订阅此发布的消息，以便 BizTalk 消息引擎能够激活业务流程的实例，并将该消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="20df9-204">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  
  
3.  <span data-ttu-id="20df9-205">业务流程实例将此消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="20df9-205">The orchestration instance publishes the message back to the MessageBox.</span></span>  
  
4.  <span data-ttu-id="20df9-206">文件发送端口会订阅此消息，以便 BizTalk 能够将消息发送到文件适配器。</span><span class="sxs-lookup"><span data-stu-id="20df9-206">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  
  
5.  <span data-ttu-id="20df9-207">文件适配器将包含结果集的消息写入到指定的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="20df9-207">The File adapter writes the message containing the result set to the designated output folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20df9-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20df9-208">See Also</span></span>  
 <span data-ttu-id="20df9-209">[教程： 使用 TIBCO 企业消息服务的 BizTalk 适配器将数据发送](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span><span class="sxs-lookup"><span data-stu-id="20df9-209">[Tutorial: Using the BizTalk Adapter for TIBCO Enterprise Message Service to Send Data](../core/tutorial-use-tibco-enterprise-message-service-adapter-in-biztalk-to-send-data.md) </span></span>  
 <span data-ttu-id="20df9-210">[教程： 使用 Microsoft BizTalk Adapter for TIBCO 企业消息服务](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span><span class="sxs-lookup"><span data-stu-id="20df9-210">[Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Enterprise Message Service](../core/tutorials-use-the-microsoft-biztalk-adapter-for-tibco-message-service.md) </span></span>  
 [<span data-ttu-id="20df9-211">入门</span><span class="sxs-lookup"><span data-stu-id="20df9-211">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)