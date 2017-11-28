---
title: "CreateApp （应用程序部署示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 010c574c1c9c799d6235b9d10e3378b46c3d1548
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="createapp-application-deployment-sample"></a><span data-ttu-id="bd592-102">CreateApp（应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="bd592-102">CreateApp (Application Deployment Sample)</span></span>
<span data-ttu-id="bd592-103">本主题介绍如何使用 CreateApp 示例，该示例演示如何使用 BTSTask 命令行工具部署和取消部署 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd592-103">This topic explains how to use the CreateApp sample, which demonstrates using the BTSTask command-line tool to deploy and undeploy a BizTalk application.</span></span> <span data-ttu-id="bd592-104">您可以使用本示例中包含的脚本等自动执行夜间生成过程，来部署和取消部署 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd592-104">You could use scripts such as those included in this sample to automate your nightly build process to deploy and undeploy BizTalk applications.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd592-105">应始终将部署脚本编写为在静默模式下运行。</span><span class="sxs-lookup"><span data-stu-id="bd592-105">You should always write your deployment scripts to run in silent mode.</span></span> <span data-ttu-id="bd592-106">否则，将显示要求用户输入的对话框。</span><span class="sxs-lookup"><span data-stu-id="bd592-106">If you do not, dialog boxes will display that require user input.</span></span> <span data-ttu-id="bd592-107">这将停止部署过程，直到您手动关闭此对话框为止，并可能导致导入过程挂起。</span><span class="sxs-lookup"><span data-stu-id="bd592-107">This will stop the deployment process until the dialog box is manually dismissed, which can cause the import process to hang.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="bd592-108">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="bd592-108">What This Sample Does</span></span>  
 <span data-ttu-id="bd592-109">本示例包含用于自动执行应用程序部署任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="bd592-109">The sample includes scripts that automate application deployment tasks.</span></span> <span data-ttu-id="bd592-110">若要执行这些任务，请运行生成 BizTalk 项目和文件的脚本。</span><span class="sxs-lookup"><span data-stu-id="bd592-110">To perform these tasks, you run a script that generates the BizTalk project and files.</span></span> <span data-ttu-id="bd592-111">然后运行生成两个 BizTalk 应用程序 .msi 文件的脚本 – 一个 .msi 文件包含应用程序中的所有项目 ， 而另一个 .msi 文件只包含应用程序中的一个程序集 。</span><span class="sxs-lookup"><span data-stu-id="bd592-111">Then you run a script that generates two BizTalk application .msi files – an .msi file that contains all of the artifacts in an application, and another that contains only one assembly in the application.</span></span> <span data-ttu-id="bd592-112">接着，运行使用 .msi 文件将应用程序导入某一 BizTalk 组并在本地计算机上安装该应用程序的脚本。</span><span class="sxs-lookup"><span data-stu-id="bd592-112">Next you run a script that uses an .msi file to import an application into a BizTalk group and install the application onto the local computer.</span></span> <span data-ttu-id="bd592-113">安装期间，该应用程序中包含的预处理脚本将创建由该应用程序使用的文件夹，并将其操作记录到文件中。</span><span class="sxs-lookup"><span data-stu-id="bd592-113">During installation, a pre-processing script included in the application creates folders used by the application and logs its actions to a file.</span></span> <span data-ttu-id="bd592-114">最后，运行删除并卸载该应用程序的脚本。</span><span class="sxs-lookup"><span data-stu-id="bd592-114">Finally, you run a script that deletes and uninstalls the application.</span></span> <span data-ttu-id="bd592-115">卸载期间，该应用程序中包含的预处理脚本将删除在安装期间创建的文件和文件夹，并将其操作记录到文件中。</span><span class="sxs-lookup"><span data-stu-id="bd592-115">During uninstallation, a pre-processing script included in the application removes the files and folders that were created during installation and logs its actions to a file.</span></span>  
  
 <span data-ttu-id="bd592-116">下面列出了本示例中包含的脚本：</span><span class="sxs-lookup"><span data-stu-id="bd592-116">The following are the scripts included with this sample:</span></span>  
  
