---
title: 教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器将数据写入 PeopleSoft Enterprise |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 837dd4db-576d-41c1-9fe8-e1e46861270b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 152579975225efd803aa7f07613da8962048130a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396622"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-write-data-to-peoplesoft-enterprise"></a><span data-ttu-id="07fea-102">教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器将数据写入 PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="07fea-102">Tutorial: Using the BizTalk Adapter for PeopleSoft Enterprise to Write Data to PeopleSoft Enterprise</span></span>
<span data-ttu-id="07fea-103">可以使用用于 PeopleSoft Enterprise 的 BizTalk 适配器将数据写入 PeopleSoft 系统接收来自贸易合作伙伴或内部应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="07fea-103">The BizTalk Adapter for PeopleSoft Enterprise can be used to write data to a PeopleSoft System with information received from a trading partner or internal application.</span></span> <span data-ttu-id="07fea-104">本演练描述说明了此功能的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="07fea-104">This walkthrough describes an SDK sample that illustrates this functionality.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="07fea-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="07fea-105">Prerequisites</span></span>  

- <span data-ttu-id="07fea-106">Java 2 平台必须安装在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上运行用于 PeopleSoft Enterprise 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="07fea-106">The Java 2 Platform must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- <span data-ttu-id="07fea-107">PeopleSoft Java Object Adapter JAR 文件中， **psjoa.jar**应复制到可以访问的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上运行用于 PeopleSoft Enterprise 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="07fea-107">The PeopleSoft Java Object Adapter JAR file, **psjoa.jar** should be copied to a folder that is accessible to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on.</span></span>  

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="07fea-108">必须安装在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于 PeopleSoft Enterprise 的 BizTalk 适配器在运行，以便在生成和部署示例。</span><span class="sxs-lookup"><span data-stu-id="07fea-108">must be installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that the BizTalk Adapter for PeopleSoft Enterprise is running on in order to build and deploy the sample.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="07fea-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="07fea-109">What This Sample Does</span></span>  
 <span data-ttu-id="07fea-110">此示例选取一个文件夹中的 XML 文件、 将该文件发送到业务流程，，然后使用用于 PeopleSoft Enterprise 的 BizTalk 适配器以从 XML 文件中的数据在 PeopleSoft 系统中创建一条记录。</span><span class="sxs-lookup"><span data-stu-id="07fea-110">This sample picks up an XML file from a folder, sends the file to an orchestration, and then uses the BizTalk Adapter for PeopleSoft Enterprise to create a record in the PeopleSoft system from the data in the XML file.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="07fea-111">此示例设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="07fea-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="07fea-112">此示例设计中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和创建，用于说明适用于 PeopleSoft Enterprise 的 BizTalk 适配器使用 BizTalk 业务流程的基本功能。</span><span class="sxs-lookup"><span data-stu-id="07fea-112">This sample was designed in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and was created to illustrate basic functionality using the BizTalk Adapter for PeopleSoft Enterprise with a BizTalk orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="07fea-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="07fea-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="07fea-114">该示例位于以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="07fea-114">The sample is located in the following folder:</span></span>  

 <span data-ttu-id="07fea-115">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span><span class="sxs-lookup"><span data-stu-id="07fea-115">\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftOneWaySend</span></span>  

 <span data-ttu-id="07fea-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="07fea-116">The following table shows the files in this sample and describes their purpose.</span></span>  


