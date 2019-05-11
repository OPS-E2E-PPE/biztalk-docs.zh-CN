---
title: 警告-信封架构需要根记录节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.envelopeSchemaNeedsRoot
ms.assetid: 3fbc1571-1270-4c5e-adcf-00633bf46efe
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4869a5a346e49d7febbccb628799430922dd8cb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393684"
---
# <a name="warning---envelope-schema-needs-root-record-node"></a><span data-ttu-id="fb7c0-102">警告-信封架构需要根记录节点</span><span class="sxs-lookup"><span data-stu-id="fb7c0-102">Warning - Envelope Schema Needs Root Record Node</span></span>
<span data-ttu-id="fb7c0-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="fb7c0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="fb7c0-104">BEC1010</span><span class="sxs-lookup"><span data-stu-id="fb7c0-104">BEC1010</span></span>  
  
 <span data-ttu-id="fb7c0-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="fb7c0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="fb7c0-106">信封架构需要具有至少一个根**记录**节点的子级作为其**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="fb7c0-106">Envelope schemas are required to have at least one root **Record** node as a child of its **Schema** node.</span></span>  
  
 <span data-ttu-id="fb7c0-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="fb7c0-107">**User Action**</span></span>  
  
 <span data-ttu-id="fb7c0-108">右键单击**架构**节点中，单击**插入子记录**上为快捷菜单，然后按为插入的描述性名称**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="fb7c0-108">Right-click the **Schema** node, click **Insert Child Record** on the shortcut menu, and then type a descriptive name for the inserted **Record** node.</span></span> <span data-ttu-id="fb7c0-109">一般情况下，信封架构也会在根目录下插入其他节点**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="fb7c0-109">In general, envelope schemas will also have additional nodes inserted within the root **Record** node.</span></span>