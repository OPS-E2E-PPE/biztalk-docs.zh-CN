---
title: 使用 BTARN 管理控制台 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, activating
- activating agreements
- BTARN Management Console, Scope pane
- tracking
- creating, trading partners
- BTARN Management Console, agreements
- process configuration
- agreements, modifying
- BTARN Management Console, home organizations
- agreements, creating
- BTARN Management Console, trading partners
- agreements, deleting
- deleting, agreements
- BTARN Management Console
- agreements, listing
- modifying, trading partners
- creating, agreements
- trading partners, creating
- modifying, agreements
- BAM tracking
- Scope pane [BTARN Management Console]
- trading partners, modifying
- trading partners, deleting
- BTARN Management Console, process configurations
- deleting, trading partners
- BTARN Management Console, about BTARN Management Console
- home organizations
ms.assetid: 000ee93d-eb1d-4ff8-a9cf-0547beff027d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39157aa2454690a77ffbb1a5c2492bc07404c602
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209717"
---
# <a name="using-the-btarn-management-console"></a>使用 BTARN 管理控制台
本主题介绍如何从 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理控制台来管理 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
 打开[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台，通过单击**启动**，依次指向**程序**，依次指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台左侧的作用域窗格包括所有 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 配置节点。 无论您在作用域窗格选择了什么配置项，右侧的结果窗格中都会包括这些配置项的所有特定的实例。  
  
## <a name="operations-in-the-scope-pane"></a>作用域窗格中的操作  
 可以在作用域窗格中对节点执行下列操作：  
  
-   设置合作伙伴发送端口要使用的 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送和接收管道。 有关详细信息，请参阅[设置 BTARN 发送和接收管道](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md)。  
  
-   启用业务活动监视 (BAM) 跟踪。 有关详细信息，请参阅[启用 BAM 跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)。  
  
-   请确保任何新导入的配置是通过右键单击作用域窗格中中的配置节点，然后单击显示在控制台**刷新**。  
  
-   通过右键单击结果窗格中查看其他列**过程配置设置**或**协议**节点在作用域窗格中，指向**视图**，，然后单击**添加/删除列**。 通过使用可用的列和显示的列之间移动列**添加或删除**按钮。 此命令对于具有许多可用列（[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在默认情况下不显示这些列）的协议特别有用。  
  
## <a name="process-configurations"></a>进程配置  
 可以对流程配置执行下列操作：  
  
-   通过右键单击添加新的过程配置**过程配置设置**作用域节点，指向**新建**，然后单击**过程配置**。 有关详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
-   通过右键单击结果窗格中的过程配置，然后单击编辑现有的过程配置**属性**，或通过双击过程配置。 有关详细信息，请参阅[如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  
  
-   通过右键单击结果窗格中的过程配置，然后单击删除现有的过程配置**删除**。  
  
-   创建基于现有的过程配置通过右键单击你想要基于新的配置，结果窗格中的配置，然后单击新的过程配置**从副本的新过程配置**. 这将显示一个新**进程配置属性**对话框中使用的现有配置设置填充。 输入一个新**显示代码**，然后单击**确定**以创建新的配置。 有关详细信息，请参阅[使用 PIP 规范创建过程配置](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)。  
  
-   显示的过程配置通过右键单击结果窗格中的特定配置，然后单击关联的所有协议列表**显示协议**。 这将会切换焦点到**协议**作用域窗格中的节点并在结果窗格中显示关联的协议。 你可以还原到协议的完整列表，请右键单击**协议**作用域窗格中，然后单击的节点**全部显示**。  
  
## <a name="home-organizations"></a>本组织  
 可以对本组织执行下列操作：  
  
-   通过右键单击添加新的主组织**本组织**作用域节点，指向**新建**，然后单击**本组织**。 有关详细信息，请参阅[创建或编辑了主页的组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)。  
  
-   通过右键单击主组织在结果窗格中，然后单击编辑现有主组织**属性**，或通过双击本组织。 有关详细信息，请参阅[创建或编辑了主页的组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)。  
  
-   通过右键单击主组织在结果窗格中，然后单击删除现有主组织**删除**。  
  
## <a name="partners"></a>伙伴  
 可以对合作伙伴执行下列操作：  
  
-   通过右键单击添加一个新伙伴**合作伙伴**作用域节点，指向**新建**，然后单击**合作伙伴**。 有关详细信息，请参阅[创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)。  
  
-   通过右键单击结果窗格中的合作伙伴然后单击编辑现有的伙伴**属性**，或通过双击合作伙伴。 有关详细信息，请参阅[创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)。  
  
-   通过右键单击结果窗格中的合作伙伴然后单击删除现有的伙伴**删除**。  
  
## <a name="agreements"></a>协议  
 可以对协议执行下列操作：  
  
-   通过右键单击添加新协议**协议**作用域节点，指向**新建**，然后单击**协议**。 有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
-   通过右键单击在结果窗格中，该协议，然后单击编辑现有协议**属性**，或通过双击协议。 有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
-   通过右键单击在结果窗格中，该协议，然后单击删除现有协议**删除**。  
  
-   通过右键单击在结果窗格中，已停用的协议，然后单击激活协议**激活**。 此时将启用与该协议相关联的消息，使其可以被发送或接收。 您也可以停用协议，以防止发送或接收与协议相关联的消息。  
  
-   回到后显示的过程配置相关联中的协议列表的协议的完整列表，请右键单击**协议**作用域窗格中，然后单击的节点**全部显示**.  
  
## <a name="see-also"></a>另请参阅  
 [设置 BTARN 发送和接收管道](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md)   
 [启用 BAM 跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)   
 [如何创建或编辑过程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [创建或编辑主组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)   
 [创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)