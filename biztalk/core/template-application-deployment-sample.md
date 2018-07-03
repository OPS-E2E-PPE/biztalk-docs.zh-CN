---
title: 模板 （应用程序部署示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- scripts, deploying
- deploying, scripts
- examples, deploying
ms.assetid: 7e77ff8e-b2bc-4d38-b5fd-329d6d54221f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d096dac4d1c51101ddadff9eb6c49c04202d375
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000054"
---
# <a name="template-application-deployment-sample"></a><span data-ttu-id="e477c-102">模板（应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="e477c-102">Template (Application Deployment Sample)</span></span>
<span data-ttu-id="e477c-103">本主题介绍如何使用“模板”示例来进行应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="e477c-103">This topic describes how to use the Template sample for application deployment.</span></span>  
  
 <span data-ttu-id="e477c-104">可以创建和使用两种类型的部署脚本自定义 BizTalk 应用程序部署： 预处理脚本和后处理脚本。</span><span class="sxs-lookup"><span data-stu-id="e477c-104">You can create and use two types of deployment scripts to customize BizTalk application deployment: pre-processing scripts and post-processing scripts.</span></span> <span data-ttu-id="e477c-105">预处理脚本在应用程序安装和导入开始前以及在卸载完成后调用。</span><span class="sxs-lookup"><span data-stu-id="e477c-105">Pre-processing scripts are invoked before application installation and import begins and after uninstallation completes.</span></span> <span data-ttu-id="e477c-106">后续处理脚本在应用程序安装和导入完成后以及在卸载开始前调用。</span><span class="sxs-lookup"><span data-stu-id="e477c-106">Post-processing scripts are invoked after application installation and import completes and before uninstallation begins.</span></span>  
  
 <span data-ttu-id="e477c-107">您可以编写预处理脚本和后续处理脚本，以便针对上述每项操作进行调用。</span><span class="sxs-lookup"><span data-stu-id="e477c-107">You can write pre- and post- processing scripts so that they are invoked for each of these operations.</span></span> <span data-ttu-id="e477c-108">或者，您也可以将脚本配置为仅在其中一项操作后执行。</span><span class="sxs-lookup"><span data-stu-id="e477c-108">Alternatively, you can configure scripts to execute after only one of them.</span></span> <span data-ttu-id="e477c-109">有关编写脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="e477c-109">For more information about writing scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
 <span data-ttu-id="e477c-110">本主题演示如何编写并部署脚本，使其仅在一项操作之前或之后调用。</span><span class="sxs-lookup"><span data-stu-id="e477c-110">This topic demonstrates how to write and deploy a script so that it is invoked before or after only one operation.</span></span> <span data-ttu-id="e477c-111">具体方法是：编写一段脚本，此脚本通过检查三个环境变量的值来决定操作调用上下文中的操作。</span><span class="sxs-lookup"><span data-stu-id="e477c-111">You do this by writing a script that checks the values of three environment variables to determine the operation in the context of which it is being called.</span></span> <span data-ttu-id="e477c-112">根据此上下文，脚本将继续执行或停止执行。</span><span class="sxs-lookup"><span data-stu-id="e477c-112">Based on this context, the script either continues or discontinues execution.</span></span>  
  
 <span data-ttu-id="e477c-113">本主题介绍如何执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e477c-113">This topic describes how to take the following steps:</span></span>  
  
1.  <span data-ttu-id="e477c-114">设置日志文件位置，以便生成脚本操作的日志文件。</span><span class="sxs-lookup"><span data-stu-id="e477c-114">Set the log file location, so that you can generate a log file of the script operations.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e477c-115">最佳做法是，始终生成日志文件以便验证脚本操作并解决任何问题。</span><span class="sxs-lookup"><span data-stu-id="e477c-115">As a best practice, you should always generate a log file so that you can verify script operations and troubleshoot any problems.</span></span>  
  
2.  <span data-ttu-id="e477c-116">新建一个 BizTalk 应用程序，并向该应用程序添加示例脚本。</span><span class="sxs-lookup"><span data-stu-id="e477c-116">Create a new BizTalk application and add the sample scripts to it.</span></span>  
  
