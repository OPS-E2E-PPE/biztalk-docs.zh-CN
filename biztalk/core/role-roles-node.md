---
title: 角色 （角色节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Role node [binding file]
ms.assetid: dfe2a579-7090-4d85-87e5-d627598c4ee8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 652702d35eb0ab1f9fd974491e5ae94e2a1cec4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254704"
---
# <a name="role-roles-node"></a><span data-ttu-id="f6b46-102">角色 （角色节点）</span><span class="sxs-lookup"><span data-stu-id="f6b46-102">Role (Roles Node)</span></span>
<span data-ttu-id="f6b46-103">绑定文件的角色节点的角色节点指定绑定到与绑定文件一起导出的服务的角色有关的信息。</span><span class="sxs-lookup"><span data-stu-id="f6b46-103">The Role node of the Roles node of a binding file specifies information about a role that is bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-role-node"></a><span data-ttu-id="f6b46-104">节点中的角色节点</span><span class="sxs-lookup"><span data-stu-id="f6b46-104">Nodes in the Role node</span></span>  
 <span data-ttu-id="f6b46-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="f6b46-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="f6b46-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="f6b46-106">**Name**</span></span>|<span data-ttu-id="f6b46-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="f6b46-107">**Node Type**</span></span>|<span data-ttu-id="f6b46-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f6b46-108">**Data Type**</span></span>|<span data-ttu-id="f6b46-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6b46-109">**Description**</span></span>|<span data-ttu-id="f6b46-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="f6b46-110">**Restrictions**</span></span>|<span data-ttu-id="f6b46-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="f6b46-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="f6b46-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="f6b46-112">Name</span></span>|<span data-ttu-id="f6b46-113">特性</span><span class="sxs-lookup"><span data-stu-id="f6b46-113">Attribute</span></span>|<span data-ttu-id="f6b46-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6b46-114">xs:string</span></span>|<span data-ttu-id="f6b46-115">指定的角色的名称。</span><span class="sxs-lookup"><span data-stu-id="f6b46-115">Specifies the name of the role.</span></span>|<span data-ttu-id="f6b46-116">可选</span><span class="sxs-lookup"><span data-stu-id="f6b46-116">Not required</span></span>|<span data-ttu-id="f6b46-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="f6b46-117">Default value: empty</span></span>|  
|<span data-ttu-id="f6b46-118">RoleLinkTypeName</span><span class="sxs-lookup"><span data-stu-id="f6b46-118">RoleLinkTypeName</span></span>|<span data-ttu-id="f6b46-119">特性</span><span class="sxs-lookup"><span data-stu-id="f6b46-119">Attribute</span></span>|<span data-ttu-id="f6b46-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6b46-120">xs:string</span></span>|<span data-ttu-id="f6b46-121">指定与角色关联的角色链接类型的名称</span><span class="sxs-lookup"><span data-stu-id="f6b46-121">Specifies the name of the role link type associated with the role</span></span>|<span data-ttu-id="f6b46-122">可选</span><span class="sxs-lookup"><span data-stu-id="f6b46-122">Not required</span></span>|<span data-ttu-id="f6b46-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="f6b46-123">Default value: empty</span></span>|  
|<span data-ttu-id="f6b46-124">RoleType</span><span class="sxs-lookup"><span data-stu-id="f6b46-124">RoleType</span></span>|<span data-ttu-id="f6b46-125">特性</span><span class="sxs-lookup"><span data-stu-id="f6b46-125">Attribute</span></span>|<span data-ttu-id="f6b46-126">RoleRefType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="f6b46-126">RoleRefType (SimpleType)</span></span>|<span data-ttu-id="f6b46-127">指定与角色关联的角色类型。</span><span class="sxs-lookup"><span data-stu-id="f6b46-127">Specifies the role type associated with the role.</span></span>|<span data-ttu-id="f6b46-128">Required</span><span class="sxs-lookup"><span data-stu-id="f6b46-128">Required</span></span>|<span data-ttu-id="f6b46-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="f6b46-129">Default value: none</span></span><br /><br /> <span data-ttu-id="f6b46-130">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="f6b46-130">Possible values include:</span></span><br /><br /> <span data-ttu-id="f6b46-131">-未知</span><span class="sxs-lookup"><span data-stu-id="f6b46-131">-   Unknown</span></span><br /><span data-ttu-id="f6b46-132">实现</span><span class="sxs-lookup"><span data-stu-id="f6b46-132">-   Implements</span></span><br /><span data-ttu-id="f6b46-133">-使用</span><span class="sxs-lookup"><span data-stu-id="f6b46-133">-   Uses</span></span>|  
|[<span data-ttu-id="f6b46-134">已登记参与方</span><span class="sxs-lookup"><span data-stu-id="f6b46-134">Enlisted Parties</span></span>](../core/enlisted-parties-role-node.md)|<span data-ttu-id="f6b46-135">录制</span><span class="sxs-lookup"><span data-stu-id="f6b46-135">Record</span></span>|<span data-ttu-id="f6b46-136">ArrayOfEnlistedParty (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="f6b46-136">ArrayOfEnlistedParty (ComplexType)</span></span>|<span data-ttu-id="f6b46-137">已登记的参与方绑定到此角色的容器节点。</span><span class="sxs-lookup"><span data-stu-id="f6b46-137">Container node for the enlisted parties bound to this role.</span></span>|<span data-ttu-id="f6b46-138">可选</span><span class="sxs-lookup"><span data-stu-id="f6b46-138">Not required</span></span>|<span data-ttu-id="f6b46-139">默认值：无</span><span class="sxs-lookup"><span data-stu-id="f6b46-139">Default value: none</span></span>|