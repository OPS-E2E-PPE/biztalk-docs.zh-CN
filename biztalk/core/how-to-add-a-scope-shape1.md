---
title: 如何添加作用域形状 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faabba82196f7e595427f36c0d07d66769bafd18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387318"
---
# <a name="how-to-add-a-scope-shape"></a>如何添加作用域形状
请按照这些步骤添加作用域形状。  
  
### <a name="to-add-a-scope-shape"></a>若要添加作用域形状  
  
1.  右键单击下的箭头**ReceiveFromIn**端口，指向**插入形状**，然后单击**范围**。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     在作用域形状中，您将可能有错误的操作。  
  
     例如，在 SQLExecute 业务流程中添加发送、 接收和发送端口。 在此示例中，我们正在向 DB2 发送一条消息。 DB2 提供响应。 它运行业务流程的其余部分，并返回到 OutFile 端口返回信息。  
  
2.  在作用域形状中，设置**事务**到**None**。  
  
3.  作用域形状内右键单击并选择**新建异常处理程序**。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     这会创建捕获异常块。 如果从后端出现异常，它会捕获到捕获异常块内。  
  
4.  在捕获异常块中，必须添加逻辑。  
  
     必须设置的最重要逻辑是您需要错误消息的类型。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 的异常处理](../core/using-biztalk-server-exception-handling2.md)