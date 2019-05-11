---
title: 消息赋值中使用 Xpath |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XPaths, XPath function
- XPaths, messages
- code samples, XPaths
- messages, XPaths
- XPath function
- XPaths, code samples
- XPaths, nodes
ms.assetid: f2e12409-bb77-4315-b03b-5c7736ae51d5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18968936cc1271d42fdf490ce2395c437b3ecfd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396729"
---
# <a name="using-xpaths-in-message-assignments"></a>消息赋值中使用 Xpath
可以使用**xpath**函数将一个 XPath 值分配到消息部分，或将值分配为 XPath 引用消息部分。 将分配给消息和消息部分的详细信息，请参阅[构造消息](../core/constructing-messages.md)。  
  
> [!NOTE]
>  Xpath 函数的详细信息，请参阅 XML 路径语言 (XPath) 上的第三方文档。  
  
> [!NOTE]
>  利用**xpath**函数并不限于消息赋值。 您还可以使用它在任何表达式中，例如：  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  如果你想要将值分配为字符串，使用 XPath string （） 函数。 例如：  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  引擎不识别架构，因此只能读取值或将值写入到存在于包含一个节点 （完整路径必须存在） 的消息或引擎将引发异常。 这是 true，即使您提供默认值。  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a>将分配到消息部分中的 XPath  
 请考虑以下架构：  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="catalog">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element minOccurs="1" maxOccurs="unbounded" name="book">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="title" type="xs:string" />  
              <xs:element name="author">  
                <xs:complexType>  
                  <xs:sequence>  
                    <xs:element name="FirstName" type="xs:string" />  
                    <xs:element name="LastName" type="xs:string" />  
                  </xs:sequence>  
                </xs:complexType>  
              </xs:element>  
              <xs:element name="price" type="xs:string" />  
            </xs:sequence>  
            <xs:attribute name="country" type="xs:string" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 您可以按如下所示使用函数设置该架构类型的文档实例的值：  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a>通过 XPath 将分配到消息部分  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a>使用 XPath 从节点和节点将分配设置  
 此外可以使用 XPath 将 XML 节点和节点集到 XML 元素、 一个类或基于架构或基于类的消息。  
  
 假设有 XML 可序列化的类称为 Book，并考虑下面的示例：  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 示例一 — 选择目录中的第四个书元素，并将其分配给一个 XML 元素变量：  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 示例二 — 选择目录中的第四个书元素，并将其使用 XML 反序列化到 Book 类实例转换：  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 示例三 — 选择目录中的第四个书元素，并将其转换为 Book 类型的消息：  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 示例四 — 选择的目录，其中 MyMethod 将 XmlNodeSet 作为参数中的所有 book 元素：  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 示例五 — 将一个书元素添加到"BookOfTheMonth"容器：  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 示例六 — 将价格不超过二十或到一组推荐书籍的所有书都添加：  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 示例七 — 调用返回的 XML 元素的用户代码：  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 之前应用示例五和七个示例：  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 应用示例五和七个示例： 之后  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth>  
              <Book country="USA">  
                     <title>McSharry</title>  
                     <author>  
                            <FirstName>Nancy</FirstName>  
                            <LastName>Jensen</LastName>  
                     </author>  
              </Book>  
       </BookOfTheMonth>  
       <BestPriceBooks/>  
       <AdvertisedByPartner>  
              <Book country="USA">  
                     <title>The Rooster</title>  
                     <author>  
                            <FirstName>Mindy</FirstName>  
                            <LastName>Martin</LastName>  
                     </author>  
              </Book>  
       </AdvertisedByPartner>  
</RecommendedBooks>  
```