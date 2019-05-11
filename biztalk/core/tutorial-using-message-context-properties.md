---
title: 教程：使用 TIBCO EMS 消息上下文属性 |Microsoft Docs
description: 使用 TIBCO Enterprise Message Service 消息描述符字段在业务流程中的对 BizTalk Server 使用的分步指南
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef7ce23a38c528b3dc7e3d0a3d98c39412e9c175
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393844"
---
# <a name="tutorial-use-tibco-ems-message-descriptors"></a>教程：使用 TIBCO EMS 消息描述符

## <a name="overview"></a>概述
本教程演示如何使用 BizTalk Server 上下文属性在您的业务流程中设置 TIBCO Enterprise Message Service (EMS) 消息描述符字段。 本教程假定你具有一个业务流程从接收端口接收消息并将消息发送到 TIBCO Enterprise Message Service 的绑定到的 Microsoft BizTalk 适配器的发送端口。  
  
 以下过程演示如何通过更改 TibcoEMS.Priority 上下文属性的值来更改 TIBCO EMS 消息的优先级。 在 BizTalk Server 中，消息是不可变的。 因此，若要更改属性值，必须创建和修改新消息。 创建和修改新消息的方法是插入消息赋值形状在接收和发送形状之间。 但是，您必须首先引用架构 DLL 才能访问 TIBCO EMS 属性。  
  
## <a name="reference-the-schema-dll"></a>引用架构 DLL  
  
1.  在 Visual Studio 中，打开 BizTalk Server 项目，并打开**解决方案资源管理器**。  
  
2.  右键单击**引用**，然后选择**添加引用**。  
  
     此时将显示“添加引用”对话框。  
  
3.  单击**浏览**选项卡。  
  
     **选择组件**对话框随即出现。  
  
4.  找到 **\<TIBCO EMS_Adapter_installation_directory\>\bin**，然后选择**Microsoft.Adapters.TibcoEMSProperties.dll**。  
  
5.  单击 **“打开”**。  
  
     中将显示该 DLL**选定的组件**中**添加引用**对话框。  
  
6.  单击**确定**然后双击您的业务流程访问业务流程设计器。  
  
7.  上**视图**菜单，依次指向**其他 Windows**，然后单击**业务流程视图**。  
  
8.  在业务流程视图中，右键单击**消息**，然后选择**新消息**。  
  
9. 编辑新的消息属性和分配**消息类型**。  
  
     会将 Message_1 分配给 Message_2。 因此，您必须为这两个消息分配相同的消息类型。  
  
10. 在“视图”菜单上，单击“工具箱”。  
  
11. 拖动**消息赋值**形状拖到您想要创建新的消息的业务流程。  
  
12. 编辑外部 ConstructMessage_1 形状和中选择新消息，Message_2**构造消息**属性。  
  
13. 双击内部 MessageAssignment_1 形状。  
  
     将显示 BizTalk 表达式编辑器。  
  
14. 在 BizTalk 表达式编辑器中，键入你的代码。  
  
15. 首先复制现有的消息，然后将值分配给消息上下文属性。  
  
     语法是`Message(property) = value;`。 例如：  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     可以使用自定义消息中的受支持属性的列表，请参阅 TIBCO EMS。  
  
16. 单击**确定**关闭 BizTalk 表达式编辑器并保存您的代码。  
  
17. 单击发送形状并将分配**消息**要**Message_2**。  
  
18. 验证消息流的其余部分中的形状对适当的消息。  
  
19. 右键单击你的项目在解决方案资源管理器，然后选择**生成**。  
  
20. 右键单击你的项目并选择**部署**。  
  
21. 选择**绑定**，**登记**，并**启动**BizTalk 资源管理器来测试业务流程中。  
  
## <a name="see-also"></a>请参阅  
[TIBCO EMS 消息上下文属性](../core/message-context-properties-in-biztalk-server.md)