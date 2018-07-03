---
title: MQSSendPipelineComponent （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- pipelines, examples
- MQSeries adapters, examples
- examples, pipelines
ms.assetid: ac709e45-524b-45ab-9673-060790ecbed2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc89b19f1e493c46e6128d390774479eb59bc6b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975910"
---
# <a name="mqssendpipelinecomponent-biztalk-server-sample"></a><span data-ttu-id="46936-102">MQSSendPipelineComponent（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="46936-102">MQSSendPipelineComponent (BizTalk Server Sample)</span></span>
<span data-ttu-id="46936-103">本示例演示如何写入从 XML 文件读取一组 MQSeries 属性值并将其应用到消息的管道组件。</span><span class="sxs-lookup"><span data-stu-id="46936-103">This sample demonstrates how to write a pipeline component that reads a set of MQSeries property values from an XML file and applies them to a message.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="46936-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="46936-104">What This Sample Does</span></span>  
 <span data-ttu-id="46936-105">此示例包含两种[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目、 管道组件项目和一个进行的管道项目使用的管道组件。</span><span class="sxs-lookup"><span data-stu-id="46936-105">This sample is composed of two [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects, a pipeline component project and a pipeline project that makes use of the pipeline component.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="46936-106">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="46936-106">Where to Find This Sample</span></span>  
  
- <span data-ttu-id="46936-107">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent</span><span class="sxs-lookup"><span data-stu-id="46936-107">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent</span></span>  
  
- <span data-ttu-id="46936-108">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline</span><span class="sxs-lookup"><span data-stu-id="46936-108">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline</span></span>  
  
  <span data-ttu-id="46936-109">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="46936-109">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|                                                                              <span data-ttu-id="46936-110">**File**</span><span class="sxs-lookup"><span data-stu-id="46936-110">**File**</span></span>                                                                               |                                         <span data-ttu-id="46936-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="46936-111">**Description**</span></span>                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| <span data-ttu-id="46936-112">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln、</span><span class="sxs-lookup"><span data-stu-id="46936-112">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln,</span></span><br /><br /> <span data-ttu-id="46936-113">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="46936-113">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj</span></span> |                    <span data-ttu-id="46936-114">管道组件的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="46936-114">The project and solution files for the pipeline component.</span></span>                    |
|                                              <span data-ttu-id="46936-115">SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs</span><span class="sxs-lookup"><span data-stu-id="46936-115">SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs</span></span>                                              |                      <span data-ttu-id="46936-116">管道组件的 Visual C#® 源文件。</span><span class="sxs-lookup"><span data-stu-id="46936-116">The Visual C#® source file for the pipeline component.</span></span>                      |
|                                                      <span data-ttu-id="46936-117">SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml</span><span class="sxs-lookup"><span data-stu-id="46936-117">SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml</span></span>                                                      |                 <span data-ttu-id="46936-118">由管道组件读取和使用的 MQSeries 属性。</span><span class="sxs-lookup"><span data-stu-id="46936-118">The MQSeries properties read and used by the pipeline component.</span></span>                 |
|   <span data-ttu-id="46936-119">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj、</span><span class="sxs-lookup"><span data-stu-id="46936-119">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj,</span></span><br /><br /> <span data-ttu-id="46936-120">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln</span><span class="sxs-lookup"><span data-stu-id="46936-120">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln</span></span>   |                     <span data-ttu-id="46936-121">BizTalk 管道的项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="46936-121">The project and solution files for the BizTalk pipeline.</span></span>                     |
|                                               <span data-ttu-id="46936-122">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk</span><span class="sxs-lookup"><span data-stu-id="46936-122">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk</span></span>                                               |                   <span data-ttu-id="46936-123">BizTalk 管道项目的强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="46936-123">The strong naming key file for the BizTalk pipeline project.</span></span>                   |
|                                               <span data-ttu-id="46936-124">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="46936-124">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp</span></span>                                               | <span data-ttu-id="46936-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道。</span><span class="sxs-lookup"><span data-stu-id="46936-125">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span> |
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="46936-126">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="46936-126">How to Use This Sample</span></span>  
 <span data-ttu-id="46936-127">若要创建应用程序，必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="46936-127">To create the application, you must complete the following steps:</span></span>  
  
1. <span data-ttu-id="46936-128">为应用程序创建文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-128">Create the folders for the application.</span></span>  
  
2. <span data-ttu-id="46936-129">修改和编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]管道组件项目。</span><span class="sxs-lookup"><span data-stu-id="46936-129">Modify and compile the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the pipeline component.</span></span>  
  
3. <span data-ttu-id="46936-130">将编译的程序集和头文件复制到相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-130">Copy the compiled assembly and the header file to the appropriate folders.</span></span>  
  
4. <span data-ttu-id="46936-131">修改 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="46936-131">Modify the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span>  
  
5. <span data-ttu-id="46936-132">编译和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道项目。</span><span class="sxs-lookup"><span data-stu-id="46936-132">Compile and deploy the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline project.</span></span>  
  
6. <span data-ttu-id="46936-133">设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置。</span><span class="sxs-lookup"><span data-stu-id="46936-133">Set up a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location.</span></span>  
  
7. <span data-ttu-id="46936-134">创建 MQSeries 队列。</span><span class="sxs-lookup"><span data-stu-id="46936-134">Create a MQSeries queue.</span></span>  
  
8. <span data-ttu-id="46936-135">设置发送端口。</span><span class="sxs-lookup"><span data-stu-id="46936-135">Set up a send port.</span></span>  
  
9. <span data-ttu-id="46936-136">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="46936-136">Enable the receive location and start the send port.</span></span>  
  
## <a name="creating-the-folders-for-the-application"></a><span data-ttu-id="46936-137">为应用程序创建文件夹</span><span class="sxs-lookup"><span data-stu-id="46936-137">Creating the Folders for the Application</span></span>  
 <span data-ttu-id="46936-138">此过程将为应用程序创建相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-138">This procedure creates the appropriate folders for the application.</span></span>  
  
#### <a name="to-create-the-folders-for-the-application"></a><span data-ttu-id="46936-139">若要创建的应用程序的文件夹</span><span class="sxs-lookup"><span data-stu-id="46936-139">To create the folders for the application</span></span>  
  
1.  <span data-ttu-id="46936-140">创建名为的文件夹**temp**如果尚不存在在 C:\ 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="46936-140">Create a folder named **temp** on your C:\ drive if it does not already exist.</span></span>  
  
2.  <span data-ttu-id="46936-141">在中创建文件夹**C:\temp**名为目录**Pickup3**。</span><span class="sxs-lookup"><span data-stu-id="46936-141">Create a folder under the **C:\temp** directory named **Pickup3**.</span></span>  
  
## <a name="modifying-and-compiling-the-project-for-the-pipeline-component"></a><span data-ttu-id="46936-142">修改和编译管道组件的项目</span><span class="sxs-lookup"><span data-stu-id="46936-142">Modifying and Compiling the Project for the Pipeline Component</span></span>  
 <span data-ttu-id="46936-143">此过程修改和编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]管道组件项目。</span><span class="sxs-lookup"><span data-stu-id="46936-143">This procedure modifies and compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the pipeline component.</span></span>  
  