3.  <span data-ttu-id="e477c-117">导出包含应用程序项目的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="e477c-117">Export an .msi file containing the application artifacts.</span></span>  
  
4.  <span data-ttu-id="e477c-118">从 BizTalk 组删除此应用程序，以便将此 .msi 文件导入回原来的组中，并从此 .msi 文件进行安装。</span><span class="sxs-lookup"><span data-stu-id="e477c-118">Delete the application from the BizTalk group, so that you can import the .msi file back into the same group as well as install it from the .msi file.</span></span>  
  
5.  <span data-ttu-id="e477c-119">导入此应用程序，然后检查日志文件以查看是否已记录导入操作。</span><span class="sxs-lookup"><span data-stu-id="e477c-119">Import the application, and check the log file to see that the import operation was logged.</span></span>  
  
6.  <span data-ttu-id="e477c-120">安装此应用程序，然后检查日志文件以查看是否已将安装日志附加到该日志文件中。</span><span class="sxs-lookup"><span data-stu-id="e477c-120">Install the application, and check the log file to see that the installation log was appended to the log file.</span></span>  
  
7.  <span data-ttu-id="e477c-121">查看日志文件，注意脚本执行了哪些操作以及执行这些操作的时间。</span><span class="sxs-lookup"><span data-stu-id="e477c-121">View the log files and note what operations the scripts performed and when they were performed.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e477c-122">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="e477c-122">What This Sample Does</span></span>  
 <span data-ttu-id="e477c-123">针对本示例提供的两个 .bat 文件包含用于导入、安装和卸载的环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="e477c-123">Two .bat files provided for this sample contain the values of the environment variables for import, installation, and uninstallation.</span></span> <span data-ttu-id="e477c-124">SamplePreProcessing.bat 包含预处理脚本的变量。</span><span class="sxs-lookup"><span data-stu-id="e477c-124">SamplePreProcessing.bat contains variables for a pre-processing script.</span></span> <span data-ttu-id="e477c-125">SamplePostProcessing.bat 包含后处理脚本的变量。</span><span class="sxs-lookup"><span data-stu-id="e477c-125">SamplePostProcessing.bat contains variables for a post-processing script.</span></span> <span data-ttu-id="e477c-126">这些文件还演示了如何记录来自脚本的消息。</span><span class="sxs-lookup"><span data-stu-id="e477c-126">The files also demonstrate how to log messages from scripts.</span></span> <span data-ttu-id="e477c-127">您可以将这些文件的相关部分复制到脚本中。</span><span class="sxs-lookup"><span data-stu-id="e477c-127">You can copy the relevant sections of these files into your scripts.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e477c-128">脚本文件中的某些注释不正确，具体如下：</span><span class="sxs-lookup"><span data-stu-id="e477c-128">Some of the comments within the script files are incorrect, as follows:</span></span>  
>   
>  <span data-ttu-id="e477c-129">在 SamplePreProcessing.bat 中，脚本注释“Pre uninstall part of the script called for an existing application”应为“Post uninstall part of the script called for an existing application”。</span><span class="sxs-lookup"><span data-stu-id="e477c-129">In SamplePreProcessing.bat, the script comment, “Pre uninstall part of the script called for an existing application” should read "Post uninstall part of the script called for an existing application."</span></span>  
>   
>  <span data-ttu-id="e477c-130">在 SamplePostProcessing.bat 中，脚本注释“Post uninstall part of the script called for an existing application”应为“Pre uninstall part of the script called for an existing application”。</span><span class="sxs-lookup"><span data-stu-id="e477c-130">In SamplePostProcessing.bat, the script comment, “Post uninstall part of the script called for an existing application” should read "Pre uninstall part of the script called for an existing application."</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e477c-131">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="e477c-131">Where to Find This Sample</span></span>  
 <span data-ttu-id="e477c-132">该示例位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹中的，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="e477c-132">The sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder, as follows:</span></span>  
  
 <span data-ttu-id="e477c-133">*\<示例路径\>* \Application Deployment\Template</span><span class="sxs-lookup"><span data-stu-id="e477c-133">*\<Samples Path\>* \Application Deployment\Template</span></span>  
  
 <span data-ttu-id="e477c-134">如前所述，本示例包括下列两个文件：</span><span class="sxs-lookup"><span data-stu-id="e477c-134">As previously mentioned, the sample includes the following two files:</span></span>  
  
