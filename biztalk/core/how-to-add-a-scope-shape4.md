---
title: "如何添加作用域形状 4 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a81bb85412784616d185b64ee39f1e777d19fea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
请按照这些步骤添加**作用域**形状。  
  
### <a name="to-add-a-scope-shape"></a>添加作用域形状  
  
1.  右键单击下箭头**ReceiveFromIn**端口，请指向**插入形状**，然后单击**作用域**。  
  
     在作用域形状中，你将可能具有错误的操作。  
  
     例如，在 SQLExecute 业务流程中添加发送、接收和发送端口。 在此示例中，将向服务器发送消息。 服务器发出响应， 它运行业务流程的其余部分，并将返回到 OutFile 端口的信息。  
  
2.  在作用域形状中，设置**事务**到**无**。  
  
3.  在作用域形状右击并选择**新异常处理程序**。  
  
     这将创建**捕获异常**块。 如果从后端，则会发生异常，则将它捕获在**捕获异常**块。  
  
4.  在**捕获异常**块中，你必须添加的逻辑。  
    必须设置的最重要逻辑是你希望收到的错误消息的类型。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling4.md)