-   <span data-ttu-id="bd592-117">**Build.bat。**</span><span class="sxs-lookup"><span data-stu-id="bd592-117">**Build.bat.**</span></span> <span data-ttu-id="bd592-118">生成密钥文件，在 Visual Studio 中生成项目并对 .dll 文件签名。</span><span class="sxs-lookup"><span data-stu-id="bd592-118">Generates a key file, builds the project in Visual Studio, and signs the .dll files.</span></span>  
  
-   <span data-ttu-id="bd592-119">**CreateFullAndPartialMSI.bat。**</span><span class="sxs-lookup"><span data-stu-id="bd592-119">**CreateFullAndPartialMSI.bat.**</span></span> <span data-ttu-id="bd592-120">按顺序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bd592-120">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="bd592-121">使用 BTSTask [AddApp 命令](../core/addapp-command.md)创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd592-121">Uses the BTSTask [AddApp command](../core/addapp-command.md) to create an application.</span></span>  
  
    2.  <span data-ttu-id="bd592-122">使用 BTSTask [AddResource 命令](../core/addresource-command.md)将添加到应用程序三 BizTalk 程序集生成 Build.bat 以及其他资源。</span><span class="sxs-lookup"><span data-stu-id="bd592-122">Uses the BTSTask [AddResource command](../core/addresource-command.md) to add to the application three BizTalk assemblies as well as other resources that were generated by Build.bat.</span></span>  
  
    3.  <span data-ttu-id="bd592-123">使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)将导出到.msi 文件的应用程序的项目名为 CreateApplicationSample.msi。</span><span class="sxs-lookup"><span data-stu-id="bd592-123">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export the application's artifacts into an .msi file named CreateApplicationSample.msi.</span></span>  
  
    4.  <span data-ttu-id="bd592-124">使用 BTSTask [ListApp 命令](../core/listapp-command.md)来生成名为 AppManifest.xml，列出所有包含在应用程序的项目的应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="bd592-124">Uses the BTSTask [ListApp Command](../core/listapp-command.md) to generate an application manifest named AppManifest.xml, which lists all of the artifacts contained in the application.</span></span>  
  
    5.  <span data-ttu-id="bd592-125">使用 BTSTask [ExportApp 命令](../core/exportapp-command.md)导出到名为 CreateApplicationSamplePartial.msi.msi 文件业务流程程序集的仅。</span><span class="sxs-lookup"><span data-stu-id="bd592-125">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export only the orchestrations assembly into an .msi file named CreateApplicationSamplePartial.msi.</span></span> <span data-ttu-id="bd592-126">该操作是通过向 ResourceSpec 参数提供 ResourceSpecPartial.xml 执行的。</span><span class="sxs-lookup"><span data-stu-id="bd592-126">It does this by providing ResourceSpecPartial.xml for the ResourceSpec parameter.</span></span> <span data-ttu-id="bd592-127">ResouceSpecPartial.xml 是随本示例提供的 ResourceSpecComplete.xml 的已编辑版本。</span><span class="sxs-lookup"><span data-stu-id="bd592-127">ResouceSpecPartial.xml is an edited version of ResourceSpecComplete.xml that has been provided with this sample.</span></span> <span data-ttu-id="bd592-128">已对该文件进行编辑，使其仅包含对业务流程程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="bd592-128">This file has been edited so that it contains a reference to the orchestrations assembly only.</span></span> <span data-ttu-id="bd592-129">使用此参数时 ， BTSTask 仅导出在 ResourceSpecPartial.xml 文件中列出的项目 – 在本示例中为业务流程程序集 。</span><span class="sxs-lookup"><span data-stu-id="bd592-129">When provided with this parameter, BTSTask exports only the artifacts listed in the ResourceSpecPartial.xml file – in this case, the orchestrations assembly.</span></span>  
  
    6.  <span data-ttu-id="bd592-130">从该组的 BizTalk 管理数据库中删除此应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd592-130">Deletes the application from the BizTalk Management database for the group.</span></span>  
  
