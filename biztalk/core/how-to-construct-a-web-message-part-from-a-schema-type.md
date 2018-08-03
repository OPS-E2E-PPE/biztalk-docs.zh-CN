---
title: 如何构造 Web 消息部分从架构类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be8fd01e67309387749e7e512eca84bdb0f83db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984790"
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a>如何从架构类型构造 Web 消息部分
从架构类型中使用创建 Web 消息部分**转换**形状。 也可以通过使用 .NET 帮助程序类设置各个部分来从架构类型创建 Web 消息部分。 使用.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a>从架构类型构建 Web 消息部分  
  
1. 添加一个新映射。 有关创建映射的信息，请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。  
  
2. 在 BizTalk 映射器中，单击**打开目标架构**中**目标架构**窗格的映射，并在**BizTalk 类型选取器**对话框中，展开**架构**节点中，选择添加的 Web 引用的架构，然后单击**确定**。  
  
   > [!NOTE]
   >  Web 引用架构的格式**\<项目默认命名空间\>。\<Web 引用名\>。引用**。  
  
3. 在中**目标架构的根节点**对话框中，选择目标架构的根节点，然后单击**确定**。 有关如何确定 Web 消息部分类型的根节点的详细信息，请参阅[如何确定 Web 消息部分类型](../core/how-to-determine-a-web-message-part-type.md)。  
  
4. 单击**打开源架构**中**源架构**窗格的映射，并在**BizTalk 类型选取器**对话框中，展开**架构**节点中，选择要将数据从，映射的源架构，然后单击**确定**。  
  
5. 在 BizTalk 映射器中，创建源架构和目标架构之间的链接。  
  
6. 打开现有的业务流程 （或创建新的业务流程），打开**工具箱**，然后单击**BizTalk 业务流程**选项卡。  
  
7. 拖动**构造消息**向业务流程的形状。  
  
8. 编辑**构造的消息**yo 为创建 Web 消息类型的属性以包含消息实例。  
  
9. 拖动**转换**形状拖至**构造消息**形状，然后双击以打开**转换配置**对话框。  
  
10. 单击**现有的映射**按钮，然后选择在步骤 1 中创建的映射**完全限定的映射名称**列表框。  
  
11. 在中**转换**窗格中，选择**源**。 在中**源转换**窗格中，选择一个有效的消息实例从列表框。  
  
12. 在中**转换**窗格中，选择**目标**。 在中**目标转换**窗格中，选择 Web 消息实例从列表框中，然后单击**确定**。  
  
    有关使用详细信息**转换配置**对话框中，请参阅[如何配置转换形状](../core/how-to-configure-the-transform-shape.md)。  
  
    您也可以使用此过程将 Web 方法响应消息实例映射到其他 Web 消息实例。  
  
## <a name="see-also"></a>请参阅  
 [构造 Web 消息](../core/constructing-web-messages.md)