---
title: 任务 4：配置构造消息形状 2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43a7b912-0293-41be-b992-309eca550801
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47251eb4d9011c2c0221af75e7190abe2487a440
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399233"
---
# <a name="task-4-configure-the-construct-message-shape"></a>任务 4：配置构造消息形状
构造消息包含消息赋值与 Begin、 Edit 和 End Doc 代码的说明。  
  
 使用以下过程配置构造消息形状。  
  
### <a name="to-configure-the-construct-message-shape"></a>若要配置构造消息形状  
  
1. 将构造消息形状在 receivebegindoc 和 sendbegindoc 之间。  
  
   -   **构造的消息：** BeginDocSessionMsg  
  
   -   **名称：** ConstructBeginDocMessageWithSession  
  
   1.  将消息赋值形状拖至业务流程你想要创建新的消息。  
  
   2.  双击内部 MessageAssignment_1 形状。  
  
        将显示 BizTalk 表达式编辑器。  
  
   3.  键入在代码中，例如：  
  
   ```  
   BeginDocSessionMsg = BeginDocMsg;  
   BeginDocSessionMsg(JDE.ReserveSession) = true;  
   BeginDocSessionMsg(JDE.SessionID) = 0;  
   ```  
  
    这将告知适配器您想要启动会话。 SessionID 初始化为 0，但当响应返回将由 J.D.分配 ID Edwards OneWorld 服务器。  
  
    ![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")  
  
2. 将拖至 SendEditLine 之前构造消息。  
  
   - **构造的消息：** EditLineSessionMsg  
  
   - **名称：** ConstructEditLineMessageWithSession  
  
     ![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")  
  
   1.  将消息赋值形状拖至业务流程你想要创建新的消息。  
  
   2.  双击内部 MessageAssignment_1 形状。  
  
        将显示 BizTalk 表达式编辑器。  
  
   3.  键入在代码中，例如：  
  
   ```  
   EditLineSessionMsg = EditLineMsg;  
   EditLineSessionMsg(JDE.ReserveSession) = true;  
   EditLineSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
    ![](../core/media/jde-editline-editor.gif "JDE_editline_editor")  
  
3. 将拖至 SendEndDoc 之前构造消息。  
  
   -   **构造的消息：** EndDocSessionMsg  
  
   -   **名称：** ConstructEndDocMessageWithSession  
  
   1.  将消息赋值形状拖至业务流程你想要创建新的消息。  
  
   2.  双击内部 MessageAssignment_1 形状。  
  
        将显示 BizTalk 表达式编辑器。  
  
   3.  键入在代码中，例如：  
  
   ```  
   EndDocSessionMsg = EndDocMsg;  
   EndDocSessionMsg(JDE.ReserveSession) = false;  
   EndDocSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
## <a name="see-also"></a>请参阅  
 [任务 1:创建端口](../core/task-1-create-the-ports2.md)   
 [任务 2:创建消息](../core/task-2-create-the-messages1.md)   
 [任务 3:配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [任务 5:配置转换形状](../core/task-5-configure-the-transform-shape1.md)