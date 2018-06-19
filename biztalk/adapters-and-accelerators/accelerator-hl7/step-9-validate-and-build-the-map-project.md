---
title: 步骤 9： 验证并生成映射项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, maps
- message enrichment tutorial, maps
- maps, building
- maps, validating
ms.assetid: 10716b0b-702c-48bb-85a9-d58d8f33b68b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1eb4580a9c89534204e492aebdd21988a6ce0e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206469"
---
# <a name="step-9-validate-and-build-the-map-project"></a><span data-ttu-id="c9a5e-102">步骤 9： 验证并生成映射项目</span><span class="sxs-lookup"><span data-stu-id="c9a5e-102">Step 9: Validate and Build the Map Project</span></span>
<span data-ttu-id="c9a5e-103">在此步骤中，你使用**验证映射**以确定映射是否包含任何内部不一致，或者具有其他问题，防止将其用于有效地映射架构的命令。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-103">In this step, you use the **Validate Map** command to determine if the map contains any internal inconsistencies, or has other issues that would prevent it from being used effectively for mapping schemas.</span></span> <span data-ttu-id="c9a5e-104">你也会生成此项目以生成该程序集包含你创建的资源 （架构和映射）。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-104">You also build the project to generate an assembly that contains the resources (schemas and the map) that you created.</span></span> <span data-ttu-id="c9a5e-105">这还可以确保到目前为止完成的工作中没有编译错误。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-105">This also ensures that there are no compile errors in the work that you have completed so far.</span></span>  
  
### <a name="to-validate-the-map-project"></a><span data-ttu-id="c9a5e-106">若要验证映射项目</span><span class="sxs-lookup"><span data-stu-id="c9a5e-106">To validate the map project</span></span>  
  
1.  <span data-ttu-id="c9a5e-107">在解决方案资源管理器，右键单击**DoorbellMap.btm**映射，并依次**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-107">In Solution Explorer, right-click the **DoorbellMap.btm** map, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="c9a5e-108">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-108">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="c9a5e-109">由于不映射到目标架构中的所有可用元素，因此，可能显示某些警告。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-109">Some warnings may appear because you are not mapping to all available elements in the destination schema.</span></span>  
  
     <span data-ttu-id="c9a5e-110">如果不显示任何成功消息，请检查映射项目。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-110">If no success message appears, troubleshoot the map project.</span></span>  
  
### <a name="to-build-the-map-project"></a><span data-ttu-id="c9a5e-111">若要生成映射项目</span><span class="sxs-lookup"><span data-stu-id="c9a5e-111">To build the map project</span></span>  
  
-   <span data-ttu-id="c9a5e-112">在解决方案资源管理器，右键单击**BTAHL7 项目**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Build**.</span></span> <span data-ttu-id="c9a5e-113">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-113">Ensure that a success message appears in the output window.</span></span>  
  
     <span data-ttu-id="c9a5e-114">如果不显示任何成功消息，请检查映射项目。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-114">If no success message appears, troubleshoot the map project.</span></span>  
  
 <span data-ttu-id="c9a5e-115">继续执行[步骤 10： 创建业务流程](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="c9a5e-115">Proceed to [Step 10: Create an Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a5e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9a5e-116">See Also</span></span>  
 [<span data-ttu-id="c9a5e-117">消息扩充教程</span><span class="sxs-lookup"><span data-stu-id="c9a5e-117">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)