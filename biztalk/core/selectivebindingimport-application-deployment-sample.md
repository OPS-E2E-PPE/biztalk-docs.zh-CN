---
title: SelectiveBindingImport （应用程序部署示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding files, importing
- examples, applications
- binding files, examples
- examples, importing
- applications, binding files
- applications, examples
- applications, importing
- deploying, scripts
- examples, binding files
ms.assetid: 963bfc80-8cc4-4d90-96b4-e85ae04405cf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e6a2aa02decf1e4ed9c4a9838077be0c3b97b2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974827"
---
# <a name="selectivebindingimport-application-deployment-sample"></a><span data-ttu-id="1e868-102">SelectiveBindingImport（应用程序部署示例）</span><span class="sxs-lookup"><span data-stu-id="1e868-102">SelectiveBindingImport (Application Deployment Sample)</span></span>
<span data-ttu-id="1e868-103">本主题介绍如何使用 SelectiveBindingImport 示例。</span><span class="sxs-lookup"><span data-stu-id="1e868-103">This topic explains how to use the SelectiveBindingImport sample.</span></span> <span data-ttu-id="1e868-104">将某应用程序导入不同的目标环境时，可以使用本示例脚本将不同的绑定应用到此应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e868-104">You can use this sample script to apply different bindings to an application when you import the application into different destination environments.</span></span> <span data-ttu-id="1e868-105">如要从存储在网络共享位置上的绑定文件导入绑定，则可以使用此方法。</span><span class="sxs-lookup"><span data-stu-id="1e868-105">You can use this approach when you want to import the bindings from binding files that are stored on a network share.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e868-106">如果不需要在应用程序导入期间自动从网络共享位置导入绑定文件，则可以将为其指定了不同目标环境的各绑定文件添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e868-106">If you do not need to automatically import binding files from a network share during application import, you can add to the application different binding files that have different destination environments specified.</span></span> <span data-ttu-id="1e868-107">导入应用程序时，可以指定相应环境，然后用于此环境的绑定文件将自动加以应用。</span><span class="sxs-lookup"><span data-stu-id="1e868-107">When you import the application, you can specify the environment, and the bindings for that environment will be applied automatically.</span></span> <span data-ttu-id="1e868-108">有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-108">For more information, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
 <span data-ttu-id="1e868-109">通常，BizTalk 应用程序会从开发环境依次转移到测试环境、过渡环境和生产环境。</span><span class="sxs-lookup"><span data-stu-id="1e868-109">BizTalk applications are typically moved from development to testing to staging and then to production environments.</span></span> <span data-ttu-id="1e868-110">在不同环境下使用的绑定通常也不同。</span><span class="sxs-lookup"><span data-stu-id="1e868-110">The bindings used in different environments are typically different.</span></span> <span data-ttu-id="1e868-111">使用本示例，可以按如下方式针对不同环境应用绑定：</span><span class="sxs-lookup"><span data-stu-id="1e868-111">Using this sample, you can apply bindings for different environments as follows:</span></span>  
  
1.  <span data-ttu-id="1e868-112">将所有要使用的绑定文件放在网络共享位置中。</span><span class="sxs-lookup"><span data-stu-id="1e868-112">Placing all the binding files that you want to use on a network share.</span></span>  
  
2.  <span data-ttu-id="1e868-113">将后续处理脚本添加到应用程序，此脚本将在应用程序导入期间从此位置导入适于特定目标环境的相应绑定文件。</span><span class="sxs-lookup"><span data-stu-id="1e868-113">Adding a post-processing script to the application that will import from this location the correct binding file for the particular destination environment during application import.</span></span> <span data-ttu-id="1e868-114">此脚本通过读取您在本地计算机上设置的名为 %ENVIRONMENT% 的环境变量来检测环境。</span><span class="sxs-lookup"><span data-stu-id="1e868-114">The script detects the environment by reading an environment variable named %ENVIRONMENT% that you set on the local computer,</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1e868-115">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="1e868-115">What This Sample Does</span></span>  
 <span data-ttu-id="1e868-116">本示例演示如何使用 BizTalk 应用程序 .msi 文件中包含的后续处理脚本选择性地从网络共享位置导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="1e868-116">This sample illustrates how to selectively import binding files from a network share by using a post-processing script contained in a BizTalk application .msi file.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1e868-117">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="1e868-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="1e868-118">你可以查找下面的示例文件夹和文件下的*\<示例路径\>* \Application Deployment\SelectiveBindingImport:</span><span class="sxs-lookup"><span data-stu-id="1e868-118">You can find the following sample folders and files under *\<Samples Path\>* \Application Deployment\SelectiveBindingImport:</span></span>  
  
-   <span data-ttu-id="1e868-119">Develop（文件夹）</span><span class="sxs-lookup"><span data-stu-id="1e868-119">Develop (Folder)</span></span>  
  
    -   <span data-ttu-id="1e868-120">Dev.xml</span><span class="sxs-lookup"><span data-stu-id="1e868-120">Dev.xml</span></span>  
  