#### <a name="to-modify-and-compile-the-project-for-the-pipeline-component"></a><span data-ttu-id="46936-144">修改和编译管道组件的项目</span><span class="sxs-lookup"><span data-stu-id="46936-144">To modify and compile the project for the pipeline component</span></span>  
  
1. <span data-ttu-id="46936-145">双击解决方案文件**SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln**以打开中的解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="46936-145">Double-click the solution file, **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln** to open the solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="46936-146">双击类文件**CSetMQSeriesHeaderPropertyComponent.cs**以打开中的类文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="46936-146">Double-click the class file **CSetMQSeriesHeaderPropertyComponent.cs** to open the class file in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="46936-147">找到变量**samplesDir**，验证此变量设置为位置**C:\temp**。</span><span class="sxs-lookup"><span data-stu-id="46936-147">Locate the variable **samplesDir**, verify that this variable is set to the location **C:\temp**.</span></span>  
  
4. <span data-ttu-id="46936-148">右键单击解决方案资源管理器中的解决方案，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="46936-148">Right-click the solution in the Solution Explorer and click **Build**.</span></span> <span data-ttu-id="46936-149">这会将项目编译到 dll 位于**SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\** 目录。</span><span class="sxs-lookup"><span data-stu-id="46936-149">This will compile the project into a dll located in the **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\** directory.</span></span>  
  