-   <span data-ttu-id="bd592-131">**CreateNewAppFromMSI.bat。**</span><span class="sxs-lookup"><span data-stu-id="bd592-131">**CreateNewAppFromMSI.bat.**</span></span> <span data-ttu-id="bd592-132">使用 CreateFullAndPartialMSI.bat 生成的 CreateApplicationSample.msi 在本地计算机上安装名为 CreateApplicationSample 的应用程序，并将该应用程序导入到 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="bd592-132">Uses CreateApplicationSample.msi generated by CreateFullAndPartialMSI.bat to install an application named CreateApplicationSample on the local computer as well as import the application into the BizTalk group.</span></span> <span data-ttu-id="bd592-133">安装期间，PreProcScript.bat 将自动运行，如后文所述。</span><span class="sxs-lookup"><span data-stu-id="bd592-133">During installation, PreProcScript.bat runs automatically, as described later.</span></span>  
  
-   <span data-ttu-id="bd592-134">**RemoveApp.bat。**</span><span class="sxs-lookup"><span data-stu-id="bd592-134">**RemoveApp.bat.**</span></span> <span data-ttu-id="bd592-135">按顺序执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bd592-135">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="bd592-136">使用 BTSTask [RemoveApp 命令](../core/removeapp-command.md)若要从组 BizTalk 管理数据库中删除 CreateApplicationSample 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd592-136">Uses the BTSTask [RemoveApp Command](../core/removeapp-command.md) to delete the CreateApplicationSample application from the BizTalk Management database for the group.</span></span>  
  
    2.  <span data-ttu-id="bd592-137">使用 BTSTask [UninstallApp 命令](../core/uninstallapp-command.md)以从本地计算机上卸载 CreateApplicationSample 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bd592-137">Uses the BTSTask [UninstallApp Command](../core/uninstallapp-command.md) to uninstall the CreateApplicationSample application from the local computer.</span></span> <span data-ttu-id="bd592-138">安装期间，PreProcScript.bat 将自动运行，如下文所述。</span><span class="sxs-lookup"><span data-stu-id="bd592-138">During installation, PreProcScript.bat runs automatically, as described next.</span></span>  
  