|                               <span data-ttu-id="07fea-117">**Runtime 项目文件名**</span><span class="sxs-lookup"><span data-stu-id="07fea-117">**Runtime Project Filename**</span></span>                                |                                                                                                                                                                           <span data-ttu-id="07fea-118">**运行时项目文件说明**</span><span class="sxs-lookup"><span data-stu-id="07fea-118">**Runtime Project File Description**</span></span>                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="07fea-119">OneWaySend.btproj，</span><span class="sxs-lookup"><span data-stu-id="07fea-119">OneWaySend.btproj,</span></span><br /><br /> <span data-ttu-id="07fea-120">OneWaySend.sln</span><span class="sxs-lookup"><span data-stu-id="07fea-120">OneWaySend.sln</span></span>                       |                                                                                                                                                                      <span data-ttu-id="07fea-121">应用程序的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="07fea-121">Project and solution files for the application.</span></span>                                                                                                                                                                      |
| <span data-ttu-id="07fea-122">LOCATIONService.xsd,</span><span class="sxs-lookup"><span data-stu-id="07fea-122">LOCATIONService.xsd,</span></span><br /><br /> <span data-ttu-id="07fea-123">LOCATIONService_1.xsd,</span><span class="sxs-lookup"><span data-stu-id="07fea-123">LOCATIONService_1.xsd,</span></span><br /><br /> <span data-ttu-id="07fea-124">LOCATIONService_2.xsd</span><span class="sxs-lookup"><span data-stu-id="07fea-124">LOCATIONService_2.xsd</span></span> | <span data-ttu-id="07fea-125">应用程序的架构文件。</span><span class="sxs-lookup"><span data-stu-id="07fea-125">Schema files for the application.</span></span> <span data-ttu-id="07fea-126">**注意：** 在项目中的适配器架构文件最初创建使用**添加适配器元数据向导**。</span><span class="sxs-lookup"><span data-stu-id="07fea-126">**Note:**  The adapter schema files in the project were originally created using the **Add Adapter Metadata Wizard**.</span></span> <span data-ttu-id="07fea-127">添加适配器元数据向导的详细信息请参阅主题"如何添加适配器元数据向 BizTalk 项目"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="07fea-127">For more information on the Add Adapter Metadata Wizard see the topic "How to Add Adapter Metadata to a BizTalk Project" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span> |
|                                 <span data-ttu-id="07fea-128">PeopleSoftOneWaySend.odx</span><span class="sxs-lookup"><span data-stu-id="07fea-128">PeopleSoftOneWaySend.odx</span></span>                                  |                                                                                                                                                                        <span data-ttu-id="07fea-129">使用应用程序的业务流程。</span><span class="sxs-lookup"><span data-stu-id="07fea-129">The orchestration used by the application.</span></span>                                                                                                                                                                         |
|                                 <span data-ttu-id="07fea-130">PeopleSoftOneWaySend.snk</span><span class="sxs-lookup"><span data-stu-id="07fea-130">PeopleSoftOneWaySend.snk</span></span>                                  |                                                                                                                                                                                <span data-ttu-id="07fea-131">强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="07fea-131">The strong naming key file.</span></span>                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="07fea-132">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="07fea-132">How to Use This Sample</span></span>  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a><span data-ttu-id="07fea-133">创建 PeopleSoft Enterprise 适配器的新实例</span><span class="sxs-lookup"><span data-stu-id="07fea-133">Create a new instance of the PeopleSoft Enterprise adapter</span></span>  

1. <span data-ttu-id="07fea-134">启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="07fea-134">Launch the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="07fea-135">单击**启动**，**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]， **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="07fea-135">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="07fea-136">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="07fea-136">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  

3. <span data-ttu-id="07fea-137">右键单击**适配器**，然后指向**新建**，**适配器...**</span><span class="sxs-lookup"><span data-stu-id="07fea-137">Right-click **Adapters** and point to **New**, **Adapter…**</span></span> <span data-ttu-id="07fea-138">若要显示**适配器属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-138">to display the **Adapter Properties** dialog.</span></span>  

4. <span data-ttu-id="07fea-139">输入一个值**名称**字段，例如**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="07fea-139">Enter a value for the **Name** field, for example **PeopleSoft**.</span></span>  

5. <span data-ttu-id="07fea-140">选择**PeopleSoft enterprise （)** 从列表中可用的适配器**适配器**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="07fea-140">Select **PeopleSoft Enterprise(r)** from the list of adapters available in the **Adapter** dropdown and click **OK**.</span></span>  

#### <a name="create-a-biztalk-send-port"></a><span data-ttu-id="07fea-141">创建 BizTalk 发送端口</span><span class="sxs-lookup"><span data-stu-id="07fea-141">Create a BizTalk Send Port</span></span>  