## <a name="copying-the-assembly-and-header-file-to-appropriate-folders"></a><span data-ttu-id="46936-150">将程序集和头文件复制到相应文件夹</span><span class="sxs-lookup"><span data-stu-id="46936-150">Copying the Assembly and Header File to Appropriate Folders</span></span>  
 <span data-ttu-id="46936-151">此过程将编译的程序集和头文件复制到相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-151">This procedure copies the compiled assembly and the header file to the appropriate folders.</span></span>  
  
#### <a name="to-copy-the-compiled-assembly-and-header-file-to-the-appropriate-folders"></a><span data-ttu-id="46936-152">将编译的程序集和头文件复制到相应文件夹</span><span class="sxs-lookup"><span data-stu-id="46936-152">To copy the compiled assembly and header file to the appropriate folders</span></span>  
  
1. <span data-ttu-id="46936-153">将已编译的程序集复制**setmqseriesheaderpropertycomponent.dll 复制**到 BizTalk 管道组件文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-153">Copy the compiled assembly **SetMQSeriesHeaderPropertyComponent.dll** to the BizTalk pipeline components folder.</span></span> <span data-ttu-id="46936-154">BizTalk 管道组件文件夹的默认位置是 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] 管道组件。</span><span class="sxs-lookup"><span data-stu-id="46936-154">The default location for the BizTalk pipeline components folder is [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components.</span></span>  
  
2. <span data-ttu-id="46936-155">将 MQHeader 属性文件复制**setmqsmqmdhdrprops.xml 复制**到**C:\temp**目录。</span><span class="sxs-lookup"><span data-stu-id="46936-155">Copy the MQHeader properties file **SetMQSMQMDHdrProps.xml** to the **C:\temp** directory.</span></span>  
  
## <a name="modifying-the-project-for-the-biztalk-server-pipeline"></a><span data-ttu-id="46936-156">修改 BizTalk Server 管道项目</span><span class="sxs-lookup"><span data-stu-id="46936-156">Modifying the Project for the BizTalk Server Pipeline</span></span>  
 <span data-ttu-id="46936-157">此过程修改 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 管道的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="46936-157">This procedure modifies the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span>  
  
#### <a name="to-modify-the-project-for-the-biztalk-server-pipeline"></a><span data-ttu-id="46936-158">修改 BizTalk Server 管道的项目</span><span class="sxs-lookup"><span data-stu-id="46936-158">To modify the project for the BizTalk Server pipeline</span></span>  
  
1. <span data-ttu-id="46936-159">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，通过双击解决方案文件中，打开解决方案**SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln**。</span><span class="sxs-lookup"><span data-stu-id="46936-159">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution by double-clicking the solution file, **SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln**.</span></span>  
  
2. <span data-ttu-id="46936-160">为项目创建强名称密钥文件。</span><span class="sxs-lookup"><span data-stu-id="46936-160">Create a strong name key file for the project.</span></span> <span data-ttu-id="46936-161">若要这样做，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="46936-161">To do that, do the following:</span></span>  
  
   1. <span data-ttu-id="46936-162">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="46936-162">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command prompt.</span></span>  
  
   2. <span data-ttu-id="46936-163">将目录更改为\<示例路径\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent。</span><span class="sxs-lookup"><span data-stu-id="46936-163">Change directories to \<SamplesPath\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent.</span></span>  
  
   3. <span data-ttu-id="46936-164">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="46936-164">Type the following:</span></span>  
  
       `sn -k MQSSendPipelineComponent.snk`  
  
   4. <span data-ttu-id="46936-165">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="46936-165">Press ENTER.</span></span> <span data-ttu-id="46936-166">这样将创建密钥文件。</span><span class="sxs-lookup"><span data-stu-id="46936-166">This will create the key file.</span></span>  
  
