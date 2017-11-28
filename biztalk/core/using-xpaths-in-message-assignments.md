---
title: "在消息分配中使用 Xpath |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ec1e5b56f382601c79324df8651c91c483cb4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-xpaths-in-message-assignments"></a><span data-ttu-id="d0abf-102">在消息分配中使用 Xpath</span><span class="sxs-lookup"><span data-stu-id="d0abf-102">Using XPaths in Message Assignments</span></span>
<span data-ttu-id="d0abf-103">你可以使用**xpath**函数将一个 XPath 值分配到消息部分，或将值分配给 XPath 引用消息部分。</span><span class="sxs-lookup"><span data-stu-id="d0abf-103">You can use the **xpath** function to assign an XPath value to a message part, or to assign a value to an XPath that refers to a message part.</span></span> <span data-ttu-id="d0abf-104">将分配给消息和消息部分的详细信息，请参阅[构造消息](../core/constructing-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="d0abf-104">For more information on assigning to messages and message parts, see [Constructing Messages](../core/constructing-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0abf-105">有关 xpath 函数的详细信息，请参阅 XML Path 语言 (XPath) 的第三方文档。</span><span class="sxs-lookup"><span data-stu-id="d0abf-105">For more information on the xpath function, see third-party documentation on the XML Path Language (XPath).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0abf-106">使用**xpath**函数并不局限于消息赋值。</span><span class="sxs-lookup"><span data-stu-id="d0abf-106">The use of the **xpath** function is not limited to message assignment.</span></span> <span data-ttu-id="d0abf-107">您还可以在任何表达式中使用它，例如：</span><span class="sxs-lookup"><span data-stu-id="d0abf-107">You can also use it in any expression, for example:</span></span>  
  
```  
If ((System.Double) xpath(_RequestMessage.part, "number(//book[last()]/price)") == 75.00 && (System.Boolean) xpath(msgBoolean, "string(//boolean)") == false)...  
```  
  
> [!NOTE]
>  <span data-ttu-id="d0abf-108">如果要对字符串赋值，请使用 XPath string() 函数。</span><span class="sxs-lookup"><span data-stu-id="d0abf-108">If you want to assign a value to a string, use the XPath string() function.</span></span> <span data-ttu-id="d0abf-109">例如：</span><span class="sxs-lookup"><span data-stu-id="d0abf-109">For example:</span></span>  
  
```  
myString = xpath(msg, "string(/*/book[1]/title)");  
```  
  
> [!NOTE]
>  <span data-ttu-id="d0abf-110">引擎不识别架构，因此您只能从包含消息（必须存在完整路径）中现有的节点读取值或向其中写入值，否则引擎将引发异常。</span><span class="sxs-lookup"><span data-stu-id="d0abf-110">The engine is not schema-aware, so you can only read values from or write values to a node that exists in the containing message (the complete path must exist), or the engine will raise an exception.</span></span> <span data-ttu-id="d0abf-111">即使您提供默认值，也是如此。</span><span class="sxs-lookup"><span data-stu-id="d0abf-111">This is true even if you supply a default value.</span></span>  
  
## <a name="assigning-to-an-xpath-in-a-message-part"></a><span data-ttu-id="d0abf-112">对消息部分中的 XPath 赋值</span><span class="sxs-lookup"><span data-stu-id="d0abf-112">Assigning to an XPath in a message part</span></span>  
 <span data-ttu-id="d0abf-113">请考虑以下架构：</span><span class="sxs-lookup"><span data-stu-id="d0abf-113">Consider the following schema:</span></span>  
  
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
  
 <span data-ttu-id="d0abf-114">您可以使用如下函数设置该架构类型的文档实例的值：</span><span class="sxs-lookup"><span data-stu-id="d0abf-114">You can use the  function as follows to set values on a document instance of that schema type:</span></span>  
  
```  
//assumes that a message named _ResponseMessage is already constructed  
_ResponseMessage.part = _RequestMessage.part;  
xpath(_ResponseMessage.part, "/*/book[1]/@country") = "USA";  
xpath(_ResponseMessage.part, "/*/book[1]/title") = "Legends";  
xpath(_ResponseMessage.part, "/*/book[1]/author/FirstName") = "A";  
xpath(_ResponseMessage.part, "/*/book[1]/author/LastName") = "B";  
xpath(_ResponseMessage.part, "/*/book[1]/price") = 50;  
```  
  
## <a name="assigning-to-a-message-part-from-an-xpath"></a><span data-ttu-id="d0abf-115">通过 XPath 对消息部分赋值</span><span class="sxs-lookup"><span data-stu-id="d0abf-115">Assigning to a message part from an XPath</span></span>  
  
```  
//assumes that a message named objMessage is already constructed  
objMessage.BooleanPart = xpath("false()");  
objMessage.IntPart = xpath("100");  
objMessage.StringPart = xpath("'Hello'");  
objMessage.StringPart2 = xpath("'World'");  
```  
  
## <a name="using-xpath-to-assign-from-nodes-and-node-sets"></a><span data-ttu-id="d0abf-116">使用 XPath 从节点和节点集赋值</span><span class="sxs-lookup"><span data-stu-id="d0abf-116">Using XPath to assign from nodes and node sets</span></span>  
 <span data-ttu-id="d0abf-117">您也可以使用 XPath 将 XML 节点和节点集赋予一个 XML 元素、一个类或者一条基于架构或基于类的消息。</span><span class="sxs-lookup"><span data-stu-id="d0abf-117">You can also use XPath to assign XML nodes and node sets to an XML element, a class, or a schema-based or class-based message.</span></span>  
  
 <span data-ttu-id="d0abf-118">假设有一个称为 Book 的 XML 序列化类，请考虑下列示例：</span><span class="sxs-lookup"><span data-stu-id="d0abf-118">Suppose you have an XML-serializable class called Book, and consider the following examples:</span></span>  
  
```  
[Serializable]  
Class Book {...}  
```  
  
 <span data-ttu-id="d0abf-119">示例一 — 选择目录中的第四个书元素，并将其赋予一个 XML 元素变量：</span><span class="sxs-lookup"><span data-stu-id="d0abf-119">Example One — select the fourth book element from the catalog, and assign it to an XML element variable:</span></span>  
  
```  
myXmlElement = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="d0abf-120">示例二 — 选择目录中的第四个书元素，并使用 XML 反序列化将其转换为 Book 类实例：</span><span class="sxs-lookup"><span data-stu-id="d0abf-120">Example Two — select the fourth book element from the catalog, and convert it using XML deserialization into a Book class instance:</span></span>  
  
```  
myBook = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="d0abf-121">示例三 — 选择目录中的第四个书元素，并将其转换为 Book 类型的消息：</span><span class="sxs-lookup"><span data-stu-id="d0abf-121">Example Three — select the fourth book element from the catalog, and convert it a message of type Book:</span></span>  
  
```  
myBookMsg = xpath(myMsg, "/catalog/book[3]");  
```  
  
 <span data-ttu-id="d0abf-122">示例四 — 选择目录中的所有书元素，其中 MyMethod 将 XmlNodeSet 作为参数：</span><span class="sxs-lookup"><span data-stu-id="d0abf-122">Example Four — select all book elements in the catalog, where MyMethod takes an XmlNodeSet as a parameter:</span></span>  
  
```  
MyMethod(xpath(myMsg, "/catalog/book"));  
```  
  
 <span data-ttu-id="d0abf-123">示例五 — 将一个书元素添加到“BookOfTheMonth”容器：</span><span class="sxs-lookup"><span data-stu-id="d0abf-123">Example Five — add a book element to the "BookOfTheMonth" container:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BookOfTheMonth") = myBook;  
```  
  
 <span data-ttu-id="d0abf-124">示例六 — 将价格不超过二十的所有书添加到一组推荐书中：</span><span class="sxs-lookup"><span data-stu-id="d0abf-124">Example Six — add all books that are priced at twenty or less to a set of recommended books:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/BestPriceBooks") = xpath(MyMsg, "/catalog/book[@price <= 20]");  
```  
  
 <span data-ttu-id="d0abf-125">示例七 — 调用返回 XML 元素的用户代码：</span><span class="sxs-lookup"><span data-stu-id="d0abf-125">Example Seven — call user code that returns an XML element:</span></span>  
  
```  
xpath(MyMsg2, "/RecommendedBooks/AdvertisedByPartner") = GetPartnerAdvertisedBook();  
```  
  
 <span data-ttu-id="d0abf-126">应用示例五和示例七之前：</span><span class="sxs-lookup"><span data-stu-id="d0abf-126">Before applying examples five and seven:</span></span>  
  
```  
<RecommendedBooks>  
       <BookOfTheMonth/>  
       <BestPriceBooks/>  
       <AdvertisedByPartner/>  
</RecommendedBooks>  
```  
  
 <span data-ttu-id="d0abf-127">应用示例五和示例七之后：</span><span class="sxs-lookup"><span data-stu-id="d0abf-127">After applying examples five and seven:</span></span>  
  
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