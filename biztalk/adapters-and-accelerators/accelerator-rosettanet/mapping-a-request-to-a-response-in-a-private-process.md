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
ms.openlocfilehash: cd0ec4be1703c81061cf38310a467932a917bca3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283232"
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a>将请求映射为在专用流程中的响应
本主题介绍如何将专用响应方流程收到的请求消息映射 — 从 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]公用响应方流程，可以发送到的响应消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用响应方流程。  
  
 当响应方接收请求消息时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到专用业务流程的业务流程，从公用流程，将请求消息路由至业务 (LOB) 程序。 响应方需要来自 LOB 程序生成回发起方的 RosettaNet 响应消息的响应服务内容。 许多响应消息中的元素是使用请求消息中的值进行填充。 因此，可以将合并在响应方专用流程业务流程，以帮助 LOB 程序生成所需格式的响应服务内容消息映射。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包含将映射添加到响应方专用业务流程时，可以使用以下示例：  
  
-   [3A2 请求到 3A2 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [3A4 请求到 3A4 响应映射示例](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [使用业务规则的 3A4 专用响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a>若要创建映射  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  上**文件**菜单，依次指向**打开**，然后单击**项目**。  
  
3.  找到包含包含你想要将地图添加专用业务流程的 BizTalk 项目的文件夹。  
  
4.  在解决方案资源管理器中，右键单击项目，指向“添加”，然后单击“新建项”。  
  
5.  在添加新项窗口中**类别**窗格中，单击**映射文件**。 在模板窗格中单击**映射**。 在中**名称**框中，键入映射的名称，然后单击**打开**。  
  
6.  在源架构窗格中，单击**打开源架构**。  
  
7.  在 BizTalk 类型选取器窗口中，展开**架构**，选择你想要将映射中，然后单击请求消息的 PIP 架构**确定**。  
  
8.  在目标架构窗格中，单击**打开目标架构**。  
  
9. 在 BizTalk 类型选取器窗口中，展开**引用**，展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，展开**架构**，选择的 PIP 架构响应消息，你想要将映射，然后依次**确定**。  
  
10. 右键单击\<*架构*\>节点的源架构，然后单击**展开树节点**。  
  
11. 对于目标架构中重复步骤 10。  
  
12. 在源架构窗格中，单击并按住你想要将映射到目标架构中的字段的字段。 将拖至目标架构窗格中的相应节点。  
  
13. 对于具有两个架构之间进行映射的所有字段重复步骤 12。  
  
14. 验证和测试映射。 有关详细信息，请参阅 BizTalk Server 帮助中的"编译和测试映射"主题。  
  
### <a name="to-add-the-map-to-the-orchestration"></a>若要将地图添加到业务流程  
  
1.  在解决方案资源管理器，双击专用业务流程。  
  
    > [!NOTE]
    >  请确保该业务流程具有对包含架构的程序集的引用。  
  
2.  在工具箱中，单击**转换**形状，并将其拖到业务流程具有将转换为响应消息的请求消息中的点。  
  
    > [!NOTE]
    >  有关示例的位置**转换**形状中，请参阅 PIP3A4PrivateResponder.odx 业务流程。 该文件位于\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for rosettanet\sdk\pipautomation\3a4\pr。 此示例会将**转换**立即形状下**放在 IsActivityDoubleAction**形状。 有关详细信息，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。  
  
    > [!NOTE]
    >  有关如何将多个映射合并多个 Pip 的示例，请参阅[双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)。  
  
3.  在业务流程设计图面上，单击**揅 constructmessage1**。 在属性窗口中，键入该形状的名称和要构造的消息的名称。  
  
4.  在业务流程设计图面上，单击**转换**。 在属性窗口中，单击省略号按钮 (**...**) 旁边**映射名称**。  
  
5.  在转换配置窗口中，单击**现有的映射**，然后在**完全限定的映射名称**，单击刚创建的映射。  
  
6.  下**转换**，单击**源**。 单击变量下的空框，并从下拉列表中选择请求消息的名称。  
  
7.  下**转换**，单击**目标**。 单击变量下的空框，然后从下拉列表中选择响应消息的名称。  
  
8.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)