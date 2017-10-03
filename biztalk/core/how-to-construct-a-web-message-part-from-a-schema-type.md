---
title: "如何构造中的架构类型的 Web 消息部件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3434dc46be2fa43885346ac8d146e9326ab1ea73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a>如何从架构类型构造 Web 消息部分
从架构类型中使用创建的 Web 消息部分**转换**形状。 也可以通过使用 .NET 帮助程序类设置各个部分来从架构类型创建 Web 消息部分。 通过使用一个.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a>从架构类型构建 Web 消息部分  
  
1.  添加一个新映射。 有关创建映射的信息，请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。  
  
2.  在 BizTalk 映射程序中，单击**打开目标架构**中**目标架构**窗格中的代码图并在**BizTalk 类型选取器**对话框框中，展开**架构**节点，选择所添加的 Web 引用的架构，然后单击**确定**。  
  
    > [!NOTE]
    >  Web 引用架构的格式是**\<项目默认命名空间 >。\<Web 引用名称 >。引用**。  
  
3.  在**目标架构的根节点**对话框中，选择目标架构的根节点，然后单击**确定**。 有关如何确定 Web 消息部件类型的根节点的详细信息，请参阅[如何确定 Web 消息部件类型](../core/how-to-determine-a-web-message-part-type.md)。  
  
4.  单击**打开源架构**中**源架构**窗格中的代码图并在**BizTalk 类型选取器**对话框框中，展开**架构**节点、 选择要将数据从，映射的源架构，然后单击**确定**。  
  
5.  在 BizTalk 映射器中，创建源架构和目标架构之间的链接。  
  
6.  打开现有的业务流程 （或创建新的业务流程），打开**工具箱**，然后单击**BizTalk 业务流程**选项卡。  
  
7.  拖动**构造消息**形状上的与业务流程。  
  
8.  编辑**构造消息**属性以包含消息实例，则为创建 Web 消息类型。  
  
9. 拖动**转换**形状拖到**构造消息**的形状，然后双击以打开**转换配置**对话框。  
  
10. 单击**现有映射**按钮，然后选择你在第一步中创建中的映射**完全限定的映射名称**列表框。  
  
11. 在**转换**窗格中，选择**源**。 在**源转换**窗格中，选择有效的消息实例从列表框。  
  
12. 在**转换**窗格中，选择**目标**。 在**目标转换**窗格中，选择 Web 消息从列表框中，实例，然后单击**确定**。  
  
 有关使用**转换配置**对话框中，请参阅[如何配置转换形状](../core/how-to-configure-the-transform-shape.md)。  
  
 您也可以使用此过程将 Web 方法响应消息实例映射到其他 Web 消息实例。  
  
## <a name="see-also"></a>另请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)