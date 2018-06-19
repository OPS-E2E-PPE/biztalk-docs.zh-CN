---
title: 管理前期和后期处理脚本 |Microsoft 文档
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
ms.openlocfilehash: 18926a0c51e5ab5f65b32373d20b2931ccaa627d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262469"
---
# <a name="manage-pre--and-post-processing-scripts"></a><span data-ttu-id="a088f-102">管理前期和后期处理脚本</span><span class="sxs-lookup"><span data-stu-id="a088f-102">Manage Pre- and Post-processing Scripts</span></span>

## <a name="overview"></a><span data-ttu-id="a088f-103">概述</span><span class="sxs-lookup"><span data-stu-id="a088f-103">Overview</span></span>
<span data-ttu-id="a088f-104">本部分介绍如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理预处理脚本和后处理脚本。</span><span class="sxs-lookup"><span data-stu-id="a088f-104">This section provides instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage pre- and post-processing scripts.</span></span> <span data-ttu-id="a088f-105">您可以创建要在导入、安装或卸载（删除）BizTalk 应用程序时运行的脚本，并随后将其添加到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="a088f-105">You can create a script that you want to have run when a BizTalk application is imported, installed, or uninstalled (removed), and then add the script to the application.</span></span> <span data-ttu-id="a088f-106">添加脚本时，您要指定它是预处理脚本（在导入、安装前和卸载后运行）还是后处理脚本（在导入或安装后及卸载前运行）。</span><span class="sxs-lookup"><span data-stu-id="a088f-106">When you add a script, you specify whether it is a pre-preprocessing script, which runs before import, installation and after uninstallation, or a post-processing script, which runs after import or installation, and before uninstallation.</span></span>  
  
 <span data-ttu-id="a088f-107">如果在导出应用程序时选择该脚本，则该脚本将被包含在应用程序的 .msi 文件中。</span><span class="sxs-lookup"><span data-stu-id="a088f-107">If you select the script when exporting the application, the script is included in the .msi file for the application.</span></span> <span data-ttu-id="a088f-108">安装、卸载或导入应用程序时，该脚本将自动运行，具体运行情况取决于您所编写的脚本内容。</span><span class="sxs-lookup"><span data-stu-id="a088f-108">When you install, uninstall, or import the application, the script automatically runs, depending on how you have written the script.</span></span> <span data-ttu-id="a088f-109">有关创建和使用脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="a088f-109">For more information about creating and using scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a088f-110">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="a088f-110">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="a088f-111">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="a088f-111">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a088f-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a088f-112">Next steps</span></span> 
  
-   [<span data-ttu-id="a088f-113">将预或后续处理脚本添加到应用程序</span><span class="sxs-lookup"><span data-stu-id="a088f-113">Add a Pre- or Post-processing Script to an Application</span></span>](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)  
  
-   [<span data-ttu-id="a088f-114">更改预或后续处理脚本的目标位置</span><span class="sxs-lookup"><span data-stu-id="a088f-114">Change the Destination Location of a Pre- or Post-processing Script</span></span>](../core/how-to-change-the-destination-location-of-a-pre-or-post-processing-script.md)  
  
-   [<span data-ttu-id="a088f-115">从应用程序中删除预或后续处理脚本</span><span class="sxs-lookup"><span data-stu-id="a088f-115">Remove a Pre- or Post-processing Script from an Application</span></span>](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)