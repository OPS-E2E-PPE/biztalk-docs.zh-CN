---
title: Namespace 管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4638c47c-3cdd-43af-aa00-da98e7293503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa476034a578be24bf388c87f38f910565cd2548
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022467"
---
# <a name="namespace-management"></a><span data-ttu-id="fcf5d-102">命名空间管理</span><span class="sxs-lookup"><span data-stu-id="fcf5d-102">Namespace Management</span></span>
<span data-ttu-id="fcf5d-103">BizTalk 编辑器支持命名空间。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-103">BizTalk Editor provides support for namespaces.</span></span> <span data-ttu-id="fcf5d-104">XML 命名空间是可以在 XML 消息中用作元素或属性名称的名称集合。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-104">An XML namespace is a collection of names that can be used as element or attribute names in an XML message.</span></span> <span data-ttu-id="fcf5d-105">命名空间对元素和属性名称进行限定，以避免可能在相同架构中其他位置定义的相同元素和属性名称之间存在冲突。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-105">The namespace qualifies element and attribute names to avoid conflicts between the same element and attribute names that might be defined elsewhere within the same schema.</span></span>  
  
 <span data-ttu-id="fcf5d-106">命名空间由统一资源定位符 (URI) 标识为统一资源定位符 (URL) 或统一资源名称 (URN)。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-106">Namespaces are identified by a Universal Resource Identifier (URI), either as a Uniform Resource Locator (URL) or a Uniform Resource Name (URN).</span></span> <span data-ttu-id="fcf5d-107">还为它们提供了较短的前缀别名，该别名预置了分隔冒号 (:)，以分隔元素或属性名称本身。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-107">They are also given a typically short prefix alias that is prepended with a separating colon (:) from the element or attribute name itself.</span></span> <span data-ttu-id="fcf5d-108">例如，它是经常可以看到以下命名空间声明内的**架构**架构的 XSD 表示形式中的元素。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-108">For example, it is common to see the following namespace declaration within the **schema** element in the XSD representation of the schema.</span></span>  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 <span data-ttu-id="fcf5d-109">前缀为 xs，您看到在整个 XSD 表示形式符合条件的此类元素作为**元素**元素 (xs: element) 和**属性**元素 (xs:attribute)。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-109">The prefix is xs, which you see throughout the XSD representation, qualifying such elements as the **element** element (xs:element) and the **attribute** element (xs:attribute).</span></span>  
  
 <span data-ttu-id="fcf5d-110">当首次创建新的架构，而不考虑它是消息架构还是属性架构，务必要设置**目标 Namespace**的属性**架构**节点正确。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-110">When you first create a new schema, regardless of whether it is a message schema or a property schema, it is important to set the **Target Namespace** property of the **Schema** node properly.</span></span> <span data-ttu-id="fcf5d-111">在其他架构使用导入/包括/重新定义机制使用该架构之前以及定义任何属性升级之前，您需要建立目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-111">You need to establish the target namespace before the schema is used by another schema with the import/include/redefine mechanisms, and before any property promotions are defined.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="fcf5d-112">如果要使用仅大小写的两个命名空间，BizTalk 数据库必须安装使用区分大小写的排序规则。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-112">If you will be using two namespaces that vary only by case, the BizTalk database must be installed with a case-sensitive collation.</span></span> <span data-ttu-id="fcf5d-113">例如，区分大小写的排序规则包括启用了区分大小写功能的二进制和非二进制排序规则。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-113">Examples of case-sensitive collations include binary and non-binary collations with case-sensitivity enabled.</span></span> <span data-ttu-id="fcf5d-114">如果不这样，则架构解析将由于 XML 区分大小写而失败。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-114">If this is not done, schema resolution will fail because XML is case-sensitive.</span></span>  
  
 <span data-ttu-id="fcf5d-115">以下两个命名空间作为命名空间声明自动添加到架构的 XML 架构定义 (XSD) 语言表示形式中的 schema 元素：</span><span class="sxs-lookup"><span data-stu-id="fcf5d-115">The following two namespaces are automatically added as namespace declarations to the schema element in the XML Schema definition (XSD) language representation of the schema:</span></span>  
  
- <span data-ttu-id="fcf5d-116">xmlns:b ="<http://schemas.microsoft.com/BizTalk/2003>"</span><span class="sxs-lookup"><span data-stu-id="fcf5d-116">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>"</span></span>  
  
- <span data-ttu-id="fcf5d-117">xmlns:xs ="<http://www.w3.org/2001/XMLSchema>"</span><span class="sxs-lookup"><span data-stu-id="fcf5d-117">xmlns:xs="<http://www.w3.org/2001/XMLSchema>"</span></span>  
  
  <span data-ttu-id="fcf5d-118">在正创建的架构中使用其他架构的过程中，将会声明其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-118">In the course of using other schemas within the schema you are creating, other namespaces will be declared.</span></span> <span data-ttu-id="fcf5d-119">您可以检查这些命名空间，以及自动包括的命名空间中**导入**对话框，可以使用访问**导入**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-119">You can examine these namespaces, as well as the automatically included namespaces, in the **Imports** dialog box that you can access by using the **Imports** property of the **Schema** node.</span></span> <span data-ttu-id="fcf5d-120">要创建使用其他架构中的其他架构中声明的数据类型有关的详细信息，请参阅[，使用其他架构](../core/schemas-that-use-other-schemas.md)并[创建使用其他架构的](../core/how-to-create-schemas-that-use-other-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-120">For more information about using other data types declared in other schemas within the schema you are creating, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md) and [Creating Schemas That Use Other Schemas](../core/how-to-create-schemas-that-use-other-schemas.md).</span></span>  
  
  <span data-ttu-id="fcf5d-121">在中，可以检查与属性架构相关联的命名空间**升级属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="fcf5d-121">Namespaces associated with property schemas can be examined in the **Promote Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf5d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcf5d-122">See Also</span></span>  
 [<span data-ttu-id="fcf5d-123">创建架构时的注意事项</span><span class="sxs-lookup"><span data-stu-id="fcf5d-123">Considerations When Creating Schemas</span></span>](../core/considerations-when-creating-schemas.md)