-   <span data-ttu-id="e477c-135">SamplePreProcessing.bat</span><span class="sxs-lookup"><span data-stu-id="e477c-135">SamplePreProcessing.bat</span></span>  
  
-   <span data-ttu-id="e477c-136">SamplePostProcessing.bat</span><span class="sxs-lookup"><span data-stu-id="e477c-136">SamplePostProcessing.bat</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="e477c-137">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="e477c-137">How to Use This Sample</span></span>  
 <span data-ttu-id="e477c-138">若要运行本示例，请执行下列步骤。</span><span class="sxs-lookup"><span data-stu-id="e477c-138">To run the sample, take the following steps.</span></span>  
  
### <a name="to-set-the-logging-location"></a><span data-ttu-id="e477c-139">设置日志记录位置</span><span class="sxs-lookup"><span data-stu-id="e477c-139">To set the logging location</span></span>  
  
-   <span data-ttu-id="e477c-140">打开这两个脚本示例并更改 LogFile 变量，使其指向日志文件的写入位置。</span><span class="sxs-lookup"><span data-stu-id="e477c-140">Open both the script samples and change the LogFile variable to point to the location where the log files are to be written.</span></span> <span data-ttu-id="e477c-141">您必须提供包含文件名的完整路径。</span><span class="sxs-lookup"><span data-stu-id="e477c-141">You must provide the full path including the file name.</span></span> <span data-ttu-id="e477c-142">如果该路径包含空格，则必须将该路径括在双引号 (") 中。</span><span class="sxs-lookup"><span data-stu-id="e477c-142">If it includes spaces, you must enclose the path in double quotation marks (").</span></span>  
  
     <span data-ttu-id="e477c-143">例如：</span><span class="sxs-lookup"><span data-stu-id="e477c-143">Example:</span></span>  
  
     <span data-ttu-id="e477c-144">设置 LogFile ="*\<示例路径\>* \ApplicationDeployment\Templates\SampleLogOut.txt"</span><span class="sxs-lookup"><span data-stu-id="e477c-144">set LogFile="*\<Samples Path\>* \ApplicationDeployment\Templates\SampleLogOut.txt"</span></span>  
  
### <a name="to-create-a-new-application"></a><span data-ttu-id="e477c-145">新建应用程序</span><span class="sxs-lookup"><span data-stu-id="e477c-145">To create a new application</span></span>  
  
1. <span data-ttu-id="e477c-146">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e477c-146">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="e477c-147">在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] 和 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="e477c-147">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and expand the BizTalk group.</span></span>  
  
3. <span data-ttu-id="e477c-148">右键单击**应用程序**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="e477c-148">Right-click **Applications** and then click **New**.</span></span>  
  
4. <span data-ttu-id="e477c-149">在中**应用程序名称**，类型`SamplesTemplate`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e477c-149">In **Application name**, type `SamplesTemplate`, and then click **OK**.</span></span>  
  
### <a name="to-add-the-scripts-to-the-application"></a><span data-ttu-id="e477c-150">若要将脚本添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="e477c-150">To add the scripts to the application</span></span>  
  
1.  <span data-ttu-id="e477c-151">展开刚创建的 SamplesTemplate 应用程序的文件夹，右击**资源**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="e477c-151">Expand the folder of the SamplesTemplate application that you just created and right-click **Resources** in the left pane.</span></span>  
  
2.  <span data-ttu-id="e477c-152">指向**外**然后单击**预处理脚本**。</span><span class="sxs-lookup"><span data-stu-id="e477c-152">Point to **Add** and click **Pre-processing Scripts**.</span></span>  
  
