---
title: 管理预处理和后处理脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 107ada12-fef2-4b56-8ff8-228c13761104
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b39deb7d053ec21677e519852184550d6f3c793d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328048"
---
# <a name="manage-pre--and-post-processing-scripts"></a><span data-ttu-id="dca0b-102">管理预处理和后处理脚本</span><span class="sxs-lookup"><span data-stu-id="dca0b-102">Manage Pre- and Post-processing Scripts</span></span>

## <a name="overview"></a><span data-ttu-id="dca0b-103">概述</span><span class="sxs-lookup"><span data-stu-id="dca0b-103">Overview</span></span>
<span data-ttu-id="dca0b-104">本部分说明了使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理预处理脚本和后处理脚本。</span><span class="sxs-lookup"><span data-stu-id="dca0b-104">This section provides instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage pre- and post-processing scripts.</span></span> <span data-ttu-id="dca0b-105">您可以创建你想要导入、 安装或卸载 BizTalk 应用程序时运行的脚本 （删除），并将脚本添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="dca0b-105">You can create a script that you want to have run when a BizTalk application is imported, installed, or uninstalled (removed), and then add the script to the application.</span></span> <span data-ttu-id="dca0b-106">当您添加脚本时，指定是否在运行之前导入、 安装和卸载之后，预处理脚本或后处理脚本，运行导入或安装之后并在卸载之前。</span><span class="sxs-lookup"><span data-stu-id="dca0b-106">When you add a script, you specify whether it is a pre-preprocessing script, which runs before import, installation and after uninstallation, or a post-processing script, which runs after import or installation, and before uninstallation.</span></span>  
  
 <span data-ttu-id="dca0b-107">如果导出应用程序时选择的脚本，该脚本将包含在应用程序的.msi 文件。</span><span class="sxs-lookup"><span data-stu-id="dca0b-107">If you select the script when exporting the application, the script is included in the .msi file for the application.</span></span> <span data-ttu-id="dca0b-108">当你安装、 卸载或导入应用程序时，该脚本自动运行，具体取决于如何所编写的脚本。</span><span class="sxs-lookup"><span data-stu-id="dca0b-108">When you install, uninstall, or import the application, the script automatically runs, depending on how you have written the script.</span></span> <span data-ttu-id="dca0b-109">有关创建和使用脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="dca0b-109">For more information about creating and using scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dca0b-110">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="dca0b-110">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="dca0b-111">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="dca0b-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="dca0b-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dca0b-112">Next steps</span></span> 
  
-   [<span data-ttu-id="dca0b-113">向应用程序添加预处理脚本和后期处理脚本</span><span class="sxs-lookup"><span data-stu-id="dca0b-113">Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="dca0b-114">更改预处理脚本或后期处理脚本的目标位置</span><span class="sxs-lookup"><span data-stu-id="dca0b-114">Change the Destination Location of a Pre- or Post-processing Script</span></span>](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="dca0b-115">从应用程序中删除预处理脚本或后期处理脚本</span><span class="sxs-lookup"><span data-stu-id="dca0b-115">Remove a Pre- or Post-processing Script from an Application</span></span>](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)