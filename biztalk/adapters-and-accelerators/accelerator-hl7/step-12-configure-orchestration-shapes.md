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
# <a name="step-12-configure-orchestration-shapes"></a><span data-ttu-id="90f62-102">步骤 12： 配置业务流程形状</span><span class="sxs-lookup"><span data-stu-id="90f62-102">Step 12: Configure Orchestration Shapes</span></span>
<span data-ttu-id="90f62-103">在此步骤中，你将完成业务流程形状的配置才能删除缺少配置智能标记。</span><span class="sxs-lookup"><span data-stu-id="90f62-103">In this step, you complete the configuration of the orchestration shapes in order to remove the insufficient configuration smart tags.</span></span> <span data-ttu-id="90f62-104">你指定**DoorbellOutputMessage**作为第一个转换过程中，输出指定**DoorbellMap.btm**作为用于在该进程中的映射。</span><span class="sxs-lookup"><span data-stu-id="90f62-104">You designate **DoorbellOutputMessage** as the output of the first transform process, designating **DoorbellMap.btm** as the map used in that process.</span></span> <span data-ttu-id="90f62-105">然后指定**DoorbellFinalMessage**作为第二个输出转换过程中，并添加丰富的消息的其他字段数据的表达式。</span><span class="sxs-lookup"><span data-stu-id="90f62-105">You then designate **DoorbellFinalMessage** as the output of the second transform process, and add the expression that enriches the message with additional field data.</span></span>  
  
 <span data-ttu-id="90f62-106">**先决条件：** [知识库文章 941261](http://support.microsoft.com/kb/941261)必须设置业务流程配置之前应用。</span><span class="sxs-lookup"><span data-stu-id="90f62-106">**Prerequisite:** [KB article 941261](http://support.microsoft.com/kb/941261) must be applied before setting up Orchestration Configuration.</span></span>  
  
### <a name="to-configure-orchestration-shapes"></a><span data-ttu-id="90f62-107">配置业务流程形状</span><span class="sxs-lookup"><span data-stu-id="90f62-107">To configure orchestration shapes</span></span>  
  
1.  <span data-ttu-id="90f62-108">业务流程设计视图图面上的 Visual Studio，请单击**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="90f62-108">On the orchestration Design view surface of Visual Studio, click the **ConstructMessage_1** shape.</span></span>  
  
2.  <span data-ttu-id="90f62-109">在**属性**窗口中，单击**消息构造**属性中，选择**DoorbellOutputMessage**从下拉列表，然后按**输入**。</span><span class="sxs-lookup"><span data-stu-id="90f62-109">In the **Properties** window, click the **Messages Constructed** property, select **DoorbellOutputMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="90f62-110">在业务流程设计视图图面中，单击**DoorbellTransform**形状内**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="90f62-110">On the orchestration Design view surface, click the **DoorbellTransform** shape inside of the **ConstructMessage_1** shape.</span></span> <span data-ttu-id="90f62-111">在**属性**窗口中，单击**映射名称**，然后单击属性字段中的省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="90f62-111">In the **Properties** window, click **Map Name**, and then click the ellipsis (…) button in the attribute field.</span></span>  
  
4.  <span data-ttu-id="90f62-112">在转换的配置对话框中，选择**现有映射**。</span><span class="sxs-lookup"><span data-stu-id="90f62-112">In the Transform Configuration dialog box, select **Existing Map**.</span></span> <span data-ttu-id="90f62-113">在**完全限定的映射名称**下拉列表中，单击**BTAHL7_Project.DoorbellMap**。</span><span class="sxs-lookup"><span data-stu-id="90f62-113">In the **Fully Qualified Map Name** drop-down list, click **BTAHL7_Project.DoorbellMap**.</span></span>  
  
5.  <span data-ttu-id="90f62-114">单击**源**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="90f62-114">Click **Source** in the left pane.</span></span>  
  
6.  <span data-ttu-id="90f62-115">单击下的空框中**变量名称**单击**DoorBellInputMessage**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="90f62-115">Click the empty box under **Variable Name** and click **DoorBellInputMessage** from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="90f62-116">单击**目标**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="90f62-116">Click **Destination** in the left pane.</span></span>  
  
8.  <span data-ttu-id="90f62-117">单击下的空框中**变量名称**单击**DoorbellOutputMessage**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="90f62-117">Click the empty box under **Variable Name** and click **DoorbellOutputMessage** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="90f62-118">单击**确定**以保存更改。</span><span class="sxs-lookup"><span data-stu-id="90f62-118">Click **OK** to save changes.</span></span>  
  
10. <span data-ttu-id="90f62-119">在业务流程设计视图图面中，单击**ConstructMessage_2**形状。</span><span class="sxs-lookup"><span data-stu-id="90f62-119">On the orchestration Design view surface, click the **ConstructMessage_2** shape.</span></span>  
  
11. <span data-ttu-id="90f62-120">在**属性**窗口中，单击**消息构造**，选择**DoorbellFinalMessage**从下拉列表，然后按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="90f62-120">In the **Properties** window, click **Messages Constructed**, select **DoorbellFinalMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
12. <span data-ttu-id="90f62-121">在业务流程设计视图图面中，单击**DoorbellFinalTransform**形状内**ConstructMessage_2**形状。</span><span class="sxs-lookup"><span data-stu-id="90f62-121">On the orchestration Design view surface, click the **DoorbellFinalTransform** shape inside of the **ConstructMessage_2** shape.</span></span> <span data-ttu-id="90f62-122">在**属性**窗口中，单击**表达式**，然后单击省略号 （...） 按钮以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="90f62-122">In the **Properties** window, click **Expression**, and then click the ellipsis (…) button to open BizTalk Expression Editor.</span></span>  
  
13. <span data-ttu-id="90f62-123">在 BizTalk 表达式编辑器中，在文本字段中单击，然后粘贴以下文本：</span><span class="sxs-lookup"><span data-stu-id="90f62-123">In BizTalk Expression Editor, click in the text field and paste the following text:</span></span>  
  
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
  
14. <span data-ttu-id="90f62-124">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="90f62-124">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="90f62-125">在"HeaderInfo.LoadXml"表达式中，删除回车和表达式中的空间。</span><span class="sxs-lookup"><span data-stu-id="90f62-125">In the "HeaderInfo.LoadXml" expression, delete the carriage returns and spaces within the expression.</span></span> <span data-ttu-id="90f62-126">"HeaderInfo.LoadXml"语句应在一行上。</span><span class="sxs-lookup"><span data-stu-id="90f62-126">The "HeaderInfo.LoadXml" statement should be on one line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90f62-127">前面的第一个块是文本的硬编码的 XML 标头的示例。</span><span class="sxs-lookup"><span data-stu-id="90f62-127">The first block of the preceding text is an example of a hard-coded XML header.</span></span> <span data-ttu-id="90f62-128">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序需要标头段。</span><span class="sxs-lookup"><span data-stu-id="90f62-128">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a header segment.</span></span> <span data-ttu-id="90f62-129">你可以自定义你的环境的需要根据这些标头值。</span><span class="sxs-lookup"><span data-stu-id="90f62-129">You can customize these header values according to the needs of your environment.</span></span> <span data-ttu-id="90f62-130">前面的文本的第二个块定义在多部分消息中所需的三个消息部分。</span><span class="sxs-lookup"><span data-stu-id="90f62-130">The second block of the preceding text defines the three message parts required in a multipart message.</span></span> <span data-ttu-id="90f62-131">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序需要多部分消息。</span><span class="sxs-lookup"><span data-stu-id="90f62-131">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a multipart message.</span></span> <span data-ttu-id="90f62-132">前面的文本的第三个块包含提升的属性，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序检查 HL7 平面文件消息序列化为 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="90f62-132">The third block of the preceding text contains the promoted properties that the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer examines in order to serialize an XML message into an HL7 flat-file message.</span></span>  
  
 <span data-ttu-id="90f62-133">继续执行[步骤 13： 创建和配置端口](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="90f62-133">Proceed to [Step 13: Create and Configure Ports](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f62-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90f62-134">See Also</span></span>  
 [<span data-ttu-id="90f62-135">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="90f62-135">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)