-   <span data-ttu-id="bd592-139">**PreProcScript.bat。**</span><span class="sxs-lookup"><span data-stu-id="bd592-139">**PreProcScript.bat.**</span></span> <span data-ttu-id="bd592-140">执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bd592-140">Takes the following actions:</span></span>  
  
    -   <span data-ttu-id="bd592-141">每次运行时，设置用户提供的程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="bd592-141">Each time it runs, sets the public key token for the assembly that has been provided by the user.</span></span>  
  
    -   <span data-ttu-id="bd592-142">在应用程序安装期间，创建 CreateApplicationSample 应用程序用于包含消息的下列文件夹：</span><span class="sxs-lookup"><span data-stu-id="bd592-142">During application installation, creates the following folders that will be used by the CreateApplicationSample application to contain messages:</span></span>  
  
         <span data-ttu-id="bd592-143">C:\CreateApplicationSample\Out</span><span class="sxs-lookup"><span data-stu-id="bd592-143">C:\CreateApplicationSample\Out</span></span>  
  
         <span data-ttu-id="bd592-144">C:\CreateApplicationSample\In</span><span class="sxs-lookup"><span data-stu-id="bd592-144">C:\CreateApplicationSample\In</span></span>  
  
    -   <span data-ttu-id="bd592-145">在应用程序卸载期间，删除在安装期间创建的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd592-145">During application uninstallation, deletes the files and folders that were created during installation.</span></span> <span data-ttu-id="bd592-146">同时，还将从全局程序集缓存 (GAC) 卸载安装期间在 GAC 中安装的任意程序集，并将其操作记录到文件中。</span><span class="sxs-lookup"><span data-stu-id="bd592-146">Also uninstalls from the global assembly cache (GAC) any assemblies that were installed in the GAC during installation and logs its actions to a file.</span></span> <span data-ttu-id="bd592-147">若要从 GAC 卸载程序集，该脚本引用用户提供的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="bd592-147">To uninstall the assemblies from the GAC, it refers to the public key token provided by the user.</span></span>  
  
    -   <span data-ttu-id="bd592-148">在安装和卸载期间，将在以下位置创建日志文件：</span><span class="sxs-lookup"><span data-stu-id="bd592-148">During both installation and uninstallation, creates a log file in the following location:</span></span>  
  
         <span data-ttu-id="bd592-149">C:\ScriptLog.txt</span><span class="sxs-lookup"><span data-stu-id="bd592-149">C:\ScriptLog.txt</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="bd592-150">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="bd592-150">Where to Find This Sample</span></span>  
 <span data-ttu-id="bd592-151">你可以在下的以下文件夹中找到示例文件*\<示例路径 >*\Application 部署\\:</span><span class="sxs-lookup"><span data-stu-id="bd592-151">You can find the sample files in the following folders under *\<Samples Path>*\Application Deployment\\:</span></span>  
  
-   <span data-ttu-id="bd592-152">CreateApp（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-152">CreateApp (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-153">Build.bat</span><span class="sxs-lookup"><span data-stu-id="bd592-153">Build.bat</span></span>  
  
    -   <span data-ttu-id="bd592-154">CreateFullAndPartialMSI.bat</span><span class="sxs-lookup"><span data-stu-id="bd592-154">CreateFullAndPartialMSI.bat</span></span>  
  
    -   <span data-ttu-id="bd592-155">CreateNewAppFromMSI.bat</span><span class="sxs-lookup"><span data-stu-id="bd592-155">CreateNewAppFromMSI.bat</span></span>  
  
    -   <span data-ttu-id="bd592-156">RemoveApp.bat</span><span class="sxs-lookup"><span data-stu-id="bd592-156">RemoveApp.bat</span></span>  
  
-   <span data-ttu-id="bd592-157">CreateApp\Bindings（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-157">CreateApp\Bindings (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-158">CreateApplicationSampleBindings.xml</span><span class="sxs-lookup"><span data-stu-id="bd592-158">CreateApplicationSampleBindings.xml</span></span>  
  
-   <span data-ttu-id="bd592-159">CreateApp\Dlls（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-159">CreateApp\Dlls (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-160">Empty</span><span class="sxs-lookup"><span data-stu-id="bd592-160">Empty</span></span>  
  
-   <span data-ttu-id="bd592-161">CreateApp\ResourceSpecs（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-161">CreateApp\ResourceSpecs (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-162">ResourceSpecPartial.xml</span><span class="sxs-lookup"><span data-stu-id="bd592-162">ResourceSpecPartial.xml</span></span>  
  
    -   <span data-ttu-id="bd592-163">ResourceSpecComplete.xml</span><span class="sxs-lookup"><span data-stu-id="bd592-163">ResourceSpecComplete.xml</span></span>  
  
-   <span data-ttu-id="bd592-164">CreateApp\Scripts（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-164">CreateApp\Scripts (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-165">PreProcScript.bat</span><span class="sxs-lookup"><span data-stu-id="bd592-165">PreProcScript.bat</span></span>  
  
