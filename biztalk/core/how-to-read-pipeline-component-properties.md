---
title: 如何读取管道组件属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, properties
ms.assetid: 10b1c59c-7ba4-453f-9aaa-1ce9ecf31fac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f9a91edb33167ca97ea73949c8419d1df1521ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335687"
---
# <a name="how-to-read-pipeline-component-properties"></a><span data-ttu-id="9df18-102">如何读取管道组件属性</span><span class="sxs-lookup"><span data-stu-id="9df18-102">How to Read Pipeline Component Properties</span></span>
<span data-ttu-id="9df18-103">属性窗口包含组件的两部分： 常规属性和组件属性。</span><span class="sxs-lookup"><span data-stu-id="9df18-103">The Properties window contains two sections for components: general properties and component properties.</span></span> <span data-ttu-id="9df18-104">常规属性是通用的所有组件，但是它们的值组件之间发生变化。</span><span class="sxs-lookup"><span data-stu-id="9df18-104">General properties are common to all components, though their values change between components.</span></span>  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a><span data-ttu-id="9df18-105">读取管道组件的常规属性</span><span class="sxs-lookup"><span data-stu-id="9df18-105">To read the general properties for a pipeline component</span></span>  
  
1.  <span data-ttu-id="9df18-106">将管道组件拖放到管道，该阶段，或选择某一组件，如果管道中已存在。</span><span class="sxs-lookup"><span data-stu-id="9df18-106">Drag the pipeline component into a stage of the pipeline, or select a component if it already exists in the pipeline.</span></span>  
  
2.  <span data-ttu-id="9df18-107">在属性窗口中**常规**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="9df18-107">In the Properties window, in the **General** section, do the following.</span></span>  
  
    |<span data-ttu-id="9df18-108">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9df18-108">Use this</span></span>|<span data-ttu-id="9df18-109">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9df18-109">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9df18-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="9df18-110">**Name**</span></span>|<span data-ttu-id="9df18-111">指明组件名称。</span><span class="sxs-lookup"><span data-stu-id="9df18-111">Indicates the component name.</span></span>|  
    |<span data-ttu-id="9df18-112">**程序集**</span><span class="sxs-lookup"><span data-stu-id="9df18-112">**Assembly**</span></span>|<span data-ttu-id="9df18-113">指示程序集和组件的相关的.NET 信息。</span><span class="sxs-lookup"><span data-stu-id="9df18-113">Indicates the assembly and associated .NET information for the component.</span></span>|  
    |<span data-ttu-id="9df18-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="9df18-114">**Description**</span></span>|<span data-ttu-id="9df18-115">指示管道组件的友好名称。</span><span class="sxs-lookup"><span data-stu-id="9df18-115">Indicates the friendly name of the pipeline component.</span></span>|  
    |<span data-ttu-id="9df18-116">**托管**</span><span class="sxs-lookup"><span data-stu-id="9df18-116">**Managed**</span></span>|<span data-ttu-id="9df18-117">指示是否已托管管道组件。</span><span class="sxs-lookup"><span data-stu-id="9df18-117">Indicates whether the pipeline component is managed.</span></span> <span data-ttu-id="9df18-118">**是**如果组件是.NET 托管的组件;**否**如果管道组件是一个 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="9df18-118">**Yes** if the component is a .NET managed component; **No** if the pipeline component is a COM component.</span></span>|  
    |<span data-ttu-id="9df18-119">**路径**</span><span class="sxs-lookup"><span data-stu-id="9df18-119">**Path**</span></span>|<span data-ttu-id="9df18-120">指示该.NET 组件的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="9df18-120">Indicates the fully qualified path to the .NET component.</span></span>|  
    |<span data-ttu-id="9df18-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="9df18-121">**Type**</span></span>|<span data-ttu-id="9df18-122">指示组件类型，该程序集，以及相关组件的.NET 信息。</span><span class="sxs-lookup"><span data-stu-id="9df18-122">Indicates the component type, the assembly, and the associated .NET information for the component.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9df18-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9df18-123">See Also</span></span>  
 <span data-ttu-id="9df18-124">[配置本地管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9df18-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="9df18-125">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="9df18-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)