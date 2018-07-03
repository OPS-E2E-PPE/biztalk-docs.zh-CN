---
title: 将请求映射为在专用流程中的响应 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- private processes, mapping requests
- private processes, customizing
- orchestrations, adding maps
- maps, adding to orchestrations
- maps, creating
- customizing private processes
- requests, mapping
- requests, private processes
ms.assetid: 5452c0a2-3a9b-43e7-bfa7-713eef0eab3b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb7cab4ba412a46f61df89daefd86df260454195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976222"
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a>将请求映射为在专用流程中的响应
本主题介绍如何将专用响应方流程收到的请求消息映射 — 从 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]公用响应方流程，可以发送到的响应消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用响应方流程。  
  
 当响应方收到请求消息时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将请求消息从公用业务流程路由到专用业务流程，再路由到业务线 (LOB) 程序。 响应方需要来自 LOB 程序的响应服务内容，以生成返回给发起方的 RosettaNet 响应消息。 响应消息中的许多元素是用请求消息中的值填充的。 因此，可以将映射并入响应方专用业务流程中，以帮助 LOB 程序生成所需格式的响应服务内容消息。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包含的以下示例可供你在将映射添加到响应方专用流程时使用：  
  
-   [3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [使用业务规则的 3A4 专用响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a>若要创建映射  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  上**文件**菜单，依次指向**打开**，然后单击**项目**。  
  
3.  找到包含 BizTalk 项目的文件夹，该项目包含要添加映射的专用业务流程。  
  
4.  在解决方案资源管理器中，右键单击项目，指向“添加”，然后单击“新建项”。  
  
5.  在添加新项窗口中**类别**窗格中，单击**映射文件**。 在模板窗格中单击**映射**。 在中**名称**框中，键入映射的名称，然后单击**打开**。  
  
6.  在源架构窗格中，单击**打开源架构**。  
  
7.  在 BizTalk 类型选取器窗口中，展开**架构**，选择你想要将映射中，然后单击请求消息的 PIP 架构**确定**。  
  
8.  在目标架构窗格中，单击**打开目标架构**。  
  
9. 在 BizTalk 类型选取器窗口中，展开**引用**，展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，展开**架构**，选择的 PIP 架构响应消息，你想要将映射，然后依次**确定**。  
  
10. 右键单击\<*架构*\>节点的源架构，然后单击**展开树节点**。  
  
11. 对于其他目标架构，请重复步骤 10。  
  
12. 在“源架构”窗格中，单击并按住一个要映射为目标架构中的某个字段的字段。 然后拖动到“目标架构”窗格中所对应的节点。  
  
13. 对于需要在两个架构之间映射的每个字段，请重复步骤 12。  
  
14. 验证和测试映射。 有关详细信息，请参阅 BizTalk Server 帮助中的"编译和测试映射"主题。  
  
### <a name="to-add-the-map-to-the-orchestration"></a>向业务流程添加映射  
  
1.  在解决方案资源管理器中，双击专用业务流程。  
  
    > [!NOTE]
    >  请确保业务流程具有对包含架构的程序集的引用。  
  
2.  在工具箱中，单击**转换**形状，并将其拖到业务流程具有将转换为响应消息的请求消息中的点。  
  
    > [!NOTE]
    >  有关示例的位置**转换**形状中，请参阅 PIP3A4PrivateResponder.odx 业务流程。 该文件位于\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for rosettanet\sdk\pipautomation\3a4\pr。 此示例会将**转换**立即形状下**放在 IsActivityDoubleAction**形状。 有关详细信息，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。  
  
    > [!NOTE]
    >  有关如何将多个映射合并多个 Pip 的示例，请参阅[双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)。  
  
3.  在业务流程设计图面上，单击**揅 constructmessage1**。 在“属性”窗口中，键入形状的名称和要构造的消息的名称。  
  
4.  在业务流程设计图面上，单击**转换**。 在属性窗口中，单击省略号按钮 (**...**) 旁边**映射名称**。  
  
5.  在转换配置窗口中，单击**现有的映射**，然后在**完全限定的映射名称**，单击刚创建的映射。  
  
6.  下**转换**，单击**源**。 单击变量下的空框，然后从下拉列表中选择请求消息的名称。  
  
7.  下**转换**，单击**目标**。 单击变量下的空框，然后从下拉列表中选择响应消息的名称。  
  
8.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)