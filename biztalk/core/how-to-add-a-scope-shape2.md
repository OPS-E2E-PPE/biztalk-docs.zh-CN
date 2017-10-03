---
title: "如何添加作用域形状 2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- adding, Scope shapes
ms.assetid: 9449210f-1f29-4b86-a14b-148caa06ac6b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef67618c553702ae32cd0a88f6d2f77eb1ff053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
使用以下过程添加**作用域**形状。  
  
### <a name="to-add-a-scope-shape"></a>添加作用域形状  
  
1.  右键单击下箭头**ReceiveFromIn**端口，请指向**插入形状**，然后选择**作用域**。  
  
     在**作用域**形状，你将操作可能具有错误的设置。  
  
     例如，在 SQLExecute 业务流程中添加发送、接收和发送端口。 在此示例中，将向服务器发送消息。 服务器发出响应， 它运行业务流程的其余部分，并将返回到 OutFile 端口的信息。  
  
2.  在**作用域**形状，设置**事务类型**到**无**。  
  
3.  右键单击内部**作用域**调整和选择**新异常处理程序**。  
  
     这将创建**捕获异常**块。 如果从后端系统，则会发生异常，则将它捕获在**捕获异常**块。  
  
4.  在**捕获异常**块中，你必须添加的逻辑。  
  
     必须设置的最重要逻辑是你希望收到的错误消息的类型。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling3.md)