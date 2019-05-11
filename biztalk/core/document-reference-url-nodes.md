---
title: 文档引用 URL 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c9cbc37b48ad6592215723695b54edc17e834b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350965"
---
# <a name="document-reference-url-nodes"></a><span data-ttu-id="1913d-102">文档引用 URL 节点</span><span class="sxs-lookup"><span data-stu-id="1913d-102">Document Reference URL Nodes</span></span>
<span data-ttu-id="1913d-103">文档引用 URL 节点位于开发人员从知识工作者创建的观察模型导入的活动定义文件中。</span><span class="sxs-lookup"><span data-stu-id="1913d-103">Document Reference URL nodes exist in the activity definition file that the developer imports from the knowledge worker created observation model.</span></span> <span data-ttu-id="1913d-104">文档引用 URL 节点包含对包含此活动与相关的文档的位置的引用。</span><span class="sxs-lookup"><span data-stu-id="1913d-104">Document Reference URL nodes contain references to a location that contains a document that is related to this activity.</span></span> <span data-ttu-id="1913d-105">这可以是文档的任何类型，例如活动表示采购订单审批工作流，文档引用 URL 可能指向底层采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="1913d-105">This can be any type of document, for example an activity that represents a purchase order approval work flow, the Document Reference URL might point to the underlying purchase order document.</span></span>  
  
## <a name="working-with-document-reference-url-nodes"></a><span data-ttu-id="1913d-106">使用文档引用 URL 节点</span><span class="sxs-lookup"><span data-stu-id="1913d-106">Working with Document Reference URL nodes</span></span>  
 <span data-ttu-id="1913d-107">文档引用 URL 的数据源通常是**MessageRefURL** BizTalk Server 系统属性。</span><span class="sxs-lookup"><span data-stu-id="1913d-107">The data source for the Document Reference URL is typically the **MessageRefURL** BizTalk Server system property.</span></span> <span data-ttu-id="1913d-108">此外可以使用自定义架构的存储 Url 和将属性映射到文档引用 URL 从自定义架构。</span><span class="sxs-lookup"><span data-stu-id="1913d-108">You can also use custom schemas that store URLs and map the property to the Document Reference URL from the custom schema.</span></span>  
  
 <span data-ttu-id="1913d-109">请注意关于文档引用 Url 的项：</span><span class="sxs-lookup"><span data-stu-id="1913d-109">Items to note about Document Reference URLs:</span></span>  
  
-   <span data-ttu-id="1913d-110">您可以添加一个或多个文档引用 Url，但每个节点必须具有活动中的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="1913d-110">You can add one or more Document Reference URLs, but each node must have unique name within the activity.</span></span>  
  
-   <span data-ttu-id="1913d-111">**MessageRefURL**在 WSS、 FILE 和 FTP 传输适配器的情况下的值仅填充填充文档引用 URL 节点所需的属性。</span><span class="sxs-lookup"><span data-stu-id="1913d-111">The **MessageRefURL** property needed to populate a Document Reference URL node is only populated with a value in the case of WSS, FILE, and FTP transport adapters.</span></span>  
  
-   <span data-ttu-id="1913d-112">尽管业务最终用户可以在 BAM 门户中查看此引用，引用 URL 的主要用途是允许自定义用户界面开发人员可以访问关联的文档信息，以便它们可以将其提交给最终用户。</span><span class="sxs-lookup"><span data-stu-id="1913d-112">While business end-users can view this reference in the BAM portal, the primary purpose of the reference URL is to allow custom user interface developers to gain access to associated document information so that they can present it to the end user.</span></span>  <span data-ttu-id="1913d-113">在 BAM 门户中查看文档引用的详细信息，请参阅[相关文档](../core/related-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="1913d-113">For more information on viewing the document reference in the BAM portal, see [Related Documents](../core/related-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1913d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1913d-114">See Also</span></span>  
 [<span data-ttu-id="1913d-115">“TPE 活动视图”节点</span><span class="sxs-lookup"><span data-stu-id="1913d-115">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)