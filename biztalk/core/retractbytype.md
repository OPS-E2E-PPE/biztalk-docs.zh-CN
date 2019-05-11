---
title: RetractByType | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RetractByType function [Business Rules Engine], TypedXMLDocument
- RetractByType function [Business Rules Engine]
- RetractByType function [Business Rules Engine], .NET objects
- RetractByType function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e8867553-ee3c-46be-84cd-d5373eaf3337
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 460684c52f00df531eb73f397fdc187829522be2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309510"
---
# <a name="retractbytype"></a><span data-ttu-id="68a6f-102">RetractByType</span><span class="sxs-lookup"><span data-stu-id="68a6f-102">RetractByType</span></span>
<span data-ttu-id="68a6f-103">**RetractByType**函数可以取消工作内存中指定类型的所有实例而**Retract**函数可以都取消某一类型的仅对特定项目。</span><span class="sxs-lookup"><span data-stu-id="68a6f-103">The **RetractByType** function retracts all instances of a specified type in the working memory, whereas the **Retract**function retracts only specific items of a certain type.</span></span> <span data-ttu-id="68a6f-104">以下各段介绍如何**RetractByType**函数适用于不同类型的实体。</span><span class="sxs-lookup"><span data-stu-id="68a6f-104">The following paragraphs describe how the **RetractByType** function works with entities of different types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="68a6f-105">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="68a6f-105">.NET Objects</span></span>  
 <span data-ttu-id="68a6f-106">从工作内存中取消给定的类类型的所有对象。</span><span class="sxs-lookup"><span data-stu-id="68a6f-106">All objects for a given class type are retracted from working memory.</span></span> <span data-ttu-id="68a6f-107">从.NET 类事实窗格到只需将该类**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="68a6f-107">You simply drag the class from the .NET Classes fact pane into the **RetractByType** function.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="68a6f-108">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="68a6f-108">TypedXmlDocument</span></span>  
 <span data-ttu-id="68a6f-109">取消所有实例。</span><span class="sxs-lookup"><span data-stu-id="68a6f-109">All instances are retracted.</span></span> <span data-ttu-id="68a6f-110">这意味着，所有**TypedXmlDocument**具有相同的 s **DocumentType.Selector**中取消。</span><span class="sxs-lookup"><span data-stu-id="68a6f-110">This means that all **TypedXmlDocument**s with the same **DocumentType.Selector** are retracted.</span></span> <span data-ttu-id="68a6f-111">应将相应的节点从到的 XML 架构事实窗格拖**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="68a6f-111">You should drag the appropriate node from the XML Schemas fact pane into the **RetractByType** function.</span></span> <span data-ttu-id="68a6f-112">与一致**Retract**函数，如果您执行**RetractByType**对文档根节点，不仅将所有**TypedXmlDocuments**添加与该**DocumentType**收回，但所有子**TypedXmlDocuments** (**XmlNode**树层次结构中) 与这些父关联**TypedXmlDocuments**还将取消。</span><span class="sxs-lookup"><span data-stu-id="68a6f-112">Consistent with the **Retract** function, if you perform a **RetractByType** on the document root node, not only will all **TypedXmlDocuments** asserted with that **DocumentType** be retracted, but all child **TypedXmlDocuments** (**XmlNode**s in the tree hierarchy) associated with those parent **TypedXmlDocuments** will also be retracted.</span></span>  
  
## <a name="typeddatatable-and-dataconnection"></a><span data-ttu-id="68a6f-113">TypedDataTable 和 DataConnection</span><span class="sxs-lookup"><span data-stu-id="68a6f-113">TypedDataTable and DataConnection</span></span>  
 <span data-ttu-id="68a6f-114">**收回**并**RetractByType**是两个等效**TypedDataTable**并**DataConnection**。</span><span class="sxs-lookup"><span data-stu-id="68a6f-114">**Retract** and **RetractByType** are equivalent for both **TypedDataTable** and **DataConnection**.</span></span> <span data-ttu-id="68a6f-115">因为**DataSetName.DataTableName**是唯一的标识符的两种类型，只有一个实例引擎中任何位置中没有时间。</span><span class="sxs-lookup"><span data-stu-id="68a6f-115">Because **DataSetName.DataTableName** is a unique identifier for both types, there is only one instance in the engine at any point in time.</span></span> <span data-ttu-id="68a6f-116">如同**Retract**，将拖到表**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="68a6f-116">As with **Retract**, you drag the table into the **RetractByType** function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a6f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="68a6f-117">See Also</span></span>  
 [<span data-ttu-id="68a6f-118">引擎控制函数</span><span class="sxs-lookup"><span data-stu-id="68a6f-118">Engine Control Functions</span></span>](../core/engine-control-functions.md)