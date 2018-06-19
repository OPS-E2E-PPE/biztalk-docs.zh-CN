---
title: 如何添加作用域 Shape5 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 1e16eda1-c4bd-4428-a477-78c453aeb1aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7bbe3f5fbb267fee618ac7f0b91c35ad33e1758
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246733"
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
请按照这些步骤添加**作用域**形状。  
  
### <a name="to-add-a-scope-shape"></a>若要添加作用域形状  
  
1.  右键单击下箭头**ReceiveFromIn**端口，请指向**插入形状**，然后单击**作用域**。  
  
     在**作用域**形状，你将操作可能具有错误的设置。  
  
     例如，在 SQLExecute 业务流程中添加发送、接收和发送端口。 在此示例中，将向服务器发送消息。 服务器发出响应， 它运行业务流程的其余部分，并将返回到 OutFile 端口的信息。  
  
2.  在**作用域**形状，设置**事务类型**到**无**。  
  
3.  右键单击内部**作用域**调整和选择**新异常处理程序**。  
  
     这将创建`Catch Exception`块。 如果从后端，则会发生异常，则将它捕获在`Catch Exception`块。  
  
4.  在`Catch Exception`块中，必须添加逻辑。  
  
     必须设置的最重要逻辑是你希望收到的错误消息的类型。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling5.md)