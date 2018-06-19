---
title: 如何为 Functoid 检测配置问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32afc333-934c-4ffb-b1b5-61af07157200
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8561156091c992e9329ef7d9627589eff9e0ed6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968963"
---
# <a name="how-to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="ce48b-102">如何检测 Functoid 的配置问题</span><span class="sxs-lookup"><span data-stu-id="ce48b-102">How to Detect Configuration Issues for a Functoid</span></span>
<span data-ttu-id="ce48b-103">使用映射时，您可能会遇到 functoid 和/或链接的配置问题。</span><span class="sxs-lookup"><span data-stu-id="ce48b-103">While working with maps, you might encounter issues with configuration of a functoid and/or link.</span></span> <span data-ttu-id="ce48b-104">BizTalk 映射器使用可视化效果机制来帮助快速识别与 functoid 配置相关的问题。</span><span class="sxs-lookup"><span data-stu-id="ce48b-104">The BizTalk Mapper uses a visualization mechanism to help quickly identify problems associated with a functoid configuration.</span></span> <span data-ttu-id="ce48b-105">此视觉指示将呈现为 functoid 图标的警告批注 (有关例如![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) 的关系视图中。</span><span class="sxs-lookup"><span data-stu-id="ce48b-105">This visual indication renders as a warning annotation on the functoid icon (for e.g. ![Functoid IntelliSense](../core/media/mapper-functoidintellisense.gif "Mapper_FunctoidIntelliSense")) in the relationship view.</span></span> <span data-ttu-id="ce48b-106">本主题提供有关如何检测 functoid 配置问题的信息。</span><span class="sxs-lookup"><span data-stu-id="ce48b-106">This topic provides information about how to detect the configuration issues for a functoid.</span></span>  
  
 <span data-ttu-id="ce48b-107">当映射器检测到未正确配置 functoid 时，将显示警告状态图标。</span><span class="sxs-lookup"><span data-stu-id="ce48b-107">The warning status icon appears when the Mapper detects that a functoid is not properly configured.</span></span> <span data-ttu-id="ce48b-108">将鼠标放到 functoid 上还会显示有关映射器所发现问题的简短信息。</span><span class="sxs-lookup"><span data-stu-id="ce48b-108">Moving the mouse over the functoid also displays brief information of the issue identified by the Mapper.</span></span> <span data-ttu-id="ce48b-109">例如，如果 functoid 不含有最低数量的有效输入，则 functoid 的工具提示将提到要求的输入参数数。</span><span class="sxs-lookup"><span data-stu-id="ce48b-109">For example, if a functoid does not have minimum number of valid inputs, the tooltip for the functoid mentions the number of input parameters required.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ce48b-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="ce48b-110">Prerequisites</span></span>  
 <span data-ttu-id="ce48b-111">此操作要求 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="ce48b-111">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-detect-configuration-issues-for-a-functoid"></a><span data-ttu-id="ce48b-112">检测 functoid 的配置问题</span><span class="sxs-lookup"><span data-stu-id="ce48b-112">To detect configuration issues for a functoid</span></span>  
  
1.  <span data-ttu-id="ce48b-113">将所需的 functoid 从工具箱拖到网格页中。</span><span class="sxs-lookup"><span data-stu-id="ce48b-113">Drag the required functoid from the toolbox onto the grid page.</span></span> <span data-ttu-id="ce48b-114">您将看到带有警告图标的 functoid。</span><span class="sxs-lookup"><span data-stu-id="ce48b-114">You see the functoid with a warning icon.</span></span>  
  
2.  <span data-ttu-id="ce48b-115">您可以执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ce48b-115">You can do one of the following:</span></span>  
  
    -   <span data-ttu-id="ce48b-116">将鼠标指针移到 functoid 上。</span><span class="sxs-lookup"><span data-stu-id="ce48b-116">Move the mouse pointer on the functoid.</span></span> <span data-ttu-id="ce48b-117">此时工具提示将显示有关错误和需要执行的操作信息。</span><span class="sxs-lookup"><span data-stu-id="ce48b-117">The tooltip displays information about the error and what you need to do.</span></span>  
  
         <span data-ttu-id="ce48b-118">下图显示了配置 functoid“加法”时含错误信息的工具提示。</span><span class="sxs-lookup"><span data-stu-id="ce48b-118">The following figure displays a tooltip with error information while configuring the functoid “Addition.”</span></span>  
  
         <span data-ttu-id="ce48b-119">![Functoid 配置中的错误检测](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span><span class="sxs-lookup"><span data-stu-id="ce48b-119">![Error detection in functoid configuration](../core/media/errordetectionfunctoid.gif "ErrorDetectionFunctoid")</span></span>  
  
    -   <span data-ttu-id="ce48b-120">双击该 functoid。</span><span class="sxs-lookup"><span data-stu-id="ce48b-120">Double-click the functoid.</span></span> <span data-ttu-id="ce48b-121">**配置\<Functoid\> Functoid**对话框中显示针对输入参数的警告图标。</span><span class="sxs-lookup"><span data-stu-id="ce48b-121">The **Configure \<Functoid\> Functoid** dialog box displays warning icons against the input parameters.</span></span> <span data-ttu-id="ce48b-122">这表明所选 functoid 未配置输入参数。</span><span class="sxs-lookup"><span data-stu-id="ce48b-122">This indicates that the input parameters of the selected functoid are not configured.</span></span>  
  
         <span data-ttu-id="ce48b-123">下图显示了有关“加法”functoid 输入参数的错误信息。</span><span class="sxs-lookup"><span data-stu-id="ce48b-123">The following figure displays error information about input parameters for the “Addition” functoid.</span></span>  
  
         <span data-ttu-id="ce48b-124">![未配置 functoid 时显示的警告](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span><span class="sxs-lookup"><span data-stu-id="ce48b-124">![Warning displayed when functoid is not configured](../core/media/configure-input-parameters-warningicon.gif "Configure_input_parameters_WarningIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce48b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce48b-125">See Also</span></span>  
 [<span data-ttu-id="ce48b-126">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="ce48b-126">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)