1. <span data-ttu-id="07fea-142">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="07fea-142">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Send Ports**.</span></span>  

2. <span data-ttu-id="07fea-143">右键单击**发送端口**，然后指向**新建**，**静态单向发送端口**以显示**发送端口属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-143">Right-click **Send Ports** and point to **New**, **Static One-Way Send Port** to display the **Send Port Properties** dialog.</span></span>  

3. <span data-ttu-id="07fea-144">输入一个值**名称**字段，例如**PeopleSoftOneWaySP**。</span><span class="sxs-lookup"><span data-stu-id="07fea-144">Enter a value for the **Name** field, for example **PeopleSoftOneWaySP**.</span></span>  

4. <span data-ttu-id="07fea-145">从中可用的适配器列表中选择 PeopleSoft 适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-145">Select the PeopleSoft adapter from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="07fea-146">此值是在创建 PeopleSoft Enterprise 适配器时指定的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="07fea-146">This value is the name that was specified when the PeopleSoft Enterprise adapter was created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

5. <span data-ttu-id="07fea-147">输入以下值：**适配器必需属性**:</span><span class="sxs-lookup"><span data-stu-id="07fea-147">Enter the following values for the **Adapter Required Properties**:</span></span>  


   |       <span data-ttu-id="07fea-148">**属性**</span><span class="sxs-lookup"><span data-stu-id="07fea-148">**Property**</span></span>       |                                                                                                                                        <span data-ttu-id="07fea-149">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="07fea-149">**Value**</span></span>                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="07fea-150">应用程序服务器路径</span><span class="sxs-lookup"><span data-stu-id="07fea-150">Application server path</span></span>  | <span data-ttu-id="07fea-151">PeopleSoft 服务器的计算机和端口位置，例如 / / PSServer:8888。</span><span class="sxs-lookup"><span data-stu-id="07fea-151">PeopleSoft Server's machine and port location, for example //PSServer:8888.</span></span> <span data-ttu-id="07fea-152">**注意：** 如果不指定端口号，则使用默认端口为 9000，以便在上例中您可以输入值 //PSServer 如果 PeopleSoft 服务器使用默认端口值 9000。</span><span class="sxs-lookup"><span data-stu-id="07fea-152">**Note:**  If you do not specify a port number, the default port of 9000 is used so in the example above you could enter a value of //PSServer if the PeopleSoft Server uses the default port value of 9000.</span></span> |
   |        <span data-ttu-id="07fea-153">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="07fea-153">JAVA_HOME</span></span>         |                                                                                          <span data-ttu-id="07fea-154">与 Java 2 平台 SDK 文件，例如 C:\j2sdk1.4.2_08 相关联的主目录的路径</span><span class="sxs-lookup"><span data-stu-id="07fea-154">Path to the home directory associated with the Java 2 Platform SDK files, for example C:\j2sdk1.4.2_08</span></span>                                                                                          |
   |         <span data-ttu-id="07fea-155">Password</span><span class="sxs-lookup"><span data-stu-id="07fea-155">Password</span></span>         |                                                                                                                 <span data-ttu-id="07fea-156">连接到 PeopleSoft 系统时使用的密码。</span><span class="sxs-lookup"><span data-stu-id="07fea-156">Password used when connecting to the PeopleSoft system.</span></span>                                                                                                                  |
   | <span data-ttu-id="07fea-157">PeopleSoft 8.x JAR 文件</span><span class="sxs-lookup"><span data-stu-id="07fea-157">PeopleSoft 8.x JAR files</span></span> |                                                                                          <span data-ttu-id="07fea-158">PeopleSoft Java Object Adapter JAR 文件的位置**psjoa.jar**，例如 C:\JARS\psjoa.jar。</span><span class="sxs-lookup"><span data-stu-id="07fea-158">Location of the PeopleSoft Java Object Adapter JAR file, **psjoa.jar**, for example C:\JARS\psjoa.jar.</span></span>                                                                                          |
   |        <span data-ttu-id="07fea-159">“用户名”</span><span class="sxs-lookup"><span data-stu-id="07fea-159">User name</span></span>         |                                                                                                                    <span data-ttu-id="07fea-160">用于连接到 PeopleSoft 系统的用户名。</span><span class="sxs-lookup"><span data-stu-id="07fea-160">Username for connecting to the PeopleSoft system.</span></span>                                                                                                                     |


