---
title: "相关文档 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b87f0d31010a8bf80e09c59f05f2f9302a510e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="related-documents"></a><span data-ttu-id="2bf4a-102">相关的文档</span><span class="sxs-lookup"><span data-stu-id="2bf4a-102">Related Documents</span></span>
<span data-ttu-id="2bf4a-103">查询结果详细信息的“相关文档”区域显示与活动相关的引用文档的列表。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-103">The Related Documents area of the query results detail displays a list of documents that are reference documents that relate to the activity.</span></span> <span data-ttu-id="2bf4a-104">文档可以是任何类型，包括 CAD 映像。WAV 文件或采购订单。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-104">The documents can be of any type, including a CAD image, a .WAV file, or a purchase order.</span></span> <span data-ttu-id="2bf4a-105">例如，“采购订单”活动通常将“采购订单”作为基本文档类型。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-105">For example, a Purchase Order activity will typically have a Purchase Order as a base document type.</span></span> <span data-ttu-id="2bf4a-106">该列表将包含采购订单的链接。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-106">The list will contain a link to the purchase order.</span></span>  
  
## <a name="adding-document-references"></a><span data-ttu-id="2bf4a-107">文档中添加引用</span><span class="sxs-lookup"><span data-stu-id="2bf4a-107">Adding document references</span></span>  
 <span data-ttu-id="2bf4a-108">在两种方式之一生成相关文档的列表：</span><span class="sxs-lookup"><span data-stu-id="2bf4a-108">The list of related documents is generated in one of two ways:</span></span>  
  
-   <span data-ttu-id="2bf4a-109">当你开发跟踪配置文件时包括文档引用 URL 节点在内的活动树中，并且然后将其映射从包含指向物理文档的引用的源。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-109">When you develop your tracking profile you include a Document Reference URL node in the activity tree and then map it from a source containing a reference pointer to the physical document.</span></span>  
  
-   <span data-ttu-id="2bf4a-110">集成开发人员以编程方式填充的列表，通过调用自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-110">Your integration developer programmatically populates the list by calling your custom application.</span></span>  
  
 <span data-ttu-id="2bf4a-111">定义使用这些方法之一的文档引用将添加中的行\<activityname\>_References 表与文档位置。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-111">Defining the document reference using either of these methods adds a row in the \<activityname\>_References table with the document location.</span></span>  
  
 <span data-ttu-id="2bf4a-112">如果已执行这些任务任一，**相关文档**区域为空。</span><span class="sxs-lookup"><span data-stu-id="2bf4a-112">If neither of these tasks has been performed, the **Related Document** area is blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf4a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bf4a-113">See Also</span></span>  
 [<span data-ttu-id="2bf4a-114">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="2bf4a-114">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)