---
title: "警告-信封架构需要根记录节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.envelopeSchemaNeedsRoot
ms.assetid: 3fbc1571-1270-4c5e-adcf-00633bf46efe
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ccc0f472e15a31c9bef6e1090e8c153f730acbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="warning---envelope-schema-needs-root-record-node"></a><span data-ttu-id="8f0b7-102">警告-信封架构需要根记录节点</span><span class="sxs-lookup"><span data-stu-id="8f0b7-102">Warning - Envelope Schema Needs Root Record Node</span></span>
<span data-ttu-id="8f0b7-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="8f0b7-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8f0b7-104">BEC1010</span><span class="sxs-lookup"><span data-stu-id="8f0b7-104">BEC1010</span></span>  
  
 <span data-ttu-id="8f0b7-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f0b7-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8f0b7-106">信封架构都需要有至少一个根**记录**节点的子级作为其**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-106">Envelope schemas are required to have at least one root **Record** node as a child of its **Schema** node.</span></span>  
  
 <span data-ttu-id="8f0b7-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="8f0b7-107">**User Action**</span></span>  
  
 <span data-ttu-id="8f0b7-108">右键单击**架构**节点，单击**插入子记录**上为快捷菜单，然后按插入的描述性名称**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-108">Right-click the **Schema** node, click **Insert Child Record** on the shortcut menu, and then type a descriptive name for the inserted **Record** node.</span></span> <span data-ttu-id="8f0b7-109">一般情况下，信封架构也将具有插入根目录内的其他节点**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="8f0b7-109">In general, envelope schemas will also have additional nodes inserted within the root **Record** node.</span></span>