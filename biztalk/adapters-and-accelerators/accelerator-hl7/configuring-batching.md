---
title: 配置批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ab9ead01273e54826db670e7e6d6a2e9af6200
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204565"
---
# <a name="configuring-batching"></a>配置批处理
你使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器来创建批处理，批处理中 / 批处理出批处理，并选择可用架构的出站批处理。  
  
> [!NOTE]
>  你必须配置贸易合作伙伴使用 BizTalk 资源管理器，然后才能配置消息批处理。  
  
 下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**批定义**选项卡。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和配置批处理。  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a>若要启用消息批处理用于出站批处理 （创建批处理）  
  
1.  在**启动**菜单上，打开**BizTalk Server 管理**。  
  
2.  在管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk应用程序 1**。  
  
3.  单击**业务流程**，右键单击**BatchOrchestration.Orchestration_1**，然后选择**属性**。  
  
4.  在业务流程属性对话框中，单击**绑定**在控制台树中。  
  
5.  在**绑定**窗格中，选择适当的主机的**主机**。 单击 **“确定”**。  
  
6.  右键单击**BatchOrchestration.Orchestration_1**，然后选择**Enlist**。  
  
7.  右键单击**BatchOrchestration.Orchestration_1**，然后选择**启动**。  
  
### <a name="to-run-btahl7-configuration-explorer"></a>若要运行 BTAHL7 配置资源管理器  
  
-   在**启动**菜单上，打开**Microsoft BizTalk Accelerator for HL7** ，然后单击**BTAHL7 配置资源管理器**。  
  
### <a name="to-configure-batching"></a>若要配置批处理  
  
-   在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，请在**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，的方，然后在**批处理定义**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**所需的碎片**|选择以下选项之一：<br /><br /> -   **是**。 若要启用碎片。<br />-   **不**。 若要禁用碎片。 **注意：** 为新的当事方，**所需的碎片**默认为**否**。|  
    |**选择消息**|选择你想要将作为从一批发送的消息类型**可用消息**窗口中，然后单击右箭头转向 (**>>**)。|  
    |**选择消息确认**|选择要为其以从一批的形式发送的确认的消息类型**可用消息确认**窗口中，然后单击向右移动 (**>>**)。|  
  
    > [!NOTE]
    >  你可能看不到架构添加到你在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]项目中时，在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器正在运行。 若要查看这些文件，你可能需要在重新启动[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="see-also"></a>另请参阅  
 [计划批处理](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)