-   <span data-ttu-id="1e868-121">Production（文件夹）</span><span class="sxs-lookup"><span data-stu-id="1e868-121">Production (Folder)</span></span>  
  
    -   <span data-ttu-id="1e868-122">Production.xml</span><span class="sxs-lookup"><span data-stu-id="1e868-122">Production.xml</span></span>  
  
-   <span data-ttu-id="1e868-123">Staging（文件夹）</span><span class="sxs-lookup"><span data-stu-id="1e868-123">Staging (Folder)</span></span>  
  
    -   <span data-ttu-id="1e868-124">Staging.xml</span><span class="sxs-lookup"><span data-stu-id="1e868-124">Staging.xml</span></span>  
  
-   <span data-ttu-id="1e868-125">Test（文件夹）</span><span class="sxs-lookup"><span data-stu-id="1e868-125">Test (Folder)</span></span>  
  
    -   <span data-ttu-id="1e868-126">Test.xml</span><span class="sxs-lookup"><span data-stu-id="1e868-126">Test.xml</span></span>  
  
-   <span data-ttu-id="1e868-127">SelectiveBindings.bat</span><span class="sxs-lookup"><span data-stu-id="1e868-127">SelectiveBindings.bat</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="1e868-128">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="1e868-128">How to Use This Sample</span></span>  
 <span data-ttu-id="1e868-129">请使用以下过程运行本示例。</span><span class="sxs-lookup"><span data-stu-id="1e868-129">Use the following procedures to run this sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="1e868-130">运行示例</span><span class="sxs-lookup"><span data-stu-id="1e868-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="1e868-131">运行**从 Build.Bat *\<示例路径\>* \Application Deployment\CreateApp**目录。</span><span class="sxs-lookup"><span data-stu-id="1e868-131">Run **Build.Bat from the *\<Samples Path\>* \Application Deployment\CreateApp** directory.</span></span> <span data-ttu-id="1e868-132">这将创建中的以下文件*\<示例路径\>* \Application Deployment\CreateApp\Dlls 文件夹： Schemas.dll、 Maps.dll 和 Orchestrations.dll。</span><span class="sxs-lookup"><span data-stu-id="1e868-132">This creates the following files in the *\<Samples Path\>* \Application Deployment\CreateApp\Dlls folder: Schemas.dll, Maps.dll, and Orchestrations.dll.</span></span>  
  
