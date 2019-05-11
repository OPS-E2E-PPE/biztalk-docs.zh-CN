---
title: ModuleRefCollection 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRefCollection node [binding file]
ms.assetid: fa8593bf-6548-4615-9f98-1e0eadde9aa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8f756d15e7b4dd88029ad169d5aac66e894aff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324504"
---
# <a name="modulerefcollection-node"></a><span data-ttu-id="882e7-102">ModuleRefCollection 节点</span><span class="sxs-lookup"><span data-stu-id="882e7-102">ModuleRefCollection Node</span></span>
<span data-ttu-id="882e7-103">绑定文件的 ModuleRefCollection 节是所有 ModuleRef 节点包含有关与绑定文件一起导出的.NET 程序集的特定信息的父节点。</span><span class="sxs-lookup"><span data-stu-id="882e7-103">The ModuleRefCollection section of a binding file is the parent node for all of the ModuleRef nodes which contain specific information about .NET assemblies exported with the binding file.</span></span>  
  
## <a name="entries-in-the-modulerefcollection-section"></a><span data-ttu-id="882e7-104">ModuleRefCollection 节中的项</span><span class="sxs-lookup"><span data-stu-id="882e7-104">Entries in the ModuleRefCollection section</span></span>  
 <span data-ttu-id="882e7-105">下表列出了可以在此部分中的绑定文件中为节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="882e7-105">The following table lists the properties that can be set for the nodes in this section of a binding file:</span></span>  
  
|<span data-ttu-id="882e7-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="882e7-106">**Name**</span></span>|<span data-ttu-id="882e7-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="882e7-107">**Node Type**</span></span>|<span data-ttu-id="882e7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="882e7-108">**Data Type**</span></span>|<span data-ttu-id="882e7-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="882e7-109">**Description**</span></span>|<span data-ttu-id="882e7-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="882e7-110">**Restrictions**</span></span>|<span data-ttu-id="882e7-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="882e7-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="882e7-112">ModuleRef</span><span class="sxs-lookup"><span data-stu-id="882e7-112">ModuleRef</span></span>](../core/moduleref-modulerefcollection-node.md)|<span data-ttu-id="882e7-113">录制</span><span class="sxs-lookup"><span data-stu-id="882e7-113">Record</span></span>|<span data-ttu-id="882e7-114">ModuleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="882e7-114">ModuleRef (ComplexType)</span></span>|<span data-ttu-id="882e7-115">与绑定文件一起导出的.NET 程序集模块的容器节点。</span><span class="sxs-lookup"><span data-stu-id="882e7-115">Container node for a .NET assembly module exported with the binding file.</span></span>|<span data-ttu-id="882e7-116">可选</span><span class="sxs-lookup"><span data-stu-id="882e7-116">Not required</span></span>|<span data-ttu-id="882e7-117">默认值：None</span><span class="sxs-lookup"><span data-stu-id="882e7-117">Default value: None</span></span>|