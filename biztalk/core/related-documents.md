---
title: 相关文档 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cb8259a6c8975673308a0aebb5e9c0336920715
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397977"
---
# <a name="related-documents"></a><span data-ttu-id="06031-102">相关的文档</span><span class="sxs-lookup"><span data-stu-id="06031-102">Related Documents</span></span>
<span data-ttu-id="06031-103">查询结果详细信息的相关文档区域显示与活动相关的参考文档的文档的列表。</span><span class="sxs-lookup"><span data-stu-id="06031-103">The Related Documents area of the query results detail displays a list of documents that are reference documents that relate to the activity.</span></span> <span data-ttu-id="06031-104">文档可以是任何类型，包括 CAD 图像。WAV 文件或采购订单。</span><span class="sxs-lookup"><span data-stu-id="06031-104">The documents can be of any type, including a CAD image, a .WAV file, or a purchase order.</span></span> <span data-ttu-id="06031-105">例如，采购订单活动通常将作为基文档类型有采购订单。</span><span class="sxs-lookup"><span data-stu-id="06031-105">For example, a Purchase Order activity will typically have a Purchase Order as a base document type.</span></span> <span data-ttu-id="06031-106">列表将包含采购订单的链接。</span><span class="sxs-lookup"><span data-stu-id="06031-106">The list will contain a link to the purchase order.</span></span>  
  
## <a name="adding-document-references"></a><span data-ttu-id="06031-107">添加文档引用</span><span class="sxs-lookup"><span data-stu-id="06031-107">Adding document references</span></span>  
 <span data-ttu-id="06031-108">在以下两种方式生成相关文档的列表：</span><span class="sxs-lookup"><span data-stu-id="06031-108">The list of related documents is generated in one of two ways:</span></span>  
  
- <span data-ttu-id="06031-109">开发您的跟踪配置文件时您将一个文档引用 URL 节点包含的活动树中，然后将其映射从包含指向物理文档的引用的源。</span><span class="sxs-lookup"><span data-stu-id="06031-109">When you develop your tracking profile you include a Document Reference URL node in the activity tree and then map it from a source containing a reference pointer to the physical document.</span></span>  
  
- <span data-ttu-id="06031-110">集成开发人员以编程方式填充通过调用自定义应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="06031-110">Your integration developer programmatically populates the list by calling your custom application.</span></span>  
  
  <span data-ttu-id="06031-111">定义使用其中一种方法的文档引用将添加中的某一行\<activityname\>_References 表与文档位置。</span><span class="sxs-lookup"><span data-stu-id="06031-111">Defining the document reference using either of these methods adds a row in the \<activityname\>_References table with the document location.</span></span>  
  
  <span data-ttu-id="06031-112">如果已执行这些任务任一，**相关文档**区域将为空。</span><span class="sxs-lookup"><span data-stu-id="06031-112">If neither of these tasks has been performed, the **Related Document** area is blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06031-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="06031-113">See Also</span></span>  
 [<span data-ttu-id="06031-114">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="06031-114">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)