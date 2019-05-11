---
title: Transform （InboundTransforms 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: c1bad23e-78a4-4fd4-95ef-30601393d53c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93ae620e3f9f40e2f76b814dbfde4b45910c63c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399191"
---
# <a name="transform-inboundtransforms-node"></a><span data-ttu-id="78ac6-102">Transform （InboundTransforms 节点）</span><span class="sxs-lookup"><span data-stu-id="78ac6-102">Transform (InboundTransforms Node)</span></span>
<span data-ttu-id="78ac6-103">绑定文件的 InboundTransforms 节点的 Transform 节点包含随绑定文件一起导出的 BizTalk Server 映射有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="78ac6-103">The Transform node of the InboundTransforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="78ac6-104">Transform 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="78ac6-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="78ac6-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="78ac6-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="78ac6-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="78ac6-106">**Name**</span></span>|<span data-ttu-id="78ac6-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="78ac6-107">**Node Type**</span></span>|<span data-ttu-id="78ac6-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="78ac6-108">**Data Type**</span></span>|<span data-ttu-id="78ac6-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="78ac6-109">**Description**</span></span>|<span data-ttu-id="78ac6-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="78ac6-110">**Restrictions**</span></span>|<span data-ttu-id="78ac6-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="78ac6-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="78ac6-112">FullName</span><span class="sxs-lookup"><span data-stu-id="78ac6-112">FullName</span></span>|<span data-ttu-id="78ac6-113">特性</span><span class="sxs-lookup"><span data-stu-id="78ac6-113">Attribute</span></span>|<span data-ttu-id="78ac6-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="78ac6-114">xs:string</span></span>|<span data-ttu-id="78ac6-115">指定的映射的完整名称。</span><span class="sxs-lookup"><span data-stu-id="78ac6-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="78ac6-116">可选</span><span class="sxs-lookup"><span data-stu-id="78ac6-116">Not required</span></span>|<span data-ttu-id="78ac6-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="78ac6-117">Default value: empty</span></span>|  
|<span data-ttu-id="78ac6-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="78ac6-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="78ac6-119">特性</span><span class="sxs-lookup"><span data-stu-id="78ac6-119">Attribute</span></span>|<span data-ttu-id="78ac6-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="78ac6-120">xs:string</span></span>|<span data-ttu-id="78ac6-121">指定映射的程序集限定的名称。</span><span class="sxs-lookup"><span data-stu-id="78ac6-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="78ac6-122">可选</span><span class="sxs-lookup"><span data-stu-id="78ac6-122">Not required</span></span>|<span data-ttu-id="78ac6-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="78ac6-123">Default value: empty</span></span>|