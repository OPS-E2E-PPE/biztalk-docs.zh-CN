---
title: 教程： 使用用于 PeopleSoft Enterprise 的 BizTalk 适配器从 PeopleSoft Enterprise 中检索数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c173fa4c-911e-4fa3-813f-e8f36b0049a5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9728e642a1ad9e03e550a652757d33038cbab79d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993422"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-retrieve-data-from-peoplesoft-enterprise"></a><span data-ttu-id="39267-102">教程：使用 PeopleSoft Enterprise 的 BizTalk 适配器以从 PeopleSoft Enterprise 中检索数据</span><span class="sxs-lookup"><span data-stu-id="39267-102">Tutorial: Using the BizTalk Adapter for PeopleSoft Enterprise to Retrieve Data from PeopleSoft Enterprise</span></span>
<span data-ttu-id="39267-103">PeopleSoft Enterprise 的 BizTalk 适配器可以用于执行针对 PeopleSoft 系统的查询，并返回查询的结果。</span><span class="sxs-lookup"><span data-stu-id="39267-103">The BizTalk Adapter for PeopleSoft Enterprise can be used to execute a query against a PeopleSoft system and return the results of the query.</span></span> <span data-ttu-id="39267-104">本演练介绍了可演示此功能的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="39267-104">This walkthrough describes an SDK sample that illustrates this functionality.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="39267-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="39267-105">Prerequisites</span></span>  

- <span data-ttu-id="39267-106">Java 2 平台必须安装在 PeopleSoft Enterprise Geis 的 BizTalk 适配器正在运行的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上。</span><span class="sxs-lookup"><span data-stu-id="39267-106">The Java 2 Platform must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise Geis running on.</span></span>  

- <span data-ttu-id="39267-107">PeopleSoft Java Object Adapter JAR 文件中， **psjoa.jar**应复制到可以访问的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上运行用于 PeopleSoft Enterprise 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="39267-107">The PeopleSoft Java Object Adapter JAR file, **psjoa.jar** should be copied to a folder that is accessible to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- <span data-ttu-id="39267-108">为了构建和部署示例，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 必须安装在运行有 PeopleSoft Enterprise 的 BizTalk 适配器的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39267-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="39267-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="39267-109">What This Sample Does</span></span>  
 <span data-ttu-id="39267-110">本示例从文件夹中选取 XML 文件，将文件发送到业务流程中，然后使用 PeopleSoft Enterprise 的 BizTalk 适配器来执行针对 PeopleSoft 系统的查询。</span><span class="sxs-lookup"><span data-stu-id="39267-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for PeopleSoft Enterprise to execute a query against a PeopleSoft system.</span></span> <span data-ttu-id="39267-111">查询的结果将写入到 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="39267-111">The result of the query is written to an XML file.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="39267-112">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="39267-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="39267-113">此示例使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 设计和创建，用于说明将 PeopleSoft Enterprise 的 BizTalk 适配器用于 BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="39267-113">This sample was designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and was created to illustrate basic functionality using the BizTalk Adapter for PeopleSoft Enterprise with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="39267-114">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="39267-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="39267-115">本示例位于以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="39267-115">The sample is located in the following folder:</span></span>  

 <span data-ttu-id="39267-116">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend</span><span class="sxs-lookup"><span data-stu-id="39267-116">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend</span></span>  

 <span data-ttu-id="39267-117">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="39267-117">The following table shows the files in this sample and describes their purpose.</span></span>  


