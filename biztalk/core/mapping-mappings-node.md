---
title: Mapping （Mappings 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e227dd0c22734e0d448aebc0bbf4a8960575a5e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325669"
---
# <a name="mapping-mappings-node"></a><span data-ttu-id="c8c4f-102">Mapping （Mappings 节点）</span><span class="sxs-lookup"><span data-stu-id="c8c4f-102">Mapping (Mappings Node)</span></span>
<span data-ttu-id="c8c4f-103">绑定文件的 Mapping 节点描述了参与方端口和角色端口类型操作登记的参与方之间的映射。</span><span class="sxs-lookup"><span data-stu-id="c8c4f-103">The Mapping node of a binding file describes the mapping between a party port and role port type operation for the enlisted party.</span></span>  
  
## <a name="nodes-in-the-mapping-node"></a><span data-ttu-id="c8c4f-104">在映射节点的节点</span><span class="sxs-lookup"><span data-stu-id="c8c4f-104">Nodes in the Mapping node</span></span>  
 <span data-ttu-id="c8c4f-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="c8c4f-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c8c4f-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="c8c4f-106">**Name**</span></span>|<span data-ttu-id="c8c4f-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="c8c4f-107">**Node Type**</span></span>|<span data-ttu-id="c8c4f-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c8c4f-108">**Data Type**</span></span>|<span data-ttu-id="c8c4f-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="c8c4f-109">**Description**</span></span>|<span data-ttu-id="c8c4f-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="c8c4f-110">**Restrictions**</span></span>|<span data-ttu-id="c8c4f-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="c8c4f-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="c8c4f-112">PortTypeName</span><span class="sxs-lookup"><span data-stu-id="c8c4f-112">PortTypeName</span></span>|<span data-ttu-id="c8c4f-113">特性</span><span class="sxs-lookup"><span data-stu-id="c8c4f-113">Attribute</span></span>|<span data-ttu-id="c8c4f-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8c4f-114">xs:string</span></span>|<span data-ttu-id="c8c4f-115">指定端口类型的名称。</span><span class="sxs-lookup"><span data-stu-id="c8c4f-115">Specifies the name of the port type.</span></span>|<span data-ttu-id="c8c4f-116">可选</span><span class="sxs-lookup"><span data-stu-id="c8c4f-116">Not required</span></span>|<span data-ttu-id="c8c4f-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="c8c4f-117">Default value: empty</span></span>|  
|<span data-ttu-id="c8c4f-118">OperationName</span><span class="sxs-lookup"><span data-stu-id="c8c4f-118">OperationName</span></span>|<span data-ttu-id="c8c4f-119">特性</span><span class="sxs-lookup"><span data-stu-id="c8c4f-119">Attribute</span></span>|<span data-ttu-id="c8c4f-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8c4f-120">xs:string</span></span>|<span data-ttu-id="c8c4f-121">指定属于此端口类型操作。</span><span class="sxs-lookup"><span data-stu-id="c8c4f-121">Specifies the operation belonging to this port type.</span></span>|<span data-ttu-id="c8c4f-122">可选</span><span class="sxs-lookup"><span data-stu-id="c8c4f-122">Not required</span></span>|<span data-ttu-id="c8c4f-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="c8c4f-123">Default value: empty</span></span>|  
|[<span data-ttu-id="c8c4f-124">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="c8c4f-124">SendPortRef</span></span>](../core/sendportref-mapping-node.md)|<span data-ttu-id="c8c4f-125">录制</span><span class="sxs-lookup"><span data-stu-id="c8c4f-125">Record</span></span>|<span data-ttu-id="c8c4f-126">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="c8c4f-126">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="c8c4f-127">与映射关联的发送端口的列表的容器节点。</span><span class="sxs-lookup"><span data-stu-id="c8c4f-127">Container node for the list of send ports associated with a mapping.</span></span>|<span data-ttu-id="c8c4f-128">可选</span><span class="sxs-lookup"><span data-stu-id="c8c4f-128">Not required</span></span>|<span data-ttu-id="c8c4f-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="c8c4f-129">Default value: none</span></span>|