---
title: 步骤 11： 创建业务流程变量 |Microsoft 文档
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
ms.openlocfilehash: a640b938628ebe3dcd6757e3f6fdfd7b1108880d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962243"
---
# <a name="step-11-create-orchestration-variables"></a>步骤 11： 创建业务流程变量
在此步骤中，你可以创建消息实例发送和接收的业务流程的业务流程变量。  
  
 HL7 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 序列化程序要求以下部件名称。 如果使用任何其他部分的名称创建多部分消息，序列化程序将拒绝该消息。 消息部分名称为：  
  
-   MSHSegment  
  
-   BodySegments  
  
-   Z 段  
  
 下面是有关 Z 段部件的重要信息：  
  
-   所有消息上文所述，无论 Z 段是否存在或不都包含三个部分。  
  
-   你可以使用 Z 段一部分来包含从消息实例，即尾随和未定义架构 （这也意味着它未声明） 中的数据。  
  
-   如果没有未声明的数据，Z 段部分为空。 查看 BizTalk 映射程序; 中的中间 XML 时，看不到 Z 段部分但是，在 BizTalk 运行状况和活动跟踪 (HAT) 工具中，你看到到每条消息的三个部分。  
  
### <a name="to-create-orchestration-variables"></a>若要创建业务流程变量  
  
1.  单击**业务流程视图**选项卡旁边**解决方案资源管理器**解决方案资源管理器下的选项卡。  
  
2.  在**业务流程视图**窗格中，右键单击**消息**，然后单击**新消息**。  
  
3.  更改**标识符**中的属性**属性**窗格**DoorbellInputMessage**，然后按**Enter**。  
  
4.  在**属性**窗格的下拉列表中**消息类型**，展开**架构**，然后单击**BTAHL7_Project.Doorbell**。  
  
5.  重复步骤 2 和 3 以创建名为的另一条消息**DoorbellOutputMessage**。  
  
6.  在**属性**窗格的下拉列表中**消息类型**，展开**架构**，然后单击**BTAHL7Schemas.ADT_A04_22_GLO_DEF**.  
  
7.  在**业务流程视图**窗格中，展开**类型**节点。 右键单击**多部分消息类型**，然后单击**新多部分消息类型**。  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]创建名为的新消息类型**MultipartType_1**与名为新消息一起**MessagePart_1**。  
  
8.  单击**MultipartType_1**，然后在**属性**窗口中，单击**标识符**，然后键入新名称**DoorbellFinalMessageType**，然后按**Enter**。  
  
    > [!NOTE]
    >  在步骤 9 到 15，你将创建多部分消息的组成部分。 在其中创建的多部分消息部分的顺序非常重要。 始终会创建标头，然后正文，然后 Z 段。  
  
    > [!NOTE]
    >  一次你已创建，并且名为消息部分中，不要重命名它们。 如有必要，删除旧的正文部分，并使用新名称创建新的正文部分。  
  
9. 在**类型**窗口下**多部分消息类型**，展开**DoorbellFinalMessageType**，然后单击**MessagePart_1**。 在**属性**窗格中，输入**MSHSegment**为**标识符**，然后按**Enter**。 中的下拉列表**类型**，展开 **.NET 类**，然后单击\<**从引用的程序集选择\>**。  
  
10. 在**选择项目类型**对话框中，在左窗格中，单击**System.Xml**。 在右窗格中，单击**XmlDocument**，然后单击**确定**。  
  
11. 在业务流程视图窗口中，右键单击**DoorbellFinalMessageType**，然后单击**新消息部分**创建 MessagePart_1。  
  
12. 在**属性**窗口中，输入**BodySegments**为**标识符**，然后按**Enter**。 中的下拉列表**类型**，展开**架构**，然后选择**BTAHL7Schemas.ADT_A04_22_GLO_DEF**从下拉列表。  
  
13. 设置**消息正文部分**属性**True**。  
  
14. 在**业务流程视图**窗口中，右键单击**DoorbellFinalMessageType**，然后单击**新消息部分**。  
  
15. 在**属性**窗格中，输入**ZSegments**为**标识符**，然后按**Enter**。 单击**类型**，展开 **.NET 类**，然后单击**System.String**从下拉列表。  
  
    > [!NOTE]
    >  你使用**System.String**为 Z 段消息部分，因为 Z 段中包含不需要符合架构的字符串数据。  
  
16. 在**业务流程视图**窗口中，右键单击**消息**，然后单击**新消息**。  
  
17. 在**属性**窗口中，输入**DoorbellFinalMessage**为**标识符**，然后按**Enter**。 中的下拉列表**消息类型**，展开**多部分消息类型**，然后单击**BTAHL7_Project.DoorbellFinalMessageType**。  
  
18. 在**业务流程视图**窗口中，右键单击**变量**，然后单击**新变量**。  
  
19. 在**属性**窗格中，输入**HeaderInfo**为**标识符**，然后按**Enter**。 中的下拉列表**类型**，双击\< **.NET 类\>**。  
  
20. 在**选择项目类型**窗口中的，在左窗格中，单击**System.Xml**。 在右窗格中，单击**XmlDocument**，然后单击**确定**。  
  
21. 在**文件**菜单上，单击**保存所有**。  
  
 继续执行[步骤 12： 配置业务流程形状](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)