2.  <span data-ttu-id="1e868-133">**创建应用程序。**</span><span class="sxs-lookup"><span data-stu-id="1e868-133">**Create the application.**</span></span> <span data-ttu-id="1e868-134">在 BizTalk Server 管理控制台中，创建应用程序，如中所述[如何创建应用程序](../core/how-to-create-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-134">In the BizTalk Server Administration console, create an application, as described in [How to Create an Application](../core/how-to-create-an-application.md).</span></span>  
  
3.  <span data-ttu-id="1e868-135">**将添加到第一步中创建的.dll 文件的应用程序。**</span><span class="sxs-lookup"><span data-stu-id="1e868-135">**Add to the application the .dll files created in the first step.**</span></span> <span data-ttu-id="1e868-136">有关说明，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-136">For instructions, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
4.  <span data-ttu-id="1e868-137">**创建环境变量，如下所示：**</span><span class="sxs-lookup"><span data-stu-id="1e868-137">**Create the ENVIRONMENT variable, as follows:**</span></span>  
  
    1.  <span data-ttu-id="1e868-138">在开始菜单中，右键单击**我的电脑**单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="1e868-138">On the Start menu, right-click **My Computer** and click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="1e868-139">上**高级**选项卡上，单击**环境变量**。</span><span class="sxs-lookup"><span data-stu-id="1e868-139">On the **Advanced** tab, click **Environment Variables**.</span></span>  
  
    3.  <span data-ttu-id="1e868-140">在**用户变量**部分中，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="1e868-140">In the **User variables** section, click **New**.</span></span>  
  
    4.  <span data-ttu-id="1e868-141">在**变量名称**，类型**环境**。</span><span class="sxs-lookup"><span data-stu-id="1e868-141">In **Variable name**, type **ENVIRONMENT**.</span></span>  
  
    5.  <span data-ttu-id="1e868-142">在**变量值**，类型上的环境的以下值：**开发**，**生产**，**过渡**，或**测试**。</span><span class="sxs-lookup"><span data-stu-id="1e868-142">In **Variable value**, type on of the following values for the environment: **Develop**, **Production**, **Staging**, or **Test**.</span></span> <span data-ttu-id="1e868-143">这些值是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="1e868-143">These values are case sensitive.</span></span>  
  
5.  <span data-ttu-id="1e868-144">单击**确定**三次。</span><span class="sxs-lookup"><span data-stu-id="1e868-144">Click **OK** three times.</span></span>  
  
6.  <span data-ttu-id="1e868-145">**将绑定文件复制到你文件系统上的位置。**</span><span class="sxs-lookup"><span data-stu-id="1e868-145">**Copy the binding files to a location on your file system.**</span></span> <span data-ttu-id="1e868-146">将 Develop、Test、Staging 和 Production 文件夹中的 .xml 绑定文件复制到您文件系统中的某个位置。</span><span class="sxs-lookup"><span data-stu-id="1e868-146">Copy the binding .xml files from the Develop, Test, Staging, and Production folders to a location on your file system.</span></span>  
  
7.  <span data-ttu-id="1e868-147">**编辑后续处理的脚本。**</span><span class="sxs-lookup"><span data-stu-id="1e868-147">**Edit the post-processing script.**</span></span> <span data-ttu-id="1e868-148">编辑 SelectiveBindings.bat，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e868-148">Edit SelectiveBindings.bat as follows:</span></span>  
  
    1.  <span data-ttu-id="1e868-149">**指定的绑定文件位置。**</span><span class="sxs-lookup"><span data-stu-id="1e868-149">**Specify the binding file location.**</span></span> <span data-ttu-id="1e868-150">在包含 BINDINGS_LOC 的行，删除 REM，然后提供指向您已将绑定文件复制到的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="1e868-150">In the line containing BINDINGS_LOC, delete REM, and provide the path to the location where you copied the binding files.</span></span>  
  
         <span data-ttu-id="1e868-151">例如：</span><span class="sxs-lookup"><span data-stu-id="1e868-151">Example:</span></span>  
  
         <span data-ttu-id="1e868-152">BINDINGS_LOC=C:\MyBindings</span><span class="sxs-lookup"><span data-stu-id="1e868-152">BINDINGS_LOC=C:\MyBindings</span></span>  
  
    2.  <span data-ttu-id="1e868-153">**指定应用程序名称。**</span><span class="sxs-lookup"><span data-stu-id="1e868-153">**Specify the application name.**</span></span> <span data-ttu-id="1e868-154">在包含 APPLICATION_NAME 的行，删除 REM，然后提供要将绑定文件导入其中的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="1e868-154">In the line containing APPLICATION_NAME, delete REM, and provide the name of the application into which you want to import the bindings.</span></span>  
  
         <span data-ttu-id="1e868-155">例如：</span><span class="sxs-lookup"><span data-stu-id="1e868-155">Example:</span></span>  
  
         <span data-ttu-id="1e868-156">APPLICATION_Name=SelectiveBindingImport</span><span class="sxs-lookup"><span data-stu-id="1e868-156">APPLICATION_Name=SelectiveBindingImport</span></span>  
  
8.  <span data-ttu-id="1e868-157">**将脚本添加到该应用程序进行后续处理脚本。**</span><span class="sxs-lookup"><span data-stu-id="1e868-157">**Add the script to the application as a post-processing script.**</span></span> <span data-ttu-id="1e868-158">有关说明，请参阅[如何添加预或对应用程序的后续处理脚本](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-158">For instructions, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
9. <span data-ttu-id="1e868-159">**导出应用程序。**</span><span class="sxs-lookup"><span data-stu-id="1e868-159">**Export the application.**</span></span> <span data-ttu-id="1e868-160">有关说明，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-160">For instructions, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
10. <span data-ttu-id="1e868-161">**删除应用程序。**</span><span class="sxs-lookup"><span data-stu-id="1e868-161">**Delete the application.**</span></span> <span data-ttu-id="1e868-162">有关说明，请参阅[如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-162">For instructions, see [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
11. <span data-ttu-id="1e868-163">**导入应用程序。**</span><span class="sxs-lookup"><span data-stu-id="1e868-163">**Import the application.**</span></span> <span data-ttu-id="1e868-164">有关说明，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-164">For instructions, see [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="1e868-165">无需指定目标环境。</span><span class="sxs-lookup"><span data-stu-id="1e868-165">You do not need to specify a destination environment.</span></span>  
  
12. <span data-ttu-id="1e868-166">**验证已应用正确的绑定文件。**</span><span class="sxs-lookup"><span data-stu-id="1e868-166">**Verify that the right binding file was applied.**</span></span> <span data-ttu-id="1e868-167">可通过检查接收位置的说明字段来执行此操作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e868-167">You can do this by checking the description field of the receive locations, as follows:</span></span>  
  
    1.  <span data-ttu-id="1e868-168">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="1e868-168">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    2.  <span data-ttu-id="1e868-169">在控制台树中，展开相应的 BizTalk 组、BizTalk 应用程序和 Receive Locations 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e868-169">In the console tree, expand the BizTalk group, the BizTalk application, and the Receive Locations folder.</span></span>  
  
    3.  <span data-ttu-id="1e868-170">在右窗格中，查看接收位置的说明。</span><span class="sxs-lookup"><span data-stu-id="1e868-170">In the right pane, view the description of the receive locations.</span></span>  
  
13. <span data-ttu-id="1e868-171">**安装应用程序。**</span><span class="sxs-lookup"><span data-stu-id="1e868-171">**Install the application.**</span></span> <span data-ttu-id="1e868-172">有关说明，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1e868-172">For instructions, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e868-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e868-173">See Also</span></span>  
 <span data-ttu-id="1e868-174">[应用程序部署 （BizTalk Server 示例文件夹中）](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="1e868-174">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="1e868-175">部署 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="1e868-175">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)