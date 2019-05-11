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
# <a name="merging-xml-documents"></a>合并 XML 文档
其中一条消息， **OrderBroker**业务流程将创建一个要更新 SQL Server 历史记录数据库。 此消息包含订单消息，以及原始订单消息中的字段。 原始订单显示在此消息字符串。 此匹配数据库中的订单历史记录的数据类型。  
  
 它不能执行一条消息，将其转换为字符串，并将其放在一个带有地图的另一条消息。 业务流程使用 helper 函数， **InsertOrderBody**，以将原始订单消息作为字符串添加到基础历史记录消息。  
  
 **OrderBroker**业务流程使用映射**CSR_OrderRequest_To_SQLHistoryInsert**，以将订单消息转换成基础历史记录消息。 有关订单信息显示为的属性**OrderLog**元素。 原始消息显示为此元素的另一个属性。  
  
 **InsertOrderBody**方法作为参数采用原始订单消息和基础历史记录消息，并返回已完成的历史记录消息。 下面的代码显示了用于将消息作为字符串的方法的部分：  
  
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
  
 验证它接收到这两个参数后, **InsertOrderBody**方法查找历史记录更新消息的根节点。 然后，创建一个节点，其中包含**OriginalMsg**属性，并将原始订单消息分配给该属性的值。 此时，该节点只是存在。 它尚不某个元素的一部分。  
  
 在创建后的特性节点，该方法查找它将使用 XPath 表达式的属性的节点。 在找到该节点后，该方法将属性节点添加到该节点的属性集合。  
  
> [!NOTE]
>  尽管**OriginalMsg**最初基础历史记录消息中不存在属性，它是，当然，在架构中指定。 您将添加到代码中的消息的 XML 元素应指定这些消息的架构中。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施重点](../core/implementation-highlights-of-the-business-process-management-solution.md)