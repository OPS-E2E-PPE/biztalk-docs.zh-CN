---
title: "导入绑定 Files1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- CLASSPATH environment variable
- importing binding files
- cleaning target computer
ms.assetid: b2a9b19b-2d3d-45ea-bd92-a2501791b86a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fca64580b692f01834b48085aa2d88085fb743
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a><span data-ttu-id="ee64f-102">导入绑定文件</span><span class="sxs-lookup"><span data-stu-id="ee64f-102">Importing Binding Files</span></span>
<span data-ttu-id="ee64f-103">在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入绑定文件之前，请验证以下各项：</span><span class="sxs-lookup"><span data-stu-id="ee64f-103">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="ee64f-104">CLASSPATH 指向 PeopleSoft 特定文件的特定位置。</span><span class="sxs-lookup"><span data-stu-id="ee64f-104">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="ee64f-105">验证这些文件的位置是否在新计算机上相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="ee64f-105">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="ee64f-106">响应的文件夹必须存在并且可在新计算机上完全相同，或编辑绑定文件。</span><span class="sxs-lookup"><span data-stu-id="ee64f-106">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="ee64f-107">如果在配置中存在 PeopleSoft Enterprise 系统密码，则在绑定文件中另存为 *****。</span><span class="sxs-lookup"><span data-stu-id="ee64f-107">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="ee64f-108">有关详细信息，请参阅[部署限制](../core/deployment-limitations3.md)。</span><span class="sxs-lookup"><span data-stu-id="ee64f-108">For more information, see [Deployment Limitations](../core/deployment-limitations3.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee64f-109">部署会覆盖接收位置配置。</span><span class="sxs-lookup"><span data-stu-id="ee64f-109">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="ee64f-110">如果在目标计算机上部署绑定文件和程序集，则发送端口和接收位置将替换为所导入的 XML 绑定文件中的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="ee64f-110">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="ee64f-111">有关导入绑定文件的分步指导信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的主题“如何将绑定导入到 BizTalk 组”。</span><span class="sxs-lookup"><span data-stu-id="ee64f-111">For step-by-step directions about importing binding files, see the topic "How to Import Bindings into a BizTalk Group" in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="cleaning-the-target-computer"></a><span data-ttu-id="ee64f-112">清理目标计算机</span><span class="sxs-lookup"><span data-stu-id="ee64f-112">Cleaning the Target Computer</span></span>  
 <span data-ttu-id="ee64f-113">按照以下步骤执行操作可清理目标计算机，从而部署新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ee64f-113">Follow these steps to clean the target computer for deploying the new application.</span></span>  
  
#### <a name="to-clean-the-target-computer"></a><span data-ttu-id="ee64f-114">若要清除目标计算机中的</span><span class="sxs-lookup"><span data-stu-id="ee64f-114">To clean the target computer</span></span>  
  
-   <span data-ttu-id="ee64f-115">删除发送端口和接收位置绑定到业务流程。</span><span class="sxs-lookup"><span data-stu-id="ee64f-115">Remove send ports and receive locations bound to the orchestration.</span></span>  
  
     <span data-ttu-id="ee64f-116">如果没有在目标计算机上安装 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，则可通过运行下面的脚本删除端口：</span><span class="sxs-lookup"><span data-stu-id="ee64f-116">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
     <span data-ttu-id="ee64f-117">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 发送 Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="ee64f-117">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
     <span data-ttu-id="ee64f-118">**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove 接收 Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="ee64f-118">**\<Microsoft BizTalk Server>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
     <span data-ttu-id="ee64f-119">例如，在命令提示符下运行：</span><span class="sxs-lookup"><span data-stu-id="ee64f-119">For example, at a command prompt, run:</span></span>  
  
     <span data-ttu-id="ee64f-120">**cscript RemoveSendPort.vbs\<发送端口名称 >**</span><span class="sxs-lookup"><span data-stu-id="ee64f-120">**cscript RemoveSendPort.vbs \<Send port name>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee64f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee64f-121">See Also</span></span>  
 [<span data-ttu-id="ee64f-122">部署端口和程序集</span><span class="sxs-lookup"><span data-stu-id="ee64f-122">Deploying Ports and Assemblies</span></span>](../core/deploying-ports-and-assemblies5.md)