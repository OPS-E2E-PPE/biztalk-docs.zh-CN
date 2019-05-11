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
ms.openlocfilehash: f313ba2063e2184b4c0fe755c32bc0cbf07e0409
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323546"
---
# <a name="namespace-management"></a><span data-ttu-id="14272-102">Namespace 管理</span><span class="sxs-lookup"><span data-stu-id="14272-102">Namespace Management</span></span>
<span data-ttu-id="14272-103">BizTalk 编辑器为命名空间提供支持。</span><span class="sxs-lookup"><span data-stu-id="14272-103">BizTalk Editor provides support for namespaces.</span></span> <span data-ttu-id="14272-104">XML 命名空间是可以用作 XML 消息中的元素或属性名称的名称的集合。</span><span class="sxs-lookup"><span data-stu-id="14272-104">An XML namespace is a collection of names that can be used as element or attribute names in an XML message.</span></span> <span data-ttu-id="14272-105">命名空间限定元素和属性名，以避免同一元素和属性名称可能相同架构中其他位置定义之间的冲突。</span><span class="sxs-lookup"><span data-stu-id="14272-105">The namespace qualifies element and attribute names to avoid conflicts between the same element and attribute names that might be defined elsewhere within the same schema.</span></span>  
  
 <span data-ttu-id="14272-106">命名空间进行标识的通用资源标识符 (URI)，作为统一资源定位器 (URL) 或统一资源名称 (URN)。</span><span class="sxs-lookup"><span data-stu-id="14272-106">Namespaces are identified by a Universal Resource Identifier (URI), either as a Uniform Resource Locator (URL) or a Uniform Resource Name (URN).</span></span> <span data-ttu-id="14272-107">系统会提供较短的前缀别名，该别名预置了分隔冒号 （:） 中的元素或属性名称本身。</span><span class="sxs-lookup"><span data-stu-id="14272-107">They are also given a typically short prefix alias that is prepended with a separating colon (:) from the element or attribute name itself.</span></span> <span data-ttu-id="14272-108">例如，它是经常可以看到以下命名空间声明内的**架构**架构的 XSD 表示形式中的元素。</span><span class="sxs-lookup"><span data-stu-id="14272-108">For example, it is common to see the following namespace declaration within the **schema** element in the XSD representation of the schema.</span></span>  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 <span data-ttu-id="14272-109">前缀为 xs，您看到在整个 XSD 表示形式符合条件的此类元素作为**元素**元素 (xs: element) 和**属性**元素 (xs:attribute)。</span><span class="sxs-lookup"><span data-stu-id="14272-109">The prefix is xs, which you see throughout the XSD representation, qualifying such elements as the **element** element (xs:element) and the **attribute** element (xs:attribute).</span></span>  
  
 <span data-ttu-id="14272-110">当首次创建新的架构，而不考虑它是消息架构还是属性架构，务必要设置**目标 Namespace**的属性**架构**节点正确。</span><span class="sxs-lookup"><span data-stu-id="14272-110">When you first create a new schema, regardless of whether it is a message schema or a property schema, it is important to set the **Target Namespace** property of the **Schema** node properly.</span></span> <span data-ttu-id="14272-111">你需要之前导入/包括/重新定义机制，则由另一个架构使用的架构和任何属性升级定义建立目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="14272-111">You need to establish the target namespace before the schema is used by another schema with the import/include/redefine mechanisms, and before any property promotions are defined.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="14272-112">如果要使用仅大小写的两个命名空间，BizTalk 数据库必须安装使用区分大小写的排序规则。</span><span class="sxs-lookup"><span data-stu-id="14272-112">If you will be using two namespaces that vary only by case, the BizTalk database must be installed with a case-sensitive collation.</span></span> <span data-ttu-id="14272-113">区分大小写的排序规则的示例包括与启用了区分大小写的二进制和非二进制排序规则。</span><span class="sxs-lookup"><span data-stu-id="14272-113">Examples of case-sensitive collations include binary and non-binary collations with case-sensitivity enabled.</span></span> <span data-ttu-id="14272-114">如果不执行此操作，架构解析将失败，因为 XML 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="14272-114">If this is not done, schema resolution will fail because XML is case-sensitive.</span></span>  
  
 <span data-ttu-id="14272-115">以下两个命名空间将自动添加到架构的 XML 架构定义 (XSD) 语言表示形式中 schema 元素的命名空间声明为：</span><span class="sxs-lookup"><span data-stu-id="14272-115">The following two namespaces are automatically added as namespace declarations to the schema element in the XML Schema definition (XSD) language representation of the schema:</span></span>  
  
- <span data-ttu-id="14272-116">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>"</span><span class="sxs-lookup"><span data-stu-id="14272-116">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>"</span></span>  
  
- <span data-ttu-id="14272-117">xmlns:xs="<http://www.w3.org/2001/XMLSchema>"</span><span class="sxs-lookup"><span data-stu-id="14272-117">xmlns:xs="<http://www.w3.org/2001/XMLSchema>"</span></span>  
  
  <span data-ttu-id="14272-118">在过程中使用其他架构中创建的架构，将声明其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="14272-118">In the course of using other schemas within the schema you are creating, other namespaces will be declared.</span></span> <span data-ttu-id="14272-119">您可以检查这些命名空间，以及自动包括的命名空间中**导入**对话框，可以使用访问**导入**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="14272-119">You can examine these namespaces, as well as the automatically included namespaces, in the **Imports** dialog box that you can access by using the **Imports** property of the **Schema** node.</span></span> <span data-ttu-id="14272-120">要创建使用其他架构中的其他架构中声明的数据类型有关的详细信息，请参阅[，使用其他架构](../core/schemas-that-use-other-schemas.md)并[创建使用其他架构的](../core/how-to-create-schemas-that-use-other-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="14272-120">For more information about using other data types declared in other schemas within the schema you are creating, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md) and [Creating Schemas That Use Other Schemas](../core/how-to-create-schemas-that-use-other-schemas.md).</span></span>  
  
  <span data-ttu-id="14272-121">在中，可以检查与属性架构相关联的命名空间**升级属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="14272-121">Namespaces associated with property schemas can be examined in the **Promote Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14272-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="14272-122">See Also</span></span>  
 [<span data-ttu-id="14272-123">创建架构时的注意事项</span><span class="sxs-lookup"><span data-stu-id="14272-123">Considerations When Creating Schemas</span></span>](../core/considerations-when-creating-schemas.md)