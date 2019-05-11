---
title: 合并 XML 文档 |Microsoft Docs
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
ms.openlocfilehash: 442df8925a37089d7a5ae933dcc572947a161095
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394592"
---
# <a name="merging-xml-documents"></a><span data-ttu-id="227a8-102">合并 XML 文档</span><span class="sxs-lookup"><span data-stu-id="227a8-102">Merging XML Documents</span></span>
<span data-ttu-id="227a8-103">其中一条消息， **OrderBroker**业务流程将创建一个要更新 SQL Server 历史记录数据库。</span><span class="sxs-lookup"><span data-stu-id="227a8-103">One of the messages that the **OrderBroker** orchestration creates is one to update the SQL Server history database.</span></span> <span data-ttu-id="227a8-104">此消息包含订单消息，以及原始订单消息中的字段。</span><span class="sxs-lookup"><span data-stu-id="227a8-104">This message contains fields from the order message as well as the original order message.</span></span> <span data-ttu-id="227a8-105">原始订单显示在此消息字符串。</span><span class="sxs-lookup"><span data-stu-id="227a8-105">The original order appears in this message a string.</span></span> <span data-ttu-id="227a8-106">此匹配数据库中的订单历史记录的数据类型。</span><span class="sxs-lookup"><span data-stu-id="227a8-106">This matches the data type for the order history in the database.</span></span>  
  
 <span data-ttu-id="227a8-107">它不能执行一条消息，将其转换为字符串，并将其放在一个带有地图的另一条消息。</span><span class="sxs-lookup"><span data-stu-id="227a8-107">It isn't possible to take a message, convert it to a string, and place it in another message with a map.</span></span> <span data-ttu-id="227a8-108">业务流程使用 helper 函数， **InsertOrderBody**，以将原始订单消息作为字符串添加到基础历史记录消息。</span><span class="sxs-lookup"><span data-stu-id="227a8-108">The orchestration uses a helper function, **InsertOrderBody**, to add the original order message as a string to the base history message.</span></span>  
  
 <span data-ttu-id="227a8-109">**OrderBroker**业务流程使用映射**CSR_OrderRequest_To_SQLHistoryInsert**，以将订单消息转换成基础历史记录消息。</span><span class="sxs-lookup"><span data-stu-id="227a8-109">The **OrderBroker** orchestration uses the map, **CSR_OrderRequest_To_SQLHistoryInsert**, to convert the order message into the base history message.</span></span> <span data-ttu-id="227a8-110">有关订单信息显示为的属性**OrderLog**元素。</span><span class="sxs-lookup"><span data-stu-id="227a8-110">The information for an order appears as attributes of an **OrderLog** element.</span></span> <span data-ttu-id="227a8-111">原始消息显示为此元素的另一个属性。</span><span class="sxs-lookup"><span data-stu-id="227a8-111">The original message appears as another attribute of this element.</span></span>  
  
 <span data-ttu-id="227a8-112">**InsertOrderBody**方法作为参数采用原始订单消息和基础历史记录消息，并返回已完成的历史记录消息。</span><span class="sxs-lookup"><span data-stu-id="227a8-112">The **InsertOrderBody** method takes as arguments the original order message, the base history message, and returns the completed history message.</span></span> <span data-ttu-id="227a8-113">下面的代码显示了用于将消息作为字符串的方法的部分：</span><span class="sxs-lookup"><span data-stu-id="227a8-113">The following code shows the portions of the method that inserts the message as a string:</span></span>  
  
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
  
 <span data-ttu-id="227a8-114">验证它接收到这两个参数后, **InsertOrderBody**方法查找历史记录更新消息的根节点。</span><span class="sxs-lookup"><span data-stu-id="227a8-114">After verifying that it received both arguments, the **InsertOrderBody** method finds the root node of the history update message.</span></span> <span data-ttu-id="227a8-115">然后，创建一个节点，其中包含**OriginalMsg**属性，并将原始订单消息分配给该属性的值。</span><span class="sxs-lookup"><span data-stu-id="227a8-115">It then creates a node containing the **OriginalMsg** attribute and assigns the original order message to the attribute's value.</span></span> <span data-ttu-id="227a8-116">此时，该节点只是存在。</span><span class="sxs-lookup"><span data-stu-id="227a8-116">At this point, the node simply exists.</span></span> <span data-ttu-id="227a8-117">它尚不某个元素的一部分。</span><span class="sxs-lookup"><span data-stu-id="227a8-117">It is not yet part of a element.</span></span>  
  
 <span data-ttu-id="227a8-118">在创建后的特性节点，该方法查找它将使用 XPath 表达式的属性的节点。</span><span class="sxs-lookup"><span data-stu-id="227a8-118">After creating the attribute node, the method finds the node where it will attach the attribute using an XPath expression.</span></span> <span data-ttu-id="227a8-119">在找到该节点后，该方法将属性节点添加到该节点的属性集合。</span><span class="sxs-lookup"><span data-stu-id="227a8-119">After it locates the node, the method adds the attribute node to the attributes collection of the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="227a8-120">尽管**OriginalMsg**最初基础历史记录消息中不存在属性，它是，当然，在架构中指定。</span><span class="sxs-lookup"><span data-stu-id="227a8-120">Although the **OriginalMsg** attribute does not initially exist in the base history message, it is, of course, specified in the schema.</span></span> <span data-ttu-id="227a8-121">您将添加到代码中的消息的 XML 元素应指定这些消息的架构中。</span><span class="sxs-lookup"><span data-stu-id="227a8-121">XML elements that you add to your messages in code should be specified in the schemas for those messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227a8-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="227a8-122">See Also</span></span>  
 [<span data-ttu-id="227a8-123">业务流程管理解决方案的实施重点</span><span class="sxs-lookup"><span data-stu-id="227a8-123">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)