3. <span data-ttu-id="46936-167">在中**解决方案资源管理器**，右键单击项目，然后单击**属性**（在中心窗口中） 中的项目启动项目设计器。</span><span class="sxs-lookup"><span data-stu-id="46936-167">In **Solution Explorer**, right-click the project and click **Properties** to launch Project Designer for the project (in the center window).</span></span>  
  
   1.  <span data-ttu-id="46936-168">在项目设计器中，单击**签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="46936-168">In the Project Designer, click **Signing** tab.</span></span>  
  
   2.  <span data-ttu-id="46936-169">在右侧窗格中，选择**为程序集签名**选项...</span><span class="sxs-lookup"><span data-stu-id="46936-169">In the right-hand pane, select the **Sign the assembly** option..</span></span>  
  
   3.  <span data-ttu-id="46936-170">单击下拉列表**选择强名称密钥文件**选项，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="46936-170">Click drop-down list for the **Choose a strong name key file** option, and click **Browse**.</span></span>  
  
   4.  <span data-ttu-id="46936-171">浏览到\<\adaptersusage\mqseriesadapter\mqssendpipelinecomponent\mqssendpipelinecomponent.snk\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="46936-171">Browse to \<SamplesPath\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk, click **Open**.</span></span>  
  
4. <span data-ttu-id="46936-172">前面创建的管道组件已添加到**预组装**此管道项目阶段。</span><span class="sxs-lookup"><span data-stu-id="46936-172">The pipeline component that you created earlier is already added to the **Pre-Assemble** stage of this pipeline project.</span></span> <span data-ttu-id="46936-173">如果尚未添加此组件，则需要完成以下步骤来添加它：</span><span class="sxs-lookup"><span data-stu-id="46936-173">If this component was not already added you would need to complete the following steps to add it:</span></span>  
  
   1. <span data-ttu-id="46936-174">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]IDE 中，单击**工具箱**左侧和右侧的选项卡。</span><span class="sxs-lookup"><span data-stu-id="46936-174">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE, click the **Toolbox** tab on the left side.</span></span>  
  
   2. <span data-ttu-id="46936-175">右键单击**工具箱**，然后单击**选择项**。</span><span class="sxs-lookup"><span data-stu-id="46936-175">Right-click the **Toolbox**, and click **Choose Items**.</span></span>  
  
   3. <span data-ttu-id="46936-176">在中**选择工具箱项**对话框中，单击**BizTalk 管道组件**选项卡上，选择**自定义组件以设置 MQseries 标头属性**组件，并然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46936-176">In the **Choose Toolbox Items** dialog box, click the **BizTalk Pipeline Components** tab, select the **Custom Component to Set MQseries header properties**component, and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="46936-177">拖动**自定义组件以设置 MQseries 标头属性**组件**预组装**此管道阶段。</span><span class="sxs-lookup"><span data-stu-id="46936-177">Drag the **Custom Component to Set MQseries header properties**component to the **Pre-Assemble** stage of this pipeline.</span></span>  
  
## <a name="compiling-and-deploying-the-pipeline-project"></a><span data-ttu-id="46936-178">编译和部署管道项目</span><span class="sxs-lookup"><span data-stu-id="46936-178">Compiling and Deploying the Pipeline Project</span></span>  
 <span data-ttu-id="46936-179">此过程编译和部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道项目。</span><span class="sxs-lookup"><span data-stu-id="46936-179">This procedure compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline project.</span></span>  
  
#### <a name="to-compile-and-deploy-the-pipeline-project"></a><span data-ttu-id="46936-180">若要编译和部署管道项目</span><span class="sxs-lookup"><span data-stu-id="46936-180">To compile and deploy the pipeline project</span></span>  
  
1.  <span data-ttu-id="46936-181">在解决方案资源管理器窗口中，右键单击该解决方案，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="46936-181">In the Solution Explorer window, right-click the solution, and then click **Deploy Solution**.</span></span> <span data-ttu-id="46936-182">这样会生成解决方案，并将程序集部署到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="46936-182">This builds the solution and deploys the assembly to the BizTalk Management database.</span></span>  
  
