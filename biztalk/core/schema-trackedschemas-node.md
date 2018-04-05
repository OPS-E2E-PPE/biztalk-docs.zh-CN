---
title: 架构 （TrackedSchemas 节点） |Microsoft 文档
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
ms.openlocfilehash: 5376c505332ed05507169c1db2dc54ec4e7bdfe6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-trackedschemas-node"></a><span data-ttu-id="701ee-102">架构（TrackedSchemas 节点）</span><span class="sxs-lookup"><span data-stu-id="701ee-102">Schema (TrackedSchemas Node)</span></span>
<span data-ttu-id="701ee-103">绑定文件的“TrackedSchemas”节点的 Schema 节点描述了绑定到与绑定文件一起导出的服务的架构。</span><span class="sxs-lookup"><span data-stu-id="701ee-103">The Schema node of the TrackedSchemas node of a binding file describes a schema bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-schema-node"></a><span data-ttu-id="701ee-104">Schema 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="701ee-104">Nodes in the Schema node</span></span>  
 <span data-ttu-id="701ee-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="701ee-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="701ee-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="701ee-106">**Name**</span></span>|<span data-ttu-id="701ee-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="701ee-107">**Node Type**</span></span>|<span data-ttu-id="701ee-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="701ee-108">**Data Type**</span></span>|<span data-ttu-id="701ee-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="701ee-109">**Description**</span></span>|<span data-ttu-id="701ee-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="701ee-110">**Restrictions**</span></span>|<span data-ttu-id="701ee-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="701ee-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="701ee-112">FullName</span><span class="sxs-lookup"><span data-stu-id="701ee-112">FullName</span></span>|<span data-ttu-id="701ee-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="701ee-113">Attribute</span></span>|<span data-ttu-id="701ee-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="701ee-114">xs:string</span></span>|<span data-ttu-id="701ee-115">指定架构的全名。</span><span class="sxs-lookup"><span data-stu-id="701ee-115">Specifies the full name for the schema.</span></span>|<span data-ttu-id="701ee-116">可选</span><span class="sxs-lookup"><span data-stu-id="701ee-116">Not required</span></span>|<span data-ttu-id="701ee-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="701ee-117">Default value: empty</span></span>|  
|<span data-ttu-id="701ee-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="701ee-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="701ee-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="701ee-119">Attribute</span></span>|<span data-ttu-id="701ee-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="701ee-120">xs:string</span></span>|<span data-ttu-id="701ee-121">指定包含此架构的程序集的限定名。</span><span class="sxs-lookup"><span data-stu-id="701ee-121">Specifies the qualified name for the assembly containing this schema.</span></span>|<span data-ttu-id="701ee-122">可选</span><span class="sxs-lookup"><span data-stu-id="701ee-122">Not required</span></span>|<span data-ttu-id="701ee-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="701ee-123">Default value: empty</span></span>|  
|<span data-ttu-id="701ee-124">AlwaysTrackAllProperties</span><span class="sxs-lookup"><span data-stu-id="701ee-124">AlwaysTrackAllProperties</span></span>|<span data-ttu-id="701ee-125">Attribute</span><span class="sxs-lookup"><span data-stu-id="701ee-125">Attribute</span></span>|<span data-ttu-id="701ee-126">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="701ee-126">xs:boolean</span></span>|<span data-ttu-id="701ee-127">指定是否跟踪指定程序集的所有属性。</span><span class="sxs-lookup"><span data-stu-id="701ee-127">Specifies whether to track all properties for the specified assembly.</span></span>|<span data-ttu-id="701ee-128">必需</span><span class="sxs-lookup"><span data-stu-id="701ee-128">Required</span></span>|<span data-ttu-id="701ee-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="701ee-129">Default value: none</span></span><br /><br /> <span data-ttu-id="701ee-130">设置为**true**若要跟踪的所有属性，否则设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="701ee-130">Set to **true** to track all properties, otherwise set to **false**.</span></span>|  
|<span data-ttu-id="701ee-131">Description</span><span class="sxs-lookup"><span data-stu-id="701ee-131">Description</span></span>|<span data-ttu-id="701ee-132">Attribute</span><span class="sxs-lookup"><span data-stu-id="701ee-132">Attribute</span></span>|<span data-ttu-id="701ee-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="701ee-133">xs:string</span></span>|<span data-ttu-id="701ee-134">为架构指定描述。</span><span class="sxs-lookup"><span data-stu-id="701ee-134">Specifies a description for the schema.</span></span>|<span data-ttu-id="701ee-135">可选</span><span class="sxs-lookup"><span data-stu-id="701ee-135">Not required</span></span>|<span data-ttu-id="701ee-136">默认值：空</span><span class="sxs-lookup"><span data-stu-id="701ee-136">Default value: empty</span></span>|  
|[<span data-ttu-id="701ee-137">TrackedPropertyNames （架构节点）</span><span class="sxs-lookup"><span data-stu-id="701ee-137">TrackedPropertyNames (Schema Node)</span></span>](../core/trackedpropertynames-schema-node.md)|<span data-ttu-id="701ee-138">录制</span><span class="sxs-lookup"><span data-stu-id="701ee-138">Record</span></span>|<span data-ttu-id="701ee-139">ArrayOfString (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="701ee-139">ArrayOfString (ComplexType)</span></span>|<span data-ttu-id="701ee-140">指定要跟踪的属性的元素的容器。</span><span class="sxs-lookup"><span data-stu-id="701ee-140">Container for the elements that specify the properties to be tracked.</span></span>|<span data-ttu-id="701ee-141">可选</span><span class="sxs-lookup"><span data-stu-id="701ee-141">Not required</span></span>|<span data-ttu-id="701ee-142">默认值：无</span><span class="sxs-lookup"><span data-stu-id="701ee-142">Default value: none</span></span>|