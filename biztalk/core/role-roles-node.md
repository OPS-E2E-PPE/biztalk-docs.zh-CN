---
title: "角色 （角色节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Role node [binding file]
ms.assetid: dfe2a579-7090-4d85-87e5-d627598c4ee8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d70e99568db262ef5abd5b0885cb814c722347f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="role-roles-node"></a><span data-ttu-id="428f5-102">角色（“角色”节点）</span><span class="sxs-lookup"><span data-stu-id="428f5-102">Role (Roles Node)</span></span>
<span data-ttu-id="428f5-103">绑定文件的“角色”节点的“角色”节点指定了与绑定到随绑定文件一起导出的服务的角色有关的信息。</span><span class="sxs-lookup"><span data-stu-id="428f5-103">The Role node of the Roles node of a binding file specifies information about a role that is bound to a service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-role-node"></a><span data-ttu-id="428f5-104">在角色节点的节点</span><span class="sxs-lookup"><span data-stu-id="428f5-104">Nodes in the Role node</span></span>  
 <span data-ttu-id="428f5-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="428f5-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="428f5-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="428f5-106">**Name**</span></span>|<span data-ttu-id="428f5-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="428f5-107">**Node Type**</span></span>|<span data-ttu-id="428f5-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="428f5-108">**Data Type**</span></span>|<span data-ttu-id="428f5-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="428f5-109">**Description**</span></span>|<span data-ttu-id="428f5-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="428f5-110">**Restrictions**</span></span>|<span data-ttu-id="428f5-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="428f5-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="428f5-112">Name</span><span class="sxs-lookup"><span data-stu-id="428f5-112">Name</span></span>|<span data-ttu-id="428f5-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="428f5-113">Attribute</span></span>|<span data-ttu-id="428f5-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="428f5-114">xs:string</span></span>|<span data-ttu-id="428f5-115">指定角色的名称。</span><span class="sxs-lookup"><span data-stu-id="428f5-115">Specifies the name of the role.</span></span>|<span data-ttu-id="428f5-116">可选</span><span class="sxs-lookup"><span data-stu-id="428f5-116">Not required</span></span>|<span data-ttu-id="428f5-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="428f5-117">Default value: empty</span></span>|  
|<span data-ttu-id="428f5-118">RoleLinkTypeName</span><span class="sxs-lookup"><span data-stu-id="428f5-118">RoleLinkTypeName</span></span>|<span data-ttu-id="428f5-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="428f5-119">Attribute</span></span>|<span data-ttu-id="428f5-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="428f5-120">xs:string</span></span>|<span data-ttu-id="428f5-121">指定与角色相关联的角色链接类型的名称</span><span class="sxs-lookup"><span data-stu-id="428f5-121">Specifies the name of the role link type associated with the role</span></span>|<span data-ttu-id="428f5-122">可选</span><span class="sxs-lookup"><span data-stu-id="428f5-122">Not required</span></span>|<span data-ttu-id="428f5-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="428f5-123">Default value: empty</span></span>|  
|<span data-ttu-id="428f5-124">RoleType</span><span class="sxs-lookup"><span data-stu-id="428f5-124">RoleType</span></span>|<span data-ttu-id="428f5-125">Attribute</span><span class="sxs-lookup"><span data-stu-id="428f5-125">Attribute</span></span>|<span data-ttu-id="428f5-126">RoleRefType (SimpleType)</span><span class="sxs-lookup"><span data-stu-id="428f5-126">RoleRefType (SimpleType)</span></span>|<span data-ttu-id="428f5-127">指定与角色相关联的角色类型。</span><span class="sxs-lookup"><span data-stu-id="428f5-127">Specifies the role type associated with the role.</span></span>|<span data-ttu-id="428f5-128">必需</span><span class="sxs-lookup"><span data-stu-id="428f5-128">Required</span></span>|<span data-ttu-id="428f5-129">默认值：无</span><span class="sxs-lookup"><span data-stu-id="428f5-129">Default value: none</span></span><br /><br /> <span data-ttu-id="428f5-130">可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="428f5-130">Possible values include:</span></span><br /><br /> <span data-ttu-id="428f5-131">-未知</span><span class="sxs-lookup"><span data-stu-id="428f5-131">-   Unknown</span></span><br /><span data-ttu-id="428f5-132">实现</span><span class="sxs-lookup"><span data-stu-id="428f5-132">-   Implements</span></span><br /><span data-ttu-id="428f5-133">-使用</span><span class="sxs-lookup"><span data-stu-id="428f5-133">-   Uses</span></span>|  
|[<span data-ttu-id="428f5-134">已登记参与方</span><span class="sxs-lookup"><span data-stu-id="428f5-134">Enlisted Parties</span></span>](../core/enlisted-parties-role-node.md)|<span data-ttu-id="428f5-135">录制</span><span class="sxs-lookup"><span data-stu-id="428f5-135">Record</span></span>|<span data-ttu-id="428f5-136">ArrayOfEnlistedParty (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="428f5-136">ArrayOfEnlistedParty (ComplexType)</span></span>|<span data-ttu-id="428f5-137">绑定到此角色的已登记参与方的容器节点。</span><span class="sxs-lookup"><span data-stu-id="428f5-137">Container node for the enlisted parties bound to this role.</span></span>|<span data-ttu-id="428f5-138">可选</span><span class="sxs-lookup"><span data-stu-id="428f5-138">Not required</span></span>|<span data-ttu-id="428f5-139">默认值：无</span><span class="sxs-lookup"><span data-stu-id="428f5-139">Default value: none</span></span>|