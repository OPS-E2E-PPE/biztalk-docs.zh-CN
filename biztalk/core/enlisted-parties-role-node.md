---
title: 登记方 （角色节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enlisted Parties node [binding file]
ms.assetid: 06dd5565-b12a-4cc8-bf6b-2fbb7d721f4b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 662f4221213240df2feb63eca0f75d96aa44449f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239685"
---
# <a name="enlisted-parties-role-node"></a><span data-ttu-id="c71fd-102">已登记参与方（角色节点）</span><span class="sxs-lookup"><span data-stu-id="c71fd-102">Enlisted Parties (Role Node)</span></span>
<span data-ttu-id="c71fd-103">对于任何“已登记参与方”节点，只要它包含与通过某个绑定文件导出的角色关联的已登记参与方相关的特定信息，则该绑定文件的“已登记参与方”节点就是此节点的父节点。</span><span class="sxs-lookup"><span data-stu-id="c71fd-103">The Enlisted Parties node of a binding file is the parent node for all of the Enlisted Party nodes which contain specific information about the enlisted parties associated with a role that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-enlisted-parties-node"></a><span data-ttu-id="c71fd-104">“已登记参与方”节点中的节点</span><span class="sxs-lookup"><span data-stu-id="c71fd-104">Nodes in the Enlisted Parties node</span></span>  
 <span data-ttu-id="c71fd-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="c71fd-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c71fd-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="c71fd-106">**Name**</span></span>|<span data-ttu-id="c71fd-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="c71fd-107">**Node Type**</span></span>|<span data-ttu-id="c71fd-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="c71fd-108">**Data Type**</span></span>|<span data-ttu-id="c71fd-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="c71fd-109">**Description**</span></span>|<span data-ttu-id="c71fd-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="c71fd-110">**Restrictions**</span></span>|<span data-ttu-id="c71fd-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="c71fd-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="c71fd-112">已登记参与的方</span><span class="sxs-lookup"><span data-stu-id="c71fd-112">Enlisted Party</span></span>](../core/enlisted-party-enlisted-parties-node.md)|<span data-ttu-id="c71fd-113">录制</span><span class="sxs-lookup"><span data-stu-id="c71fd-113">Record</span></span>|<span data-ttu-id="c71fd-114">EnlistedParty (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="c71fd-114">EnlistedParty (ComplexType)</span></span>|<span data-ttu-id="c71fd-115">指定与角色有关的已登记参与方的信息。</span><span class="sxs-lookup"><span data-stu-id="c71fd-115">Specifies information about an enlisted party that is associated with a role.</span></span>|<span data-ttu-id="c71fd-116">不需要</span><span class="sxs-lookup"><span data-stu-id="c71fd-116">Not Required</span></span>|<span data-ttu-id="c71fd-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="c71fd-117">Default value: none</span></span>|