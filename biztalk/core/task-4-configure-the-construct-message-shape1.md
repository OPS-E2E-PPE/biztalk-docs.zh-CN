---
title: "任务 4： 配置构造消息 Shape1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e66a9d-c549-42d0-849b-9e1744056429
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f781e03f83223f7d82628ee9c01728a0754b149f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="task-4-configure-the-construct-message-shape"></a>任务 4： 配置构造消息形状
构造消息将消息赋值与 Begin、Edit 和 End Doc 代码的指令保存在一起。  
  
 使用以下过程配置构造消息形状。  
  
### <a name="to-configure-the-construct-message-shape"></a>若要配置构造消息形状  
  
1.  在 ReceiveBeginDoc 和 SendBeginDoc 之间拖动构造消息形状。  
  
    -   **构造的消息：** BeginDocSessionMsg  
  
    -   **名称：** ConstructBeginDocMessageWithSession  
  
    1.  将消息赋值形状拖入要在其中创建新消息的业务流程中。  
  
    2.  双击内部 MessageAssignment_1 形状。  
  
         随即将显示 BizTalk 表达式编辑器。  
  
    3.  键入代码，例如：  
  
        ```  
        BeginDocSessionMsg = BeginDocMsg;  
        BeginDocSessionMsg(JDE.ReserveSession) = true;  
        BeginDocSessionMsg(JDE.SessionID) = 0;  
        ```  
  
         此操作将告知适配器您要启动一个会话。 SessionID 初始化为 0，但 J.D.回响应时将分配的 ID Edwards EnterpriseOne 服务器。  
  
     ![消息表达式编辑器](../core/media/message-expression-editor.gif "message_expression_editor")  
  
2.  将构造消息拖至 SendEditLine 之前。  
  
    -   **构造的消息：** EditLineSessionMsg  
  
    -   **名称：** ConstructEditLineMessageWithSession  
  
     ![发送编辑行](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")  
  
    1.  将消息赋值形状拖入要在其中创建新消息的业务流程中。  
  
    2.  双击内部 MessageAssignment_1 形状。  
  
         随即将显示 BizTalk 表达式编辑器。  
  
    3.  键入代码，例如：  
  
        ```  
        EditLineSessionMsg = EditLineMsg;  
        EditLineSessionMsg(JDE.ReserveSession) = true;  
        EditLineSessionMsg(JDE.SessionID) =  
        BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
     ![编辑行编辑器](../core/media/editline-editor.gif "editline_editor")  
  
3.  将构造消息形状拖至 SendEndDoc 之前。  
  
    -   **构造的消息：** EndDocSessionMsg  
  
    -   **名称：** ConstructEndDocMessageWithSession  
  
    1.  将消息赋值形状拖入要在其中创建新消息的业务流程中。  
  
    2.  双击内部 MessageAssignment_1 形状。  
  
         随即将显示 BizTalk 表达式编辑器。  
  
    3.  键入代码，例如：  
  
        ```  
        EndDocSessionMsg = EndDocMsg;  
        EndDocSessionMsg(JDE.ReserveSession) = false;  
        EndDocSessionMsg(JDE.SessionID) =  
           BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
## <a name="see-also"></a>另请参阅  
 [任务 1： 创建端口](../core/task-1-create-the-ports1.md)   
 [任务 2： 创建消息](../core/task-2-create-the-messages2.md)   
 [任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes2.md)   
 [任务 5： 配置转换形状](../core/task-5-configure-the-transform-shape2.md)