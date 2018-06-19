---
title: 如何读取管道组件属性 |Microsoft 文档
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
ms.openlocfilehash: 19a6ccbcbe7588a0a75b4dbe6bf821a19fab965c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254781"
---
# <a name="how-to-read-pipeline-component-properties"></a><span data-ttu-id="9eba4-102">如何读取管道组件属性</span><span class="sxs-lookup"><span data-stu-id="9eba4-102">How to Read Pipeline Component Properties</span></span>
<span data-ttu-id="9eba4-103">“属性”窗口包含组件的两部分：常规属性和组件属性。</span><span class="sxs-lookup"><span data-stu-id="9eba4-103">The Properties window contains two sections for components: general properties and component properties.</span></span> <span data-ttu-id="9eba4-104">常规属性是所有组件共有的属性，尽管常规属性的值在各个组件中都有所不同。</span><span class="sxs-lookup"><span data-stu-id="9eba4-104">General properties are common to all components, though their values change between components.</span></span>  
  
### <a name="to-read-the-general-properties-for-a-pipeline-component"></a><span data-ttu-id="9eba4-105">读取管道组件的常规属性</span><span class="sxs-lookup"><span data-stu-id="9eba4-105">To read the general properties for a pipeline component</span></span>  
  
1.  <span data-ttu-id="9eba4-106">将管道组件拖至管道的某个阶段中，或者如果管道组件已存在于管道中，则选择该组件。</span><span class="sxs-lookup"><span data-stu-id="9eba4-106">Drag the pipeline component into a stage of the pipeline, or select a component if it already exists in the pipeline.</span></span>  
  
2.  <span data-ttu-id="9eba4-107">在属性窗口中，在**常规**部分中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="9eba4-107">In the Properties window, in the **General** section, do the following.</span></span>  
  
    |<span data-ttu-id="9eba4-108">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9eba4-108">Use this</span></span>|<span data-ttu-id="9eba4-109">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9eba4-109">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9eba4-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="9eba4-110">**Name**</span></span>|<span data-ttu-id="9eba4-111">指明组件名称。</span><span class="sxs-lookup"><span data-stu-id="9eba4-111">Indicates the component name.</span></span>|  
    |<span data-ttu-id="9eba4-112">**程序集**</span><span class="sxs-lookup"><span data-stu-id="9eba4-112">**Assembly**</span></span>|<span data-ttu-id="9eba4-113">指明该组件的程序集和相关 .NET 信息。</span><span class="sxs-lookup"><span data-stu-id="9eba4-113">Indicates the assembly and associated .NET information for the component.</span></span>|  
    |<span data-ttu-id="9eba4-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="9eba4-114">**Description**</span></span>|<span data-ttu-id="9eba4-115">指明该管道组件的友好名称。</span><span class="sxs-lookup"><span data-stu-id="9eba4-115">Indicates the friendly name of the pipeline component.</span></span>|  
    |<span data-ttu-id="9eba4-116">**管理**</span><span class="sxs-lookup"><span data-stu-id="9eba4-116">**Managed**</span></span>|<span data-ttu-id="9eba4-117">指明是否托管该管道组件。</span><span class="sxs-lookup"><span data-stu-id="9eba4-117">Indicates whether the pipeline component is managed.</span></span> <span data-ttu-id="9eba4-118">**是**如果组件为.NET 托管的组件;**否**如果管道组件是一个 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="9eba4-118">**Yes** if the component is a .NET managed component; **No** if the pipeline component is a COM component.</span></span>|  
    |<span data-ttu-id="9eba4-119">**路径**</span><span class="sxs-lookup"><span data-stu-id="9eba4-119">**Path**</span></span>|<span data-ttu-id="9eba4-120">指明该 .NET 组件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="9eba4-120">Indicates the fully qualified path to the .NET component.</span></span>|  
    |<span data-ttu-id="9eba4-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="9eba4-121">**Type**</span></span>|<span data-ttu-id="9eba4-122">指明该组件的组件类型、程序集和相关的 .NET 信息。</span><span class="sxs-lookup"><span data-stu-id="9eba4-122">Indicates the component type, the assembly, and the associated .NET information for the component.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9eba4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9eba4-123">See Also</span></span>  
 <span data-ttu-id="9eba4-124">[配置本机管道组件](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="9eba4-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="9eba4-125">使用管道设计器中创建管道</span><span class="sxs-lookup"><span data-stu-id="9eba4-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)