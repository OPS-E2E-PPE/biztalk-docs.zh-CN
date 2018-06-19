---
title: RetractByType |Microsoft 文档
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
ms.openlocfilehash: da8cd4581007ad2bd93ed66ebce4f5de6378280c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268733"
---
# <a name="retractbytype"></a><span data-ttu-id="3810d-102">RetractByType</span><span class="sxs-lookup"><span data-stu-id="3810d-102">RetractByType</span></span>
<span data-ttu-id="3810d-103">**RetractByType**函数将收回在工作内存中，指定类型的所有实例，而**收回**函数将都收回仅对特定类型的特定项目。</span><span class="sxs-lookup"><span data-stu-id="3810d-103">The **RetractByType** function retracts all instances of a specified type in the working memory, whereas the **Retract**function retracts only specific items of a certain type.</span></span> <span data-ttu-id="3810d-104">以下各段介绍如何**RetractByType**函数适用于不同类型的实体。</span><span class="sxs-lookup"><span data-stu-id="3810d-104">The following paragraphs describe how the **RetractByType** function works with entities of different types.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="3810d-105">.NET 对象</span><span class="sxs-lookup"><span data-stu-id="3810d-105">.NET Objects</span></span>  
 <span data-ttu-id="3810d-106">从工作内存中取消给定类类型的所有对象。</span><span class="sxs-lookup"><span data-stu-id="3810d-106">All objects for a given class type are retracted from working memory.</span></span> <span data-ttu-id="3810d-107">你只需类将从.NET 类事实窗格拖到**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="3810d-107">You simply drag the class from the .NET Classes fact pane into the **RetractByType** function.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="3810d-108">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="3810d-108">TypedXmlDocument</span></span>  
 <span data-ttu-id="3810d-109">取消所有实例。</span><span class="sxs-lookup"><span data-stu-id="3810d-109">All instances are retracted.</span></span> <span data-ttu-id="3810d-110">这意味着所有**TypedXmlDocument**具有相同的 s **DocumentType.Selector**收回。</span><span class="sxs-lookup"><span data-stu-id="3810d-110">This means that all **TypedXmlDocument**s with the same **DocumentType.Selector** are retracted.</span></span> <span data-ttu-id="3810d-111">你应将相应的节点从 XML 架构事实窗格到**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="3810d-111">You should drag the appropriate node from the XML Schemas fact pane into the **RetractByType** function.</span></span> <span data-ttu-id="3810d-112">与一致**收回**函数，如果你执行**RetractByType**的文档根节点上，不只将所有**TypedXmlDocuments**与该断言**DocumentType**收回，但所有子**TypedXmlDocuments** (**XmlNode**树层次结构中的 s) 与这些父**TypedXmlDocuments**也将被取消。</span><span class="sxs-lookup"><span data-stu-id="3810d-112">Consistent with the **Retract** function, if you perform a **RetractByType** on the document root node, not only will all **TypedXmlDocuments** asserted with that **DocumentType** be retracted, but all child **TypedXmlDocuments** (**XmlNode**s in the tree hierarchy) associated with those parent **TypedXmlDocuments** will also be retracted.</span></span>  
  
## <a name="typeddatatable-and-dataconnection"></a><span data-ttu-id="3810d-113">TypedDataTable 和 DataConnection</span><span class="sxs-lookup"><span data-stu-id="3810d-113">TypedDataTable and DataConnection</span></span>  
 <span data-ttu-id="3810d-114">**收回**和**RetractByType**相等，则两个**TypedDataTable**和**该组**。</span><span class="sxs-lookup"><span data-stu-id="3810d-114">**Retract** and **RetractByType** are equivalent for both **TypedDataTable** and **DataConnection**.</span></span> <span data-ttu-id="3810d-115">因为**DataSetName.DataTableName**是唯一的标识符对于这两种类型，只有一个实例在引擎中的任何时刻中没有时间。</span><span class="sxs-lookup"><span data-stu-id="3810d-115">Because **DataSetName.DataTableName** is a unique identifier for both types, there is only one instance in the engine at any point in time.</span></span> <span data-ttu-id="3810d-116">与**收回**，拖动到表**RetractByType**函数。</span><span class="sxs-lookup"><span data-stu-id="3810d-116">As with **Retract**, you drag the table into the **RetractByType** function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3810d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3810d-117">See Also</span></span>  
 [<span data-ttu-id="3810d-118">引擎控制功能</span><span class="sxs-lookup"><span data-stu-id="3810d-118">Engine Control Functions</span></span>](../core/engine-control-functions.md)