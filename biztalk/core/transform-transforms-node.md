---
title: "转换 （转换节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: 2d1387f1-1668-4982-a717-52478e2a91f9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33e70e5a2bcba2925941e727034b90c9fe4b1418
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transform-transforms-node"></a><span data-ttu-id="3d540-102">Transform（Transforms 节点）</span><span class="sxs-lookup"><span data-stu-id="3d540-102">Transform (Transforms Node)</span></span>
<span data-ttu-id="3d540-103">绑定文件的“转换”节点下的“转换”节点包含有关随同该绑定文件一起导出的 BizTalk Server 映射的特定信息。</span><span class="sxs-lookup"><span data-stu-id="3d540-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="3d540-104">Transform 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="3d540-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="3d540-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="3d540-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3d540-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="3d540-106">**Name**</span></span>|<span data-ttu-id="3d540-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="3d540-107">**Node Type**</span></span>|<span data-ttu-id="3d540-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="3d540-108">**Data Type**</span></span>|<span data-ttu-id="3d540-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="3d540-109">**Description**</span></span>|<span data-ttu-id="3d540-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="3d540-110">**Restrictions**</span></span>|<span data-ttu-id="3d540-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="3d540-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3d540-112">FullName</span><span class="sxs-lookup"><span data-stu-id="3d540-112">FullName</span></span>|<span data-ttu-id="3d540-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d540-113">Attribute</span></span>|<span data-ttu-id="3d540-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d540-114">xs:string</span></span>|<span data-ttu-id="3d540-115">指定映射的全名。</span><span class="sxs-lookup"><span data-stu-id="3d540-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="3d540-116">可选</span><span class="sxs-lookup"><span data-stu-id="3d540-116">Not required</span></span>|<span data-ttu-id="3d540-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="3d540-117">Default value: empty</span></span>|  
|<span data-ttu-id="3d540-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="3d540-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="3d540-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d540-119">Attribute</span></span>|<span data-ttu-id="3d540-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d540-120">xs:string</span></span>|<span data-ttu-id="3d540-121">指定映射的程序集限定名。</span><span class="sxs-lookup"><span data-stu-id="3d540-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="3d540-122">可选</span><span class="sxs-lookup"><span data-stu-id="3d540-122">Not required</span></span>|<span data-ttu-id="3d540-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="3d540-123">Default value: empty</span></span>|