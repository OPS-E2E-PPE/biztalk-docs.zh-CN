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
# <a name="message-references-in-user-code"></a>在用户代码中的消息引用
构造一条消息时，消息的表示形式是 MessageBox 数据库中并且另一种表示在计算机上的内存。 如果你通过传递消息引用对.NET 对象或一个外部程序集，使消息分配和.NET 对象或外部程序集然后修改计算机上的内存中的表示形式，BizTalk 业务流程引擎并不知道修改。  
  
 此外，业务流程引擎不会不会使失效处于 MessageBox 数据库中的表示形式的消息部分数据。 消息部分数据具有表示形式的以下模式：  
  
-   XmlDocument 表示形式  
  
-   对象表示形式  
  
-   流表示形式  
  
-   UnderlyingPart 表示形式  
  
 如何在内存中表示消息部分数据取决于消息构造和类型是否是一个.NET 类或 XML 架构定义语言 (XSD) 架构。 但是，UnderlyingPart 表示形式始终是指向到 MessageBox 数据库的流。 由于消息提交到 MessageBox 数据库后，BizTalk Server 中的消息是不可变，业务流程引擎将使用引用消息部分数据到 MessageBox 数据库中表示。  
  
> [!NOTE]
>  构造的消息可能 MessageBox 数据库中已存在的表示形式，如果从一条消息，已提交分配部件。  
  
 例如，下面的代码会从 MessageBox 数据库中的表示形式发送 UnderlyingPart 数据：  
  
```  
// In this example, assume m1 is committed to the MessageBox  
Construct m2 {   
               m2 = m1; // m2’s part data representation is the UnderlyingPart data of m1  
               m2(myContextProperty) = “123”; // m2’s part data representation is still the UnderlyingPart data of m1  
               A.test(m2.part); // orchestration engine does not invalidate the UnderlyingPart MessageBox representation  
             }  
Send(p.o, m2);  
```  
  
 而不是使用前面的用户代码，你可以使用类似于以下内容以返回到消息 XLANG 变量的 XmlDocument 文档的代码：  
  
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