3.  <span data-ttu-id="e477c-153">单击**添加**并浏览至 SamplePreProcessing.bat。</span><span class="sxs-lookup"><span data-stu-id="e477c-153">Click **Add** and browse to SamplePreProcessing.bat.</span></span>  
  
4.  <span data-ttu-id="e477c-154">选择该文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="e477c-154">Select the file and click **Open**.</span></span>  
  
5.  <span data-ttu-id="e477c-155">在中**文件类型**，单击**system.biztalk: preprocessingscript**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e477c-155">In **File type**, click **System.BizTalk:PreprocessingScript**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e477c-156">SamplePreProcessing.bat 将添加到应用程序中，并且显示在应用程序的“资源”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e477c-156">SamplePreProcessing.bat is added to the application and is displayed in the Resources folder of the application.</span></span>  
  
6.  <span data-ttu-id="e477c-157">再次右键单击资源，指向**外**，然后单击**后续处理脚本**。</span><span class="sxs-lookup"><span data-stu-id="e477c-157">Right-click Resources again, point to **Add**, and then click **Post-processing Scripts**.</span></span>  
  
7.  <span data-ttu-id="e477c-158">单击**添加**并浏览至 SamplePostProcessing.bat。</span><span class="sxs-lookup"><span data-stu-id="e477c-158">Click **Add** and browse to SamplePostProcessing.bat.</span></span>  
  
8.  <span data-ttu-id="e477c-159">选择该文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="e477c-159">Select the file and click **Open**.</span></span>  
  
9. <span data-ttu-id="e477c-160">在中**文件类型**，单击**system.biztalk: postprocessingscript**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e477c-160">In **File type**, click **System.BizTalk:PostprocessingScript**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e477c-161">SamplePostProcessing.bat 将添加到应用程序中，并且显示在应用程序的“资源”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e477c-161">SamplePostProcessing.bat is added to the application and is displayed in the Resources folder of the application.</span></span>  
  
### <a name="to-export-an-msi-file"></a><span data-ttu-id="e477c-162">导出 .msi 文件</span><span class="sxs-lookup"><span data-stu-id="e477c-162">To export an .msi file</span></span>  
  
1.  <span data-ttu-id="e477c-163">在 BizTalk Server 管理控制台中，右键单击 SamplesTemplate 应用程序，指向**导出**，然后单击**MSI 文件**。</span><span class="sxs-lookup"><span data-stu-id="e477c-163">In the BizTalk Server Administration console, right-click the SamplesTemplate application, point to **Export**, and then click **MSI file**.</span></span>  
  
2.  <span data-ttu-id="e477c-164">在欢迎使用导出向导页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e477c-164">On the Welcome to the Export Wizard page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="e477c-165">在选择资源页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e477c-165">On the Select Resources page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="e477c-166">在指定 IIS 主机页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e477c-166">On the Specify IIS Hosts page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="e477c-167">在依赖项页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e477c-167">On the Dependencies page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="e477c-168">在目标页上，在**目标应用程序名**，键入应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="e477c-168">On the Destination page, in **Destination application name**, type the application name.</span></span>  
  
7.  <span data-ttu-id="e477c-169">在中**MSI 文件以生成**，键入 MSI 文件的完整路径，然后单击**导出**。</span><span class="sxs-lookup"><span data-stu-id="e477c-169">In **MSI file to generate**, type the full path for the MSI file, and then click **Export**.</span></span> <span data-ttu-id="e477c-170">示例： C:\MSI\SamplesTemplate.msi</span><span class="sxs-lookup"><span data-stu-id="e477c-170">Example: C:\MSI\SamplesTemplate.msi</span></span>  
  
8.  <span data-ttu-id="e477c-171">在摘要页上单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="e477c-171">On the Summary page, click **Finish**.</span></span>  
  
### <a name="delete-the-application"></a><span data-ttu-id="e477c-172">删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="e477c-172">Delete the application</span></span>  
  
-   <span data-ttu-id="e477c-173">在 BizTalk Server 管理控制台中，右键单击 SamplesTemplate 应用程序，然后依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="e477c-173">In the BizTalk Server Administration console, right-click the SamplesTemplate application, and then click **Delete**.</span></span>  
  