2.  <span data-ttu-id="46936-183">验证程序集是否已部署到 BizTalk 管理数据库：</span><span class="sxs-lookup"><span data-stu-id="46936-183">Verify the Assembly was deployed to the BizTalk Management database:</span></span>  
  
    1.  <span data-ttu-id="46936-184">打开 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="46936-184">Open the BizTalk Administration Console.</span></span>  
  
    2.  <span data-ttu-id="46936-185">单击此项可展开**BizTalk 组 [\<servername\>:\<管理数据库\>]**，然后单击以展开**程序集**文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-185">Click to expand **BizTalk Group [\<servername\>:\<management database\>]**, and then click to expand the **Assemblies** folder.</span></span>  
  
         <span data-ttu-id="46936-186">已部署的管道程序集应在下可见**程序集**文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-186">The deployed pipeline assembly should be visible under the **Assemblies** folder.</span></span>  
  
## <a name="creating-the-receive-location"></a><span data-ttu-id="46936-187">创建接收位置</span><span class="sxs-lookup"><span data-stu-id="46936-187">Creating the Receive Location</span></span>  
 <span data-ttu-id="46936-188">此过程创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置。</span><span class="sxs-lookup"><span data-stu-id="46936-188">This procedure creates a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location.</span></span>  
  
#### <a name="to-create-the-receive-location"></a><span data-ttu-id="46936-189">若要创建接收位置</span><span class="sxs-lookup"><span data-stu-id="46936-189">To create the receive location</span></span>  
  
1.  <span data-ttu-id="46936-190">在 BizTalk Server 管理控制台中，右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="46936-190">In the BizTalk Server Administration Console, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="46936-191">在中**单向接收端口属性**对话框中**名称**框中，键入"MQReply"，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46936-191">In the **One-way Receive Port Properties** dialog box, in the **Name** box type "MQReply" and click **OK**.</span></span>  
  
3.  <span data-ttu-id="46936-192">在左窗格中，单击**接收位置**选项卡，然后依次**新建**。</span><span class="sxs-lookup"><span data-stu-id="46936-192">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="46936-193">在中**接收位置属性**对话框中**名称**字段中，键入"ReceiveFile"。</span><span class="sxs-lookup"><span data-stu-id="46936-193">In the **Receive Location Properties** dialog box, in the **Name** field, type "ReceiveFile".</span></span>  
  
5.  <span data-ttu-id="46936-194">在中**传输类型**框中，选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="46936-194">In the **Transport Type** box, select **FILE**.</span></span>  
  
6.  <span data-ttu-id="46936-195">在中**接收处理程序**字段中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="46936-195">In the **Receive Handler** field, select **BizTalkServerApplication**.</span></span>  
  
7.  <span data-ttu-id="46936-196">在中**接收管道**字段中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="46936-196">In the **Receive pipeline** field, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8.  <span data-ttu-id="46936-197">在中**接收文件夹**字段中，键入"C:\temp\Pickup3"。</span><span class="sxs-lookup"><span data-stu-id="46936-197">In the **Receive folder** field, type "C:\temp\Pickup3".</span></span>  
  
9. <span data-ttu-id="46936-198">在中**文件掩码**字段中，键入"*。\*"。</span><span class="sxs-lookup"><span data-stu-id="46936-198">In the **File mask** field, type "*.\*".</span></span>  
  
10. <span data-ttu-id="46936-199">单击**确定**，然后单击**确定**再次以退出**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="46936-199">Click **OK**, and then click **OK** again to exit the **Receive Location Properties** dialog box.</span></span>  
  
## <a name="creating-a-mqseries-queue-through-the-mqseries-explorer"></a><span data-ttu-id="46936-200">创建通过 MQSeries Explorer MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="46936-200">Creating a MQSeries Queue Through the MQSeries Explorer</span></span>  
 <span data-ttu-id="46936-201">如果您拥有安装 MQSeries Server for Windows 所需的权限，则可以通过适配器对话框创建 MQSeries 队列，并可以跳过接下来的过程。</span><span class="sxs-lookup"><span data-stu-id="46936-201">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip this next procedure.</span></span>  
  
 <span data-ttu-id="46936-202">如果您没有这样的访问权限，则可以通过以下过程使用 IBM WebSphere MQ Explorer 创建队列。</span><span class="sxs-lookup"><span data-stu-id="46936-202">If you do not have such access, you can use the following procedure to create the queue using the IBM WebSphere MQ Explorer.</span></span>  
  
