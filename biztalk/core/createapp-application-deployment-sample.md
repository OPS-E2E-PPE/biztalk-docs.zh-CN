---
title: CreateApp （应用程序部署示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce2b895b11a8a2ad0fc6b863d3cd67a20c5c1007
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354182"
---
# <a name="createapp-application-deployment-sample"></a><span data-ttu-id="2ddb4-102">CreateApp （应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="2ddb4-102">CreateApp (Application Deployment Sample)</span></span>
<span data-ttu-id="2ddb4-103">本主题说明如何使用 CreateApp 示例，演示了如何使用 BTSTask 命令行工具部署和取消部署 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-103">This topic explains how to use the CreateApp sample, which demonstrates using the BTSTask command-line tool to deploy and undeploy a BizTalk application.</span></span> <span data-ttu-id="2ddb4-104">如本示例中包含的脚本可用于自动执行夜间生成过程来部署和取消部署 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-104">You could use scripts such as those included in this sample to automate your nightly build process to deploy and undeploy BizTalk applications.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ddb4-105">始终应编写你的部署脚本在无提示模式下运行。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-105">You should always write your deployment scripts to run in silent mode.</span></span> <span data-ttu-id="2ddb4-106">如果不这样做，对话框将显示要求用户输入。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-106">If you do not, dialog boxes will display that require user input.</span></span> <span data-ttu-id="2ddb4-107">这将停止部署过程，直到对话框的手动关闭，这可能导致导入过程挂起。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-107">This will stop the deployment process until the dialog box is manually dismissed, which can cause the import process to hang.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="2ddb4-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="2ddb4-108">What This Sample Does</span></span>  
 <span data-ttu-id="2ddb4-109">该示例包括自动执行应用程序部署任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-109">The sample includes scripts that automate application deployment tasks.</span></span> <span data-ttu-id="2ddb4-110">若要执行这些任务，则运行生成 BizTalk 项目和文件的脚本。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-110">To perform these tasks, you run a script that generates the BizTalk project and files.</span></span> <span data-ttu-id="2ddb4-111">然后运行生成两个 BizTalk 应用程序.msi 文件 – 一个包含的所有包含应用程序中的只有一个程序集在应用程序，另一个项目的.msi 文件的脚本。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-111">Then you run a script that generates two BizTalk application .msi files – an .msi file that contains all of the artifacts in an application, and another that contains only one assembly in the application.</span></span> <span data-ttu-id="2ddb4-112">接下来您运行的脚本使用某一.msi 文件导入到 BizTalk 组的应用程序并安装到本地计算机上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-112">Next you run a script that uses an .msi file to import an application into a BizTalk group and install the application onto the local computer.</span></span> <span data-ttu-id="2ddb4-113">在安装期间，应用程序中包含的预处理脚本创建应用程序使用的文件夹，并其操作记录到文件。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-113">During installation, a pre-processing script included in the application creates folders used by the application and logs its actions to a file.</span></span> <span data-ttu-id="2ddb4-114">最后，运行一个脚本来删除并卸载该应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-114">Finally, you run a script that deletes and uninstalls the application.</span></span> <span data-ttu-id="2ddb4-115">卸载期间，应用程序中包含的预处理脚本中删除的文件和在安装期间创建的文件夹和其操作记录到文件。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-115">During uninstallation, a pre-processing script included in the application removes the files and folders that were created during installation and logs its actions to a file.</span></span>  
  
 <span data-ttu-id="2ddb4-116">此示例随附的脚本如下：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-116">The following are the scripts included with this sample:</span></span>  
  
-   <span data-ttu-id="2ddb4-117">**Build.bat。**</span><span class="sxs-lookup"><span data-stu-id="2ddb4-117">**Build.bat.**</span></span> <span data-ttu-id="2ddb4-118">生成一个密钥文件、 生成 Visual Studio 中的项目并对.dll 文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-118">Generates a key file, builds the project in Visual Studio, and signs the .dll files.</span></span>  
  
