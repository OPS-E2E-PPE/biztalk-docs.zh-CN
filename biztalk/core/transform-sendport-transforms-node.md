---
title: Transform （Sendport-transforms 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: db9a82b2-9bc1-4bd8-8d98-a708a8d25b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca25040f9f462b35e1fd91f9afc6b1758c6559f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303031"
---
# <a name="transform-sendport-transforms-node"></a><span data-ttu-id="c9425-102">Transform （Sendport-transforms 节点）</span><span class="sxs-lookup"><span data-stu-id="c9425-102">Transform (SendPort-Transforms Node)</span></span>
<span data-ttu-id="c9425-103">绑定文件节点的 Transform 节点包含随绑定文件一起导出的 BizTalk Server 映射有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="c9425-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="c9425-104">Transform 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="c9425-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="c9425-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="c9425-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c9425-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="c9425-106">**Name**</span></span>|<span data-ttu-id="c9425-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="c9425-107">**Node Type**</span></span>|<span data-ttu-id="c9425-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c9425-108">**Data Type**</span></span>|<span data-ttu-id="c9425-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="c9425-109">**Description**</span></span>|<span data-ttu-id="c9425-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="c9425-110">**Restrictions**</span></span>|<span data-ttu-id="c9425-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="c9425-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="c9425-112">FullName</span><span class="sxs-lookup"><span data-stu-id="c9425-112">FullName</span></span>|<span data-ttu-id="c9425-113">特性</span><span class="sxs-lookup"><span data-stu-id="c9425-113">Attribute</span></span>|<span data-ttu-id="c9425-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="c9425-114">xs:string</span></span>|<span data-ttu-id="c9425-115">指定的映射的完整名称。</span><span class="sxs-lookup"><span data-stu-id="c9425-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="c9425-116">可选</span><span class="sxs-lookup"><span data-stu-id="c9425-116">Not required</span></span>|<span data-ttu-id="c9425-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="c9425-117">Default value: empty</span></span>|  
|<span data-ttu-id="c9425-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="c9425-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="c9425-119">特性</span><span class="sxs-lookup"><span data-stu-id="c9425-119">Attribute</span></span>|<span data-ttu-id="c9425-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="c9425-120">xs:string</span></span>|<span data-ttu-id="c9425-121">指定映射的程序集限定的名称。</span><span class="sxs-lookup"><span data-stu-id="c9425-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="c9425-122">可选</span><span class="sxs-lookup"><span data-stu-id="c9425-122">Not required</span></span>|<span data-ttu-id="c9425-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="c9425-123">Default value: empty</span></span>|