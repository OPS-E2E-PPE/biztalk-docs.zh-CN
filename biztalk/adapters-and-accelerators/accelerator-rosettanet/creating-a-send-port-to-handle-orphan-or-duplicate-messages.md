---
title: 创建处理孤立或重复消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a6e166a891da2a3d393d176555c2b50deed044
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284847"
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a>创建处理孤立或重复消息的发送端口
本主题介绍如何设置可用于删除孤立或重复消息的发送端口。  
  
 孤立或重复消息可能是个问题，如果 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]公用业务流程完成处理该消息的第一个副本后收到一条消息的其他副本。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将标记为重复这些消息并将它们挂起。 您可以在 BizTalk 管理控制台中查看这些消息。 有关 BizTalk 管理控制台的详细信息，请参阅"使用 BizTalk 管理控制台"中的 BizTalk Server 帮助。  
  
 孤立或重复消息保留在 BizTalk 管理控制台查看或删除它们之前。 删除它们的最有效方法是与筛选器针对孤立或重复消息的发送端口设置。 您可以移动它们使用任何 BizTalk Server 中可用的运输方式。 例如，可以通过使用文件传输移动它们。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将孤立或重复消息作为文件发送到硬盘上的位置。 这样可以轻松删除它们。 该端口可处于登记并停止状态，为在已挂起，所有消息都发送给它的情况下将显示该发送端口。  
  
> [!NOTE]
>  而不是创建用于处理重复/孤立的消息的发送端口，可以创建一个特殊的管道组件以从 MessageBox 数据库中删除这些消息。 可以使用中的 FixMsg 组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为模板的 SDK。 您必须修改`IComponent.Execute`方法返回 null。 这将导致[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]放弃发送到包含该组件的管道的任何消息。 您必须编译此管道组件并将其添加到发送管道，，然后编译、 部署和选择接收端口的发送管道。 有关详细信息，请参阅"CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]示例)"BizTalk Server 帮助中。  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a>若要创建处理孤立或重复消息的发送端口  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**视图**菜单中，单击**BizTalk 浏览器**。  
  
2. 在 BizTalk 浏览器中，展开**BizTalk 管理数据库**，然后展开**发送端口**。  
  
3. 右键单击**发送端口**，然后单击**添加发送端口**。  
  
4. 在创建新发送端口窗口中，选择**静态单向端口**，然后单击**确定**。  
  
5. 在静态单向发送端口属性窗口中**名称**框中，键入发送端口的名称。  
  
6. 在左窗格中，单击**传输**。 在右窗格中，单击**传输类型**，然后选择**文件**传输类型。 单击省略号按钮 （...） 下一步**地址 (URI)** ，键入您的硬盘上的位置，然后单击**确定**。  
  
7. 在左窗格中，单击**发送**，单击**发送管道**，然后选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。  
  
8. 在左窗格中，单击**筛选器和映射**，然后单击**筛选器**。  
  
9. 在右窗格中，在第一行的**属性**，选择**Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage**从下拉列表中，将保留**运算符**作为 **==** ，输入**True**有关**值**，然后选择**或**从下拉列表中为**组**。  
  
10. 在右窗格中，在第二个行上的**属性**，选择**Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage**从下拉列表中，将保留**运算符**作为 **==** ，然后输入**True**有关**值**。  
  
11. 单击“确定”  。  
  
12. 在 BizTalk 浏览器中，右键单击该发送端口的名称，单击**登记**。 登记发送端口后，右键单击该发送端口，然后依次**启动**。  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)