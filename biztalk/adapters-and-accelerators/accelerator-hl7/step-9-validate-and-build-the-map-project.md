---
title: 步骤 9：验证并生成映射项目 |Microsoft Docs
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
ms.openlocfilehash: 0f41cc3bbe235dfda75563d94ae0173737a58c75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286639"
---
# <a name="step-9-validate-and-build-the-map-project"></a><span data-ttu-id="095e3-102">步骤 9：验证并生成映射项目</span><span class="sxs-lookup"><span data-stu-id="095e3-102">Step 9: Validate and Build the Map Project</span></span>
<span data-ttu-id="095e3-103">在此步骤中，使用**验证映射**命令，以确定是否映射包含任何内部不一致，或存在会妨碍其为映射架构有效地使用其他问题。</span><span class="sxs-lookup"><span data-stu-id="095e3-103">In this step, you use the **Validate Map** command to determine if the map contains any internal inconsistencies, or has other issues that would prevent it from being used effectively for mapping schemas.</span></span> <span data-ttu-id="095e3-104">你还生成项目以生成包含你创建的资源 （架构和映射） 的程序集。</span><span class="sxs-lookup"><span data-stu-id="095e3-104">You also build the project to generate an assembly that contains the resources (schemas and the map) that you created.</span></span> <span data-ttu-id="095e3-105">这还可确保到目前为止完成的工作中没有任何编译错误。</span><span class="sxs-lookup"><span data-stu-id="095e3-105">This also ensures that there are no compile errors in the work that you have completed so far.</span></span>  
  
### <a name="to-validate-the-map-project"></a><span data-ttu-id="095e3-106">若要验证映射项目</span><span class="sxs-lookup"><span data-stu-id="095e3-106">To validate the map project</span></span>  
  
1.  <span data-ttu-id="095e3-107">在解决方案资源管理器中右键单击**DoorbellMap.btm**映射，然后依次**验证映射**。</span><span class="sxs-lookup"><span data-stu-id="095e3-107">In Solution Explorer, right-click the **DoorbellMap.btm** map, and then click **Validate Map**.</span></span>  
  
2.  <span data-ttu-id="095e3-108">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="095e3-108">Ensure that a success message appears in the output window.</span></span> <span data-ttu-id="095e3-109">因为不映射到目标架构中的所有可用元素，则可能出现一些警告。</span><span class="sxs-lookup"><span data-stu-id="095e3-109">Some warnings may appear because you are not mapping to all available elements in the destination schema.</span></span>  
  
     <span data-ttu-id="095e3-110">如果不显示任何成功消息，进行故障排除映射项目。</span><span class="sxs-lookup"><span data-stu-id="095e3-110">If no success message appears, troubleshoot the map project.</span></span>  
  
### <a name="to-build-the-map-project"></a><span data-ttu-id="095e3-111">若要生成映射项目</span><span class="sxs-lookup"><span data-stu-id="095e3-111">To build the map project</span></span>  
  
- <span data-ttu-id="095e3-112">在解决方案资源管理器中右键单击**BTAHL7 项目**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="095e3-112">In Solution Explorer, right-click **BTAHL7 Project**, and then click **Build**.</span></span> <span data-ttu-id="095e3-113">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="095e3-113">Ensure that a success message appears in the output window.</span></span>  
  
   <span data-ttu-id="095e3-114">如果不显示任何成功消息，进行故障排除映射项目。</span><span class="sxs-lookup"><span data-stu-id="095e3-114">If no success message appears, troubleshoot the map project.</span></span>  
  
  <span data-ttu-id="095e3-115">请继续执行[步骤 10:创建一个业务流程](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="095e3-115">Proceed to [Step 10: Create an Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="095e3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="095e3-116">See Also</span></span>  
 [<span data-ttu-id="095e3-117">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="095e3-117">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)