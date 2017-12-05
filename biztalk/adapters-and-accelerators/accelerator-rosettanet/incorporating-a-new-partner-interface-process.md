---
title: "合并新的合作伙伴接口进程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, PIP schemas
- PIP schemas
- PIP schemas, deploying
- PIP schemas, downloading
- creating, PIP schemas
- PIP schemas, creating
ms.assetid: 6a5fcbcb-c6aa-40c0-bcca-dd0c391e7f42
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bf80c8bb577f4ddc8aec3282805714a830c7d23
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="incorporating-a-new-partner-interface-process"></a><span data-ttu-id="292ae-102">合并新的合作伙伴接口进程</span><span class="sxs-lookup"><span data-stu-id="292ae-102">Incorporating a New Partner Interface Process</span></span>
<span data-ttu-id="292ae-103">你可以在 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 程序集中并入新的 RosettaNet 合作伙伴接口流程 (PIP) 架构。</span><span class="sxs-lookup"><span data-stu-id="292ae-103">You can incorporate a new RosettaNet Partner Interface Process (PIP) schema in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] assemblies.</span></span> <span data-ttu-id="292ae-104">你可以通过执行以下步骤来完成此任务：</span><span class="sxs-lookup"><span data-stu-id="292ae-104">You do so by:</span></span>  
  
-   <span data-ttu-id="292ae-105">从 RosettaNet Web 站点下载 PIP 架构[http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)。</span><span class="sxs-lookup"><span data-stu-id="292ae-105">Downloading the PIP schema from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
-   <span data-ttu-id="292ae-106">将该架构作为 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] RNPIP 程序集的一部分或作为单独 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 程序集的一部分部署到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="292ae-106">Deploying the schema to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as part of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIPs assembly or as part of a separate [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] assembly.</span></span> <span data-ttu-id="292ae-107">有关详细信息，请参阅[与新 PIP 扩展 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)。</span><span class="sxs-lookup"><span data-stu-id="292ae-107">For more information, see [Extending BTARN with a New PIP](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md).</span></span>  
  
-   <span data-ttu-id="292ae-108">在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台中创建新的流程配置设置。</span><span class="sxs-lookup"><span data-stu-id="292ae-108">Creating a new Process Configuration Setting in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="292ae-109">有关详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="292ae-109">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
 <span data-ttu-id="292ae-110">下载的架构文件通常为 .dtd 格式，并带有一个 .doc 文件格式的 RosettaNet 组织的伴随 PIP 规范。</span><span class="sxs-lookup"><span data-stu-id="292ae-110">The downloaded schema is generally in .dtd format, with an accompanying PIP specification from the RosettaNet organization as a .doc file.</span></span> <span data-ttu-id="292ae-111">扩展管道以使用新架构的流程中包含将 PIP 的 .dtd 文件转换为 .xsd 文件的步骤。</span><span class="sxs-lookup"><span data-stu-id="292ae-111">The process of extending the pipeline to use the new schema includes converting the PIP .dtd file into an .xsd file.</span></span>  
  
 <span data-ttu-id="292ae-112">安装 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 后，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 将包含若干个 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="292ae-112">When you install [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a number of XSD schemas.</span></span> <span data-ttu-id="292ae-113">你可以找到这些架构中的\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas 文件夹。</span><span class="sxs-lookup"><span data-stu-id="292ae-113">You can find those schemas in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas folder.</span></span> <span data-ttu-id="292ae-114">BTARN 将这些架构置入 RNPIPs.dll 文件中。</span><span class="sxs-lookup"><span data-stu-id="292ae-114">BTARN builds these schemas into an RNPIPs.dll file.</span></span> <span data-ttu-id="292ae-115">如果你需要更改这些架构中的一个，则必须打开同一文件夹中的 RNPIP 项目，在 BizTalk 编辑器中更改该架构，然后重新编译并重新部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="292ae-115">If you have to change one of these schemas, you must open the RNPIPs project in the same folder, change the schema in BizTalk Editor, and then recompile and redeploy the assembly.</span></span> <span data-ttu-id="292ae-116">重新部署 RNPIPs.dll 文件后，必须重新部署使用该架构的管道。</span><span class="sxs-lookup"><span data-stu-id="292ae-116">After you redeploy the RNPIPs.dll file, you must redeploy the pipeline that uses the schema.</span></span> <span data-ttu-id="292ae-117">你可以使用此流程将新架构并入 BTARN 中，但通过扩展管道来包含新架构更加方便。</span><span class="sxs-lookup"><span data-stu-id="292ae-117">You could use this process to incorporate a new schema in BTARN, but it is easier to extend the pipeline to include the new schema.</span></span>  
  
### <a name="to-obtain-the-pip-schema"></a><span data-ttu-id="292ae-118">获取 PIP 架构</span><span class="sxs-lookup"><span data-stu-id="292ae-118">To obtain the PIP schema</span></span>  
  
-   <span data-ttu-id="292ae-119">在 Internet Explorer 中，转到 RosettaNet Web 站点[http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)。</span><span class="sxs-lookup"><span data-stu-id="292ae-119">In Internet Explorer, go to the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292ae-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="292ae-120">See Also</span></span>  
 [<span data-ttu-id="292ae-121">使用新 PIP 扩展 BTARN</span><span class="sxs-lookup"><span data-stu-id="292ae-121">Extending BTARN with a New PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)