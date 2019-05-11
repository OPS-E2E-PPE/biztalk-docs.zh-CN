---
title: 如何卸载 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], uninstalling
- applications, uninstalling
- uninstalling, applications
- undeploying, uninstalling
ms.assetid: ab721c6e-194e-4b8a-bfd1-d0139d284373
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec0383549edc37d1767e69d9fcb6ac571a56ae04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333784"
---
# <a name="how-to-uninstall-a-biztalk-application"></a><span data-ttu-id="70cac-102">如何卸载 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="70cac-102">How to Uninstall a BizTalk Application</span></span>
<span data-ttu-id="70cac-103">本主题介绍如何使用添加或删除程序控制面板或 BTSTask 命令行工具卸载 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="70cac-103">This topic describes how to use the Add or Remove Programs control panel or the BTSTask command-line tool to uninstall a BizTalk application.</span></span> <span data-ttu-id="70cac-104">这些是用于卸载应用程序的唯一受支持的方法。</span><span class="sxs-lookup"><span data-stu-id="70cac-104">These are the only supported methods for uninstalling an application.</span></span> <span data-ttu-id="70cac-105">如果你安装此应用程序的多个.msi 文件，例如若要更新应用程序中，双击该.msi 文件或使用 msiexec 可能无法完全卸载该应用程序，因此不支持的卸载方法。</span><span class="sxs-lookup"><span data-stu-id="70cac-105">If you installed multiple .msi files for this application, for example to update the application, double-clicking the .msi file or using msiexec may not completely uninstall the application and are therefore not supported uninstallation methods.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="70cac-106">卸载 BizTalk 应用程序在运行时可导致应用程序中出现错误。</span><span class="sxs-lookup"><span data-stu-id="70cac-106">Uninstalling a BizTalk application while it is running can cause errors in the application.</span></span> <span data-ttu-id="70cac-107">若要避免此问题，最佳的做法是，我们建议你验证存在先决条件，没有正在运行的服务实例应用程序，如中所述[如何搜索所有服务实例](../core/how-to-search-for-all-service-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="70cac-107">In order to avoid this problem, as a best practice we recommend that you verify there are no running service instances for the application, as described in [How to Search for All Service Instances](../core/how-to-search-for-all-service-instances.md).</span></span> <span data-ttu-id="70cac-108">如果有必要，您可以停止应用程序通过使用完全停止选项来完全停止所有正在运行的实例，如中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="70cac-108">If necessary, you can stop the application by using the Full Stop option to completely stop all running instances, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span> <span data-ttu-id="70cac-109">请注意时执行此操作时，将无法完成进程内消息数。</span><span class="sxs-lookup"><span data-stu-id="70cac-109">Be aware that when you do this, in-process messages will not complete.</span></span>  
  
 <span data-ttu-id="70cac-110">预处理或后处理脚本应包含在应用程序.msi 文件中删除所有的文件和应用程序时将其卸载相关的设置。</span><span class="sxs-lookup"><span data-stu-id="70cac-110">A pre- or post-processing script should be included in the application .msi file to remove all of the files and settings associated with the application when it is uninstalled.</span></span> <span data-ttu-id="70cac-111">如果尚未包括预处理或后处理脚本，此主题中的过程将从本地文件系统，但存在以下例外删除应用程序的文件和设置。</span><span class="sxs-lookup"><span data-stu-id="70cac-111">If a pre- or post-processing script has not been included, the procedures in this topic will remove the application's files and settings from the local file system, with the following exceptions.</span></span>  
  
- <span data-ttu-id="70cac-112">如果应用程序中包括虚拟目录，虚拟目录和其文件被删除，除非应用程序安装后将文件添加到虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="70cac-112">If the application includes a virtual directory, the virtual directory and its files are deleted, unless files were added to the virtual directory after the application was installed.</span></span> <span data-ttu-id="70cac-113">在这种情况下，虚拟目录以及添加的文件不会删除。</span><span class="sxs-lookup"><span data-stu-id="70cac-113">In this case, the virtual directory and the added files are not deleted.</span></span> <span data-ttu-id="70cac-114">如果你想要删除的虚拟目录以及添加的文件，您必须执行显式删除。</span><span class="sxs-lookup"><span data-stu-id="70cac-114">If you want to delete the virtual directory and the added files, you must do so explicitly.</span></span>  
  
- <span data-ttu-id="70cac-115">预处理和后处理脚本将被删除，但不是会删除在安装或卸载期间由脚本添加任何文件，也不会撤消脚本执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="70cac-115">Pre- and post-processing scripts are deleted, but any files added by the scripts during installation or uninstallation are not deleted, nor are any actions taken by the scripts undone.</span></span> <span data-ttu-id="70cac-116">如果你想要删除脚本所添加的文件或撤消其操作，您必须执行显式删除。</span><span class="sxs-lookup"><span data-stu-id="70cac-116">If you want to delete files added by scripts or undo their actions, you must do so explicitly.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="70cac-117">仅 pre-或后处理脚本时导入应用程序在其部署属性中指定了目标位置将在卸载期间运行。</span><span class="sxs-lookup"><span data-stu-id="70cac-117">Only pre-or post-processing scripts that have a destination location specified in its deployment properties when the application is imported will run during uninstallation.</span></span> <span data-ttu-id="70cac-118">有关详细信息，请参阅[How to Add 的预处理或后处理脚本保存到应用程序](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="70cac-118">For more information, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
- <span data-ttu-id="70cac-119">卸载 BizTalk 应用程序时，永远不会删除证书。</span><span class="sxs-lookup"><span data-stu-id="70cac-119">Certificates are never deleted when you uninstall a BizTalk application.</span></span> <span data-ttu-id="70cac-120">如果你想要删除证书，你必须执行显式删除。</span><span class="sxs-lookup"><span data-stu-id="70cac-120">If you want to delete a certificate, you must do so explicitly.</span></span> <span data-ttu-id="70cac-121">此外，不会从 Windows 注册表删除组件和 BizTalk 程序集不会从全局程序集缓存 (GAC) 中删除。</span><span class="sxs-lookup"><span data-stu-id="70cac-121">In addition, components are not removed from the Windows Registry and BizTalk assemblies are not removed from the global assembly cache (GAC).</span></span> <span data-ttu-id="70cac-122">如果你想要将其删除，你必须执行显式删除。</span><span class="sxs-lookup"><span data-stu-id="70cac-122">If you want to remove them, you must do so explicitly.</span></span> <span data-ttu-id="70cac-123">有关详细信息，请参阅[如何删除其他文件和 BizTalk 应用程序设置](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="70cac-123">For more information, see [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="70cac-124">如果在完成之前取消卸载操作，BizTalk Server 将回滚卸载，除了由预处理或后处理脚本在执行操作之前执行任何操作已取消。</span><span class="sxs-lookup"><span data-stu-id="70cac-124">If you cancel the uninstallation operation before it completes, BizTalk Server will roll back the uninstallation, except for any actions that were taken by pre- or post-processing scripts before the operation was canceled.</span></span> <span data-ttu-id="70cac-125">若要开始卸载之前，请还原到其状态的应用程序，请双击该.msi 文件并重新安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="70cac-125">To restore the application to its state before you started the uninstallation, double-click the .msi file and reinstall the application.</span></span> <span data-ttu-id="70cac-126">如果为此应用程序安装了多个.msi 文件，应该双击每个.msi 文件以重新安装该应用程序最初安装的.msi 文件的顺序。</span><span class="sxs-lookup"><span data-stu-id="70cac-126">If multiple .msi files have been installed for this application, you should double-click each .msi file to reinstall the application in the order in which the .msi files were originally installed.</span></span>  
  
  <span data-ttu-id="70cac-127">有关后续处理脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="70cac-127">For more information about post-processing scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70cac-128">若要完全取消部署 BizTalk 应用程序，您还必须删除它从 BizTalk 组中，如中所述[如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)。</span><span class="sxs-lookup"><span data-stu-id="70cac-128">To completely undeploy a BizTalk application, you must also delete it from the BizTalk group, as described in [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="70cac-129">先决条件</span><span class="sxs-lookup"><span data-stu-id="70cac-129">Prerequisites</span></span>  
 <span data-ttu-id="70cac-130">若要执行本主题中的过程，必须具有相应权限的身份登录。</span><span class="sxs-lookup"><span data-stu-id="70cac-130">To perform the procedures in this topic, you must be logged on with appropriate permissions.</span></span> <span data-ttu-id="70cac-131">有关详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="70cac-131">For more information, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-uninstall-a-biztalk-application"></a><span data-ttu-id="70cac-132">若要卸载 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="70cac-132">To uninstall a BizTalk application</span></span>  
  
#### <a name="using-uninstall-or-change-a-program"></a><span data-ttu-id="70cac-133">使用卸载或更改程序</span><span class="sxs-lookup"><span data-stu-id="70cac-133">Using Uninstall or change a program</span></span>  
  
1.  <span data-ttu-id="70cac-134">在运行该应用程序的计算机，单击**启动**，单击**控制面板**，然后双击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="70cac-134">On the computer running the application, click **Start**, click **Control Panel**, and then double-click  **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="70cac-135">上**卸载或更改程序**页上，右键单击 BizTalk 应用程序，以删除，然后单击**卸载**。</span><span class="sxs-lookup"><span data-stu-id="70cac-135">On **Uninstall or change a program** page, right-click the BizTalk application to remove, and then click **Uninstall**.</span></span>  
  
     <span data-ttu-id="70cac-136">Windows 安装程序中删除指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="70cac-136">Windows Installer removes the specified application.</span></span>  
  
3.  <span data-ttu-id="70cac-137">如果多台计算机上运行该应用程序，重复的每台计算机上的这些步骤。</span><span class="sxs-lookup"><span data-stu-id="70cac-137">If the application is running on multiple computers, repeat these steps on each computer.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="70cac-138">使用命令行</span><span class="sxs-lookup"><span data-stu-id="70cac-138">Using the command line</span></span>  
  
1. <span data-ttu-id="70cac-139">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="70cac-139">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="70cac-140">键入以下命令，替换适当的值下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="70cac-140">Type the following command, substituting the appropriate value, as described in the following table:</span></span>  
  
    <span data-ttu-id="70cac-141">**BTSTask UninstallApp** [**/ApplicationName:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="70cac-141">**BTSTask UninstallApp** [**/ApplicationName:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="70cac-142">例如：</span><span class="sxs-lookup"><span data-stu-id="70cac-142">Example:</span></span>  
  
    <span data-ttu-id="70cac-143">**BTSTask UninstallApp /ApplicationName:MyApplication**</span><span class="sxs-lookup"><span data-stu-id="70cac-143">**BTSTask UninstallApp /ApplicationName:MyApplication**</span></span>  
  
   |<span data-ttu-id="70cac-144">参数</span><span class="sxs-lookup"><span data-stu-id="70cac-144">Parameter</span></span>|<span data-ttu-id="70cac-145">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="70cac-145">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="70cac-146">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="70cac-146">**/ApplicationName**</span></span>|<span data-ttu-id="70cac-147">若要卸载的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="70cac-147">Name of the BizTalk application to uninstall.</span></span> <span data-ttu-id="70cac-148">如果名称包含空格，则必须将其括在双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="70cac-148">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70cac-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="70cac-149">See Also</span></span>  
 <span data-ttu-id="70cac-150">[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="70cac-150">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="70cac-151">UninstallApp 命令</span><span class="sxs-lookup"><span data-stu-id="70cac-151">UninstallApp Command</span></span>](../core/uninstallapp-command.md)