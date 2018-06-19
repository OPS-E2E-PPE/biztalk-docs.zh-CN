---
title: 消息在用户代码中的引用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a1584be-35fd-4dc2-a5a9-559300e67e0e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264f50da516f44d8fc87186614a79bb81aaf77ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263245"
---
# <a name="message-references-in-user-code"></a><span data-ttu-id="76676-102">在用户代码中的消息引用</span><span class="sxs-lookup"><span data-stu-id="76676-102">Message References in User Code</span></span>
<span data-ttu-id="76676-103">构造一条消息时，消息的表示形式是 MessageBox 数据库中并且另一种表示在计算机上的内存。</span><span class="sxs-lookup"><span data-stu-id="76676-103">When a message is constructed, a representation of the message is in the MessageBox database and another representation is in memory on the computer.</span></span> <span data-ttu-id="76676-104">如果你通过传递消息引用对.NET 对象或一个外部程序集，使消息分配和.NET 对象或外部程序集然后修改计算机上的内存中的表示形式，BizTalk 业务流程引擎并不知道修改。</span><span class="sxs-lookup"><span data-stu-id="76676-104">If you make the message assignment by passing a message reference to a .NET object or to an external assembly, and then the .NET object or the external assembly modifies the representation in memory on the computer, the BizTalk Orchestration Engine is not aware of the modification.</span></span>  
  
 <span data-ttu-id="76676-105">此外，业务流程引擎不会不会使失效处于 MessageBox 数据库中的表示形式的消息部分数据。</span><span class="sxs-lookup"><span data-stu-id="76676-105">Moreover, the orchestration engine does not invalidate the message part data that is in the representation in the MessageBox database.</span></span> <span data-ttu-id="76676-106">消息部分数据具有表示形式的以下模式：</span><span class="sxs-lookup"><span data-stu-id="76676-106">Message part data has the following modes of representation:</span></span>  
  
-   <span data-ttu-id="76676-107">XmlDocument 表示形式</span><span class="sxs-lookup"><span data-stu-id="76676-107">XmlDocument representation</span></span>  
  
-   <span data-ttu-id="76676-108">对象表示形式</span><span class="sxs-lookup"><span data-stu-id="76676-108">Object representation</span></span>  
  
-   <span data-ttu-id="76676-109">流表示形式</span><span class="sxs-lookup"><span data-stu-id="76676-109">Stream representation</span></span>  
  
-   <span data-ttu-id="76676-110">UnderlyingPart 表示形式</span><span class="sxs-lookup"><span data-stu-id="76676-110">UnderlyingPart representation</span></span>  
  
 <span data-ttu-id="76676-111">如何在内存中表示消息部分数据取决于消息构造和类型是否是一个.NET 类或 XML 架构定义语言 (XSD) 架构。</span><span class="sxs-lookup"><span data-stu-id="76676-111">How the message part data is represented in memory depends on the message construction and whether the type is a .NET class or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="76676-112">但是，UnderlyingPart 表示形式始终是指向到 MessageBox 数据库的流。</span><span class="sxs-lookup"><span data-stu-id="76676-112">However, the UnderlyingPart representation is always a stream pointing into the MessageBox database.</span></span> <span data-ttu-id="76676-113">由于消息提交到 MessageBox 数据库后，BizTalk Server 中的消息是不可变，业务流程引擎将使用引用消息部分数据到 MessageBox 数据库中表示。</span><span class="sxs-lookup"><span data-stu-id="76676-113">Because messages in BizTalk Server are immutable after the message is committed to the MessageBox database, the orchestration engine uses the representation in the MessageBox database to reference message part data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76676-114">构造的消息可能 MessageBox 数据库中已存在的表示形式，如果从一条消息，已提交分配部件。</span><span class="sxs-lookup"><span data-stu-id="76676-114">A constructed message may already have a representation in the MessageBox database if you assign parts from a message that is already committed.</span></span>  
  
 <span data-ttu-id="76676-115">例如，下面的代码会从 MessageBox 数据库中的表示形式发送 UnderlyingPart 数据：</span><span class="sxs-lookup"><span data-stu-id="76676-115">For example, the following code sends the UnderlyingPart data from the representation in the MessageBox database:</span></span>  
  
```  
// In this example, assume m1 is committed to the MessageBox  
Construct m2 {   
               m2 = m1; // m2’s part data representation is the UnderlyingPart data of m1  
               m2(myContextProperty) = “123”; // m2’s part data representation is still the UnderlyingPart data of m1  
               A.test(m2.part); // orchestration engine does not invalidate the UnderlyingPart MessageBox representation  
             }  
Send(p.o, m2);  
```  
  
 <span data-ttu-id="76676-116">而不是使用前面的用户代码，你可以使用类似于以下内容以返回到消息 XLANG 变量的 XmlDocument 文档的代码：</span><span class="sxs-lookup"><span data-stu-id="76676-116">Instead of using the preceding user code, you can use code that is similar to the following to return an XmlDocument document to a Message XLANG variable:</span></span>  
  
```  
Void A.test(ref XmlDocument xd) {…}  
XmlDocument B.test(XmlDocument xd) {…}  
construct m2 {  
               m2 = m1;  
               m2(myContextProperty) = “123”; // m2’s part data representation is the UnderlyingPart data of m1  
               A.test(ref m2.part); // orchestration engine has enough information to know it has to invalidate the UnderlyingPart MessageBox representation  
               // or  
               m2.part = B.test(m2.part); // orchestration engine has enough information to know it has to invalidate the UnderlyingPart MessageBox representation  
             }  
```