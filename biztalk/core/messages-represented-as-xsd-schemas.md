---
title: 消息表示为 XSD 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Assignment shape [Orchestration Designer], maps
- maps, transforms
- Expression Editor, assigning maps
ms.assetid: 646e84d4-1dcc-4f92-9205-84cb6c7df297
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c15de5c7bbf4c5d8639c1d05a427d48686b58b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324964"
---
# <a name="messages-represented-as-xsd-schemas"></a>表示为 XSD 架构的消息
XSD 消息类型的模板 XML 实例是在设计时定义，然后存储在磁盘上。 在运行时，.NET 组件提取磁盘中的 XML，并将其作为 XmlDocument 返回。 业务流程代码可以将此 XmlDocument 结果分配到业务流程中声明的消息实例。  
  
 **消息赋值**形状有一行代码：  
  
```  
MsgOut = CreateMsgHelper.Helper.GetXmlDocumentTemplate();  
```  
  
 创建 XmlDocument 帮助程序组件都具有一个静态方法：  
  
```  
private static XmlDocument _template = null;  
private static object _sync = new object();  
private static String LOCATION = @"C:\MyTemplateLocation\MyMsgTemplate.xml";  
  
public static XmlDocument GetXmlDocumentTemplate()  
{  
   XmlDocument doc = _template;  
   if (doc == null)  
   {  
      // Load the doc template from disk.  
      doc = new XmlDocument();  
      XmlTextReader reader = new XmlTextReader(LOCATION);  
      doc.Load(reader);  
  
      // Synchronize assignment to _template.  
      lock (_sync)  
      {  
         XmlDocument doc2 = _template;  
         if (doc2 == null)  
         {  
            _template = doc;  
         }  
         else  
         {  
            // Another thread beat us to it.  
            doc = doc2;  
         }  
      }  
   }  
  
   // Need to explicitly create a clone so that we are not  
   // referencing the same object statically held by this class.  
   doc = (XmlDocument) doc.CloneNode(true);  
   return doc;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [表示为.NET 类的消息](../core/messages-represented-as-net-classes.md)   
 [表示为 XLANGMessage 的消息](../core/messages-represented-as-xlangmessage.md)   
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)