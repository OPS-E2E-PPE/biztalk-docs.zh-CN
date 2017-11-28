---
title: "映射 （映射节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2c62d46e4d5c2b73eee5094ecda0e20c039798a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mapping-mappings-node"></a><span data-ttu-id="8f58b-102">Mapping（Mappings 节点）</span><span class="sxs-lookup"><span data-stu-id="8f58b-102">Mapping (Mappings Node)</span></span>
<span data-ttu-id="8f58b-103">绑定文件的 Mapping 节点描述登记的参与方的参与方端口与角色端口类型操作之间的映射。</span><span class="sxs-lookup"><span data-stu-id="8f58b-103">The Mapping node of a binding file describes the mapping between a party port and role port type operation for the enlisted party.</span></span>  
  
## <a name="nodes-in-the-mapping-node"></a><span data-ttu-id="8f58b-104">Mapping 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="8f58b-104">Nodes in the Mapping node</span></span>  
 <span data-ttu-id="8f58b-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="8f58b-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="8f58b-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="8f58b-106">**Name**</span></span>|<span data-ttu-id="8f58b-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="8f58b-107">**Node Type**</span></span>|<span data-ttu-id="8f58b-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8f58b-108">**Data Type**</span></span>|<span data-ttu-id="8f58b-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="8f58b-109">**Description**</span></span>|<span data-ttu-id="8f58b-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="8f58b-110">**Restrictions**</span></span>|<span data-ttu-id="8f58b-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="8f58b-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="8f58b-112">PortTypeName</span><span class="sxs-lookup"><span data-stu-id="8f58b-112">PortTypeName</span></span>|<span data-ttu-id="8f58b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f58b-113">Attribute</span></span>|<span data-ttu-id="8f58b-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f58b-114">xs:string</span></span>|<span data-ttu-id="8f58b-115">指定端口类型的名称。</span><span class="sxs-lookup"><span data-stu-id="8f58b-115">Specifies the name of the port type.</span></span>|<span data-ttu-id="8f58b-116">可选</span><span class="sxs-lookup"><span data-stu-id="8f58b-116">Not required</span></span>|<span data-ttu-id="8f58b-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="8f58b-117">Default value: empty</span></span>|  
|<span data-ttu-id="8f58b-118">operationName</span><span class="sxs-lookup"><span data-stu-id="8f58b-118">OperationName</span></span>|<span data-ttu-id="8f58b-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="8f58b-119">Attribute</span></span>|<span data-ttu-id="8f58b-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f58b-120">xs:string</span></span>|<span data-ttu-id="8f58b-121">指定属于此端口类型的操作。</span><span class="sxs-lookup"><span data-stu-id="8f58b-121">Specifies the operation belonging to this port type.</span></span>|<span data-ttu-id="8f58b-122">可选</span><span class="sxs-lookup"><span data-stu-id="8f58b-122">Not required</span></span>|<span data-ttu-id="8f58b-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="8f58b-123">Default value: empty</span></span>|  
|[<span data-ttu-id="8f58b-124">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="8f58b-124">SendPortRef</span></span>](../core/sendportref-mapping-node.md)|<span data-ttu-id="8f58b-125">录制</span><span class="sxs-lookup"><span data-stu-id="8f58b-125">Record</span></span>|<span data-ttu-id="8f58b-126">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="8f58b-126">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="8f58b-127">与此映射关联的发送端口列表的容器节点。</span><span class="sxs-lookup"><span data-stu-id="8f58b-127">Container node for the list of send ports associated with a mapping.</span></span>|<span data-ttu-id="8f58b-128">可选</span><span class="sxs-lookup"><span data-stu-id="8f58b-128">Not required</span></span>|<span data-ttu-id="8f58b-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="8f58b-129">Default value: none</span></span>|