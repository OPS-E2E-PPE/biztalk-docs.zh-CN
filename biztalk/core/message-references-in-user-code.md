---
title: 消息在用户代码中的引用 |Microsoft Docs
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
ms.openlocfilehash: 77603901b5fbbad945d9e6f0e34e3c4131bf33c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394550"
---
# <a name="message-references-in-user-code"></a>在用户代码中的消息引用
当构造一条消息时，消息的表示形式是 MessageBox 数据库中并且另一种表示在计算机上的内存。 如果通过传递的消息引用与.NET 对象或外部程序集，使消息赋值和.NET 对象或外部程序集然后修改计算机上的内存中的表示形式，BizTalk 业务流程引擎并不知道修改。  
  
 此外，业务流程引擎不会导致失效消息部分是 MessageBox 数据库中的表示形式中的数据。 消息部分的数据具有以下模式的表示形式：  
  
- XmlDocument 表示形式  
  
- 对象表示形式  
  
- Stream 表示形式  
  
- UnderlyingPart 表示形式  
  
  如何在内存中表示消息部分数据取决于消息构造和类型是.NET 类或 XML 架构定义语言 (XSD) 架构。 但是，UnderlyingPart 表示形式始终是指向到 MessageBox 数据库中的流。 由于 BizTalk Server 中的消息是不可变的该消息提交到 MessageBox 数据库之后，业务流程引擎将使用引用消息部分数据到 MessageBox 数据库中的表示形式。  
  
> [!NOTE]
>  构造的消息可能在 MessageBox 数据库中已存在表示形式，如果将部件分配从已提交的消息。  
  
 例如，下面的代码发送 UnderlyingPart 数据从 MessageBox 数据库中的表示形式：  
  
```  
// In this example, assume m1 is committed to the MessageBox  
Construct m2 {   
               m2 = m1; // m2’s part data representation is the UnderlyingPart data of m1  
               m2(myContextProperty) = “123”; // m2’s part data representation is still the UnderlyingPart data of m1  
               A.test(m2.part); // orchestration engine does not invalidate the UnderlyingPart MessageBox representation  
             }  
Send(p.o, m2);  
```  
  
 而不是使用前面的用户代码，您可以使用类似于以下消息 XLANG 变量返回一个 XmlDocument 文档的代码：  
  
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