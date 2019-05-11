---
title: DistributionList （DistributionListCollection 节点） |Microsoft Docs
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
ms.openlocfilehash: 732ffa00a2147212e688e9add579044c570faf6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350832"
---
# <a name="distributionlist-distributionlistcollection-node"></a><span data-ttu-id="86d10-102">DistributionList （DistributionListCollection 节点）</span><span class="sxs-lookup"><span data-stu-id="86d10-102">DistributionList (DistributionListCollection Node)</span></span>
<span data-ttu-id="86d10-103">绑定文件的 DistributionList 节点包含有关与绑定文件一起导出的通讯组列表的特定信息。</span><span class="sxs-lookup"><span data-stu-id="86d10-103">The DistributionList node of a binding file contains specific information about a distribution list that is exported with the binding file.</span></span> <span data-ttu-id="86d10-104">通讯组列表称为发送端口组在 BizTalk Server 管理器。</span><span class="sxs-lookup"><span data-stu-id="86d10-104">A distribution list is referred to as a send port group in the BizTalk Server Administrator.</span></span>  
  
## <a name="nodes-in-the-distributionlist-node"></a><span data-ttu-id="86d10-105">DistributionList 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="86d10-105">Nodes in the DistributionList node</span></span>  
 <span data-ttu-id="86d10-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="86d10-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="86d10-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="86d10-107">**Name**</span></span>|<span data-ttu-id="86d10-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="86d10-108">**Node Type**</span></span>|<span data-ttu-id="86d10-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="86d10-109">**Data Type**</span></span>|<span data-ttu-id="86d10-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="86d10-110">**Description**</span></span>|<span data-ttu-id="86d10-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="86d10-111">**Restrictions**</span></span>|<span data-ttu-id="86d10-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="86d10-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="86d10-113">“属性”</span><span class="sxs-lookup"><span data-stu-id="86d10-113">Name</span></span>|<span data-ttu-id="86d10-114">特性</span><span class="sxs-lookup"><span data-stu-id="86d10-114">Attribute</span></span>|<span data-ttu-id="86d10-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="86d10-115">xs:string</span></span>|<span data-ttu-id="86d10-116">指定分发列表的名称。</span><span class="sxs-lookup"><span data-stu-id="86d10-116">Specifies the name of the distribution list.</span></span>|<span data-ttu-id="86d10-117">可选</span><span class="sxs-lookup"><span data-stu-id="86d10-117">Not required</span></span>|<span data-ttu-id="86d10-118">默认值：空</span><span class="sxs-lookup"><span data-stu-id="86d10-118">Default value: empty</span></span>|  
|[<span data-ttu-id="86d10-119">SendPorts</span><span class="sxs-lookup"><span data-stu-id="86d10-119">SendPorts</span></span>](../core/sendports-distributionlist-node.md)|<span data-ttu-id="86d10-120">录制</span><span class="sxs-lookup"><span data-stu-id="86d10-120">Record</span></span>|<span data-ttu-id="86d10-121">ArrayOfSendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="86d10-121">ArrayOfSendPortRef (ComplexType)</span></span>|<span data-ttu-id="86d10-122">指定发送端口或通讯组列表中包含的发送端口。</span><span class="sxs-lookup"><span data-stu-id="86d10-122">Specifies the send port or send ports included in the distribution list.</span></span>|<span data-ttu-id="86d10-123">可选</span><span class="sxs-lookup"><span data-stu-id="86d10-123">Not required</span></span>|<span data-ttu-id="86d10-124">默认值：无</span><span class="sxs-lookup"><span data-stu-id="86d10-124">Default value: none</span></span>|  
|<span data-ttu-id="86d10-125">“筛选器”</span><span class="sxs-lookup"><span data-stu-id="86d10-125">Filter</span></span>|<span data-ttu-id="86d10-126">元素</span><span class="sxs-lookup"><span data-stu-id="86d10-126">Element</span></span>|<span data-ttu-id="86d10-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="86d10-127">xs:string</span></span>|<span data-ttu-id="86d10-128">指定使用此分发列表的可选筛选器表达式的名称。</span><span class="sxs-lookup"><span data-stu-id="86d10-128">Specifies the name of the optional filter expression used on this distribution list.</span></span>|<span data-ttu-id="86d10-129">Required</span><span class="sxs-lookup"><span data-stu-id="86d10-129">Required</span></span>|<span data-ttu-id="86d10-130">默认值：空</span><span class="sxs-lookup"><span data-stu-id="86d10-130">Default value: empty</span></span>|  
|<span data-ttu-id="86d10-131">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="86d10-131">ApplicationName</span></span>|<span data-ttu-id="86d10-132">元素</span><span class="sxs-lookup"><span data-stu-id="86d10-132">Element</span></span>|<span data-ttu-id="86d10-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="86d10-133">xs:string</span></span>|<span data-ttu-id="86d10-134">指定分发列表与之关联的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="86d10-134">Specifies the name of the application that the distribution list is associated with.</span></span>|<span data-ttu-id="86d10-135">Required</span><span class="sxs-lookup"><span data-stu-id="86d10-135">Required</span></span>|<span data-ttu-id="86d10-136">默认值：空</span><span class="sxs-lookup"><span data-stu-id="86d10-136">Default value: empty</span></span>|  
|<span data-ttu-id="86d10-137">Description</span><span class="sxs-lookup"><span data-stu-id="86d10-137">Description</span></span>|<span data-ttu-id="86d10-138">元素</span><span class="sxs-lookup"><span data-stu-id="86d10-138">Element</span></span>|<span data-ttu-id="86d10-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="86d10-139">xs:string</span></span>|<span data-ttu-id="86d10-140">指定分发列表的说明。</span><span class="sxs-lookup"><span data-stu-id="86d10-140">Specifies a description for the distribution list.</span></span>|<span data-ttu-id="86d10-141">Required</span><span class="sxs-lookup"><span data-stu-id="86d10-141">Required</span></span>|<span data-ttu-id="86d10-142">默认值：空</span><span class="sxs-lookup"><span data-stu-id="86d10-142">Default value: empty</span></span>|