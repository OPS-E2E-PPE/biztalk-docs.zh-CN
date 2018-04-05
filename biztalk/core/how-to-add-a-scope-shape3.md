---
title: 如何添加作用域形状 3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
ms.assetid: 8068ce97-4409-4c88-89e8-6505b56cefc5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8231dfed1ea84ba5c11e0352f789b92cc38d0f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
使用以下过程添加作用域形状。  
  
### <a name="to-add-a-scope-shape"></a>若要添加作用域形状  
  
1.  右键单击下箭头**接收**端口，请指向**插入形状**，然后选择**作用域**。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     在**作用域**形状，你将操作可能具有错误的设置。  
  
     例如，添加发送、 接收和发送端口 SQLExecute 业务流程中。 在此示例中，将向服务器发送消息。 服务器发出响应， 它运行业务流程的其余部分，并将返回到 outFile 端口的信息。  
  
2.  在**作用域**形状，设置**事务**到**无**。  
  
3.  右键单击内部**作用域**形状，然后选择**新异常处理程序**。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     这将创建**捕获异常**块。 如果从后端系统，则会发生异常，则将它捕获在**捕获异常**块。  
  
4.  在**捕获异常**块中，你必须添加的逻辑。  
  
     必须设置的最重要逻辑是你希望收到的错误消息的类型。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling1.md)