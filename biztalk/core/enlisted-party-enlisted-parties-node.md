---
title: "登记方 （登记的方节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624f74d3b49b80e8000723c3f7451c52b37c8d3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enlisted-party-enlisted-parties-node"></a><span data-ttu-id="64f21-102">已登记参与方（“已登记参与方”节点）</span><span class="sxs-lookup"><span data-stu-id="64f21-102">Enlisted Party (Enlisted Parties Node)</span></span>
<span data-ttu-id="64f21-103">绑定文件的“已登记参与方”节点包含有关已登记参与方的特定信息，该已登记参与方与随同该绑定文件一起导出的角色相关联。</span><span class="sxs-lookup"><span data-stu-id="64f21-103">The Enlisted Party node of a binding file contains specific information about an enlisted party associated with a role that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-enlisted-party-node"></a><span data-ttu-id="64f21-104">登记方节点中的节点</span><span class="sxs-lookup"><span data-stu-id="64f21-104">Nodes in the Enlisted Party node</span></span>  
 <span data-ttu-id="64f21-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="64f21-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="64f21-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="64f21-106">**Name**</span></span>|<span data-ttu-id="64f21-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="64f21-107">**Node Type**</span></span>|<span data-ttu-id="64f21-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="64f21-108">**Data Type**</span></span>|<span data-ttu-id="64f21-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="64f21-109">**Description**</span></span>|<span data-ttu-id="64f21-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="64f21-110">**Restrictions**</span></span>|<span data-ttu-id="64f21-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="64f21-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="64f21-112">Name</span><span class="sxs-lookup"><span data-stu-id="64f21-112">Name</span></span>|<span data-ttu-id="64f21-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="64f21-113">Attribute</span></span>|<span data-ttu-id="64f21-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="64f21-114">xs:string</span></span>|<span data-ttu-id="64f21-115">指定已登记参与方的名称。</span><span class="sxs-lookup"><span data-stu-id="64f21-115">Specifies the name of the enlisted party</span></span>|<span data-ttu-id="64f21-116">可选</span><span class="sxs-lookup"><span data-stu-id="64f21-116">Not required</span></span>|<span data-ttu-id="64f21-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="64f21-117">Default value: empty</span></span>|  
|[<span data-ttu-id="64f21-118">映射</span><span class="sxs-lookup"><span data-stu-id="64f21-118">Mappings</span></span>](../core/mappings-enlisted-party-node.md)|<span data-ttu-id="64f21-119">录制</span><span class="sxs-lookup"><span data-stu-id="64f21-119">Record</span></span>|<span data-ttu-id="64f21-120">ArrayOfEnlistedPartyMapping (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="64f21-120">ArrayOfEnlistedPartyMapping (ComplexType)</span></span>|<span data-ttu-id="64f21-121">用于参与方端口和角色端口类型操作之间的映射的容器节点。</span><span class="sxs-lookup"><span data-stu-id="64f21-121">Container node for the mappings between party ports and role port type operations.</span></span>|<span data-ttu-id="64f21-122">可选</span><span class="sxs-lookup"><span data-stu-id="64f21-122">Not required</span></span>|<span data-ttu-id="64f21-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="64f21-123">Default value: none</span></span>|