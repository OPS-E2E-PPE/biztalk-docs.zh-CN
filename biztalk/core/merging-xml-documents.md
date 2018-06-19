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
# <a name="merging-xml-documents"></a>合并 XML 文档
其中一条消息， **OrderBroker**业务流程都创建一个来更新 SQL Server 历史记录数据库。 此消息包含订单消息中的字段以及原始订单消息。 在此消息中，原始订单显示为字符串。 这与数据库中订单历史记录的数据类型相匹配。  
  
 无法使用映射来完成以下过程：获取消息，将该消息转换为字符串，然后将其放置到其他消息中。 业务流程使用 helper 函数， **InsertOrderBody**，以将原始顺序消息作为一个字符串添加到基历史记录消息。  
  
 **OrderBroker**业务流程使用映射， **CSR_OrderRequest_To_SQLHistoryInsert**、 将订单消息转换为基的历史记录消息。 作为的特性将显示的订单信息**OrderLog**元素。 原始消息显示为此元素的其他属性。  
  
 **InsertOrderBody**方法将作为自变量的原始的订单消息，基历史记录消息，并返回已完成的历史记录消息。 以下代码显示了将消息作为字符串插入的方法的各个部分：  
  
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
  
 验证它接收两个参数后, **InsertOrderBody**方法找到历史记录更新消息的根节点。 然后，它创建一个节点，其中包含**OriginalMsg**属性，并将原始顺序消息分配给属性的值。 此时，该节点只是存在而已， 它还不是元素的一部分。  
  
 在创建属性节点后，该方法将查找要使用 XPath 表达式附加该属性的节点。 在找到该节点之后，该方法将此属性节点添加到该节点的属性集合中。  
  
> [!NOTE]
>  尽管**OriginalMsg**属性基历史记录消息中最初不存在，它是，当然，架构中指定。 在代码中向消息添加的 XML 元素应在这些消息的架构中指定。  
  
## <a name="see-also"></a>另请参阅  
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)