---
title: "创建要处理孤立或重复消息的发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc969e316df9b493dd294769d68a15012a46904
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a>创建要处理孤立或重复消息的发送端口
本主题描述如何设置可用于删除孤立或重复消息的发送端口。  
  
 孤立或重复的消息可能会造成问题，如果[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]公共进程业务流程完成处理消息的第一个副本后接收的消息的其他副本。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将标记为重复这些消息并挂起它们。 您可以在 BizTalk 管理控制台中查看这些消息。 有关 BizTalk 管理控制台的详细信息，请参阅"使用的 BizTalk 管理控制台"中的 BizTalk Server 帮助。  
  
 在您查看并删除孤立或重复的消息之前，这些消息将一直保存在 BizTalk 管理控制台中。 删除这些消息最有效的方法是设置具有特定筛选器的发送端口，这些筛选器针对孤立或重复的消息进行设置。 你可以移动它们使用任何 BizTalk Server 中提供的传输方式。 例如，你可以通过使用文件传输移动它们。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将文件作为孤立或重复的消息发送到上一个硬盘的位置中。 这可使您轻松删除它们。 该端口可处于登记并停止的状态，在这种情况下，所有发送到该端口的消息都将显示为在该发送端口下挂起。  
  
> [!NOTE]
>  除创建发送端口来处理重复/孤立的消息外，还可以创建特殊的管道组件从 MessageBox 数据库中删除这些消息。 您可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK 中的 FixMsg 组件作为模板， 你必须修改`IComponent.Execute`方法以返回 null。 这将导致[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]要放弃所做的任何消息发送到包含该组件的管道。 您必须编译此管道组件并将其添加到发送管道，然后编译、部署该发送管道并为接收端口选择该发送管道。 有关详细信息，请参阅"CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]示例)"BizTalk Server 帮助中。  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a>创建处理孤立或重复消息的发送端口  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**视图**菜单上，单击**BizTalk 资源管理器**。  
  
2.  在 BizTalk 资源管理器中，展开**BizTalk 管理数据库**，然后展开**发送端口**。  
  
3.  右键单击**发送端口**，然后单击**添加发送端口**。  
  
4.  在创建新发送端口窗口中，选择**静态单向端口**，然后单击**确定**。  
  
5.  在静态单向发送端口属性窗口中，在**名称**框中，键入发送端口的名称。  
  
6.  在左窗格中，单击**传输**。 在右窗格中，单击**传输类型**，然后选择**文件**为传输类型。 单击旁边的省略号按钮 （...）**地址 (URI)**，在硬盘上键入位置，然后单击**确定**。  
  
7.  在左窗格中，单击**发送**，单击**发送管道**，然后选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  
  
8.  在左窗格中，单击**筛选器和映射**，然后单击**筛选器**。  
  
9. 在右窗格中，在第一行的**属性**，选择**Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage**从下拉列表中，保留**运算符**作为 **==** ，输入**True**为**值**，然后选择**或**从下拉列表中为**组**。  
  
10. 在右窗格中，第二行的**属性**，选择**Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage**从下拉列表中，保留**运算符**作为 **==** ，然后输入**True**为**值**。  
  
11. 单击 **“确定”**。  
  
12. 在 BizTalk 资源管理器，右键单击发送端口的名称，单击**Enlist**。 已登记发送端口后，请发送端口中，右键单击，然后单击**启动**。  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)