-   <span data-ttu-id="bd592-166">CreateApp\HelloApplicationDeployment（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-166">CreateApp\HelloApplicationDeployment (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-167">HelloApplicationDeployment.suo</span><span class="sxs-lookup"><span data-stu-id="bd592-167">HelloApplicationDeployment.suo</span></span>  
  
    -   <span data-ttu-id="bd592-168">HelloApplicationDeployment.sln</span><span class="sxs-lookup"><span data-stu-id="bd592-168">HelloApplicationDeployment.sln</span></span>  
  
-   <span data-ttu-id="bd592-169">CreateApp\HelloApplicationDeployment\Maps（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-169">CreateApp\HelloApplicationDeployment\Maps (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-170">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="bd592-170">POToInvoice.btm</span></span>  
  
    -   <span data-ttu-id="bd592-171">Maps.btproj</span><span class="sxs-lookup"><span data-stu-id="bd592-171">Maps.btproj</span></span>  
  
-   <span data-ttu-id="bd592-172">CreateApp\HelloApplicationDeployment\Orchestrations（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-172">CreateApp\HelloApplicationDeployment\Orchestrations (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-173">Orchestrations.btproj</span><span class="sxs-lookup"><span data-stu-id="bd592-173">Orchestrations.btproj</span></span>  
  
    -   <span data-ttu-id="bd592-174">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="bd592-174">HelloOrchestration.odx</span></span>  
  
-   <span data-ttu-id="bd592-175">CreateApp\HelloApplicationDeployment\Schemas（文件夹）</span><span class="sxs-lookup"><span data-stu-id="bd592-175">CreateApp\HelloApplicationDeployment\Schemas (Folder)</span></span>  
  
    -   <span data-ttu-id="bd592-176">Schemas.btproj</span><span class="sxs-lookup"><span data-stu-id="bd592-176">Schemas.btproj</span></span>  
  
    -   <span data-ttu-id="bd592-177">POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="bd592-177">POSchema.xsd</span></span>  
  
    -   <span data-ttu-id="bd592-178">InvoiceSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="bd592-178">InvoiceSchema.xsd</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="bd592-179">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="bd592-179">How to Use This Sample</span></span>  
 <span data-ttu-id="bd592-180">请按照以下步骤使用本示例。</span><span class="sxs-lookup"><span data-stu-id="bd592-180">Use the following procedure to use this sample.</span></span>  
  
### <a name="to-use-the-sample"></a><span data-ttu-id="bd592-181">使用本示例</span><span class="sxs-lookup"><span data-stu-id="bd592-181">To use the sample</span></span>  
  
1.  <span data-ttu-id="bd592-182">运行 Build.bat。</span><span class="sxs-lookup"><span data-stu-id="bd592-182">Run Build.bat.</span></span> <span data-ttu-id="bd592-183">此操作将生成一个密钥文件、在 HelloApplicationDeployment 文件夹下生成项目、对生成的 .dll 文件签名并将 .dll 文件放置到 Dlls 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bd592-183">This generates a key file, builds the projects under the folder HelloApplicationDeployment, signs the resulting .dll files, and places the.dll files in the Dlls folder.</span></span>  
  
2.  <span data-ttu-id="bd592-184">打开 PreProcScript.bat 文件，该文件位于 CreateApp\Scripts 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bd592-184">Open the PreProcScript.bat file, which is located in the CreateApp\Scripts folder.</span></span> <span data-ttu-id="bd592-185">在以下代码行中，删除 REM 并提供程序集的公钥标记：</span><span class="sxs-lookup"><span data-stu-id="bd592-185">In the following line of code, remove REM and provide the public key token for the assembly:</span></span>  
  
     <span data-ttu-id="bd592-186">**REM 设置 PublicKeyToken =**</span><span class="sxs-lookup"><span data-stu-id="bd592-186">**REM set PublicKeyToken=**</span></span>  
  
     <span data-ttu-id="bd592-187">例如：</span><span class="sxs-lookup"><span data-stu-id="bd592-187">Example:</span></span>  
  
     <span data-ttu-id="bd592-188">**设置 PublicKeyToken = 1234a5b6c1234567**</span><span class="sxs-lookup"><span data-stu-id="bd592-188">**set PublicKeyToken=1234a5b6c1234567**</span></span>  
  