|                               <span data-ttu-id="39267-118">**Runtime 项目文件名**</span><span class="sxs-lookup"><span data-stu-id="39267-118">**Runtime Project Filename**</span></span>                                |                                                                                                                                                                           <span data-ttu-id="39267-119">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="39267-119">**Runtime Project File Description**</span></span>                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="39267-120">TwoWaySend.btproj,</span><span class="sxs-lookup"><span data-stu-id="39267-120">TwoWaySend.btproj,</span></span><br /><br /> <span data-ttu-id="39267-121">TwoWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="39267-121">TwoWaySend.sln</span></span>                       |                                                                                                                                                                      <span data-ttu-id="39267-122">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="39267-122">Project and solution files for the application.</span></span>                                                                                                                                                                      |
| <span data-ttu-id="39267-123">LOCATIONService.xsd，</span><span class="sxs-lookup"><span data-stu-id="39267-123">LOCATIONService.xsd,</span></span><br /><br /> <span data-ttu-id="39267-124">LOCATIONService_1.xsd，</span><span class="sxs-lookup"><span data-stu-id="39267-124">LOCATIONService_1.xsd,</span></span><br /><br /> <span data-ttu-id="39267-125">LOCATIONService_2.xsd</span><span class="sxs-lookup"><span data-stu-id="39267-125">LOCATIONService_2.xsd</span></span> | <span data-ttu-id="39267-126">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="39267-126">Schema files for the application.</span></span> <span data-ttu-id="39267-127">**注意：** 项目中的适配器架构文件最初创建使用**添加适配器元数据向导**。</span><span class="sxs-lookup"><span data-stu-id="39267-127">**Note:**  The adapter schema files in the project were originally created using the **Add Adapter Metadata Wizard**.</span></span> <span data-ttu-id="39267-128">有关“添加适配器元数据向导”的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“如何向 BizTalk 项目添加适配器元数据”主题。</span><span class="sxs-lookup"><span data-stu-id="39267-128">For more information on the Add Adapter Metadata Wizard see the topic "How to Add Adapter Metadata to a BizTalk Project" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span> |
|                                 <span data-ttu-id="39267-129">PeopleSoftTwoWaySend.odx</span><span class="sxs-lookup"><span data-stu-id="39267-129">PeopleSoftTwoWaySend.odx</span></span>                                  |                                                                                                                                                                        <span data-ttu-id="39267-130">应用程序使用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="39267-130">The orchestration used by the application.</span></span>                                                                                                                                                                         |
|                                 <span data-ttu-id="39267-131">PeopleSoftTwoWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="39267-131">PeopleSoftTwoWaySend.snk</span></span>                                  |                                                                                                                                                                                <span data-ttu-id="39267-132">强命名密钥文件。</span><span class="sxs-lookup"><span data-stu-id="39267-132">The strong naming key file.</span></span>                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="39267-133">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="39267-133">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a><span data-ttu-id="39267-134">创建 PeopleSoft Enterprise 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="39267-134">Create a new instance of the PeopleSoft Enterprise adapter</span></span>  

1. <span data-ttu-id="39267-135">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="39267-135">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="39267-136">单击**启动**，**程序**， **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]， **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="39267-136">Click **Start**, **Programs**, **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="39267-137">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="39267-137">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="39267-138">右键单击**适配器**，然后指向**新建**，**适配器**以显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-138">Right-click **Adapters** and point to **New**, **Adapter** to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="39267-139">输入一个值**名称**字段，例如**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="39267-139">Enter a value for the **Name** field, for example **PeopleSoft**.</span></span>  

5. <span data-ttu-id="39267-140">选择**PeopleSoft enterprise （)** 从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39267-140">Select **PeopleSoft Enterprise(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-solicit-response-biztalk-send-port"></a><span data-ttu-id="39267-141">创建要求响应 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="39267-141">Create a Solicit-Response BizTalk Send Port</span></span>  

1. <span data-ttu-id="39267-142">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="39267-142">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="39267-143">右键单击**发送端口**，然后指向**新建**，**静态要求响应发送端口**以显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-143">Right-click **Send Ports** and point to **New**, **Static Solicit-Response Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="39267-144">输入一个值**名称**字段，例如**PeopleSoftTwoWaySP**。</span><span class="sxs-lookup"><span data-stu-id="39267-144">Enter a value for the **Name** field, for example **PeopleSoftTwoWaySP**.</span></span>  

4. <span data-ttu-id="39267-145">从中可用的适配器列表中选择 PeopleSoft 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-145">Select the PeopleSoft adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="39267-146">此值是在管理控制台创建 PeopleSoft Enterprise 适配器时指定的名称。</span><span class="sxs-lookup"><span data-stu-id="39267-146">This value is the name that was specified when the PeopleSoft Enterprise adapter was created in the Administration Console.</span></span>  

