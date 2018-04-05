---
title: 转换 （OutboundTransforms 节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: 928a93cd-7a26-4148-b1af-dc0bc316f8c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b44dc5ffd444ebaee8f1f3007f27343c389c5e5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transform-outboundtransforms-node"></a><span data-ttu-id="66bb3-102">转换 （OutboundTransforms 节点）</span><span class="sxs-lookup"><span data-stu-id="66bb3-102">Transform (OutboundTransforms Node)</span></span>
<span data-ttu-id="66bb3-103">绑定文件的 OutboundTransforms 节点的 Transform 节点包含与随该绑定文件一起导出的 BizTalk Server 映射有关的特定信息。</span><span class="sxs-lookup"><span data-stu-id="66bb3-103">The Transform node of the OutboundTransforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="66bb3-104">Transform 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="66bb3-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="66bb3-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="66bb3-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="66bb3-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="66bb3-106">**Name**</span></span>|<span data-ttu-id="66bb3-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="66bb3-107">**Node Type**</span></span>|<span data-ttu-id="66bb3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="66bb3-108">**Data Type**</span></span>|<span data-ttu-id="66bb3-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="66bb3-109">**Description**</span></span>|<span data-ttu-id="66bb3-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="66bb3-110">**Restrictions**</span></span>|<span data-ttu-id="66bb3-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="66bb3-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="66bb3-112">FullName</span><span class="sxs-lookup"><span data-stu-id="66bb3-112">FullName</span></span>|<span data-ttu-id="66bb3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="66bb3-113">Attribute</span></span>|<span data-ttu-id="66bb3-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb3-114">xs:string</span></span>|<span data-ttu-id="66bb3-115">指定映射的全名。</span><span class="sxs-lookup"><span data-stu-id="66bb3-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="66bb3-116">可选</span><span class="sxs-lookup"><span data-stu-id="66bb3-116">Not required</span></span>|<span data-ttu-id="66bb3-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="66bb3-117">Default value: empty</span></span>|  
|<span data-ttu-id="66bb3-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="66bb3-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="66bb3-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="66bb3-119">Attribute</span></span>|<span data-ttu-id="66bb3-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="66bb3-120">xs:string</span></span>|<span data-ttu-id="66bb3-121">指定映射的程序集限定名。</span><span class="sxs-lookup"><span data-stu-id="66bb3-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="66bb3-122">可选</span><span class="sxs-lookup"><span data-stu-id="66bb3-122">Not required</span></span>|<span data-ttu-id="66bb3-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="66bb3-123">Default value: empty</span></span>|