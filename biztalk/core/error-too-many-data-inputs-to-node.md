---
title: 错误-太多的数据输入到节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tooManyDataInputsToNode
ms.assetid: 176805f0-2d6d-4072-b866-132b98c7e4b5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9e465f861c4048708f41ea86f04ffd52375dec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241021"
---
# <a name="error---too-many-data-inputs-to-node"></a><span data-ttu-id="8dc55-102">错误-太多的数据输入到节点</span><span class="sxs-lookup"><span data-stu-id="8dc55-102">Error - Too Many Data Inputs to Node</span></span>
<span data-ttu-id="8dc55-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="8dc55-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8dc55-104">btm1005</span><span class="sxs-lookup"><span data-stu-id="8dc55-104">btm1005</span></span>  
  
 <span data-ttu-id="8dc55-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="8dc55-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8dc55-106">有大量的链接连接到比数输入指向目标架构中的指定节点**循环**functoid 连接到指定的节点的祖先节点。</span><span class="sxs-lookup"><span data-stu-id="8dc55-106">There are a greater number of links connected to the indicated node in the destination schema than the number of input links to the **Looping** functoid that is connected to an ancestor node of the indicated node.</span></span> <span data-ttu-id="8dc55-107">前一类型和后一类型的链接数应该一致。</span><span class="sxs-lookup"><span data-stu-id="8dc55-107">The number of links of the former and latter types should match.</span></span>  
  
 <span data-ttu-id="8dc55-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="8dc55-108">**User Action**</span></span>  
  
 <span data-ttu-id="8dc55-109">链接数连接到指定的节点和返工**循环**functoid 连接到祖先节点以便将它们与匹配。</span><span class="sxs-lookup"><span data-stu-id="8dc55-109">Rework the number of links connected to the indicated node and to the **Looping** functoid connected to the ancestor node so that they match.</span></span>