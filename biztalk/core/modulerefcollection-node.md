---
title: "ModuleRefCollection 节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ModuleRefCollection node [binding file]
ms.assetid: fa8593bf-6548-4615-9f98-1e0eadde9aa4
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 039cabd380195f840e9ffb99de5071026b3810c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="modulerefcollection-node"></a><span data-ttu-id="cc107-102">ModuleRefCollection 节点</span><span class="sxs-lookup"><span data-stu-id="cc107-102">ModuleRefCollection Node</span></span>
<span data-ttu-id="cc107-103">绑定文件的 ModuleRefCollection 节是所有 ModuleRef 节点的父节点，ModuleRef 节点包含有关与此绑定文件一起导出的 .NET 程序集的特定信息。</span><span class="sxs-lookup"><span data-stu-id="cc107-103">The ModuleRefCollection section of a binding file is the parent node for all of the ModuleRef nodes which contain specific information about .NET assemblies exported with the binding file.</span></span>  
  
## <a name="entries-in-the-modulerefcollection-section"></a><span data-ttu-id="cc107-104">ModuleRefCollection 节中的项</span><span class="sxs-lookup"><span data-stu-id="cc107-104">Entries in the ModuleRefCollection section</span></span>  
 <span data-ttu-id="cc107-105">下表列出了可为绑定文件的此节中的节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="cc107-105">The following table lists the properties that can be set for the nodes in this section of a binding file:</span></span>  
  
|<span data-ttu-id="cc107-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="cc107-106">**Name**</span></span>|<span data-ttu-id="cc107-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="cc107-107">**Node Type**</span></span>|<span data-ttu-id="cc107-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cc107-108">**Data Type**</span></span>|<span data-ttu-id="cc107-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="cc107-109">**Description**</span></span>|<span data-ttu-id="cc107-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="cc107-110">**Restrictions**</span></span>|<span data-ttu-id="cc107-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="cc107-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="cc107-112">ModuleRef</span><span class="sxs-lookup"><span data-stu-id="cc107-112">ModuleRef</span></span>](../core/moduleref-modulerefcollection-node.md)|<span data-ttu-id="cc107-113">录制</span><span class="sxs-lookup"><span data-stu-id="cc107-113">Record</span></span>|<span data-ttu-id="cc107-114">ModuleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="cc107-114">ModuleRef (ComplexType)</span></span>|<span data-ttu-id="cc107-115">与绑定文件一起导出的 .NET 程序集模块的容器节点。</span><span class="sxs-lookup"><span data-stu-id="cc107-115">Container node for a .NET assembly module exported with the binding file.</span></span>|<span data-ttu-id="cc107-116">可选</span><span class="sxs-lookup"><span data-stu-id="cc107-116">Not required</span></span>|<span data-ttu-id="cc107-117">默认值： 无</span><span class="sxs-lookup"><span data-stu-id="cc107-117">Default value: None</span></span>|