5. <span data-ttu-id="39267-147">输入以下值：**适配器必需属性**:</span><span class="sxs-lookup"><span data-stu-id="39267-147">Enter the following values for the **Adapter Required Properties**:</span></span>  


   |       <span data-ttu-id="39267-148">**属性**</span><span class="sxs-lookup"><span data-stu-id="39267-148">**Property**</span></span>       |                                                                                                                                        <span data-ttu-id="39267-149">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="39267-149">**Value**</span></span>                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="39267-150">应用程序服务器路径</span><span class="sxs-lookup"><span data-stu-id="39267-150">Application server path</span></span>  | <span data-ttu-id="39267-151">PeopleSoft Server 的计算机和端口位置，例如 //PSServer:8888。</span><span class="sxs-lookup"><span data-stu-id="39267-151">PeopleSoft Server's machine and port location, for example //PSServer:8888.</span></span> <span data-ttu-id="39267-152">**注意：** 如果不指定端口号，以便在上例中您可以输入值 //PSServer 如果 PeopleSoft 服务器使用默认端口值 9000 则使用默认端口为 9000。</span><span class="sxs-lookup"><span data-stu-id="39267-152">**Note:**  If you do not specify a port number, the default port of 9000 is used so in the example above you could enter a value of //PSServer if the PeopleSoft Server uses the default port value of 9000.</span></span> |
   |        <span data-ttu-id="39267-153">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="39267-153">JAVA_HOME</span></span>         |                                                                                          <span data-ttu-id="39267-154">与 Java 2 平台 SDK 文件相关联的主目录路径，例如 C:\j2sdk1.4.2_08</span><span class="sxs-lookup"><span data-stu-id="39267-154">Path to the home directory associated with the Java 2 Platform SDK files, for example C:\j2sdk1.4.2_08</span></span>                                                                                          |
   |         <span data-ttu-id="39267-155">Password</span><span class="sxs-lookup"><span data-stu-id="39267-155">Password</span></span>         |                                                                                                                 <span data-ttu-id="39267-156">连接到 PeopleSoft 系统时使用的密码。</span><span class="sxs-lookup"><span data-stu-id="39267-156">Password used when connecting to the PeopleSoft system.</span></span>                                                                                                                  |
   | <span data-ttu-id="39267-157">PeopleSoft 8.x JAR 文件</span><span class="sxs-lookup"><span data-stu-id="39267-157">PeopleSoft 8.x JAR files</span></span> |                                                                                          <span data-ttu-id="39267-158">PeopleSoft Java Object Adapter JAR 文件的位置**psjoa.jar**，例如 C:\JARS\psjoa.jar。</span><span class="sxs-lookup"><span data-stu-id="39267-158">Location of the PeopleSoft Java Object Adapter JAR file, **psjoa.jar**, for example C:\JARS\psjoa.jar.</span></span>                                                                                          |
   |        <span data-ttu-id="39267-159">“用户名”</span><span class="sxs-lookup"><span data-stu-id="39267-159">User name</span></span>         |                                                                                                                    <span data-ttu-id="39267-160">用于 连接到 PeopleSoft 系统的用户名 。</span><span class="sxs-lookup"><span data-stu-id="39267-160">Username for connecting to the PeopleSoft system.</span></span>                                                                                                                     |


6. <span data-ttu-id="39267-161">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="39267-161">Click **OK**.</span></span>  

7. <span data-ttu-id="39267-162">选择**XMLTransmit**中的可用管道列表**发送管道**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="39267-162">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown.</span></span>  

8. <span data-ttu-id="39267-163">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39267-163">Select the **XMLReceive** pipeline from the list of pipelines available in the **Receive pipeline** dropdown and click **OK**.</span></span>  

9. <span data-ttu-id="39267-164">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="39267-164">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-one-way-biztalk-send-port"></a><span data-ttu-id="39267-165">创建单向 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="39267-165">Create a One-Way BizTalk Send Port</span></span>  