#### <a name="to-create-a-mqseries-queue-through-the-mqseries-explorer"></a><span data-ttu-id="46936-203">通过 MQSeries Explorer 创建 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="46936-203">To create a MQSeries queue through the MQSeries Explorer</span></span>  
  
1.  <span data-ttu-id="46936-204">单击**启动**，依次指向**程序**，指向**IBM WebSphere MQ**，然后单击**WebSphere MQ Explorer**。</span><span class="sxs-lookup"><span data-stu-id="46936-204">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="46936-205">双击**队列管理器**，然后双击默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="46936-205">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="46936-206">默认的队列管理器通常命名为**QM_**\<*m a c h* \>其中*m a c h*是您的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="46936-206">The default queue manager is typically named **QM_**\<*machine_name*\> where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="46936-207">右键单击**队列**，依次指向**新建**，然后单击**本地队列**。</span><span class="sxs-lookup"><span data-stu-id="46936-207">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="46936-208">在中**创建本地队列**对话框中**队列名称**，类型**SETHEADER**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46936-208">In **Create Local Queue** dialog box, in **Queue Name**, type **SETHEADER**, and then click **OK**.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="46936-209">创建发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="46936-209">Creating the Send Port and MQSeries Queue</span></span>  
 <span data-ttu-id="46936-210">此过程创建输出消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="46936-210">This procedure creates the send port for the output message.</span></span> <span data-ttu-id="46936-211">创建发送端口时，如果尚未创建 MQSeries 队列，也将创建该队列。</span><span class="sxs-lookup"><span data-stu-id="46936-211">The MQSeries queue is also created when you create the send port if you have not already created it.</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="46936-212">若要创建的发送端口和 MQSeries 队列</span><span class="sxs-lookup"><span data-stu-id="46936-212">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="46936-213">右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="46936-213">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="46936-214">在中**发送端口属性**对话框中**名称**框中，键入"MQSolicitResponse"。</span><span class="sxs-lookup"><span data-stu-id="46936-214">In the **Send Port Properties** dialog box, in the **Name** box, type "MQSolicitResponse".</span></span>  
  
3.  <span data-ttu-id="46936-215">在中**传输类型**框中，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="46936-215">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="46936-216">在中**发送管道**框中，选择**SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="46936-216">In the **Send pipeline** box, select **SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="46936-217">在中**筛选器**，添加具有以下名称/值对的新条目：</span><span class="sxs-lookup"><span data-stu-id="46936-217">In **Filters**, add a new entry with the following name/value pairs:</span></span>  
  
    -   <span data-ttu-id="46936-218">设置**属性**到"BTS。ReceivePortName"。</span><span class="sxs-lookup"><span data-stu-id="46936-218">Set **Property** to "BTS.ReceivePortName".</span></span>  
  
    -   <span data-ttu-id="46936-219">设置**运算符**到"= ="。</span><span class="sxs-lookup"><span data-stu-id="46936-219">Set **Operator** to "==".</span></span>  
  
    -   <span data-ttu-id="46936-220">设置**值**为"ReceiveFile"。</span><span class="sxs-lookup"><span data-stu-id="46936-220">Set **Value** to "ReceiveFile".</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="46936-221">这样会将发送端口设置为订阅在 ReceiveFile 接收端口上到达的消息。</span><span class="sxs-lookup"><span data-stu-id="46936-221">This sets the send port to subscribe to messages that arrive on the ReceiveFile receive port.</span></span>  
  
6.  <span data-ttu-id="46936-222">单击**传输**。</span><span class="sxs-lookup"><span data-stu-id="46936-222">Click **Transport**.</span></span>  
  
7.  <span data-ttu-id="46936-223">在中**地址 (URI)** 字段中，单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="46936-223">In the **Address (URI)** field, click the ellipsis (…) button.</span></span>  
  