-   <span data-ttu-id="2ddb4-119">**CreateFullAndPartialMSI.bat.**</span><span class="sxs-lookup"><span data-stu-id="2ddb4-119">**CreateFullAndPartialMSI.bat.**</span></span> <span data-ttu-id="2ddb4-120">在顺序中采用以下操作：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-120">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="2ddb4-121">使用 BTSTask [AddApp 命令](../core/addapp-command.md)创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-121">Uses the BTSTask [AddApp command](../core/addapp-command.md) to create an application.</span></span>  
  
    2.  <span data-ttu-id="2ddb4-122">使用 BTSTask [AddResource 命令](../core/addresource-command.md)将 Build.bat 生成的以及其他资源添加到应用程序三个 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-122">Uses the BTSTask [AddResource command](../core/addresource-command.md) to add to the application three BizTalk assemblies as well as other resources that were generated by Build.bat.</span></span>  
  
    3.  <span data-ttu-id="2ddb4-123">使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)将导出到某一.msi 文件的应用程序的项目名为 CreateApplicationSample.msi。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-123">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export the application's artifacts into an .msi file named CreateApplicationSample.msi.</span></span>  
  
    4.  <span data-ttu-id="2ddb4-124">使用 BTSTask [ListApp 命令](../core/listapp-command.md)以生成名为 AppManifest.xml，其中列出了在应用程序中包含的项目的所有应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-124">Uses the BTSTask [ListApp Command](../core/listapp-command.md) to generate an application manifest named AppManifest.xml, which lists all of the artifacts contained in the application.</span></span>  
  
    5.  <span data-ttu-id="2ddb4-125">使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)仅将业务流程程序集导出到名为 CreateApplicationSamplePartial.msi 的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-125">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export only the orchestrations assembly into an .msi file named CreateApplicationSamplePartial.msi.</span></span> <span data-ttu-id="2ddb4-126">通过为 ResourceSpec 参数提供 ResourceSpecPartial.xml 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-126">It does this by providing ResourceSpecPartial.xml for the ResourceSpec parameter.</span></span> <span data-ttu-id="2ddb4-127">ResouceSpecPartial.xml 是本示例提供的 ResourceSpecComplete.xml 的已编辑的版本。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-127">ResouceSpecPartial.xml is an edited version of ResourceSpecComplete.xml that has been provided with this sample.</span></span> <span data-ttu-id="2ddb4-128">已编辑此文件，使其包含到只有业务流程程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-128">This file has been edited so that it contains a reference to the orchestrations assembly only.</span></span> <span data-ttu-id="2ddb4-129">如果使用此参数提供，BTSTask 导出仅列出在 ResourceSpecPartial.xml 文件 – 这种情况下，业务流程程序集的项目。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-129">When provided with this parameter, BTSTask exports only the artifacts listed in the ResourceSpecPartial.xml file – in this case, the orchestrations assembly.</span></span>  
  
    6.  <span data-ttu-id="2ddb4-130">从组的 BizTalk 管理数据库中删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-130">Deletes the application from the BizTalk Management database for the group.</span></span>  
  
-   <span data-ttu-id="2ddb4-131">**CreateNewAppFromMSI.bat.**</span><span class="sxs-lookup"><span data-stu-id="2ddb4-131">**CreateNewAppFromMSI.bat.**</span></span> <span data-ttu-id="2ddb4-132">使用 CreateFullAndPartialMSI.bat 生成的： CreateApplicationSample.msi 安装在本地计算机上名为 CreateApplicationSample 的应用程序，以及将应用程序导入 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-132">Uses CreateApplicationSample.msi generated by CreateFullAndPartialMSI.bat to install an application named CreateApplicationSample on the local computer as well as import the application into the BizTalk group.</span></span> <span data-ttu-id="2ddb4-133">在安装期间，PreProcScript.bat 将自动运行，如下文所述。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-133">During installation, PreProcScript.bat runs automatically, as described later.</span></span>  
  
-   <span data-ttu-id="2ddb4-134">**RemoveApp.bat.**</span><span class="sxs-lookup"><span data-stu-id="2ddb4-134">**RemoveApp.bat.**</span></span> <span data-ttu-id="2ddb4-135">在顺序中采用以下操作：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-135">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="2ddb4-136">使用 BTSTask [RemoveApp 命令](../core/removeapp-command.md)从该组的 BizTalk 管理数据库中删除 CreateApplicationSample 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-136">Uses the BTSTask [RemoveApp Command](../core/removeapp-command.md) to delete the CreateApplicationSample application from the BizTalk Management database for the group.</span></span>  
  
    2.  <span data-ttu-id="2ddb4-137">使用 BTSTask [UninstallApp 命令](../core/uninstallapp-command.md)若要从本地计算机上卸载 CreateApplicationSample 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-137">Uses the BTSTask [UninstallApp Command](../core/uninstallapp-command.md) to uninstall the CreateApplicationSample application from the local computer.</span></span> <span data-ttu-id="2ddb4-138">在安装期间，PreProcScript.bat 自动运行，如下所述。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-138">During installation, PreProcScript.bat runs automatically, as described next.</span></span>  
  
