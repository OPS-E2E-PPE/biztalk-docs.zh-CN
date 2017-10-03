---
title: "如何添加作用域 Shape1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094f744f7d4d6d1c405ea50d222beb8c0a67920e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
请按照这些步骤添加作用域形状。  
  
### <a name="to-add-a-scope-shape"></a>若要添加作用域形状  
  
1.  右键单击下箭头**ReceiveFromIn**端口，请指向**插入形状**，然后单击**作用域**。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     在作用域形状中，你将可能具有错误的操作。  
  
     例如，添加发送、 接收和发送端口 SQLExecute 业务流程中。 在此示例中，我们正在向 DB2 发送一条消息。 DB2 提供响应。 它运行业务流程的其余部分，并将返回到 OutFile 端口的信息。  
  
2.  在作用域形状中，设置**事务**到**无**。  
  
3.  在作用域形状中，右键单击并选择**新异常处理程序**。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     这将创建“捕获异常”块。 如果从后端，则会发生异常，它会捕获到捕获异常块内。  
  
4.  在“捕获异常”块中，必须添加逻辑。  
  
     必须设置的最重要的逻辑是你期望出现的错误消息的类型。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling2.md)