---
title: 架构 （TrackedSchemas 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Schema node
ms.assetid: a503aad6-07f8-4650-a214-4d2f6650cb80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe27ed2ce631fe27cb34ec44bb792349737dbe01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396883"
---
# <a name="schema-trackedschemas-node"></a><span data-ttu-id="233ac-102">架构 （TrackedSchemas 节点）</span><span class="sxs-lookup"><span data-stu-id="233ac-102">Schema (TrackedSchemas Node)</span></span>
<span data-ttu-id="233ac-103">绑定文件的 TrackedSchemas 节点的架构节点描述了绑定到与绑定文件一起导出的服务的架构。</span><span class="sxs-lookup"><span data-stu-id="233ac-103">The Schema node of the TrackedSchemas node of a binding file describes a schema bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-schema-node"></a><span data-ttu-id="233ac-104">节点中的架构节点</span><span class="sxs-lookup"><span data-stu-id="233ac-104">Nodes in the Schema node</span></span>  
 <span data-ttu-id="233ac-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="233ac-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="233ac-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="233ac-106">**Name**</span></span>|<span data-ttu-id="233ac-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="233ac-107">**Node Type**</span></span>|<span data-ttu-id="233ac-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="233ac-108">**Data Type**</span></span>|<span data-ttu-id="233ac-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="233ac-109">**Description**</span></span>|<span data-ttu-id="233ac-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="233ac-110">**Restrictions**</span></span>|<span data-ttu-id="233ac-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="233ac-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="233ac-112">FullName</span><span class="sxs-lookup"><span data-stu-id="233ac-112">FullName</span></span>|<span data-ttu-id="233ac-113">特性</span><span class="sxs-lookup"><span data-stu-id="233ac-113">Attribute</span></span>|<span data-ttu-id="233ac-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="233ac-114">xs:string</span></span>|<span data-ttu-id="233ac-115">指定架构的完整名称。</span><span class="sxs-lookup"><span data-stu-id="233ac-115">Specifies the full name for the schema.</span></span>|<span data-ttu-id="233ac-116">可选</span><span class="sxs-lookup"><span data-stu-id="233ac-116">Not required</span></span>|<span data-ttu-id="233ac-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="233ac-117">Default value: empty</span></span>|  
|<span data-ttu-id="233ac-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="233ac-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="233ac-119">特性</span><span class="sxs-lookup"><span data-stu-id="233ac-119">Attribute</span></span>|<span data-ttu-id="233ac-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="233ac-120">xs:string</span></span>|<span data-ttu-id="233ac-121">指定包含此架构的程序集的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="233ac-121">Specifies the qualified name for the assembly containing this schema.</span></span>|<span data-ttu-id="233ac-122">可选</span><span class="sxs-lookup"><span data-stu-id="233ac-122">Not required</span></span>|<span data-ttu-id="233ac-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="233ac-123">Default value: empty</span></span>|  
|<span data-ttu-id="233ac-124">AlwaysTrackAllProperties</span><span class="sxs-lookup"><span data-stu-id="233ac-124">AlwaysTrackAllProperties</span></span>|<span data-ttu-id="233ac-125">特性</span><span class="sxs-lookup"><span data-stu-id="233ac-125">Attribute</span></span>|<span data-ttu-id="233ac-126">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="233ac-126">xs:boolean</span></span>|<span data-ttu-id="233ac-127">指定是否为指定的程序集跟踪所有属性。</span><span class="sxs-lookup"><span data-stu-id="233ac-127">Specifies whether to track all properties for the specified assembly.</span></span>|<span data-ttu-id="233ac-128">Required</span><span class="sxs-lookup"><span data-stu-id="233ac-128">Required</span></span>|<span data-ttu-id="233ac-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="233ac-129">Default value: none</span></span><br /><br /> <span data-ttu-id="233ac-130">设置为 **，则返回 true**若要跟踪的所有属性，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="233ac-130">Set to **true** to track all properties, otherwise set to **false**.</span></span>|  
|<span data-ttu-id="233ac-131">Description</span><span class="sxs-lookup"><span data-stu-id="233ac-131">Description</span></span>|<span data-ttu-id="233ac-132">特性</span><span class="sxs-lookup"><span data-stu-id="233ac-132">Attribute</span></span>|<span data-ttu-id="233ac-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="233ac-133">xs:string</span></span>|<span data-ttu-id="233ac-134">指定架构的说明。</span><span class="sxs-lookup"><span data-stu-id="233ac-134">Specifies a description for the schema.</span></span>|<span data-ttu-id="233ac-135">可选</span><span class="sxs-lookup"><span data-stu-id="233ac-135">Not required</span></span>|<span data-ttu-id="233ac-136">默认值：空</span><span class="sxs-lookup"><span data-stu-id="233ac-136">Default value: empty</span></span>|  
|[<span data-ttu-id="233ac-137">TrackedPropertyNames（Schema 节点）</span><span class="sxs-lookup"><span data-stu-id="233ac-137">TrackedPropertyNames (Schema Node)</span></span>](../core/trackedpropertynames-schema-node.md)|<span data-ttu-id="233ac-138">录制</span><span class="sxs-lookup"><span data-stu-id="233ac-138">Record</span></span>|<span data-ttu-id="233ac-139">ArrayOfString (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="233ac-139">ArrayOfString (ComplexType)</span></span>|<span data-ttu-id="233ac-140">指定要跟踪的属性的元素的容器。</span><span class="sxs-lookup"><span data-stu-id="233ac-140">Container for the elements that specify the properties to be tracked.</span></span>|<span data-ttu-id="233ac-141">可选</span><span class="sxs-lookup"><span data-stu-id="233ac-141">Not required</span></span>|<span data-ttu-id="233ac-142">默认值：无</span><span class="sxs-lookup"><span data-stu-id="233ac-142">Default value: none</span></span>|