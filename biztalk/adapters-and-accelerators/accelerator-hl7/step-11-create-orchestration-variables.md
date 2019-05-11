---
title: 步骤 11:创建业务流程变量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
- message enrichment tutorial, orchestrations
ms.assetid: 3d1f792d-fe74-4373-86fa-3debda55e732
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1675a2e00219b8afc2f7c94c755c12140e5f3665
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288989"
---
# <a name="step-11-create-orchestration-variables"></a>步骤 11:创建业务流程变量
在此步骤中，您创建消息实例发送和接收的业务流程的业务流程变量。  
  
 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 序列化程序要求的以下部分名称。 如果使用任何其他部分组成的名称创建多部分消息，序列化程序会拒绝该消息。 消息部件名称为：  
  
- MSHSegment  
  
- BodySegments  
  
- Z 段  
  
  下面是有关 Z 段部件的重要信息：  
  
- 所有消息都包含三个部分，上文所述，而不考虑 Z 段是否存在。  
  
- 使用 Z 段部分包含从消息实例中是尾随并且未定义架构 （这也意味着它将取消声明） 中的数据。  
  
- 如果没有未声明的数据，Z 段部分为空。 查看 BizTalk 映射器; 内的中间 XML 时未看到 Z 段部分但是，在 BizTalk 运行状况与活动跟踪 (HAT) 工具中，您看到三个部分的每个消息。  
  
### <a name="to-create-orchestration-variables"></a>若要创建业务流程变量  
  
1. 单击**业务流程视图**选项卡旁边**解决方案资源管理器**在解决方案资源管理器下的选项卡。  
  
2. 在中**业务流程视图**窗格中，右键单击**消息**，然后单击**新消息**。  
  
3. 更改**标识符**属性中的**属性**窗格**DoorbellInputMessage**，然后按**Enter**。  
  
4. 在中**属性**窗格中，在下拉列表中的**消息类型**，展开**架构**，然后单击**BTAHL7_Project.Doorbell**。  
  
5. 重复步骤 2 和 3 创建名为的另一条消息**DoorbellOutputMessage**。  
  
6. 在中**属性**窗格中，在下拉列表中的**消息类型**，展开**架构**，然后单击**BTAHL7Schemas.ADT_A04_22_GLO_DEF**.  
  
7. 在中**业务流程视图**窗格中，展开**类型**节点。 右键单击**多部分消息类型**，然后单击**新建多部分消息类型**。  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] 创建名为的新消息类型**MultipartType_1**以及名为的新消息**MessagePart_1**。  
  
8. 单击**MultipartType_1**，然后在**属性**窗口中，单击**标识符**并键入新名称**DoorbellFinalMessageType**，然后按**Enter**。  
  
   > [!NOTE]
   >  在步骤 9 到 15，将创建多部分消息的部分。 创建多部分消息的部分的顺序至关重要。 始终创建标头，则正文，则 Z 段。  
  
   > [!NOTE]
   >  一次你已创建并命名为消息部分中，不要重命名它们。 如有必要，删除旧的正文部分，并使用新名称创建新的正文部分。  
  
9. 在中**类型**窗口下**多部分消息类型**，展开**DoorbellFinalMessageType**，然后单击**MessagePart_1**。 在中**属性**窗格中，输入**MSHSegment**有关**标识符**，然后按**Enter**。 中的下拉列表**类型**，展开 **.NET 类**，然后单击\<**从引用的程序集选择\>**。  
  
10. 在中**选择项目类型**对话框中，在左窗格中，单击**System.Xml**。 在右窗格中，单击**XmlDocument**，然后单击**确定**。  
  
11. 在业务流程视图窗口中，右键单击**DoorbellFinalMessageType**，然后单击**新消息部分**创建 MessagePart_1。  
  
12. 在中**属性**窗口中，输入**BodySegments**有关**标识符**，然后按**Enter**。 中的下拉列表**类型**，展开**架构**，然后选择**BTAHL7Schemas.ADT_A04_22_GLO_DEF**从下拉列表。  
  
13. 设置**消息正文部分**属性设置为**True**。  
  
14. 在中**业务流程视图**窗口中，右键单击**DoorbellFinalMessageType**，然后单击**新消息部分**。  
  
15. 在中**属性**窗格中，输入**ZSegments**有关**标识符**，然后按**Enter**。 单击**类型**，展开 **.NET 类**，然后单击**System.String**从下拉列表。  
  
    > [!NOTE]
    >  您使用**System.String**的 Z 段的消息部分，因为 Z 段包含不需要符合架构的字符串数据。  
  
16. 在中**业务流程视图**窗口中，右键单击**消息**，然后单击**新消息**。  
  
17. 在中**属性**窗口中，输入**DoorbellFinalMessage**有关**标识符**，然后按**Enter**。 中的下拉列表**消息类型**，展开**多部分消息类型**，然后单击**BTAHL7_Project.DoorbellFinalMessageType**。  
  
18. 在中**业务流程视图**窗口中，右键单击**变量**，然后单击**新变量**。  
  
19. 在中**属性**窗格中，输入**HeaderInfo**有关**标识符**，然后按**Enter**。 中的下拉列表**类型**，双击\< **.NET 类\>**。  
  
20. 在中**选择项目类型**窗口中的，在左窗格中，单击**System.Xml**。 在右窗格中，单击**XmlDocument**，然后单击**确定**。  
  
21. 在中**文件**菜单上，单击**全部保存**。  
  
    请继续执行[步骤 12:配置业务流程形状](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)