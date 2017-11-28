---
title: "转换 （InboundTransforms 节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: c1bad23e-78a4-4fd4-95ef-30601393d53c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 705b1b04b8305330ab1d5ff705c5025f24b0685c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transform-inboundtransforms-node"></a><span data-ttu-id="6025c-102">Transform（InboundTransforms 节点）</span><span class="sxs-lookup"><span data-stu-id="6025c-102">Transform (InboundTransforms Node)</span></span>
<span data-ttu-id="6025c-103">绑定文件的 InboundTransforms 节点的 Transform 节点包含与该绑定文件一起导出的 BizTalk Server 映射有关的信息。</span><span class="sxs-lookup"><span data-stu-id="6025c-103">The Transform node of the InboundTransforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="6025c-104">Transform 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="6025c-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="6025c-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="6025c-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="6025c-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="6025c-106">**Name**</span></span>|<span data-ttu-id="6025c-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="6025c-107">**Node Type**</span></span>|<span data-ttu-id="6025c-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="6025c-108">**Data Type**</span></span>|<span data-ttu-id="6025c-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="6025c-109">**Description**</span></span>|<span data-ttu-id="6025c-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="6025c-110">**Restrictions**</span></span>|<span data-ttu-id="6025c-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="6025c-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="6025c-112">FullName</span><span class="sxs-lookup"><span data-stu-id="6025c-112">FullName</span></span>|<span data-ttu-id="6025c-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="6025c-113">Attribute</span></span>|<span data-ttu-id="6025c-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="6025c-114">xs:string</span></span>|<span data-ttu-id="6025c-115">指定映射的全名。</span><span class="sxs-lookup"><span data-stu-id="6025c-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="6025c-116">可选</span><span class="sxs-lookup"><span data-stu-id="6025c-116">Not required</span></span>|<span data-ttu-id="6025c-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="6025c-117">Default value: empty</span></span>|  
|<span data-ttu-id="6025c-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="6025c-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="6025c-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="6025c-119">Attribute</span></span>|<span data-ttu-id="6025c-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="6025c-120">xs:string</span></span>|<span data-ttu-id="6025c-121">指定映射的程序集限定名。</span><span class="sxs-lookup"><span data-stu-id="6025c-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="6025c-122">可选</span><span class="sxs-lookup"><span data-stu-id="6025c-122">Not required</span></span>|<span data-ttu-id="6025c-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="6025c-123">Default value: empty</span></span>|