6. <span data-ttu-id="07fea-161">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="07fea-161">Click **OK**.</span></span>  

7. <span data-ttu-id="07fea-162">选择**XML 传输**中的可用管道列表**发送管道**下拉列表中单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="07fea-162">Select the **XML Transmit** pipeline from the list of pipelines available in the **Send pipeline** dropdown and click **OK**.</span></span>  

8. <span data-ttu-id="07fea-163">右键单击发送端口，然后单击**启动**以登记并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="07fea-163">Right-click the send port and click **Start** to enlist and start the send port.</span></span>  

#### <a name="create-a-file-receive-port"></a><span data-ttu-id="07fea-164">创建文件接收端口</span><span class="sxs-lookup"><span data-stu-id="07fea-164">Create a file receive port</span></span>  

1. <span data-ttu-id="07fea-165">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="07fea-165">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Receive Ports**.</span></span>  

2. <span data-ttu-id="07fea-166">右键单击接收端口文件夹，然后单击**新建**，**单向接收端口**显示接收端口属性对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-166">Right-click the Receive Ports folder and then click **New**, **One-way Receive Port** to display the Receive Port Properties dialog.</span></span>  

3. <span data-ttu-id="07fea-167">输入一个值**名称**字段，例如**PeopleSoftOneWayFileRP**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="07fea-167">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRP**, and click **OK**.</span></span>  

#### <a name="create-a-file-receive-location"></a><span data-ttu-id="07fea-168">创建文件接收位置</span><span class="sxs-lookup"><span data-stu-id="07fea-168">Create a file receive location</span></span>  

1.  <span data-ttu-id="07fea-169">创建一个文件夹以监视由文件接收位置，例如 C:\Filesource。</span><span class="sxs-lookup"><span data-stu-id="07fea-169">Create a folder to be monitored by the file receive location, for example C:\Filesource.</span></span>  

2.  <span data-ttu-id="07fea-170">右键单击新接收端口，然后单击**新建**，**接收位置**以显示**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-170">Right-click the new receive port and then click **New**, **Receive Location** to display the **Receive Location Properties** dialog.</span></span>  

3.  <span data-ttu-id="07fea-171">输入一个值**名称**字段，例如**PeopleSoftOneWayFileRL**。</span><span class="sxs-lookup"><span data-stu-id="07fea-171">Enter a value for the **Name** field, for example **PeopleSoftOneWayFileRL**.</span></span>  

4.  <span data-ttu-id="07fea-172">选择**文件**从列表中可用的适配器**类型**下拉列表框，然后单击**配置**按钮以显示适配器**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-172">Select **FILE** from the list of available adapters in the **Type** dropdown box and click the **Configure** button to display the adapter **Transport Properties** dialog box.</span></span>  

5.  <span data-ttu-id="07fea-173">输入您为前面创建的文件夹的位置**接收文件夹**属性，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="07fea-173">Enter the location of the folder that you created earlier for the **Receive Folder** property and click **OK**.</span></span>  

6.  <span data-ttu-id="07fea-174">选择**XMLReceive**中的可用管道列表**接收管道**下拉列表框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="07fea-174">Select **XMLReceive** from the list of available pipelines in the **Receive pipeline** dropdown box and click **OK**.</span></span>  

7.  <span data-ttu-id="07fea-175">右键单击接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="07fea-175">Right-click the receive location and click **Enable**.</span></span>  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a><span data-ttu-id="07fea-176">修改适配器架构目标命名空间属性</span><span class="sxs-lookup"><span data-stu-id="07fea-176">Modify the Adapter schema target namespace property</span></span>  

