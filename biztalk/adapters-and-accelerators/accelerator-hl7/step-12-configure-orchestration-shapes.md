---
title: 步骤 12： 配置业务流程形状 |Microsoft Docs
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
ms.openlocfilehash: d269fa177e7c0da857fb903cef5013f434554d17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991470"
---
# <a name="step-12-configure-orchestration-shapes"></a><span data-ttu-id="540d7-102">步骤 12： 配置业务流程形状</span><span class="sxs-lookup"><span data-stu-id="540d7-102">Step 12: Configure Orchestration Shapes</span></span>
<span data-ttu-id="540d7-103">在此步骤中，若要删除的配置不完全的智能标记完成业务流程形状的配置。</span><span class="sxs-lookup"><span data-stu-id="540d7-103">In this step, you complete the configuration of the orchestration shapes in order to remove the insufficient configuration smart tags.</span></span> <span data-ttu-id="540d7-104">您指定**DoorbellOutputMessage**作为输出的第一个转换过程中，指定**DoorbellMap.btm**作为该过程中使用的映射。</span><span class="sxs-lookup"><span data-stu-id="540d7-104">You designate **DoorbellOutputMessage** as the output of the first transform process, designating **DoorbellMap.btm** as the map used in that process.</span></span> <span data-ttu-id="540d7-105">然后指定**DoorbellFinalMessage**作为第二个输出转换过程中，并添加使其更加丰富的消息的其他字段数据的表达式。</span><span class="sxs-lookup"><span data-stu-id="540d7-105">You then designate **DoorbellFinalMessage** as the output of the second transform process, and add the expression that enriches the message with additional field data.</span></span>  
  
 <span data-ttu-id="540d7-106">**先决条件：** [知识库文章 941261](http://support.microsoft.com/kb/941261)必须设置业务流程配置之前应用。</span><span class="sxs-lookup"><span data-stu-id="540d7-106">**Prerequisite:** [KB article 941261](http://support.microsoft.com/kb/941261) must be applied before setting up Orchestration Configuration.</span></span>  
  
### <a name="to-configure-orchestration-shapes"></a><span data-ttu-id="540d7-107">若要配置业务流程形状</span><span class="sxs-lookup"><span data-stu-id="540d7-107">To configure orchestration shapes</span></span>  
  
1. <span data-ttu-id="540d7-108">在业务流程视图的设计图面 Visual Studio，单击**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="540d7-108">On the orchestration Design view surface of Visual Studio, click the **ConstructMessage_1** shape.</span></span>  
  
2. <span data-ttu-id="540d7-109">在中**属性**窗口中，单击**构造的消息**属性中，选择**DoorbellOutputMessage**从下拉列表，再按**输入**。</span><span class="sxs-lookup"><span data-stu-id="540d7-109">In the **Properties** window, click the **Messages Constructed** property, select **DoorbellOutputMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
3. <span data-ttu-id="540d7-110">在业务流程设计视图图面上，单击**DoorbellTransform**形状的内部**ConstructMessage_1**形状。</span><span class="sxs-lookup"><span data-stu-id="540d7-110">On the orchestration Design view surface, click the **DoorbellTransform** shape inside of the **ConstructMessage_1** shape.</span></span> <span data-ttu-id="540d7-111">在中**属性**窗口中，单击**映射名称**，然后单击属性字段中的省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="540d7-111">In the **Properties** window, click **Map Name**, and then click the ellipsis (…) button in the attribute field.</span></span>  
  
4. <span data-ttu-id="540d7-112">在转换配置对话框中，选择**现有的映射**。</span><span class="sxs-lookup"><span data-stu-id="540d7-112">In the Transform Configuration dialog box, select **Existing Map**.</span></span> <span data-ttu-id="540d7-113">在中**完全限定的映射名称**下拉列表中，单击**BTAHL7_Project.DoorbellMap**。</span><span class="sxs-lookup"><span data-stu-id="540d7-113">In the **Fully Qualified Map Name** drop-down list, click **BTAHL7_Project.DoorbellMap**.</span></span>  
  
5. <span data-ttu-id="540d7-114">单击**源**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="540d7-114">Click **Source** in the left pane.</span></span>  
  
6. <span data-ttu-id="540d7-115">单击下的空框**变量名**然后单击**DoorBellInputMessage**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="540d7-115">Click the empty box under **Variable Name** and click **DoorBellInputMessage** from the drop-down list.</span></span>  
  
7. <span data-ttu-id="540d7-116">单击**目标**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="540d7-116">Click **Destination** in the left pane.</span></span>  
  
8. <span data-ttu-id="540d7-117">单击下的空框**变量名**然后单击**DoorbellOutputMessage**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="540d7-117">Click the empty box under **Variable Name** and click **DoorbellOutputMessage** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="540d7-118">单击**确定**以保存更改。</span><span class="sxs-lookup"><span data-stu-id="540d7-118">Click **OK** to save changes.</span></span>  
  
10. <span data-ttu-id="540d7-119">在业务流程设计视图图面上，单击**ConstructMessage_2**形状。</span><span class="sxs-lookup"><span data-stu-id="540d7-119">On the orchestration Design view surface, click the **ConstructMessage_2** shape.</span></span>  
  
11. <span data-ttu-id="540d7-120">在中**属性**窗口中，单击**构造的消息**，选择**DoorbellFinalMessage**从下拉列表，再按**Enter**.</span><span class="sxs-lookup"><span data-stu-id="540d7-120">In the **Properties** window, click **Messages Constructed**, select **DoorbellFinalMessage** from the drop-down list, and then press **Enter**.</span></span>  
  
12. <span data-ttu-id="540d7-121">在业务流程设计视图图面上，单击**DoorbellFinalTransform**形状的内部**ConstructMessage_2**形状。</span><span class="sxs-lookup"><span data-stu-id="540d7-121">On the orchestration Design view surface, click the **DoorbellFinalTransform** shape inside of the **ConstructMessage_2** shape.</span></span> <span data-ttu-id="540d7-122">在中**属性**窗口中，单击**表达式**，然后单击省略号 （...） 按钮以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="540d7-122">In the **Properties** window, click **Expression**, and then click the ellipsis (…) button to open BizTalk Expression Editor.</span></span>  
  
13. <span data-ttu-id="540d7-123">在 BizTalk 表达式编辑器中，在文本字段中单击，并粘贴以下文本：</span><span class="sxs-lookup"><span data-stu-id="540d7-123">In BizTalk Expression Editor, click in the text field and paste the following text:</span></span>  
  
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
  
14. <span data-ttu-id="540d7-124">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="540d7-124">Click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="540d7-125">在"HeaderInfo.LoadXml"表达式中，删除回车符和表达式中的空格。</span><span class="sxs-lookup"><span data-stu-id="540d7-125">In the "HeaderInfo.LoadXml" expression, delete the carriage returns and spaces within the expression.</span></span> <span data-ttu-id="540d7-126">"HeaderInfo.LoadXml"语句应在同一行。</span><span class="sxs-lookup"><span data-stu-id="540d7-126">The "HeaderInfo.LoadXml" statement should be on one line.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="540d7-127">前面的第一个块是文本的硬编码的 XML 标头的示例。</span><span class="sxs-lookup"><span data-stu-id="540d7-127">The first block of the preceding text is an example of a hard-coded XML header.</span></span> <span data-ttu-id="540d7-128">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序需要标头段。</span><span class="sxs-lookup"><span data-stu-id="540d7-128">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a header segment.</span></span> <span data-ttu-id="540d7-129">您可以自定义这些标头值根据您的环境需求。</span><span class="sxs-lookup"><span data-stu-id="540d7-129">You can customize these header values according to the needs of your environment.</span></span> <span data-ttu-id="540d7-130">前面的文本的第二个块定义多部分消息中所需的三个消息部分。</span><span class="sxs-lookup"><span data-stu-id="540d7-130">The second block of the preceding text defines the three message parts required in a multipart message.</span></span> <span data-ttu-id="540d7-131">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序需要多部分消息。</span><span class="sxs-lookup"><span data-stu-id="540d7-131">The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer requires a multipart message.</span></span> <span data-ttu-id="540d7-132">前面的文本的第三个块包含升级的属性的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 平面文件消息序列化为 XML 消息序列化程序检查。</span><span class="sxs-lookup"><span data-stu-id="540d7-132">The third block of the preceding text contains the promoted properties that the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer examines in order to serialize an XML message into an HL7 flat-file message.</span></span>  
  
    <span data-ttu-id="540d7-133">请继续执行[步骤 13： 创建和配置端口](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="540d7-133">Proceed to [Step 13: Create and Configure Ports](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="540d7-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="540d7-134">See Also</span></span>  
 [<span data-ttu-id="540d7-135">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="540d7-135">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)