---
title: TrackedSchemas （ModuleRef 节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TrackedSchemas node [binding file]
ms.assetid: a2b99fbf-df6b-4a94-97b8-ac5eb819604f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303aeb1ed17b001583a596d5b550faf63ea1200b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="trackedschemas-moduleref-node"></a><span data-ttu-id="bbbf8-102">TrackedSchemas (ModuleRef 节点)</span><span class="sxs-lookup"><span data-stu-id="bbbf8-102">TrackedSchemas (ModuleRef Node)</span></span>
<span data-ttu-id="bbbf8-103">绑定文件的“TrackedSchemas”节点是所有“架构”节点的父节点，“架构”节点描述了绑定到与绑定文件一起导出的服务的架构。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-103">The TrackedSchemas node of a binding file is the parent node for all of the Schema nodes which describe the schemas bound to the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-trackedschemas-node"></a><span data-ttu-id="bbbf8-104">TrackedSchemas 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="bbbf8-104">Nodes in the TrackedSchemas node</span></span>  
 <span data-ttu-id="bbbf8-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="bbbf8-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="bbbf8-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-106">**Name**</span></span>|<span data-ttu-id="bbbf8-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-107">**Node Type**</span></span>|<span data-ttu-id="bbbf8-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-108">**Data Type**</span></span>|<span data-ttu-id="bbbf8-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-109">**Description**</span></span>|<span data-ttu-id="bbbf8-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-110">**Restrictions**</span></span>|<span data-ttu-id="bbbf8-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="bbbf8-112">架构</span><span class="sxs-lookup"><span data-stu-id="bbbf8-112">Schema</span></span>](../core/schema-trackedschemas-node.md)|<span data-ttu-id="bbbf8-113">录制</span><span class="sxs-lookup"><span data-stu-id="bbbf8-113">Record</span></span>|<span data-ttu-id="bbbf8-114">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="bbbf8-114">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="bbbf8-115">绑定到与绑定文件一起导出的服务的架构的容器节点。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-115">Container node for the schemas that are bound to the service that is exported with the binding file.</span></span>|<span data-ttu-id="bbbf8-116">可选</span><span class="sxs-lookup"><span data-stu-id="bbbf8-116">Not required</span></span>|<span data-ttu-id="bbbf8-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="bbbf8-117">Default value: none</span></span>|