8.  <span data-ttu-id="46936-224">在中**MQSeries 传输属性**对话框中**队列定义**字段中，单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="46936-224">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** field, click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="46936-225">在中**队列定义**对话框中**服务器名称**字段中，键入您的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="46936-225">In the **Queue Definition** dialog box, in the **Server Name** field, type your computer name.</span></span>  
  
10. <span data-ttu-id="46936-226">在中**队列管理器**字段中，选择默认的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="46936-226">In the **Queue Manager** field, select the default queue manager.</span></span>  
  
11. <span data-ttu-id="46936-227">在队列字段中，键入"SETHEADER"，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="46936-227">In the Queue field, type "SETHEADER", and then click **Export**.</span></span>  
  
12. <span data-ttu-id="46936-228">在中**导出**对话框中，单击**Create Queue**，然后单击**确定**或**完成**直到您退出所有对话框为止。</span><span class="sxs-lookup"><span data-stu-id="46936-228">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog.</span></span>  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a><span data-ttu-id="46936-229">启用接收位置和启动发送端口</span><span class="sxs-lookup"><span data-stu-id="46936-229">Enabling the Receive Location and Starting the Send Port</span></span>  
 <span data-ttu-id="46936-230">此过程将启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="46936-230">This procedure enables the receive location and start the send port.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="46936-231">若要启用接收位置并启动发送端口</span><span class="sxs-lookup"><span data-stu-id="46936-231">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="46936-232">在 BizTalk Server 管理控制台中，单击**接收端口**。</span><span class="sxs-lookup"><span data-stu-id="46936-232">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="46936-233">在细节窗格中，右键单击**MQIn**接收位置，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="46936-233">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="46936-234">在细节窗格中，右键单击**SetMQHeader**发送端口，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="46936-234">In the details pane, right-click the **SetMQHeader** send port and click **Start**.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="46936-235">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="46936-235">Testing the Application</span></span>  
 <span data-ttu-id="46936-236">此过程将测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="46936-236">This procedure tests the application.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="46936-237">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="46936-237">To test the application</span></span>  
  
1.  <span data-ttu-id="46936-238">Put 将文件放**C:\Temp\Pickup3**文件夹。</span><span class="sxs-lookup"><span data-stu-id="46936-238">Put a file into the **C:\Temp\Pickup3** folder.</span></span>  
  
2.  <span data-ttu-id="46936-239">启动 WebSphere MQ Explorer，双击 SETHEADER 队列以检查 SETHEADER 队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="46936-239">Launch the WebSphere MQ Explorer and double-click the SETHEADER queue to examine the message(s) in the SETHEADER queue.</span></span>  
  
     <span data-ttu-id="46936-240">若要查看 SETHEADER 队列中的所有消息上下文属性，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="46936-240">To see all of the context properties for the messages in the SETHEADER queue, complete the following steps:</span></span>  
  
    1.  <span data-ttu-id="46936-241">双击**SETHEADER**队列以显示**消息浏览器**对话框。</span><span class="sxs-lookup"><span data-stu-id="46936-241">Double-click the **SETHEADER** queue to display the **Message Browser** dialog box.</span></span>  
  
    2.  <span data-ttu-id="46936-242">在中**消息浏览器**对话框中，单击**列**以显示**消息的显示/隐藏列**对话框。</span><span class="sxs-lookup"><span data-stu-id="46936-242">In the **Message Browser** dialog box, click **Columns** to display the **Show/Hide Columns for Messages** dialog box.</span></span>  
  
    3.  <span data-ttu-id="46936-243">下**可用的列**，双击每个条目，以将其显示在**消息浏览器**对话框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="46936-243">Under **Available Columns**, double-click each entry to make it visible in the **Message Browser** dialog box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="46936-244">每条消息的消息上下文属性应会显示在**消息浏览器**对话框。</span><span class="sxs-lookup"><span data-stu-id="46936-244">The message context properties for each message should be visible in the **Message Browser** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46936-245">请参阅</span><span class="sxs-lookup"><span data-stu-id="46936-245">See Also</span></span>  
 [<span data-ttu-id="46936-246">MQSeries 适配器示例</span><span class="sxs-lookup"><span data-stu-id="46936-246">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)