---
title: "教程： 使用 TIBCO EMS 消息上下文属性 |Microsoft 文档"
description: "分步指南，以用于 BizTalk Server 业务流程中的 TIBCO 企业消息服务消息描述符字段"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fafde77ad1e6edcae71d2c33a722ac63ab8e75b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="tutorial-use-tibco-ems-message-descriptors"></a>教程： 使用 TIBCO EMS 消息描述符

## <a name="overview"></a>概述
本教程演示了如何使用 BizTalk Server 上下文属性在业务流程中设置 TIBCO Enterprise Message Service (EMS) 消息描述符字段。 该教程假定您已具备一个可执行如下操作的业务流程：从接收端口接收消息并将该消息发送到与用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器绑定的发送端口。  
  
 下面的过程演示了如何通过更改 TibcoEMS.Priority 上下文属性的值来更改 TIBCO EMS 消息的优先级。 在 BizTalk Server 中，消息是不可改变的。 因此，若要更改属性值，必须创建和修改新的消息。 通过在接收形状和发送形状之间插入消息赋值形状可以创建和修改新消息。 但是，必须首先引用架构 DLL 才能访问 TIBCO EMS 属性。  
  
## <a name="reference-the-schema-dll"></a>引用 DLL 的架构  
  
1.  在 Visual Studio 中，打开你的 BizTalk 服务器项目，并打开**解决方案资源管理器**。  
  
2.  右键单击**引用**，然后选择**添加引用**。  
  
     此时将显示“添加引用”对话框。  
  
3.  单击**浏览**选项卡。  
  
     **选择组件**对话框随即出现。  
  
4.  找到 **\<TIBCO EMS_Adapter_installation_directory\>\bin**，然后选择**Microsoft.Adapters.TibcoEMSProperties.dll**。  
  
5.  单击 **“打开”**。  
  
     DLL 将出现在**选定的组件**中**添加引用**对话框。  
  
6.  单击**确定**然后双击您的业务流程，以访问业务流程设计器。  
  
7.  上**视图**菜单上，指向**其他窗口**，然后单击**业务流程视图**。  
  
8.  在业务流程视图中，右键单击**消息**和选择**新消息**。  
  
9. 编辑新的消息属性和分配**消息类型**。  
  
     您会将 Message_1 分配给 Message_2。 因此，您必须为这两个消息分配相同的消息类型。  
  
10. 在“视图”菜单上，单击“工具箱”。  
  
11. 拖动**消息分配**形状拖到您想要创建一封新邮件的业务流程。  
  
12. 编辑外部 ConstructMessage_1 形状，并在选择新消息，Message_2，**构造消息**属性。  
  
13. 双击内部 MessageAssignment_1 形状。  
  
     随即将显示 BizTalk 表达式编辑器。  
  
14. 在 BizTalk 表达式编辑器中，键入代码。  
  
15. 首先复制现有的消息，然后对消息上下文属性赋值。  
  
     语法为 `Message(property) = value;`。 例如：  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     有关可在自定义消息中使用的受支持属性的列表，请参阅 TIBCO EMS。  
  
16. 单击**确定**关闭 BizTalk 表达式编辑器并保存你的代码。  
  
17. 单击发送形状并将分配**消息**要**Message_2**。  
  
18. 请确保其余消息流中的形状对适当的消息执行了操作。  
  
19. 右键单击你的项目在解决方案资源管理器，然后选择**生成**。  
  
20. 右键单击你的项目并选择**部署**。  
  
21. 选择**绑定**， **Enlist**，和**启动**BizTalk 资源管理器来测试您的业务流程。  
  
## <a name="see-also"></a>另请参阅  
[TIBCO EMS 消息上下文属性](../core/message-context-properties-in-biztalk-server.md)