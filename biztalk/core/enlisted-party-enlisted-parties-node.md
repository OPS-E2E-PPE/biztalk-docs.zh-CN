---
title: 已登记参与方 （已登记参与方节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 034cc538bb358f887cda761bb0cf6a0d9d1116e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389080"
---
# <a name="enlisted-party-enlisted-parties-node"></a><span data-ttu-id="5e0db-102">已登记参与方 （已登记参与方节点）</span><span class="sxs-lookup"><span data-stu-id="5e0db-102">Enlisted Party (Enlisted Parties Node)</span></span>
<span data-ttu-id="5e0db-103">绑定文件的已登记参与方节点包含有关与绑定文件一起导出的角色相关联的已登记参与方的特定信息。</span><span class="sxs-lookup"><span data-stu-id="5e0db-103">The Enlisted Party node of a binding file contains specific information about an enlisted party associated with a role that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-enlisted-party-node"></a><span data-ttu-id="5e0db-104">在已登记参与方节点的节点</span><span class="sxs-lookup"><span data-stu-id="5e0db-104">Nodes in the Enlisted Party node</span></span>  
 <span data-ttu-id="5e0db-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="5e0db-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="5e0db-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="5e0db-106">**Name**</span></span>|<span data-ttu-id="5e0db-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="5e0db-107">**Node Type**</span></span>|<span data-ttu-id="5e0db-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5e0db-108">**Data Type**</span></span>|<span data-ttu-id="5e0db-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="5e0db-109">**Description**</span></span>|<span data-ttu-id="5e0db-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="5e0db-110">**Restrictions**</span></span>|<span data-ttu-id="5e0db-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="5e0db-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="5e0db-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="5e0db-112">Name</span></span>|<span data-ttu-id="5e0db-113">特性</span><span class="sxs-lookup"><span data-stu-id="5e0db-113">Attribute</span></span>|<span data-ttu-id="5e0db-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e0db-114">xs:string</span></span>|<span data-ttu-id="5e0db-115">指定已登记参与方的名称</span><span class="sxs-lookup"><span data-stu-id="5e0db-115">Specifies the name of the enlisted party</span></span>|<span data-ttu-id="5e0db-116">可选</span><span class="sxs-lookup"><span data-stu-id="5e0db-116">Not required</span></span>|<span data-ttu-id="5e0db-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="5e0db-117">Default value: empty</span></span>|  
|[<span data-ttu-id="5e0db-118">映射</span><span class="sxs-lookup"><span data-stu-id="5e0db-118">Mappings</span></span>](../core/mappings-enlisted-party-node.md)|<span data-ttu-id="5e0db-119">录制</span><span class="sxs-lookup"><span data-stu-id="5e0db-119">Record</span></span>|<span data-ttu-id="5e0db-120">ArrayOfEnlistedPartyMapping (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="5e0db-120">ArrayOfEnlistedPartyMapping (ComplexType)</span></span>|<span data-ttu-id="5e0db-121">参与方端口和角色端口类型操作之间的映射的容器节点。</span><span class="sxs-lookup"><span data-stu-id="5e0db-121">Container node for the mappings between party ports and role port type operations.</span></span>|<span data-ttu-id="5e0db-122">可选</span><span class="sxs-lookup"><span data-stu-id="5e0db-122">Not required</span></span>|<span data-ttu-id="5e0db-123">默认值：无</span><span class="sxs-lookup"><span data-stu-id="5e0db-123">Default value: none</span></span>|