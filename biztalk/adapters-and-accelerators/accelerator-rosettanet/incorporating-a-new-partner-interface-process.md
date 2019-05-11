---
title: 并入新的合作伙伴接口流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, PIP schemas
- PIP schemas
- PIP schemas, deploying
- PIP schemas, downloading
- creating, PIP schemas
- PIP schemas, creating
ms.assetid: 6a5fcbcb-c6aa-40c0-bcca-dd0c391e7f42
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2c372adb1993aacee1ba2d56d8a5dc2f8d9d0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283554"
---
# <a name="incorporating-a-new-partner-interface-process"></a><span data-ttu-id="91acf-102">并入新的合作伙伴接口流程</span><span class="sxs-lookup"><span data-stu-id="91acf-102">Incorporating a New Partner Interface Process</span></span>
<span data-ttu-id="91acf-103">您可以将合并新的 RosettaNet 合作伙伴接口流程 (PIP) 架构中 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="91acf-103">You can incorporate a new RosettaNet Partner Interface Process (PIP) schema in Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] assemblies.</span></span> <span data-ttu-id="91acf-104">为此，：</span><span class="sxs-lookup"><span data-stu-id="91acf-104">You do so by:</span></span>  
  
- <span data-ttu-id="91acf-105">从 RosettaNet 网站下载 PIP 架构[ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859)。</span><span class="sxs-lookup"><span data-stu-id="91acf-105">Downloading the PIP schema from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
- <span data-ttu-id="91acf-106">部署到的架构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为的一部分[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Rnpip 程序集或作为单独的一部分[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]程序集。</span><span class="sxs-lookup"><span data-stu-id="91acf-106">Deploying the schema to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] as part of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIPs assembly or as part of a separate [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] assembly.</span></span> <span data-ttu-id="91acf-107">有关详细信息，请参阅[使用新 PIP 扩展 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)。</span><span class="sxs-lookup"><span data-stu-id="91acf-107">For more information, see [Extending BTARN with a New PIP](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md).</span></span>  
  
- <span data-ttu-id="91acf-108">创建新的进程配置设置中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="91acf-108">Creating a new Process Configuration Setting in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="91acf-109">有关详细信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="91acf-109">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
  <span data-ttu-id="91acf-110">下载的架构通常为.dtd 格式，但为.doc 文件的 RosettaNet 组织的伴随 PIP 规范。</span><span class="sxs-lookup"><span data-stu-id="91acf-110">The downloaded schema is generally in .dtd format, with an accompanying PIP specification from the RosettaNet organization as a .doc file.</span></span> <span data-ttu-id="91acf-111">扩展管道以使用新的架构的过程包括将 PIP 的.dtd 文件转换为.xsd 文件。</span><span class="sxs-lookup"><span data-stu-id="91acf-111">The process of extending the pipeline to use the new schema includes converting the PIP .dtd file into an .xsd file.</span></span>  
  
  <span data-ttu-id="91acf-112">当你安装[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 包括若干个 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="91acf-112">When you install [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a number of XSD schemas.</span></span> <span data-ttu-id="91acf-113">您可以找到这些架构中的\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas 文件夹。</span><span class="sxs-lookup"><span data-stu-id="91acf-113">You can find those schemas in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas folder.</span></span> <span data-ttu-id="91acf-114">BTARN 生成这些架构置入 RNPIPs.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="91acf-114">BTARN builds these schemas into an RNPIPs.dll file.</span></span> <span data-ttu-id="91acf-115">如果需要更改这些架构之一，必须在同一文件夹中打开 Rnpip 项目、 更改架构在 BizTalk 编辑器中，然后重新编译和重新部署程序集。</span><span class="sxs-lookup"><span data-stu-id="91acf-115">If you have to change one of these schemas, you must open the RNPIPs project in the same folder, change the schema in BizTalk Editor, and then recompile and redeploy the assembly.</span></span> <span data-ttu-id="91acf-116">重新部署 RNPIPs.dll 文件后，必须重新部署管道，将使用的架构。</span><span class="sxs-lookup"><span data-stu-id="91acf-116">After you redeploy the RNPIPs.dll file, you must redeploy the pipeline that uses the schema.</span></span> <span data-ttu-id="91acf-117">可以使用此过程以合并新架构 BTARN 中，但更轻松地扩展管道来包含新架构。</span><span class="sxs-lookup"><span data-stu-id="91acf-117">You could use this process to incorporate a new schema in BTARN, but it is easier to extend the pipeline to include the new schema.</span></span>  
  
### <a name="to-obtain-the-pip-schema"></a><span data-ttu-id="91acf-118">若要获取 PIP 架构</span><span class="sxs-lookup"><span data-stu-id="91acf-118">To obtain the PIP schema</span></span>  
  
-   <span data-ttu-id="91acf-119">在 Internet Explorer 中，转到 RosettaNet Web 站点[ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859)。</span><span class="sxs-lookup"><span data-stu-id="91acf-119">In Internet Explorer, go to the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91acf-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="91acf-120">See Also</span></span>  
 [<span data-ttu-id="91acf-121">使用新 PIP 扩展 BTARN</span><span class="sxs-lookup"><span data-stu-id="91acf-121">Extending BTARN with a New PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/extending-btarn-with-a-new-pip.md)