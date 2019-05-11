---
title: Transform （Transforms 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: 2d1387f1-1668-4982-a717-52478e2a91f9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16eaf34e34c51c48a926b5f4c38daa1adbf9e1f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243070"
---
# <a name="transform-transforms-node"></a><span data-ttu-id="67754-102">Transform （Transforms 节点）</span><span class="sxs-lookup"><span data-stu-id="67754-102">Transform (Transforms Node)</span></span>
<span data-ttu-id="67754-103">绑定文件节点的 Transform 节点包含随绑定文件一起导出的 BizTalk Server 映射有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="67754-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="67754-104">Transform 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="67754-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="67754-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="67754-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="67754-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="67754-106">**Name**</span></span>|<span data-ttu-id="67754-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="67754-107">**Node Type**</span></span>|<span data-ttu-id="67754-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="67754-108">**Data Type**</span></span>|<span data-ttu-id="67754-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="67754-109">**Description**</span></span>|<span data-ttu-id="67754-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="67754-110">**Restrictions**</span></span>|<span data-ttu-id="67754-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="67754-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="67754-112">FullName</span><span class="sxs-lookup"><span data-stu-id="67754-112">FullName</span></span>|<span data-ttu-id="67754-113">特性</span><span class="sxs-lookup"><span data-stu-id="67754-113">Attribute</span></span>|<span data-ttu-id="67754-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="67754-114">xs:string</span></span>|<span data-ttu-id="67754-115">指定的映射的完整名称。</span><span class="sxs-lookup"><span data-stu-id="67754-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="67754-116">可选</span><span class="sxs-lookup"><span data-stu-id="67754-116">Not required</span></span>|<span data-ttu-id="67754-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="67754-117">Default value: empty</span></span>|  
|<span data-ttu-id="67754-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="67754-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="67754-119">特性</span><span class="sxs-lookup"><span data-stu-id="67754-119">Attribute</span></span>|<span data-ttu-id="67754-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="67754-120">xs:string</span></span>|<span data-ttu-id="67754-121">指定映射的程序集限定的名称。</span><span class="sxs-lookup"><span data-stu-id="67754-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="67754-122">可选</span><span class="sxs-lookup"><span data-stu-id="67754-122">Not required</span></span>|<span data-ttu-id="67754-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="67754-123">Default value: empty</span></span>|