### <a name="to-import-the-msi-file"></a><span data-ttu-id="e477c-174">导入 .msi 文件</span><span class="sxs-lookup"><span data-stu-id="e477c-174">To import the .msi file</span></span>  
  
1.  <span data-ttu-id="e477c-175">在 BizTalk Server 管理控制台中，右键单击**应用程序**，依次指向**导入**，然后单击**MSI 文件**。</span><span class="sxs-lookup"><span data-stu-id="e477c-175">In the BizTalk Server Administration console, right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
2.  <span data-ttu-id="e477c-176">在导入向导页中，欢迎在**MSI 文件导入**，键入之前导出，然后依次的.msi 文件的路径**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e477c-176">On the Welcome to the Import Wizard page, in **MSI file to import**, type the path of the .msi file that you previously exported, and then click **Next**.</span></span> <span data-ttu-id="e477c-177">如果有必要，则可以浏览 MSI 文件通过单击 **（...）** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e477c-177">If necessary, you can browse for the MSI file by clicking the **(….)** button.</span></span>  
  
3.  <span data-ttu-id="e477c-178">在应用程序设置页上，在**应用程序名称**下拉列表中，选择应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="e477c-178">On the Application Settings page, in the **Application name** drop-down list, select the application name.</span></span>  
  
4.  <span data-ttu-id="e477c-179">在中**可用的应用程序将引用添加到**，选择要添加的引用，如果有的话，应用程序，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e477c-179">In **Available applications to add references to**, select the applications to which to add references, if any, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="e477c-180">在应用程序目标环境设置页上单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e477c-180">On the Application Target Environment Settings page, click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e477c-181">在本示例中，您无需指定目标环境。</span><span class="sxs-lookup"><span data-stu-id="e477c-181">You do not need to specify a target environment for the purposes of this sample.</span></span> <span data-ttu-id="e477c-182">有关此功能的背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="e477c-182">For background information on this feature, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span> <span data-ttu-id="e477c-183">有关添加绑定文件的说明，请参阅[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)。</span><span class="sxs-lookup"><span data-stu-id="e477c-183">For instructions on adding binding files, see [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span>  
  
6.  <span data-ttu-id="e477c-184">在导入摘要页面上，确认的摘要信息是否正确，然后依次**导入**。</span><span class="sxs-lookup"><span data-stu-id="e477c-184">On the Import Summary page, confirm that the summary information is correct, and then click **Import**.</span></span>  
  
7.  <span data-ttu-id="e477c-185">在结果页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="e477c-185">On the Results page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="e477c-186">打开执行脚本时创建的日志文件，并验证是否已记录导入操作。</span><span class="sxs-lookup"><span data-stu-id="e477c-186">Open the log file that was created when the scripts executed, and verify that import operation was logged.</span></span>  
  
### <a name="to-install-the-application"></a><span data-ttu-id="e477c-187">若要安装该应用程序</span><span class="sxs-lookup"><span data-stu-id="e477c-187">To install the application</span></span>  
  
1.  <span data-ttu-id="e477c-188">双击 .msi 文件并运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="e477c-188">Double-click the .msi file and run the Installation Wizard.</span></span>  
  
2.  <span data-ttu-id="e477c-189">打开日志文件，并验证是否已将安装操作添加到日志纪录信息中。</span><span class="sxs-lookup"><span data-stu-id="e477c-189">Open the log file and verify that installation operation was added to the logging information.</span></span>  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a><span data-ttu-id="e477c-190">验证脚本运行是否正常</span><span class="sxs-lookup"><span data-stu-id="e477c-190">To verify that the scripts functioned correctly</span></span>  
  
-   <span data-ttu-id="e477c-191">打开日志文件，验证脚本在指定操作期间是否执行。</span><span class="sxs-lookup"><span data-stu-id="e477c-191">Open the log files and verify that they executed during the specified operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e477c-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="e477c-192">See Also</span></span>  
 <span data-ttu-id="e477c-193">[应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="e477c-193">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="e477c-194">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="e477c-194">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)