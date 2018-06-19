---
title: 合并 XML 文档 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML, documents
- process management solution tutorial, merging XML documents
ms.assetid: 444c983a-397a-4342-85e1-80bb152986d9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94684cd9bf1992a592efd7b97c46838c9c9a3134
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262637"
---
# <a name="merging-xml-documents"></a><span data-ttu-id="39272-102">合并 XML 文档</span><span class="sxs-lookup"><span data-stu-id="39272-102">Merging XML Documents</span></span>
<span data-ttu-id="39272-103">其中一条消息， **OrderBroker**业务流程都创建一个来更新 SQL Server 历史记录数据库。</span><span class="sxs-lookup"><span data-stu-id="39272-103">One of the messages that the **OrderBroker** orchestration creates is one to update the SQL Server history database.</span></span> <span data-ttu-id="39272-104">此消息包含订单消息中的字段以及原始订单消息。</span><span class="sxs-lookup"><span data-stu-id="39272-104">This message contains fields from the order message as well as the original order message.</span></span> <span data-ttu-id="39272-105">在此消息中，原始订单显示为字符串。</span><span class="sxs-lookup"><span data-stu-id="39272-105">The original order appears in this message a string.</span></span> <span data-ttu-id="39272-106">这与数据库中订单历史记录的数据类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="39272-106">This matches the data type for the order history in the database.</span></span>  
  
 <span data-ttu-id="39272-107">无法使用映射来完成以下过程：获取消息，将该消息转换为字符串，然后将其放置到其他消息中。</span><span class="sxs-lookup"><span data-stu-id="39272-107">It isn't possible to take a message, convert it to a string, and place it in another message with a map.</span></span> <span data-ttu-id="39272-108">业务流程使用 helper 函数， **InsertOrderBody**，以将原始顺序消息作为一个字符串添加到基历史记录消息。</span><span class="sxs-lookup"><span data-stu-id="39272-108">The orchestration uses a helper function, **InsertOrderBody**, to add the original order message as a string to the base history message.</span></span>  
  
 <span data-ttu-id="39272-109">**OrderBroker**业务流程使用映射， **CSR_OrderRequest_To_SQLHistoryInsert**、 将订单消息转换为基的历史记录消息。</span><span class="sxs-lookup"><span data-stu-id="39272-109">The **OrderBroker** orchestration uses the map, **CSR_OrderRequest_To_SQLHistoryInsert**, to convert the order message into the base history message.</span></span> <span data-ttu-id="39272-110">作为的特性将显示的订单信息**OrderLog**元素。</span><span class="sxs-lookup"><span data-stu-id="39272-110">The information for an order appears as attributes of an **OrderLog** element.</span></span> <span data-ttu-id="39272-111">原始消息显示为此元素的其他属性。</span><span class="sxs-lookup"><span data-stu-id="39272-111">The original message appears as another attribute of this element.</span></span>  
  
 <span data-ttu-id="39272-112">**InsertOrderBody**方法将作为自变量的原始的订单消息，基历史记录消息，并返回已完成的历史记录消息。</span><span class="sxs-lookup"><span data-stu-id="39272-112">The **InsertOrderBody** method takes as arguments the original order message, the base history message, and returns the completed history message.</span></span> <span data-ttu-id="39272-113">以下代码显示了将消息作为字符串插入的方法的各个部分：</span><span class="sxs-lookup"><span data-stu-id="39272-113">The following code shows the portions of the method that inserts the message as a string:</span></span>  
  
```  
public static XmlDocument InsertOrderBody( XmlDocument orderDoc,   
                                    XmlDocument historyInsertDoc)  
{  
...  
    XmlNode root = historyInsertDoc.FirstChild;  
  
    //Create a new attribute.  
    XmlNode attr = historyInsertDoc.CreateNode(XmlNodeType.Attribute,  
                                     "OriginalMsg", root.NamespaceURI);  
    attr.Value = orderDoc.OuterXml;  
  
    try  
    {  
        // XPath expression not shown for formatting reasons and  
        // replaces ".." in the following code  
        XmlNode destnode = historyInsertDoc.SelectSingleNode("..");  
        //Add the attribute to the document.  
        destnode.Attributes.SetNamedItem(attr);  
    }  
...  
  
    return historyInsertDoc;  
}  
```  
  
 <span data-ttu-id="39272-114">验证它接收两个参数后, **InsertOrderBody**方法找到历史记录更新消息的根节点。</span><span class="sxs-lookup"><span data-stu-id="39272-114">After verifying that it received both arguments, the **InsertOrderBody** method finds the root node of the history update message.</span></span> <span data-ttu-id="39272-115">然后，它创建一个节点，其中包含**OriginalMsg**属性，并将原始顺序消息分配给属性的值。</span><span class="sxs-lookup"><span data-stu-id="39272-115">It then creates a node containing the **OriginalMsg** attribute and assigns the original order message to the attribute's value.</span></span> <span data-ttu-id="39272-116">此时，该节点只是存在而已，</span><span class="sxs-lookup"><span data-stu-id="39272-116">At this point, the node simply exists.</span></span> <span data-ttu-id="39272-117">它还不是元素的一部分。</span><span class="sxs-lookup"><span data-stu-id="39272-117">It is not yet part of a element.</span></span>  
  
 <span data-ttu-id="39272-118">在创建属性节点后，该方法将查找要使用 XPath 表达式附加该属性的节点。</span><span class="sxs-lookup"><span data-stu-id="39272-118">After creating the attribute node, the method finds the node where it will attach the attribute using an XPath expression.</span></span> <span data-ttu-id="39272-119">在找到该节点之后，该方法将此属性节点添加到该节点的属性集合中。</span><span class="sxs-lookup"><span data-stu-id="39272-119">After it locates the node, the method adds the attribute node to the attributes collection of the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39272-120">尽管**OriginalMsg**属性基历史记录消息中最初不存在，它是，当然，架构中指定。</span><span class="sxs-lookup"><span data-stu-id="39272-120">Although the **OriginalMsg** attribute does not initially exist in the base history message, it is, of course, specified in the schema.</span></span> <span data-ttu-id="39272-121">在代码中向消息添加的 XML 元素应在这些消息的架构中指定。</span><span class="sxs-lookup"><span data-stu-id="39272-121">XML elements that you add to your messages in code should be specified in the schemas for those messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39272-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39272-122">See Also</span></span>  
 [<span data-ttu-id="39272-123">实现突出显示的业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="39272-123">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)