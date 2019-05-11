---
title: 错误-已升级的属性 Max Occurs |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fcaf06dc0fccbf838c401343b3ce1e8f3b538ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347049"
---
# <a name="error---promoted-property-max-occurs"></a><span data-ttu-id="8a82a-102">错误-已升级的属性 Max Occurs</span><span class="sxs-lookup"><span data-stu-id="8a82a-102">Error - Promoted Property Max Occurs</span></span>
<span data-ttu-id="8a82a-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="8a82a-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8a82a-104">BEC2002</span><span class="sxs-lookup"><span data-stu-id="8a82a-104">BEC2002</span></span>  
  
 <span data-ttu-id="8a82a-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="8a82a-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8a82a-106">设置**Max Occurs**或某个祖先节点，要升级的节点的属性是与属性升级不兼容。</span><span class="sxs-lookup"><span data-stu-id="8a82a-106">The setting of the **Max Occurs** property of the node being promoted, or of one of its ancestor nodes, is incompatible with property promotion.</span></span> <span data-ttu-id="8a82a-107">可以在实例消息中多次出现的节点不允许使用属性升级。</span><span class="sxs-lookup"><span data-stu-id="8a82a-107">Property promotion is disallowed for nodes that can occur more than once in an instance message.</span></span> <span data-ttu-id="8a82a-108">因此， **Max Occurs**从要升级到的根节点的节点的所有节点的属性必须设置为 1。</span><span class="sxs-lookup"><span data-stu-id="8a82a-108">Therefore, the **Max Occurs** properties of all nodes from the node being promoted back to the root node must be set to 1.</span></span>  
  
 <span data-ttu-id="8a82a-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="8a82a-109">**User Action**</span></span>  
  
 <span data-ttu-id="8a82a-110">絋粄**Max Occurs**要升级的节点及其所有祖先节点的属性设置为一 (1)。</span><span class="sxs-lookup"><span data-stu-id="8a82a-110">Ensure that the **Max Occurs** property of the node being promoted and all of its ancestor nodes is set to one (1).</span></span>