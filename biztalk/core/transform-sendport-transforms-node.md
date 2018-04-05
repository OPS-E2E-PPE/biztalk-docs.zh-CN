---
title: 转换 （发送端口转换节点） |Microsoft 文档
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
ms.openlocfilehash: 0a54ed1f25b762d12f598bca84da9b9c3ddd26a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transform-sendport-transforms-node"></a><span data-ttu-id="a1501-102">转换 （发送端口转换节点）</span><span class="sxs-lookup"><span data-stu-id="a1501-102">Transform (SendPort-Transforms Node)</span></span>
<span data-ttu-id="a1501-103">绑定文件的“转换”节点下的“转换”节点包含有关随同该绑定文件一起导出的 BizTalk Server 映射的特定信息。</span><span class="sxs-lookup"><span data-stu-id="a1501-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="a1501-104">Transform 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="a1501-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="a1501-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="a1501-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="a1501-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="a1501-106">**Name**</span></span>|<span data-ttu-id="a1501-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="a1501-107">**Node Type**</span></span>|<span data-ttu-id="a1501-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a1501-108">**Data Type**</span></span>|<span data-ttu-id="a1501-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="a1501-109">**Description**</span></span>|<span data-ttu-id="a1501-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="a1501-110">**Restrictions**</span></span>|<span data-ttu-id="a1501-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="a1501-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="a1501-112">FullName</span><span class="sxs-lookup"><span data-stu-id="a1501-112">FullName</span></span>|<span data-ttu-id="a1501-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1501-113">Attribute</span></span>|<span data-ttu-id="a1501-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="a1501-114">xs:string</span></span>|<span data-ttu-id="a1501-115">指定映射的全名。</span><span class="sxs-lookup"><span data-stu-id="a1501-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="a1501-116">可选</span><span class="sxs-lookup"><span data-stu-id="a1501-116">Not required</span></span>|<span data-ttu-id="a1501-117">默认值：空</span><span class="sxs-lookup"><span data-stu-id="a1501-117">Default value: empty</span></span>|  
|<span data-ttu-id="a1501-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="a1501-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="a1501-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1501-119">Attribute</span></span>|<span data-ttu-id="a1501-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="a1501-120">xs:string</span></span>|<span data-ttu-id="a1501-121">指定映射的程序集限定名。</span><span class="sxs-lookup"><span data-stu-id="a1501-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="a1501-122">可选</span><span class="sxs-lookup"><span data-stu-id="a1501-122">Not required</span></span>|<span data-ttu-id="a1501-123">默认值：空</span><span class="sxs-lookup"><span data-stu-id="a1501-123">Default value: empty</span></span>|