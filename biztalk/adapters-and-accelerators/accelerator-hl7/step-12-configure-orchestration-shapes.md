---
title: 步骤 12： 配置业务流程形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, orchestration shapes
- orchestrations, shapes
- message enrichment tutorial, orchestrations
ms.assetid: 9388254b-2841-4489-838e-de913ceff151
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f21c373aacc949b95588c66f1243936b15ea9e89
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006422"
---
# <a name="step-12-configure-orchestration-shapes"></a>步骤 12： 配置业务流程形状
在此步骤中，你将完成业务流程形状的配置才能删除缺少配置智能标记。 你指定**DoorbellOutputMessage**作为第一个转换过程中，输出指定**DoorbellMap.btm**作为用于在该进程中的映射。 然后指定**DoorbellFinalMessage**作为第二个输出转换过程中，并添加丰富的消息的其他字段数据的表达式。  
  
 **先决条件：** [知识库文章 941261](http://support.microsoft.com/kb/941261)必须设置业务流程配置之前应用。  
  
### <a name="to-configure-orchestration-shapes"></a>配置业务流程形状  
  
1.  业务流程设计视图图面上的 Visual Studio，请单击**ConstructMessage_1**形状。  
  
2.  在**属性**窗口中，单击**消息构造**属性中，选择**DoorbellOutputMessage**从下拉列表，然后按**输入**。  
  
3.  在业务流程设计视图图面中，单击**DoorbellTransform**形状内**ConstructMessage_1**形状。 在**属性**窗口中，单击**映射名称**，然后单击属性字段中的省略号 （...） 按钮。  
  
4.  在转换的配置对话框中，选择**现有映射**。 在**完全限定的映射名称**下拉列表中，单击**BTAHL7_Project.DoorbellMap**。  
  
5.  单击**源**的左窗格中。  
  
6.  单击下的空框中**变量名称**单击**DoorBellInputMessage**从下拉列表。  
  
7.  单击**目标**的左窗格中。  
  
8.  单击下的空框中**变量名称**单击**DoorbellOutputMessage**从下拉列表。  
  
9. 单击**确定**以保存更改。  
  
10. 在业务流程设计视图图面中，单击**ConstructMessage_2**形状。  
  
11. 在**属性**窗口中，单击**消息构造**，选择**DoorbellFinalMessage**从下拉列表，然后按**Enter**.  
  
12. 在业务流程设计视图图面中，单击**DoorbellFinalTransform**形状内**ConstructMessage_2**形状。 在**属性**窗口中，单击**表达式**，然后单击省略号 （...） 按钮以打开 BizTalk 表达式编辑器。  
  
13. 在 BizTalk 表达式编辑器中，在文本字段中单击，然后粘贴以下文本：  
  
    ```  
    HeaderInfo = new System.Xml.XmlDocument();   
    HeaderInfo.LoadXml("<ns0:MSH_25_GLO_DEF xmlns:ns0=\"http://microsoft.com/HealthCare/HL7/2X\">  
        <MSH><MSH.2_EncodingCharacters>^~\\&</MSH.2_EncodingCharacters><MSH.3_SendingApplication>  
        <HD.0_NamespaceId>SrcApp</HD.0_NamespaceId><HD.1_UniversalId>SrcAppUid</HD.1_UniversalId>  
        </MSH.3_SendingApplication><MSH.4_SendingFacility><HD.0_NamespaceId>srcFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>srcFacUid</HD.1_UniversalId></MSH.4_SendingFacility><MSH.5_ReceivingApplication>  
        <HD.0_NamespaceId>dstApp</HD.0_NamespaceId><HD.1_UniversalId>dstAppUid</HD.1_UniversalId>  
        </MSH.5_ReceivingApplication><MSH.6_ReceivingFacility><HD.0_NamespaceId>dstFac</HD.0_NamespaceId>  
        <HD.1_UniversalId>dstFacUid</HD.1_UniversalId></MSH.6_ReceivingFacility><MSH.7_DateTimeOfMessage>  
        <TS.1>200307092343</TS.1></MSH.7_DateTimeOfMessage><MSH.8_Security>sec</MSH.8_Security>  
        <MSH.9_MessageType><CM_MSG.0_MessageType>ADT</CM_MSG.0_MessageType>  
        <CM_MSG.1_TriggerEvent>A04</CM_MSG.1_TriggerEvent></MSH.9_MessageType>  
        <MSH.10_MessageControlId>msgid2134</MSH.10_MessageControlId><MSH.11_ProcessingId>  
        <PT.0_ProcessingId>P</PT.0_ProcessingId></MSH.11_ProcessingId><MSH.12_VersionId>  
       <VID_0_VersionId>2.2</VID_0_VersionId></MSH.12_VersionId></MSH></ns0:MSH_25_GLO_DEF>");  
  
    DoorbellFinalMessage.MSHSegment = HeaderInfo;  
    DoorbellFinalMessage.BodySegments = DoorbellOutputMessage;  
    DoorbellFinalMessage.ZSegments = "";  
  
    DoorbellFinalMessage(BTAHL7Schemas.MSH1) = 124;   
    DoorbellFinalMessage(BTAHL7Schemas.MessageEncoding) = 65001;  
    DoorbellFinalMessage(BTAHL7Schemas.MSH2) = "^~\\&";  
    DoorbellFinalMessage(BTAHL7Schemas.ParseError) = false;   
    DoorbellFinalMessage(BTAHL7Schemas.ZPartPresent) = false;  
    DoorbellFinalMessage(BTAHL7Schemas.SegmentDelimiter2Char) = true;  
  
    ```  
  
14. 单击 **“确定”**。  
  
    > [!IMPORTANT]
    >  在"HeaderInfo.LoadXml"表达式中，删除回车和表达式中的空间。 "HeaderInfo.LoadXml"语句应在一行上。  
  
    > [!NOTE]
    >  前面的第一个块是文本的硬编码的 XML 标头的示例。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序需要标头段。 你可以自定义你的环境的需要根据这些标头值。 前面的文本的第二个块定义在多部分消息中所需的三个消息部分。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序需要多部分消息。 前面的文本的第三个块包含提升的属性，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序检查 HL7 平面文件消息序列化为 XML 消息。  
  
 继续执行[步骤 13： 创建和配置端口](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)