---
title: ModuleRef （ModuleRefCollection 节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRef node [binding file]
ms.assetid: 61787779-33bd-499a-a5c1-c1e0bd306b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed580b022e9896ade824c8cf8eccc2458c7ddce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262901"
---
# <a name="moduleref-modulerefcollection-node"></a><span data-ttu-id="817b6-102">ModuleRef （ModuleRefCollection 节点）</span><span class="sxs-lookup"><span data-stu-id="817b6-102">ModuleRef (ModuleRefCollection Node)</span></span>
<span data-ttu-id="817b6-103">绑定文件的 ModuleRef 节点包含有关与该绑定文件一起导出的 .NET 程序集的特定信息。</span><span class="sxs-lookup"><span data-stu-id="817b6-103">The ModuleRef node of a binding file contains specific information about a .NET assembly that was exported with the binding file.</span></span> <span data-ttu-id="817b6-104">ModuleRef 节点可以包含但不限于程序集的说明，这些说明包括自定义代码、架构和业务流程。</span><span class="sxs-lookup"><span data-stu-id="817b6-104">A ModuleRef node can include but is not limited to descriptions of assemblies that contain custom code, schemas, and orchestrations.</span></span>  
  
## <a name="nodes-in-the-moduleref-node"></a><span data-ttu-id="817b6-105">ModuleRef 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="817b6-105">Nodes in the ModuleRef node</span></span>  
 <span data-ttu-id="817b6-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="817b6-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="817b6-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="817b6-107">**Name**</span></span>|<span data-ttu-id="817b6-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="817b6-108">**Node Type**</span></span>|<span data-ttu-id="817b6-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="817b6-109">**Data Type**</span></span>|<span data-ttu-id="817b6-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="817b6-110">**Description**</span></span>|<span data-ttu-id="817b6-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="817b6-111">**Restrictions**</span></span>|<span data-ttu-id="817b6-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="817b6-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="817b6-113">服务</span><span class="sxs-lookup"><span data-stu-id="817b6-113">Services</span></span>](../core/services-moduleref-node.md)|<span data-ttu-id="817b6-114">录制</span><span class="sxs-lookup"><span data-stu-id="817b6-114">Record</span></span>|<span data-ttu-id="817b6-115">ArrayOfServiceRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="817b6-115">ArrayOfServiceRef (ComplexType)</span></span>|<span data-ttu-id="817b6-116">与此 .NET 程序集关联的服务的容器节点。</span><span class="sxs-lookup"><span data-stu-id="817b6-116">Container node for services associated with this .NET assembly.</span></span>|<span data-ttu-id="817b6-117">可选</span><span class="sxs-lookup"><span data-stu-id="817b6-117">Not required</span></span>|<span data-ttu-id="817b6-118">默认值：无</span><span class="sxs-lookup"><span data-stu-id="817b6-118">Default value: none</span></span>|  
|[<span data-ttu-id="817b6-119">TrackedSchemas （ModuleRef 节点）</span><span class="sxs-lookup"><span data-stu-id="817b6-119">TrackedSchemas (ModuleRef Node)</span></span>](../core/trackedschemas-moduleref-node.md)|<span data-ttu-id="817b6-120">录制</span><span class="sxs-lookup"><span data-stu-id="817b6-120">Record</span></span>|<span data-ttu-id="817b6-121">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="817b6-121">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="817b6-122">与此 .NET 程序集关联的架构的容器节点。</span><span class="sxs-lookup"><span data-stu-id="817b6-122">Container node for schemas associated with this .NET assembly</span></span>|<span data-ttu-id="817b6-123">可选</span><span class="sxs-lookup"><span data-stu-id="817b6-123">Not required</span></span>|<span data-ttu-id="817b6-124">默认值：无</span><span class="sxs-lookup"><span data-stu-id="817b6-124">Default value: none</span></span>|