1. <span data-ttu-id="07fea-177">启动[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并打开 OneWaySend.sln。</span><span class="sxs-lookup"><span data-stu-id="07fea-177">Launch [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and open OneWaySend.sln.</span></span> <span data-ttu-id="07fea-178">单击**文件**，**打开**，**项目/解决方案...**</span><span class="sxs-lookup"><span data-stu-id="07fea-178">Click **File**, **Open**, **Project/Solution…**</span></span> <span data-ttu-id="07fea-179">若要显示**打开项目**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-179">to display the **Open Project** dialog.</span></span>  

2. <span data-ttu-id="07fea-180">浏览到 OneWaySend.sln 文件，单击以选择此文件，然后单击**打开**以打开包含示例项目的解决方案。</span><span class="sxs-lookup"><span data-stu-id="07fea-180">Browse to the OneWaySend.sln file, click to select this file and click **Open** to open the solution that contains the sample project.</span></span>  

3. <span data-ttu-id="07fea-181">单击**视图**菜单，然后选择**解决方案资源管理器**以显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="07fea-181">Click the **View** menu and select **Solution Explorer** to display the Solution Explorer.</span></span>  

4. <span data-ttu-id="07fea-182">双击解决方案资源管理器以将其打开中的 LOCATIONService_1.xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="07fea-182">Double-click the LOCATIONService_1.xsd file in the Solution Explorer to open it.</span></span>  

5. <span data-ttu-id="07fea-183">右键单击**架构**节点的 LOCATIONService_1.xsd，然后选择**属性**菜单选项以显示架构的属性。</span><span class="sxs-lookup"><span data-stu-id="07fea-183">Right-click the **Schema** node of LOCATIONService_1.xsd and select the **Properties** menu option to display the properties for the schema.</span></span>  

6. <span data-ttu-id="07fea-184">编辑**目标 Namespace**属性以使用适当的值的适配器名称，例如**Target Namespace**属性应按如下所示：</span><span class="sxs-lookup"><span data-stu-id="07fea-184">Edit the **Target Namespace** property to use the appropriate values for the adapter name, for example the **Target Namespace** property should read as follows:</span></span>  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    <span data-ttu-id="07fea-185">其中*PeopleSoft*是 PeopleSoft 适配器的名称，因为在 BizTalk 管理控制台中查看。</span><span class="sxs-lookup"><span data-stu-id="07fea-185">Where *PeopleSoft* is the name of the PeopleSoft adapter as viewed in the BizTalk Administration Console.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="07fea-186">如果已配置的值**目标 Namespace**与输入的文档实例中指定，则由处理输入的文档实例时，将发生路由失败的命名空间不匹配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="07fea-186">If the configured value for **Target Namespace** does not match the namespace specified in the input document instance then a routing failure will occur when the input document instance is processed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a><span data-ttu-id="07fea-187">从适配器架构生成文档实例</span><span class="sxs-lookup"><span data-stu-id="07fea-187">Generate a document instance from the Adapter schema</span></span>  

1.  <span data-ttu-id="07fea-188">双击**LOCATIONService_1.xsd**在解决方案资源管理器在架构编辑器中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="07fea-188">Double-click **LOCATIONService_1.xsd** in the Solution Explorer to open the file in the Schema Editor.</span></span>  

2.  <span data-ttu-id="07fea-189">右键单击**\<架构\>** 节点在架构编辑器中，单击**属性**以显示该节点的属性。</span><span class="sxs-lookup"><span data-stu-id="07fea-189">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  

3.  <span data-ttu-id="07fea-190">选择**CreateEx**从列表中的可用节点**根引用**下拉框中。</span><span class="sxs-lookup"><span data-stu-id="07fea-190">Select **CreateEx** from the list of available nodes in the **Root Reference** dropdown box.</span></span> <span data-ttu-id="07fea-191">这应这样做为了生成示例文档实例时它将生成从**CreateEx**架构节点。</span><span class="sxs-lookup"><span data-stu-id="07fea-191">This should be done so that when you generate a sample document instance it will be generated from the **CreateEx** node of the schema.</span></span>  

4.  <span data-ttu-id="07fea-192">右键单击解决方案资源管理器中的 LOCATIONService_1.xsd，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="07fea-192">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Properties**.</span></span>  

5.  <span data-ttu-id="07fea-193">在属性窗口中，单击以选中**输出实例文件名**下**常规**部分。</span><span class="sxs-lookup"><span data-stu-id="07fea-193">In the Properties window, click to select the **Output Instance Filename** option under the **General** section.</span></span>  

6.  <span data-ttu-id="07fea-194">单击省略号按钮 （...） 以显示**选择输出文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-194">Click the ellipses button (…) to display the **Select Output File** dialog.</span></span>  

7.  <span data-ttu-id="07fea-195">指定的文件夹和输出文件实例名称，例如**C:\instance.xml**然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="07fea-195">Specify a folder and name for the output file instance, for example **C:\instance.xml** and click **Save**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="07fea-196">未指定为 file 接收位置在此处指定的文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="07fea-196">Do not specify the location of the folder that was specified for the file receive location here.</span></span>  

8.  <span data-ttu-id="07fea-197">右键单击解决方案资源管理器中的 LOCATIONService_1.xsd，然后单击**生成实例**以在指定位置生成文档实例。</span><span class="sxs-lookup"><span data-stu-id="07fea-197">Right-click LOCATIONService_1.xsd in Solution Explorer and click **Generate Instance** to generate a document instance in the specified location.</span></span>  

9. <span data-ttu-id="07fea-198">右键单击**\<架构\>** 节点在架构编辑器中，单击**属性**以显示该节点的属性。</span><span class="sxs-lookup"><span data-stu-id="07fea-198">Right-click the **\<Schema\>** node in the Schema Editor, and click **Properties** to display the properties for the node.</span></span>  

10. <span data-ttu-id="07fea-199">选择 (**默认值)** 从列表中的可用节点**根引用**下拉框中。</span><span class="sxs-lookup"><span data-stu-id="07fea-199">Select (**Default)** from the list of available nodes in the **Root Reference** dropdown box.</span></span>  

#### <a name="modify-the-generated-document-instance"></a><span data-ttu-id="07fea-200">修改生成的文档实例</span><span class="sxs-lookup"><span data-stu-id="07fea-200">Modify the generated document instance</span></span>  

1.  <span data-ttu-id="07fea-201">在诸如记事本之类的文本编辑器中打开生成的文档实例，并编辑文档实例，以确保这些字段中的数据将在 PeopleSoft 系统中生成唯一的记录，如下面的 XML 文件介绍了中的字段的内容定义位置的记录：</span><span class="sxs-lookup"><span data-stu-id="07fea-201">Open the generated document instance in a text editor such as Notepad and edit the contents of the document instance to ensure that the data in these fields will generate a unique record in the PeopleSoft system, for example the XML file below describes the fields in a record that define a location:</span></span>  

    ```  
    <ns0:CreateEx xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>9991</ns0:LOCATION>  
      <ns0:interactiveMode>true</ns0:interactiveMode>  
       <ns0:properties>  
        <ns0:LOCATION_TBL_sequence>  
          <ns0:LOCATION_TBL>  
            <ns0:COUNTRY>USA</ns0:COUNTRY>  
            <ns0:DESCR>Adapter Test</ns0:DESCR>  
            <ns0:EFFDT>2006-05-31</ns0:EFFDT>  
            <ns0:EFF_STATUS>A</ns0:EFF_STATUS>  
            <ns0:SETID>SHARE</ns0:SETID>  
          </ns0:LOCATION_TBL>  
        </ns0:LOCATION_TBL_sequence>  
      </ns0:properties>  
    </ns0:CreateEx>  
    ```  

    > [!NOTE]
    >  <span data-ttu-id="07fea-202">在上述示例中， *PeopleSoft*是 BizTalk 管理控制台中的适配器实际名称的占位符。</span><span class="sxs-lookup"><span data-stu-id="07fea-202">In the example above, *PeopleSoft* is a placeholder for the actual name of the adapter as viewed in the BizTalk Administration Console.</span></span>  

2.  <span data-ttu-id="07fea-203">保存修改后的文档实例。</span><span class="sxs-lookup"><span data-stu-id="07fea-203">Save the modified document instance.</span></span>  

#### <a name="build-and-deploy-the-project"></a><span data-ttu-id="07fea-204">生成并部署项目</span><span class="sxs-lookup"><span data-stu-id="07fea-204">Build and deploy the project</span></span>  

1. <span data-ttu-id="07fea-205">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**属性**启动项目设计器。</span><span class="sxs-lookup"><span data-stu-id="07fea-205">Right-click the OneWaySend project in Solution Explorer and click **Properties** to launch the Project Designer.</span></span>  

2. <span data-ttu-id="07fea-206">单击**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="07fea-206">Click the **Deployment** tab.</span></span>  

3. <span data-ttu-id="07fea-207">输入适当的值**服务器**属性和**配置数据库**下的属性**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="07fea-207">Enter the appropriate values for the **Server** property and the **Configuration Database** property under **BizTalk Group**.</span></span>  

4. <span data-ttu-id="07fea-208">右键单击解决方案资源管理器中的 OneWaySend 项目，然后单击**部署**以生成项目，并部署到的程序集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置数据库。</span><span class="sxs-lookup"><span data-stu-id="07fea-208">Right-click the OneWaySend project in Solution Explorer and click **Deploy** to build the project and deploy the assembly to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration database.</span></span>  

#### <a name="bind-and-enlist-the-orchestration"></a><span data-ttu-id="07fea-209">绑定并登记业务流程</span><span class="sxs-lookup"><span data-stu-id="07fea-209">Bind and Enlist the orchestration</span></span>  

1. <span data-ttu-id="07fea-210">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，然后单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="07fea-210">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, and click **Orchestrations**.</span></span>  

2. <span data-ttu-id="07fea-211">单击**刷新**按钮在 MMC 工具栏或按**F5**若要刷新在键盘上键[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台视图。</span><span class="sxs-lookup"><span data-stu-id="07fea-211">Click the **Refresh** button in the MMC toolbar or press the **F5** key on your keyboard to refresh the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console view.</span></span>  

3. <span data-ttu-id="07fea-212">双击业务流程以显示**业务流程属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="07fea-212">Double-click the orchestration to display the **Orchestration Properties** dialog.</span></span>  

4. <span data-ttu-id="07fea-213">单击**绑定**以显示业务流程的绑定选项对话框的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="07fea-213">Click **Bindings** in the left pane of the dialog to display the Bindings options for the orchestration.</span></span>  

5. <span data-ttu-id="07fea-214">指定适当的值的绑定选项，例如：</span><span class="sxs-lookup"><span data-stu-id="07fea-214">Specify the appropriate values for the binding options, for example:</span></span>  


   |      <span data-ttu-id="07fea-215">**参数**</span><span class="sxs-lookup"><span data-stu-id="07fea-215">**Parameter**</span></span>       |        <span data-ttu-id="07fea-216">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="07fea-216">**Value**</span></span>         |
   |--------------------------|--------------------------|
   |           <span data-ttu-id="07fea-217">主机</span><span class="sxs-lookup"><span data-stu-id="07fea-217">Host</span></span>           | <span data-ttu-id="07fea-218">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="07fea-218">BizTalkServerApplication</span></span> |
   |     <span data-ttu-id="07fea-219">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="07fea-219">FileReceivePort</span></span>      |  <span data-ttu-id="07fea-220">PeopleSoftOneWayFileRP</span><span class="sxs-lookup"><span data-stu-id="07fea-220">PeopleSoftOneWayFileRP</span></span>  |
   | <span data-ttu-id="07fea-221">PeopleSoftOneWaySendPort</span><span class="sxs-lookup"><span data-stu-id="07fea-221">PeopleSoftOneWaySendPort</span></span> |    <span data-ttu-id="07fea-222">PeopleSoftOneWaySP</span><span class="sxs-lookup"><span data-stu-id="07fea-222">PeopleSoftOneWaySP</span></span>    |


6. <span data-ttu-id="07fea-223">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="07fea-223">Click OK.</span></span>  

#### <a name="start-the-orchestration"></a><span data-ttu-id="07fea-224">启动业务流程</span><span class="sxs-lookup"><span data-stu-id="07fea-224">Start the orchestration</span></span>  

- <span data-ttu-id="07fea-225">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击该业务流程，然后单击**启动**以登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="07fea-225">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the orchestration and click **Start** to enlist and start the orchestration.</span></span>  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a><span data-ttu-id="07fea-226">拖放到该文件所监视的文件夹的文档实例接收位置</span><span class="sxs-lookup"><span data-stu-id="07fea-226">Drop a document instance into the folder monitored by the file receive location</span></span>  

-   <span data-ttu-id="07fea-227">将文件接收位置的文件夹到先前创建的文档实例复制配置为监视。</span><span class="sxs-lookup"><span data-stu-id="07fea-227">Copy the document instance that was created earlier to the folder that the file receive location is configured to monitor.</span></span>  

#### <a name="verify-that-the-peoplesoft-system-is-updated"></a><span data-ttu-id="07fea-228">验证 PeopleSoft 系统已更新</span><span class="sxs-lookup"><span data-stu-id="07fea-228">Verify that the PeopleSoft system is updated</span></span>  

- <span data-ttu-id="07fea-229">使用 PeopleSoft web 界面验证记录已创建从 XML 文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="07fea-229">Use the PeopleSoft web interface to verify that the record was created from the data in the XML file.</span></span>  

  <span data-ttu-id="07fea-230">如果成功处理的文档实例，会发生以下事件序列：</span><span class="sxs-lookup"><span data-stu-id="07fea-230">The following sequence of events occurs if the document instance is processed successfully:</span></span>  

1.  <span data-ttu-id="07fea-231">文件适配器从文件夹中检索该文件，并将其发布到 MessageBox 作为 BizTalk 消息。</span><span class="sxs-lookup"><span data-stu-id="07fea-231">The File adapter retrieves the file from the folder and publishes it to the MessageBox as a BizTalk message.</span></span>  

2.  <span data-ttu-id="07fea-232">业务流程订阅此发布的消息，以便 BizTalk 消息引擎将激活业务流程的实例并将消息发送到业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="07fea-232">The orchestration subscribes to this published message so the BizTalk Messaging Engine will activate an instance of the orchestration and send the message to the orchestration instance.</span></span>  

3.  <span data-ttu-id="07fea-233">业务流程实例处理使用业务流程中指定的逻辑消息，并将消息发布回 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="07fea-233">The orchestration instance processes the message using the logic specified in the orchestration and publishes the message back to the MessageBox.</span></span>  

4.  <span data-ttu-id="07fea-234">PeopleSoft 发送端口订阅此发布消息，因此 BizTalk 消息引擎将消息发送到 PeopleSoft 发送端口。</span><span class="sxs-lookup"><span data-stu-id="07fea-234">The PeopleSoft send port subscribes to this published message and so the BizTalk Messaging Engine sends the message to the PeopleSoft send port.</span></span>  

5.  <span data-ttu-id="07fea-235">发送端口将消息传递给 BizTalk 适配器，用于 PeopleSoft Enterprise。</span><span class="sxs-lookup"><span data-stu-id="07fea-235">The send port hands the message to the BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

6.  <span data-ttu-id="07fea-236">用于 PeopleSoft Enterprise 的 BizTalk 适配器调用 CreateEx 方法来创建 XML 文件中使用的数据的记录。</span><span class="sxs-lookup"><span data-stu-id="07fea-236">The BizTalk Adapter for PeopleSoft Enterprise invokes the CreateEx method to create a record using the data in the XML file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="07fea-237">请参阅</span><span class="sxs-lookup"><span data-stu-id="07fea-237">See Also</span></span>  
 [<span data-ttu-id="07fea-238">教程：使用用于 PeopleSoft Enterprise 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="07fea-238">Tutorials: Using BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)