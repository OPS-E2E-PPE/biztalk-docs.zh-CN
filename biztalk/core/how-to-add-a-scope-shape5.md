---
title: 如何添加作用域 Shape5 |Microsoft Docs
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
ms.openlocfilehash: 35301e9e3cd66ab26d06208501c535b73305f5a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343395"
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
请按照这些步骤添加**作用域**形状。  
  
### <a name="to-add-a-scope-shape"></a>若要添加作用域形状  
  
1.  右键单击下的箭头**ReceiveFromIn**端口，指向**插入形状**，然后单击**范围**。  
  
     在中**作用域**形状，你将可能有错误的操作设置。  
  
     例如，在 SQLExecute 业务流程中添加发送、 接收和发送端口。 在此示例中，向服务器发送一条消息。 服务器发出响应。 它运行业务流程的其余部分，并返回到 OutFile 端口返回信息。  
  
2.  在中**作用域**形状中，设置**事务类型**到**None**。  
  
3.  内右击**作用域**形状，然后选择**新建异常处理程序**。  
  
     这将创建`Catch Exception`块。 如果从后端出现异常，则在捕获到`Catch Exception`块。  
  
4.  在`Catch Exception`块中，必须添加逻辑。  
  
     必须设置的最重要逻辑是您希望收到的错误消息的类型。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling5.md)