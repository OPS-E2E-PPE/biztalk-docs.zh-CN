---
title: 消息表示为 XSD 架构 |Microsoft 文档
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
ms.openlocfilehash: 47242dc01ed05ca2ab3c2cb71daffc5a81f9462c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262965"
---
# <a name="messages-represented-as-xsd-schemas"></a><span data-ttu-id="dfdd1-102">表示为 XSD 架构的消息</span><span class="sxs-lookup"><span data-stu-id="dfdd1-102">Messages Represented as XSD Schemas</span></span>
<span data-ttu-id="dfdd1-103">XSD 消息类型的模板 XML 实例是在设计时定义，然后存储在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="dfdd1-103">A template XML instance of the XSD message type is defined at design time and then stored on disk.</span></span> <span data-ttu-id="dfdd1-104">在运行时，.NET 组件拾取从磁盘的 XML，并将其作为 XmlDocument 返回。</span><span class="sxs-lookup"><span data-stu-id="dfdd1-104">At run time, a .NET component picks up the XML from disk and returns it as an XmlDocument.</span></span> <span data-ttu-id="dfdd1-105">业务流程代码可以将此 XmlDocument 结果分配给在业务流程中声明的消息实例。</span><span class="sxs-lookup"><span data-stu-id="dfdd1-105">The orchestration code can assign this XmlDocument result to the message instance declared in the orchestration.</span></span>  
  
 <span data-ttu-id="dfdd1-106">**消息分配**形状具有一行代码：</span><span class="sxs-lookup"><span data-stu-id="dfdd1-106">The **Message Assignment** shape has a single line of code:</span></span>  
  
```  
MsgOut = CreateMsgHelper.Helper.GetXmlDocumentTemplate();  
```  
  
 <span data-ttu-id="dfdd1-107">创建 XmlDocument 帮助程序组件具有一个静态方法：</span><span class="sxs-lookup"><span data-stu-id="dfdd1-107">The Helper Component that creates the XmlDocument has a single static method:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dfdd1-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfdd1-108">See Also</span></span>  
 <span data-ttu-id="dfdd1-109">[.NET 类表示的消息](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="dfdd1-109">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 <span data-ttu-id="dfdd1-110">[表示为 XLANGMessage 的消息](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="dfdd1-110">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="dfdd1-111">构造在用户代码中的消息</span><span class="sxs-lookup"><span data-stu-id="dfdd1-111">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)