1. <span data-ttu-id="39267-166">创建发送端口使用的目标文件夹，例如 C:\Files\Out。</span><span class="sxs-lookup"><span data-stu-id="39267-166">Create a target folder to be used by the send port, for example C:\Files\Out.</span></span>  

2. <span data-ttu-id="39267-167">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="39267-167">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

3. <span data-ttu-id="39267-168">右键单击**发送端口**，然后指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-168">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port** to display the **Send Port Properties** dialog.</span></span>  

4. <span data-ttu-id="39267-169">输入一个值**名称**字段，例如**PeopleSoftTwoWayFileSP**。</span><span class="sxs-lookup"><span data-stu-id="39267-169">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileSP**.</span></span>  

5. <span data-ttu-id="39267-170">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-170">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

6. <span data-ttu-id="39267-171">输入您为前面创建的文件夹的位置**目标文件夹**属性，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39267-171">Enter the location of the folder that you created earlier for the **Destination Folder** property and click **OK**.</span></span>  

7. <span data-ttu-id="39267-172">选择**XMLTransmit**中的可用管道列表**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39267-172">Select the **XMLTransmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="39267-173">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="39267-173">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="39267-174">创建文件接收端口</span><span class="sxs-lookup"><span data-stu-id="39267-174">Create a file receive port</span></span>  

1. <span data-ttu-id="39267-175">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="39267-175">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="39267-176">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-176">Right-click the Receive Ports folder and then click **New**, **One-Way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="39267-177">输入一个值**名称**字段，例如**PeopleSoftTwoWayFileRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39267-177">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="39267-178">创建文件接收位置</span><span class="sxs-lookup"><span data-stu-id="39267-178">Create a file receive location</span></span>  

1.  <span data-ttu-id="39267-179">创建由文件接收位置监视的文件夹，例如 C:\Files\In。</span><span class="sxs-lookup"><span data-stu-id="39267-179">Create a folder to be monitored by the file receive location, for example C:\Files\In.</span></span>  

2.  <span data-ttu-id="39267-180">右键单击新接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-180">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="39267-181">输入一个值**名称**字段，例如**PeopleSoftTwoWayFileRL**。</span><span class="sxs-lookup"><span data-stu-id="39267-181">Enter a value for the **Name** field, for example **PeopleSoftTwoWayFileRL**.</span></span>  

4.  <span data-ttu-id="39267-182">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-182">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="39267-183">输入您为前面创建的文件夹的位置**接收文件夹**属性，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39267-183">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="39267-184">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="39267-184">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="39267-185">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="39267-185">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a><span data-ttu-id="39267-186">修改适配器架构目标命名空间属性</span><span class="sxs-lookup"><span data-stu-id="39267-186">Modify the Adapter schema target namespace property</span></span>  