3.  <span data-ttu-id="bd592-189">运行 CreateFullAndPartialMSI.bat。</span><span class="sxs-lookup"><span data-stu-id="bd592-189">Run CreateFullAndPartialMSI.bat.</span></span> <span data-ttu-id="bd592-190">此操作将创建两个应用程序 .msi 文件：CreateApplicationSample.msi 和 CreateApplicationSamplePartial.msi。</span><span class="sxs-lookup"><span data-stu-id="bd592-190">This creates two application .msi files, CreateApplicationSample.msi and CreateApplicationSamplePartial.msi.</span></span>  
  
4.  <span data-ttu-id="bd592-191">运行 CreateNewAppFromMSI.bat。</span><span class="sxs-lookup"><span data-stu-id="bd592-191">Run CreateNewAppFromMSI.bat.</span></span> <span data-ttu-id="bd592-192">此操作将 CreateApplicationSample 应用程序导入到 BizTalk 组并将其安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="bd592-192">This imports the CreateApplicationSample application into the BizTalk group and installs it on the local computer.</span></span>  
  
5.  <span data-ttu-id="bd592-193">检查 C:\ScriptLog.txt 中的脚本日志文件，验证该脚本是否已记录其安装操作。</span><span class="sxs-lookup"><span data-stu-id="bd592-193">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its installation actions.</span></span>  
  
6.  <span data-ttu-id="bd592-194">验证 CreateApplicationSample 应用程序是否显示在 BizTalk Server 管理控制台和“添加或删除程序”中。</span><span class="sxs-lookup"><span data-stu-id="bd592-194">Verify that the CreateApplicationSample application appears both in the BizTalk Server Administration console and Add or Remove Programs.</span></span>  
  
7.  <span data-ttu-id="bd592-195">运行 RemoveApp.bat。</span><span class="sxs-lookup"><span data-stu-id="bd592-195">Run RemoveApp.bat.</span></span> <span data-ttu-id="bd592-196">此操作将从 BizTalk 管理数据库中删除 CreateApplicationSample，并从本地计算机中进行卸载。</span><span class="sxs-lookup"><span data-stu-id="bd592-196">This deletes the CreateApplicationSample from the BizTalk Management database and uninstalls it from the local computer.</span></span>  
  
8.  <span data-ttu-id="bd592-197">检查 C:\ScriptLog.txt 中的脚本日志文件，验证该脚本是否已记录其卸载操作。</span><span class="sxs-lookup"><span data-stu-id="bd592-197">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its uninstallation actions.</span></span> <span data-ttu-id="bd592-198">这些操作应显示在先前在安装期间记录的安装操作之后。</span><span class="sxs-lookup"><span data-stu-id="bd592-198">They should appear after the installation actions logged earlier, during installation.</span></span>  
  
9. <span data-ttu-id="bd592-199">验证 CreateApplicationSample 应用程序是否不再显示在 BizTalk Server 管理控制台或“添加或删除程序”中。</span><span class="sxs-lookup"><span data-stu-id="bd592-199">Verify that the CreateApplicationSample application no longer appears in either the BizTalk Server Administration console or Add or Remove Programs.</span></span>  
  
10. <span data-ttu-id="bd592-200">验证是否已删除在安装期间创建的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bd592-200">Verify that the folders that were created during installation have been deleted.</span></span>  
  
11. <span data-ttu-id="bd592-201">验证是否已从 GAC 卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="bd592-201">Verify that the assemblies have been uninstalled from the GAC.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd592-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd592-202">See Also</span></span>  
 <span data-ttu-id="bd592-203">[应用程序部署 （BizTalk Server 示例文件夹中）](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="bd592-203">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="bd592-204">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="bd592-204">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)