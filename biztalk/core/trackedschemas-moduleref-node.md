---
title: TrackedSchemas （ModuleRef 节点） |Microsoft Docs
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
ms.openlocfilehash: 0aa14543e64685e6f12a268c4e825c01d277fda9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313976"
---
# <a name="trackedschemas-moduleref-node"></a><span data-ttu-id="022b3-102">TrackedSchemas （ModuleRef 节点）</span><span class="sxs-lookup"><span data-stu-id="022b3-102">TrackedSchemas (ModuleRef Node)</span></span>
<span data-ttu-id="022b3-103">绑定文件的 TrackedSchemas 节点是所有描述绑定到与绑定文件一起导出的服务的架构的架构节点的父节点。</span><span class="sxs-lookup"><span data-stu-id="022b3-103">The TrackedSchemas node of a binding file is the parent node for all of the Schema nodes which describe the schemas bound to the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-trackedschemas-node"></a><span data-ttu-id="022b3-104">TrackedSchemas 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="022b3-104">Nodes in the TrackedSchemas node</span></span>  
 <span data-ttu-id="022b3-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="022b3-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="022b3-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="022b3-106">**Name**</span></span>|<span data-ttu-id="022b3-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="022b3-107">**Node Type**</span></span>|<span data-ttu-id="022b3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="022b3-108">**Data Type**</span></span>|<span data-ttu-id="022b3-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="022b3-109">**Description**</span></span>|<span data-ttu-id="022b3-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="022b3-110">**Restrictions**</span></span>|<span data-ttu-id="022b3-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="022b3-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="022b3-112">架构</span><span class="sxs-lookup"><span data-stu-id="022b3-112">Schema</span></span>](../core/schema-trackedschemas-node.md)|<span data-ttu-id="022b3-113">录制</span><span class="sxs-lookup"><span data-stu-id="022b3-113">Record</span></span>|<span data-ttu-id="022b3-114">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="022b3-114">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="022b3-115">绑定到与绑定文件一起导出的服务的架构的容器节点。</span><span class="sxs-lookup"><span data-stu-id="022b3-115">Container node for the schemas that are bound to the service that is exported with the binding file.</span></span>|<span data-ttu-id="022b3-116">可选</span><span class="sxs-lookup"><span data-stu-id="022b3-116">Not required</span></span>|<span data-ttu-id="022b3-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="022b3-117">Default value: none</span></span>|