1. <span data-ttu-id="39267-187">启动[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后打开 TwoWaySend.sln。</span><span class="sxs-lookup"><span data-stu-id="39267-187">Launch [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and open TwoWaySend.sln.</span></span> <span data-ttu-id="39267-188">单击**文件**，**打开**，**项目/解决方案**以显示**打开项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-188">Click **File**, **Open**, **Project/Solution** to display the **Open Project** dialog.</span></span>  

2. <span data-ttu-id="39267-189">浏览到 TwoWaySend.sln 文件，单击以选择此文件，然后单击**打开**以打开包含示例项目的解决方案。</span><span class="sxs-lookup"><span data-stu-id="39267-189">Browse to the TwoWaySend.sln file, click to select this file and click **Open** to open the solution that contains the sample project.</span></span>  

3. <span data-ttu-id="39267-190">单击**视图**菜单，然后选择**解决方案资源管理器**以显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="39267-190">Click the **View** menu and select **Solution Explorer** to display the Solution Explorer.</span></span>  

4. <span data-ttu-id="39267-191">双击“解决方案资源管理器”中的 LOCATIONService_1.xsd 文件以将其打开。</span><span class="sxs-lookup"><span data-stu-id="39267-191">Double-click the LOCATIONService_1.xsd file in the Solution Explorer to open it.</span></span>  

5. <span data-ttu-id="39267-192">右键单击**架构**节点的 LOCATIONService_1.xsd，然后选择**属性**菜单选项以显示架构的属性。</span><span class="sxs-lookup"><span data-stu-id="39267-192">Right-click the **Schema** node of LOCATIONService_1.xsd and select the **Properties** menu option to display the properties for the schema.</span></span>  

6. <span data-ttu-id="39267-193">编辑**目标 Namespace**属性以使用适当的值的适配器名称，例如**Target Namespace**属性应按如下所示：</span><span class="sxs-lookup"><span data-stu-id="39267-193">Edit the **Target Namespace** property to use the appropriate values for the adapter name, for example the **Target Namespace** property should read as follows:</span></span>  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    <span data-ttu-id="39267-194">其中*PeopleSoft*是 PeopleSoft 适配器的名称，因为在中查看[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="39267-194">Where *PeopleSoft* is the name of the PeopleSoft adapter as viewed in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="39267-195">如果已配置的值**目标 Namespace**与输入的文档实例中指定，则由处理输入的文档实例时，将发生路由失败的命名空间不匹配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39267-195">If the configured value for **Target Namespace** does not match the namespace specified in the input document instance then a routing failure will occur when the input document instance is processed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="39267-196">从适配器架构生成文档实例</span><span class="sxs-lookup"><span data-stu-id="39267-196">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="39267-197">双击**LOCATIONService_1.xsd**在解决方案资源管理器在架构编辑器中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="39267-197">Double-click **LOCATIONService_1.xsd** in Solution Explorer to open the file in Schema Editor.</span></span>  

2.  <span data-ttu-id="39267-198">右键单击**\<架构\>** 节点在架构编辑器中单击**属性**显示节点的属性。</span><span class="sxs-lookup"><span data-stu-id="39267-198">Right-click the **\<Schema\>** node in Schema Editor and click **Properties** to display properties for the node.</span></span>  

3.  <span data-ttu-id="39267-199">选择**获取**从列表中的可用节点**根引用**下拉框中。</span><span class="sxs-lookup"><span data-stu-id="39267-199">Select **Get** from the list of available nodes in the **Root Reference** dropdown box.</span></span> <span data-ttu-id="39267-200">这应这样做为了生成示例文档实例时它将生成从**获取**架构节点。</span><span class="sxs-lookup"><span data-stu-id="39267-200">This should be done so that when you generate a sample document instance it will be generated from the **Get** node of the schema.</span></span>  

4.  <span data-ttu-id="39267-201">右键单击**LOCATIONService_1.xsd**在解决方案资源管理器中单击**属性**要在属性窗口中显示属性。</span><span class="sxs-lookup"><span data-stu-id="39267-201">Right-click **LOCATIONService_1.xsd** in Solution Explorer and click **Properties** to display properties in the Properties window.</span></span>  

5.  <span data-ttu-id="39267-202">在属性窗口中，单击以选中**输出实例文件名**选项。</span><span class="sxs-lookup"><span data-stu-id="39267-202">In the Properties window, click to select the **Output Instance Filename** option.</span></span>  

6.  <span data-ttu-id="39267-203">单击省略号按钮 （...） 以显示**选择输出文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-203">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

7.  <span data-ttu-id="39267-204">指定的文件夹和输出文件实例名称，例如**C:\instance.xml**然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="39267-204">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="39267-205">请勿指定为此处的文件接收位置指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="39267-205">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

8.  <span data-ttu-id="39267-206">右键单击解决方案资源管理器中的 LOCATIONService_1.xsd，然后单击**生成实例**以在指定位置生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="39267-206">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

9. <span data-ttu-id="39267-207">右键单击**\<架构\>** 节点在架构编辑器中单击**属性**以显示该节点的属性。</span><span class="sxs-lookup"><span data-stu-id="39267-207">Right-click the **\<Schema\>** node in Schema Editor and click **Properties** to display the properties for the node.</span></span>  

10. <span data-ttu-id="39267-208">选择 (**默认值)** 从列表中的可用节点**根引用**下拉框中。</span><span class="sxs-lookup"><span data-stu-id="39267-208">Select (**Default)** from the list of available nodes in the **Root Reference** dropdown box.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="39267-209">修改生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="39267-209">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="39267-210">在文本编辑器（如记事本）中打开生成的文档实例，并编辑文档实例的内容，以确保这些字段中的数据将返回现有记录：</span><span class="sxs-lookup"><span data-stu-id="39267-210">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data in these fields will return an existing record:</span></span>  

    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
    <ns0:SETID>SHARE</ns0:SETID>  
    <ns0:LOCATION>WFKLOC</ns0:LOCATION>  
    <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="39267-211">在上述示例中， *PeopleSoft*是 BizTalk 管理控制台中的适配器实际名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="39267-211">In the example above, *PeopleSoft* is a placeholder for the actual name of the adapter as viewed in the BizTalk Administration Console.</span></span> <span data-ttu-id="39267-212">*共享*并*WFKLOC*都是用于识别 PeopleSoft 系统中特定记录值的占位符。</span><span class="sxs-lookup"><span data-stu-id="39267-212">*SHARE* and *WFKLOC* are placeholders for values used to identify a particular record in the PeopleSoft system.</span></span>  

2.  <span data-ttu-id="39267-213">保存修改后的文档实例。</span><span class="sxs-lookup"><span data-stu-id="39267-213">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="39267-214">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="39267-214">Build and deploy the project</span></span>  

1. <span data-ttu-id="39267-215">右键单击解决方案资源管理器中的 TwoWaySend 项目，然后单击**属性**以显示项目的项目设计器。</span><span class="sxs-lookup"><span data-stu-id="39267-215">Right-click the TwoWaySend project in Solution Explorer and click **Properties** to display the Project Designer for the project.</span></span>  

2. <span data-ttu-id="39267-216">单击**部署**项目设计器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="39267-216">Click the **Deployment** tab in the Project Designer.</span></span>  

3. <span data-ttu-id="39267-217">输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="39267-217">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="39267-218">右键单击解决方案资源管理器中的 TwoWaySend 项目，然后单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="39267-218">Right-click the TwoWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="39267-219">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="39267-219">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="39267-220">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="39267-220">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="39267-221">单击**刷新**按钮[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="39267-221">Click the **Refresh** button in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console view.</span></span>  

3. <span data-ttu-id="39267-222">双击业务流程以显示**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="39267-222">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="39267-223">单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="39267-223">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="39267-224">指定绑定选项的适当值，例如：</span><span class="sxs-lookup"><span data-stu-id="39267-224">Specify the appropriate values for the binding options, for example:</span></span>  


   |      <span data-ttu-id="39267-225">**参数**</span><span class="sxs-lookup"><span data-stu-id="39267-225">**Parameter**</span></span>      |        <span data-ttu-id="39267-226">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="39267-226">**Value**</span></span>         |
   |-------------------------|--------------------------|
   |          <span data-ttu-id="39267-227">主机</span><span class="sxs-lookup"><span data-stu-id="39267-227">Host</span></span>           | <span data-ttu-id="39267-228">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="39267-228">BizTalkServerApplication</span></span> |
   |     <span data-ttu-id="39267-229">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="39267-229">FileReceivePort</span></span>     |  <span data-ttu-id="39267-230">PeopleSoftTwoWayFileRP</span><span class="sxs-lookup"><span data-stu-id="39267-230">PeopleSoftTwoWayFileRP</span></span>  |
   | <span data-ttu-id="39267-231">PeopleSoftTwoWaySend678</span><span class="sxs-lookup"><span data-stu-id="39267-231">PeopleSoftTwoWaySend678</span></span> |    <span data-ttu-id="39267-232">PeopleSoftTwoWaySP</span><span class="sxs-lookup"><span data-stu-id="39267-232">PeopleSoftTwoWaySP</span></span>    |
   |      <span data-ttu-id="39267-233">ResponsePort</span><span class="sxs-lookup"><span data-stu-id="39267-233">ResponsePort</span></span>       |  <span data-ttu-id="39267-234">PeopleSoftTwoWayFileSP</span><span class="sxs-lookup"><span data-stu-id="39267-234">PeopleSoftTwoWayFileSP</span></span>  |


6. <span data-ttu-id="39267-235">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="39267-235">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="39267-236">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="39267-236">Start the orchestration</span></span>  

- <span data-ttu-id="39267-237">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该业务流程，然后单击**启动**以登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="39267-237">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="39267-238">将文档实例拖到由文件接收位置监视的文件夹</span><span class="sxs-lookup"><span data-stu-id="39267-238">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="39267-239">将以前创建的文档实例复制到文件接收位置配置为监视的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="39267-239">Copy the document instance that was created earlier to the folder that the file receive location is configured to monitor.</span></span>  

#### <a name="verify-that-the-document-instance-was-processed-by-the-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="39267-240">验证文档实例是否由 PeopleSoft Enterprise 的 BizTalk 适配器处理。</span><span class="sxs-lookup"><span data-stu-id="39267-240">Verify that the document instance was processed by the BizTalk Adapter for PeopleSoft Enterprise</span></span>  

- <span data-ttu-id="39267-241">打开将文件发送端口配置为发送到的目标文件夹，并验证是否已生成输出文档。</span><span class="sxs-lookup"><span data-stu-id="39267-241">Open the folder that the file send port is configured to send to and verify that an output document was generated.</span></span> <span data-ttu-id="39267-242">此文件应包含 PeopleSoft Enterprise 的 BizTalk 适配器处理的查询结果。</span><span class="sxs-lookup"><span data-stu-id="39267-242">This file should contain the results of the query that was processed by the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

  <span data-ttu-id="39267-243">成功处理文档实例后，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="39267-243">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="39267-244">文件适配器从文件夹中检索文件，并作为 BizTalk 消息将其发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="39267-244">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="39267-245">业务流程会订阅此发布的消息，以便 BizTalk 消息引擎能够激活业务流程的实例，并将该消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="39267-245">The orchestration subscribes to this published message so the BizTalk Messaging Engine activates an instance of the orchestration and sends the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="39267-246">业务流程实例将此消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="39267-246">The orchestration instance publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="39267-247">要求响应发送端口会订阅此发布的消息，因此 BizTalk 消息引擎会将消息发送到 PeopleSoft 发送端口中。</span><span class="sxs-lookup"><span data-stu-id="39267-247">The solicit-response send port subscribes to this published message so the BizTalk Messaging Engine sends the message to the PeopleSoft send port.</span></span>  

5.  <span data-ttu-id="39267-248">发送端口会将消息交给适用于 PeopleSoft Enterprise 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="39267-248">The send port hands the message to the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

6.  <span data-ttu-id="39267-249">PeopleSoft Enterprise 的 BizTalk 适配器会使用定义在输入文件中的参数针对 PeopleSoft 系统执行 Get 语句。</span><span class="sxs-lookup"><span data-stu-id="39267-249">The BizTalk Adapter for PeopleSoft Enterprise executes a Get statement against the PeopleSoft system using the parameters defined in the input file.</span></span>  

7.  <span data-ttu-id="39267-250">PeopleSoft Enterprise 的 BizTalk 适配器会为业务流程中的要求响应端口以响应消息形式返回 Get 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="39267-250">The BizTalk Adapter for PeopleSoft Enterprise returns the results of the Get statement as the response message for the solicit-response port in the orchestration.</span></span>  

8.  <span data-ttu-id="39267-251">业务流程将结果集发布到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="39267-251">The orchestration publishes the result set to the MessageBox.</span></span>  

9. <span data-ttu-id="39267-252">文件发送端口会订阅此消息，以便 BizTalk 能够将消息发送到文件适配器。</span><span class="sxs-lookup"><span data-stu-id="39267-252">The File send port subscribes to this message so BizTalk sends the message to the File adapter.</span></span>  

10. <span data-ttu-id="39267-253">文件适配器将包含结果集的消息写入到指定的输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="39267-253">The File adapter writes the message containing the result set to the designated output folder.</span></span>  

## <a name="see-also"></a><span data-ttu-id="39267-254">请参阅</span><span class="sxs-lookup"><span data-stu-id="39267-254">See Also</span></span>  
 [<span data-ttu-id="39267-255">教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="39267-255">Tutorials: Using BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)