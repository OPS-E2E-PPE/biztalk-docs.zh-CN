---
title: "文档引用 URL 节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7939a7e74483b8df192530fd9da2deafeda0681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="document-reference-url-nodes"></a><span data-ttu-id="b6cae-102">文档引用 URL 节点</span><span class="sxs-lookup"><span data-stu-id="b6cae-102">Document Reference URL Nodes</span></span>
<span data-ttu-id="b6cae-103">文档引用 URL 节点位于开发人员从知识工作者创建的观察模型导入的活动定义文件中。</span><span class="sxs-lookup"><span data-stu-id="b6cae-103">Document Reference URL nodes exist in the activity definition file that the developer imports from the knowledge worker created observation model.</span></span> <span data-ttu-id="b6cae-104">文档引用 URL 节点包含一个位置的引用，该位置包含与此活动相关的文档。</span><span class="sxs-lookup"><span data-stu-id="b6cae-104">Document Reference URL nodes contain references to a location that contains a document that is related to this activity.</span></span> <span data-ttu-id="b6cae-105">该文档可以是任何类型的文档，例如，对于表示采购订单审批工作流的活动，文档引用 URL 可能指向底层采购订单文档。</span><span class="sxs-lookup"><span data-stu-id="b6cae-105">This can be any type of document, for example an activity that represents a purchase order approval work flow, the Document Reference URL might point to the underlying purchase order document.</span></span>  
  
## <a name="working-with-document-reference-url-nodes"></a><span data-ttu-id="b6cae-106">使用文档引用 URL 节点</span><span class="sxs-lookup"><span data-stu-id="b6cae-106">Working with Document Reference URL nodes</span></span>  
 <span data-ttu-id="b6cae-107">文档引用 URL 的数据源通常是**MessageRefURL** BizTalk 服务器系统属性。</span><span class="sxs-lookup"><span data-stu-id="b6cae-107">The data source for the Document Reference URL is typically the **MessageRefURL** BizTalk Server system property.</span></span> <span data-ttu-id="b6cae-108">您还可以使用存储 URL 的自定义架构，然后将该属性映射到该自定义架构中的文档引用 URL。</span><span class="sxs-lookup"><span data-stu-id="b6cae-108">You can also use custom schemas that store URLs and map the property to the Document Reference URL from the custom schema.</span></span>  
  
 <span data-ttu-id="b6cae-109">关于文档引用 URL 的注意事项：</span><span class="sxs-lookup"><span data-stu-id="b6cae-109">Items to note about Document Reference URLs:</span></span>  
  
-   <span data-ttu-id="b6cae-110">您可以添加一个或多个文档引用 URL，但每个节点在活动内都必须具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="b6cae-110">You can add one or more Document Reference URLs, but each node must have unique name within the activity.</span></span>  
  
-   <span data-ttu-id="b6cae-111">**MessageRefURL**填充文档引用 URL 节点所需的属性仅使用在 WSS、 文件和 FTP 传输适配器的情况下某个值填充。</span><span class="sxs-lookup"><span data-stu-id="b6cae-111">The **MessageRefURL** property needed to populate a Document Reference URL node is only populated with a value in the case of WSS, FILE, and FTP transport adapters.</span></span>  
  
-   <span data-ttu-id="b6cae-112">虽然业务最终用户可以在 BAM 门户中查看此引用，引用 URL 的主要目的是以允许自定义用户界面开发人员可以访问关联文档信息，以便它们可以将其提交给最终用户。</span><span class="sxs-lookup"><span data-stu-id="b6cae-112">While business end-users can view this reference in the BAM portal, the primary purpose of the reference URL is to allow custom user interface developers to gain access to associated document information so that they can present it to the end user.</span></span>  <span data-ttu-id="b6cae-113">有关在 BAM 门户中查看的文档引用的详细信息，请参阅[相关文档](../core/related-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="b6cae-113">For more information on viewing the document reference in the BAM portal, see [Related Documents](../core/related-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cae-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6cae-114">See Also</span></span>  
 [<span data-ttu-id="b6cae-115">键入活动视图节点</span><span class="sxs-lookup"><span data-stu-id="b6cae-115">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)