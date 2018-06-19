---
title: 在消息分配中使用 Xpath |Microsoft 文档
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
ms.openlocfilehash: d9ec1e5b56f382601c79324df8651c91c483cb4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288109"
---
# <a name="using-xpaths-in-message-assignments"></a>在消息分配中使用 Xpath
你可以使用**xpath**函数将一个 XPath 值分配到消息部分，或将值分配给 XPath 引用消息部分。 将分配给消息和消息部分的详细信息，请参阅[构造消息](../core/constructing-messages.md)。  
  
> [!NOTE]
>  有关 xpath 函数的详细信息，请参阅 XML Path 语言 (XPath) 的第三方文档。  
  
> [!NOTE]
>  使用**xpath**函数并不局限于消息赋值。 您还可以在任何表达式中使用它，例如：  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  如果要对字符串赋值，请使用 XPath string() 函数。 例如：  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  引擎不识别架构，因此您只能从包含消息（必须存在完整路径）中现有的节点读取值或向其中写入值，否则引擎将引发异常。 即使您提供默认值，也是如此。  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a>对消息部分中的 XPath 赋值  
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
  
 您可以使用如下函数设置该架构类型的文档实例的值：  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a>通过 XPath 对消息部分赋值  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a>使用 XPath 从节点和节点集赋值  
 您也可以使用 XPath 将 XML 节点和节点集赋予一个 XML 元素、一个类或者一条基于架构或基于类的消息。  
  
 假设有一个称为 Book 的 XML 序列化类，请考虑下列示例：  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 示例一 — 选择目录中的第四个书元素，并将其赋予一个 XML 元素变量：  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 示例二 — 选择目录中的第四个书元素，并使用 XML 反序列化将其转换为 Book 类实例：  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 示例三 — 选择目录中的第四个书元素，并将其转换为 Book 类型的消息：  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 示例四 — 选择目录中的所有书元素，其中 MyMethod 将 XmlNodeSet 作为参数：  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 示例五 — 将一个书元素添加到“BookOfTheMonth”容器：  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 示例六 — 将价格不超过二十的所有书添加到一组推荐书中：  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 示例七 — 调用返回 XML 元素的用户代码：  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 应用示例五和示例七之前：  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 应用示例五和示例七之后：  
  
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