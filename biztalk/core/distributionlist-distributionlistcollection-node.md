---
title: DistributionList （DistributionListCollection 节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionList node [binding file]
ms.assetid: 51864a5c-1697-4804-ac18-8211494f3ff0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 931443cdca27e5c06767f075298d50ff999545a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239333"
---
# <a name="distributionlist-distributionlistcollection-node"></a><span data-ttu-id="a7426-102">DistributionList （DistributionListCollection 节点）</span><span class="sxs-lookup"><span data-stu-id="a7426-102">DistributionList (DistributionListCollection Node)</span></span>
<span data-ttu-id="a7426-103">绑定文件的 DistributionList 节点包含有关与绑定文件一起导出的分发列表的特定信息。</span><span class="sxs-lookup"><span data-stu-id="a7426-103">The DistributionList node of a binding file contains specific information about a distribution list that is exported with the binding file.</span></span> <span data-ttu-id="a7426-104">分发列表指 BizTalk Server Administrator 组中的发送端口组。</span><span class="sxs-lookup"><span data-stu-id="a7426-104">A distribution list is referred to as a send port group in the BizTalk Server Administrator.</span></span>  
  
## <a name="nodes-in-the-distributionlist-node"></a><span data-ttu-id="a7426-105">DistributionList 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="a7426-105">Nodes in the DistributionList node</span></span>  
 <span data-ttu-id="a7426-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="a7426-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="a7426-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="a7426-107">**Name**</span></span>|<span data-ttu-id="a7426-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="a7426-108">**Node Type**</span></span>|<span data-ttu-id="a7426-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a7426-109">**Data Type**</span></span>|<span data-ttu-id="a7426-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="a7426-110">**Description**</span></span>|<span data-ttu-id="a7426-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="a7426-111">**Restrictions**</span></span>|<span data-ttu-id="a7426-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="a7426-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="a7426-113">Name</span><span class="sxs-lookup"><span data-stu-id="a7426-113">Name</span></span>|<span data-ttu-id="a7426-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7426-114">Attribute</span></span>|<span data-ttu-id="a7426-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="a7426-115">xs:string</span></span>|<span data-ttu-id="a7426-116">指定分发列表的名称。</span><span class="sxs-lookup"><span data-stu-id="a7426-116">Specifies the name of the distribution list.</span></span>|<span data-ttu-id="a7426-117">可选</span><span class="sxs-lookup"><span data-stu-id="a7426-117">Not required</span></span>|<span data-ttu-id="a7426-118">默认值：空</span><span class="sxs-lookup"><span data-stu-id="a7426-118">Default value: empty</span></span>|  
|[<span data-ttu-id="a7426-119">发送端口</span><span class="sxs-lookup"><span data-stu-id="a7426-119">SendPorts</span></span>](../core/sendports-distributionlist-node.md)|<span data-ttu-id="a7426-120">录制</span><span class="sxs-lookup"><span data-stu-id="a7426-120">Record</span></span>|<span data-ttu-id="a7426-121">ArrayOfSendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="a7426-121">ArrayOfSendPortRef (ComplexType)</span></span>|<span data-ttu-id="a7426-122">指定在分发列表中包括的一个或多个发送端口。</span><span class="sxs-lookup"><span data-stu-id="a7426-122">Specifies the send port or send ports included in the distribution list.</span></span>|<span data-ttu-id="a7426-123">可选</span><span class="sxs-lookup"><span data-stu-id="a7426-123">Not required</span></span>|<span data-ttu-id="a7426-124">默认值：无</span><span class="sxs-lookup"><span data-stu-id="a7426-124">Default value: none</span></span>|  
|<span data-ttu-id="a7426-125">“筛选器”</span><span class="sxs-lookup"><span data-stu-id="a7426-125">Filter</span></span>|<span data-ttu-id="a7426-126">元素</span><span class="sxs-lookup"><span data-stu-id="a7426-126">Element</span></span>|<span data-ttu-id="a7426-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a7426-127">xs:string</span></span>|<span data-ttu-id="a7426-128">指定此分发列表中使用的可选筛选器表达式的名称。</span><span class="sxs-lookup"><span data-stu-id="a7426-128">Specifies the name of the optional filter expression used on this distribution list.</span></span>|<span data-ttu-id="a7426-129">必需</span><span class="sxs-lookup"><span data-stu-id="a7426-129">Required</span></span>|<span data-ttu-id="a7426-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="a7426-130">Default value: empty</span></span>|  
|<span data-ttu-id="a7426-131">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="a7426-131">ApplicationName</span></span>|<span data-ttu-id="a7426-132">元素</span><span class="sxs-lookup"><span data-stu-id="a7426-132">Element</span></span>|<span data-ttu-id="a7426-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="a7426-133">xs:string</span></span>|<span data-ttu-id="a7426-134">指定分发列表与之关联的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a7426-134">Specifies the name of the application that the distribution list is associated with.</span></span>|<span data-ttu-id="a7426-135">必需</span><span class="sxs-lookup"><span data-stu-id="a7426-135">Required</span></span>|<span data-ttu-id="a7426-136">默认值：空</span><span class="sxs-lookup"><span data-stu-id="a7426-136">Default value: empty</span></span>|  
|<span data-ttu-id="a7426-137">Description</span><span class="sxs-lookup"><span data-stu-id="a7426-137">Description</span></span>|<span data-ttu-id="a7426-138">元素</span><span class="sxs-lookup"><span data-stu-id="a7426-138">Element</span></span>|<span data-ttu-id="a7426-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="a7426-139">xs:string</span></span>|<span data-ttu-id="a7426-140">指定分发列表的说明。</span><span class="sxs-lookup"><span data-stu-id="a7426-140">Specifies a description for the distribution list.</span></span>|<span data-ttu-id="a7426-141">必需</span><span class="sxs-lookup"><span data-stu-id="a7426-141">Required</span></span>|<span data-ttu-id="a7426-142">默认值：空</span><span class="sxs-lookup"><span data-stu-id="a7426-142">Default value: empty</span></span>|