-   <span data-ttu-id="2ddb4-139">**PreProcScript.bat.**</span><span class="sxs-lookup"><span data-stu-id="2ddb4-139">**PreProcScript.bat.**</span></span> <span data-ttu-id="2ddb4-140">将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-140">Takes the following actions:</span></span>  
  
    -   <span data-ttu-id="2ddb4-141">每次运行时，设置已由用户提供的程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-141">Each time it runs, sets the public key token for the assembly that has been provided by the user.</span></span>  
  
    -   <span data-ttu-id="2ddb4-142">应用程序在安装期间，创建 CreateApplicationSample 应用程序将用于包含消息的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-142">During application installation, creates the following folders that will be used by the CreateApplicationSample application to contain messages:</span></span>  
  
         <span data-ttu-id="2ddb4-143">C:\CreateApplicationSample\Out</span><span class="sxs-lookup"><span data-stu-id="2ddb4-143">C:\CreateApplicationSample\Out</span></span>  
  
         <span data-ttu-id="2ddb4-144">C:\CreateApplicationSample\In</span><span class="sxs-lookup"><span data-stu-id="2ddb4-144">C:\CreateApplicationSample\In</span></span>  
  
    -   <span data-ttu-id="2ddb4-145">在应用程序卸载期间删除的文件和在安装期间创建的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-145">During application uninstallation, deletes the files and folders that were created during installation.</span></span> <span data-ttu-id="2ddb4-146">此外从全局程序集缓存 (GAC) 卸载安装期间在 GAC 中安装任何程序集和其操作记录到文件。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-146">Also uninstalls from the global assembly cache (GAC) any assemblies that were installed in the GAC during installation and logs its actions to a file.</span></span> <span data-ttu-id="2ddb4-147">若要从 GAC 卸载程序集，它指由用户提供的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-147">To uninstall the assemblies from the GAC, it refers to the public key token provided by the user.</span></span>  
  
    -   <span data-ttu-id="2ddb4-148">安装和卸载，期间创建的日志文件中的以下位置：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-148">During both installation and uninstallation, creates a log file in the following location:</span></span>  
  
         <span data-ttu-id="2ddb4-149">C:\ScriptLog.txt</span><span class="sxs-lookup"><span data-stu-id="2ddb4-149">C:\ScriptLog.txt</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="2ddb4-150">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="2ddb4-150">Where to Find This Sample</span></span>  
 <span data-ttu-id="2ddb4-151">您可以在下的以下文件夹中找到示例文件*\<示例路径\>* \Application 部署\\:</span><span class="sxs-lookup"><span data-stu-id="2ddb4-151">You can find the sample files in the following folders under *\<Samples Path\>* \Application Deployment\\:</span></span>  
  
