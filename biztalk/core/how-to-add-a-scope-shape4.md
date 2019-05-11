---
title: 如何添加作用域形状 4 |Microsoft Docs
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
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce1e97c941de98c700b549dfe6307794ca38fb31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343405"
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
请按照这些步骤添加**作用域**形状。  
  
### <a name="to-add-a-scope-shape"></a>若要添加作用域形状  
  
1.  右键单击下的箭头**ReceiveFromIn**端口，指向**插入形状**，然后单击**范围**。  
  
     在作用域形状中，您将可能有错误的操作。  
  
     例如，在 SQLExecute 业务流程中添加发送、 接收和发送端口。 在此示例中，向服务器发送一条消息。 服务器发出响应。 它运行业务流程的其余部分，并返回到 OutFile 端口返回信息。  
  
2.  在作用域形状中，设置**事务**到**None**。  
  
3.  作用域形状内右键单击并选择**新建异常处理程序**。  
  
     这将创建**捕获异常**块。 如果从后端出现异常，则在捕获到**捕获异常**块。  
  
4.  在中**捕获异常**块中，必须添加逻辑。  
    必须设置的最重要逻辑是您希望收到的错误消息的类型。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling4.md)