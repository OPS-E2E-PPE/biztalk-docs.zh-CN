---
title: 如何添加作用域形状 3 |Microsoft Docs
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
ms.openlocfilehash: 85b022dc0335ccd3b247c5c2fcad0553fad2ede4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387343"
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
使用以下过程添加作用域形状。  
  
### <a name="to-add-a-scope-shape"></a>若要添加作用域形状  
  
1.  右键单击下的箭头**接收**端口，指向**插入形状**，然后选择**范围**。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     在中**作用域**形状，你将可能有错误的操作设置。  
  
     例如，在 SQLExecute 业务流程中添加发送、 接收和发送端口。 在此示例中，向服务器发送一条消息。 服务器发出响应。 它运行业务流程的其余部分，并返回到 outFile 端口返回信息。  
  
2.  在中**作用域**形状中，设置**事务**到**None**。  
  
3.  内右击**作用域**形状，然后选择**新建异常处理程序**。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     这将创建**捕获异常**块。 如果从后端系统会发生异常，则在捕获到**捕获异常**块。  
  
4.  在中**捕获异常**块中，必须添加逻辑。  
  
     必须设置的最重要逻辑是您希望收到的错误消息的类型。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling1.md)