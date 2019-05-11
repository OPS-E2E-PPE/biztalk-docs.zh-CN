---
title: ModuleRef （ModuleRefCollection 节点） |Microsoft Docs
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
ms.openlocfilehash: 604efe0b0d5d93c6d545b7725d2a0f85609fc32a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394418"
---
# <a name="moduleref-modulerefcollection-node"></a><span data-ttu-id="0481d-102">ModuleRef （ModuleRefCollection 节点）</span><span class="sxs-lookup"><span data-stu-id="0481d-102">ModuleRef (ModuleRefCollection Node)</span></span>
<span data-ttu-id="0481d-103">绑定文件的 ModuleRef 节点包含有关与绑定文件一起导出的.NET 程序集的特定信息。</span><span class="sxs-lookup"><span data-stu-id="0481d-103">The ModuleRef node of a binding file contains specific information about a .NET assembly that was exported with the binding file.</span></span> <span data-ttu-id="0481d-104">ModuleRef 节点可以包括但不限于包含自定义代码、 架构和业务流程的程序集的说明。</span><span class="sxs-lookup"><span data-stu-id="0481d-104">A ModuleRef node can include but is not limited to descriptions of assemblies that contain custom code, schemas, and orchestrations.</span></span>  
  
## <a name="nodes-in-the-moduleref-node"></a><span data-ttu-id="0481d-105">ModuleRef 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="0481d-105">Nodes in the ModuleRef node</span></span>  
 <span data-ttu-id="0481d-106">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="0481d-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="0481d-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="0481d-107">**Name**</span></span>|<span data-ttu-id="0481d-108">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="0481d-108">**Node Type**</span></span>|<span data-ttu-id="0481d-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0481d-109">**Data Type**</span></span>|<span data-ttu-id="0481d-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="0481d-110">**Description**</span></span>|<span data-ttu-id="0481d-111">**限制**</span><span class="sxs-lookup"><span data-stu-id="0481d-111">**Restrictions**</span></span>|<span data-ttu-id="0481d-112">**注释**</span><span class="sxs-lookup"><span data-stu-id="0481d-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="0481d-113">服务</span><span class="sxs-lookup"><span data-stu-id="0481d-113">Services</span></span>](../core/services-moduleref-node.md)|<span data-ttu-id="0481d-114">录制</span><span class="sxs-lookup"><span data-stu-id="0481d-114">Record</span></span>|<span data-ttu-id="0481d-115">ArrayOfServiceRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="0481d-115">ArrayOfServiceRef (ComplexType)</span></span>|<span data-ttu-id="0481d-116">与此.NET 程序集关联的服务的容器节点。</span><span class="sxs-lookup"><span data-stu-id="0481d-116">Container node for services associated with this .NET assembly.</span></span>|<span data-ttu-id="0481d-117">可选</span><span class="sxs-lookup"><span data-stu-id="0481d-117">Not required</span></span>|<span data-ttu-id="0481d-118">默认值：无</span><span class="sxs-lookup"><span data-stu-id="0481d-118">Default value: none</span></span>|  
|[<span data-ttu-id="0481d-119">TrackedSchemas（ModuleRef 节点）</span><span class="sxs-lookup"><span data-stu-id="0481d-119">TrackedSchemas (ModuleRef Node)</span></span>](../core/trackedschemas-moduleref-node.md)|<span data-ttu-id="0481d-120">录制</span><span class="sxs-lookup"><span data-stu-id="0481d-120">Record</span></span>|<span data-ttu-id="0481d-121">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="0481d-121">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="0481d-122">与此.NET 程序集相关联的架构的容器节点</span><span class="sxs-lookup"><span data-stu-id="0481d-122">Container node for schemas associated with this .NET assembly</span></span>|<span data-ttu-id="0481d-123">可选</span><span class="sxs-lookup"><span data-stu-id="0481d-123">Not required</span></span>|<span data-ttu-id="0481d-124">默认值：无</span><span class="sxs-lookup"><span data-stu-id="0481d-124">Default value: none</span></span>|