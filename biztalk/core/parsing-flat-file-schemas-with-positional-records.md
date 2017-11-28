---
title: "分析包含的位置记录的平面文件架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], flat file documents
- pipeline components [custom], parsing
ms.assetid: 1ceb8c06-ac21-490e-b3d5-54e5035e5f6a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4a6a1d5d6c263c0f794d1b703eff256f15c43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="parsing-flat-file-schemas-with-positional-records"></a><span data-ttu-id="ff661-102">分析包含的位置记录的平面文件架构</span><span class="sxs-lookup"><span data-stu-id="ff661-102">Parsing Flat File Schemas with Positional Records</span></span>
<span data-ttu-id="ff661-103">在解析带有大小不等的位置记录的平面文件架构时，您必须在每个架构记录或尾部中都包含一个标记，以便指示每个位置记录的大小。</span><span class="sxs-lookup"><span data-stu-id="ff661-103">When parsing a flat file schema with positional records of unequal size, you must include a tag within each schema record or the trailer to indicate the size of each positional record.</span></span> <span data-ttu-id="ff661-104">否则，解析引擎将返回最长的记录大小。</span><span class="sxs-lookup"><span data-stu-id="ff661-104">Otherwise, the parsing engine returns the longest record size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff661-105">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff661-105">See Also</span></span>  
 [<span data-ttu-id="ff661-106">使用平面文件分析引擎</span><span class="sxs-lookup"><span data-stu-id="ff661-106">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)