-   <span data-ttu-id="2ddb4-152">CreateApp （文件夹）</span><span class="sxs-lookup"><span data-stu-id="2ddb4-152">CreateApp (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-153">Build.bat</span><span class="sxs-lookup"><span data-stu-id="2ddb4-153">Build.bat</span></span>  
  
    -   <span data-ttu-id="2ddb4-154">CreateFullAndPartialMSI.bat</span><span class="sxs-lookup"><span data-stu-id="2ddb4-154">CreateFullAndPartialMSI.bat</span></span>  
  
    -   <span data-ttu-id="2ddb4-155">CreateNewAppFromMSI.bat</span><span class="sxs-lookup"><span data-stu-id="2ddb4-155">CreateNewAppFromMSI.bat</span></span>  
  
    -   <span data-ttu-id="2ddb4-156">RemoveApp.bat</span><span class="sxs-lookup"><span data-stu-id="2ddb4-156">RemoveApp.bat</span></span>  
  
-   <span data-ttu-id="2ddb4-157">CreateApp\Bindings （文件夹）</span><span class="sxs-lookup"><span data-stu-id="2ddb4-157">CreateApp\Bindings (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-158">CreateApplicationSampleBindings.xml</span><span class="sxs-lookup"><span data-stu-id="2ddb4-158">CreateApplicationSampleBindings.xml</span></span>  
  
-   <span data-ttu-id="2ddb4-159">CreateApp\Dlls (Folder)</span><span class="sxs-lookup"><span data-stu-id="2ddb4-159">CreateApp\Dlls (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-160">Empty</span><span class="sxs-lookup"><span data-stu-id="2ddb4-160">Empty</span></span>  
  
-   <span data-ttu-id="2ddb4-161">CreateApp\ResourceSpecs （文件夹）</span><span class="sxs-lookup"><span data-stu-id="2ddb4-161">CreateApp\ResourceSpecs (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-162">ResourceSpecPartial.xml</span><span class="sxs-lookup"><span data-stu-id="2ddb4-162">ResourceSpecPartial.xml</span></span>  
  
    -   <span data-ttu-id="2ddb4-163">ResourceSpecComplete.xml</span><span class="sxs-lookup"><span data-stu-id="2ddb4-163">ResourceSpecComplete.xml</span></span>  
  
-   <span data-ttu-id="2ddb4-164">CreateApp\Scripts (Folder)</span><span class="sxs-lookup"><span data-stu-id="2ddb4-164">CreateApp\Scripts (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-165">PreProcScript.bat</span><span class="sxs-lookup"><span data-stu-id="2ddb4-165">PreProcScript.bat</span></span>  
  
-   <span data-ttu-id="2ddb4-166">CreateApp\HelloApplicationDeployment (Folder)</span><span class="sxs-lookup"><span data-stu-id="2ddb4-166">CreateApp\HelloApplicationDeployment (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-167">HelloApplicationDeployment.suo</span><span class="sxs-lookup"><span data-stu-id="2ddb4-167">HelloApplicationDeployment.suo</span></span>  
  
    -   <span data-ttu-id="2ddb4-168">HelloApplicationDeployment.sln</span><span class="sxs-lookup"><span data-stu-id="2ddb4-168">HelloApplicationDeployment.sln</span></span>  
  
-   <span data-ttu-id="2ddb4-169">CreateApp\HelloApplicationDeployment\Maps (Folder)</span><span class="sxs-lookup"><span data-stu-id="2ddb4-169">CreateApp\HelloApplicationDeployment\Maps (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-170">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="2ddb4-170">POToInvoice.btm</span></span>  
  
    -   <span data-ttu-id="2ddb4-171">Maps.btproj</span><span class="sxs-lookup"><span data-stu-id="2ddb4-171">Maps.btproj</span></span>  
  
-   <span data-ttu-id="2ddb4-172">CreateApp\HelloApplicationDeployment\Orchestrations (Folder)</span><span class="sxs-lookup"><span data-stu-id="2ddb4-172">CreateApp\HelloApplicationDeployment\Orchestrations (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-173">Orchestrations.btproj</span><span class="sxs-lookup"><span data-stu-id="2ddb4-173">Orchestrations.btproj</span></span>  
  
    -   <span data-ttu-id="2ddb4-174">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="2ddb4-174">HelloOrchestration.odx</span></span>  
  
-   <span data-ttu-id="2ddb4-175">CreateApp\HelloApplicationDeployment\Schemas (Folder)</span><span class="sxs-lookup"><span data-stu-id="2ddb4-175">CreateApp\HelloApplicationDeployment\Schemas (Folder)</span></span>  
  
    -   <span data-ttu-id="2ddb4-176">Schemas.btproj</span><span class="sxs-lookup"><span data-stu-id="2ddb4-176">Schemas.btproj</span></span>  
  
    -   <span data-ttu-id="2ddb4-177">POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="2ddb4-177">POSchema.xsd</span></span>  
  
    -   <span data-ttu-id="2ddb4-178">InvoiceSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="2ddb4-178">InvoiceSchema.xsd</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="2ddb4-179">如何使用此示例</span><span class="sxs-lookup"><span data-stu-id="2ddb4-179">How to Use This Sample</span></span>  
 <span data-ttu-id="2ddb4-180">使用以下过程使用此示例。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-180">Use the following procedure to use this sample.</span></span>  
  
### <a name="to-use-the-sample"></a><span data-ttu-id="2ddb4-181">若要使用的示例</span><span class="sxs-lookup"><span data-stu-id="2ddb4-181">To use the sample</span></span>  
  
1.  <span data-ttu-id="2ddb4-182">运行 Build.bat。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-182">Run Build.bat.</span></span> <span data-ttu-id="2ddb4-183">这将生成一个密钥文件、 HelloApplicationDeployment 文件夹下生成项目、 对生成的.dll 文件进行签名和放置到 Dlls 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-183">This generates a key file, builds the projects under the folder HelloApplicationDeployment, signs the resulting .dll files, and places the.dll files in the Dlls folder.</span></span>  
  
2.  <span data-ttu-id="2ddb4-184">打开 PreProcScript.bat 文件，位于 CreateApp\Scripts 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-184">Open the PreProcScript.bat file, which is located in the CreateApp\Scripts folder.</span></span> <span data-ttu-id="2ddb4-185">在以下代码行，删除 REM 并提供该程序集的公钥标记：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-185">In the following line of code, remove REM and provide the public key token for the assembly:</span></span>  
  
     <span data-ttu-id="2ddb4-186">**REM set PublicKeyToken=**</span><span class="sxs-lookup"><span data-stu-id="2ddb4-186">**REM set PublicKeyToken=**</span></span>  
  
     <span data-ttu-id="2ddb4-187">例如：</span><span class="sxs-lookup"><span data-stu-id="2ddb4-187">Example:</span></span>  
  
     <span data-ttu-id="2ddb4-188">**set PublicKeyToken=1234a5b6c1234567**</span><span class="sxs-lookup"><span data-stu-id="2ddb4-188">**set PublicKeyToken=1234a5b6c1234567**</span></span>  
  
3.  <span data-ttu-id="2ddb4-189">运行 CreateFullAndPartialMSI.bat。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-189">Run CreateFullAndPartialMSI.bat.</span></span> <span data-ttu-id="2ddb4-190">这将创建两个应用程序.msi 文件： CreateApplicationSample.msi 和 CreateApplicationSamplePartial.msi。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-190">This creates two application .msi files, CreateApplicationSample.msi and CreateApplicationSamplePartial.msi.</span></span>  
  
4.  <span data-ttu-id="2ddb4-191">运行 CreateNewAppFromMSI.bat。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-191">Run CreateNewAppFromMSI.bat.</span></span> <span data-ttu-id="2ddb4-192">此操作将 CreateApplicationSample 应用程序导入到 BizTalk 组，并将其安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-192">This imports the CreateApplicationSample application into the BizTalk group and installs it on the local computer.</span></span>  
  
5.  <span data-ttu-id="2ddb4-193">检查位于 C:\ScriptLog.txt 以验证该脚本已记录其安装操作的脚本日志文件。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-193">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its installation actions.</span></span>  
  
6.  <span data-ttu-id="2ddb4-194">验证 CreateApplicationSample 应用程序显示在 BizTalk Server 管理控制台并添加或删除程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-194">Verify that the CreateApplicationSample application appears both in the BizTalk Server Administration console and Add or Remove Programs.</span></span>  
  
7.  <span data-ttu-id="2ddb4-195">运行 RemoveApp.bat。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-195">Run RemoveApp.bat.</span></span> <span data-ttu-id="2ddb4-196">这将从 BizTalk 管理数据库中删除 CreateApplicationSample，并从本地计算机进行卸载。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-196">This deletes the CreateApplicationSample from the BizTalk Management database and uninstalls it from the local computer.</span></span>  
  
8.  <span data-ttu-id="2ddb4-197">检查 C:\ScriptLog.txt 以验证该脚本已记录其卸载操作所位于的脚本日志文件。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-197">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its uninstallation actions.</span></span> <span data-ttu-id="2ddb4-198">它们应显示在安装过程中更早版本，记录的安装操作之后。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-198">They should appear after the installation actions logged earlier, during installation.</span></span>  
  
9. <span data-ttu-id="2ddb4-199">验证 CreateApplicationSample 应用程序不会再出现在 BizTalk Server 管理控制台或添加或删除程序。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-199">Verify that the CreateApplicationSample application no longer appears in either the BizTalk Server Administration console or Add or Remove Programs.</span></span>  
  
10. <span data-ttu-id="2ddb4-200">验证在安装期间创建的文件夹已被删除。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-200">Verify that the folders that were created during installation have been deleted.</span></span>  
  
11. <span data-ttu-id="2ddb4-201">验证已从 GAC 卸载了程序集。</span><span class="sxs-lookup"><span data-stu-id="2ddb4-201">Verify that the assemblies have been uninstalled from the GAC.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ddb4-202">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ddb4-202">See Also</span></span>  
 <span data-ttu-id="2ddb4-203">[应用程序部署 （BizTalk Server 示例文件夹）](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="2ddb4-203">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="2ddb4-204">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="2ddb4-204">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)