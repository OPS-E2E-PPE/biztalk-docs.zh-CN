---
title: 步骤 5：创建用于将确认传递至 ADT 系统使用文件适配器的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15b9663f8203a9cf907de76df680eefe069a17ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288083"
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a><span data-ttu-id="94da2-102">步骤 5：创建用于将确认传递至 ADT 系统使用文件适配器的发送端口</span><span class="sxs-lookup"><span data-stu-id="94da2-102">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>
<span data-ttu-id="94da2-103">在此步骤中，创建要生成确认使用文件适配器的发送端口。</span><span class="sxs-lookup"><span data-stu-id="94da2-103">In this step, you create the send port to generate acknowledgments using the File adapter.</span></span>  

### <a name="to-create-the-tutorialsendackadt-send-port"></a><span data-ttu-id="94da2-104">若要创建 Tutorial_sendAck_ADT 发送端口</span><span class="sxs-lookup"><span data-stu-id="94da2-104">To create the Tutorial_sendAck_ADT send port</span></span>  

1. <span data-ttu-id="94da2-105">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，创建\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_ 的快捷键sendAck_ADT 文件夹。</span><span class="sxs-lookup"><span data-stu-id="94da2-105">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, create the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT folder.</span></span>  

2. <span data-ttu-id="94da2-106">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="94da2-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

3. <span data-ttu-id="94da2-107">在发送端口属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94da2-107">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="94da2-108">使用此选项</span><span class="sxs-lookup"><span data-stu-id="94da2-108">Use this</span></span>      |                                <span data-ttu-id="94da2-109">执行的操作</span><span class="sxs-lookup"><span data-stu-id="94da2-109">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="94da2-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="94da2-110">**Name**</span></span>      |                      <span data-ttu-id="94da2-111">类型**Tutorial_sendAck_ADT**。</span><span class="sxs-lookup"><span data-stu-id="94da2-111">Type **Tutorial_sendAck_ADT**.</span></span>                       |
   | <span data-ttu-id="94da2-112">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="94da2-112">**Transport type**</span></span> |                 <span data-ttu-id="94da2-113">选择**文件**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-113">Select **FILE** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="94da2-114">**配置**</span><span class="sxs-lookup"><span data-stu-id="94da2-114">**Configure**</span></span>    | <span data-ttu-id="94da2-115">单击**配置**以打开**File 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="94da2-115">Click **Configure** to open the **File Transport Properties** dialog box.</span></span> |


4. <span data-ttu-id="94da2-116">在 FILE 传输属性对话框中，执行以下操作，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="94da2-116">In the FILE Transport Properties dialog box, do the following and then click **OK**.</span></span>  


   |        <span data-ttu-id="94da2-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="94da2-117">Use this</span></span>        |                                                                     <span data-ttu-id="94da2-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="94da2-118">To do this</span></span>                                                                      |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="94da2-119">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="94da2-119">**Destination folder**</span></span> | <span data-ttu-id="94da2-120">浏览到**\<**<em>驱动器</em>**:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_sendAck_ADT**。</span><span class="sxs-lookup"><span data-stu-id="94da2-120">Browse to **\<**<em>drive</em>**:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_sendAck_ADT**.</span></span> |
   |     <span data-ttu-id="94da2-121">**文件名**</span><span class="sxs-lookup"><span data-stu-id="94da2-121">**File name**</span></span>      |                                   <span data-ttu-id="94da2-122">类型 **%MessageID%.txt** （替换带.txt 扩展名的.xml 扩展名）。</span><span class="sxs-lookup"><span data-stu-id="94da2-122">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>                                    |


5. <span data-ttu-id="94da2-123">在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="94da2-123">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

6. <span data-ttu-id="94da2-124">在左窗格中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="94da2-124">In the left pane, click **Filters**, and then do the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="94da2-125">第一个筛选器意味着您要订阅的确认消息。</span><span class="sxs-lookup"><span data-stu-id="94da2-125">The first filter means that you are subscribing for the acknowledgment message.</span></span> <span data-ttu-id="94da2-126">第二个筛选器意味着您要订阅确认发送到发布服务器 Tutorial_ADTSystem。</span><span class="sxs-lookup"><span data-stu-id="94da2-126">The second filter means that you are subscribing to the acknowledgment that is destined for the publisher Tutorial_ADTSystem.</span></span>  

    <span data-ttu-id="94da2-127">单击**确定**您何时准备好继续。</span><span class="sxs-lookup"><span data-stu-id="94da2-127">Click **OK** when you are ready to continue.</span></span>  


   |          <span data-ttu-id="94da2-128">使用此选项</span><span class="sxs-lookup"><span data-stu-id="94da2-128">Use this</span></span>          |                                            <span data-ttu-id="94da2-129">执行的操作</span><span class="sxs-lookup"><span data-stu-id="94da2-129">To do this</span></span>                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   |        <span data-ttu-id="94da2-130">**属性**</span><span class="sxs-lookup"><span data-stu-id="94da2-130">**Property**</span></span>        | <span data-ttu-id="94da2-131">单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-131">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="94da2-132">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="94da2-132">**Operator**</span></span>        |                              <span data-ttu-id="94da2-133">选择**==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-133">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="94da2-134">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="94da2-134">**Value**</span></span>          |                <span data-ttu-id="94da2-135">类型**<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**。</span><span class="sxs-lookup"><span data-stu-id="94da2-135">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.</span></span>                 |
   |        <span data-ttu-id="94da2-136">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="94da2-136">**Group By**</span></span>        |                              <span data-ttu-id="94da2-137">选择**或**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-137">Select **OR** from the drop-down list.</span></span>                              |
   | <span data-ttu-id="94da2-138">**属性 （第二行）**</span><span class="sxs-lookup"><span data-stu-id="94da2-138">**Property (second line)**</span></span> | <span data-ttu-id="94da2-139">单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-139">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span> |
   |        <span data-ttu-id="94da2-140">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="94da2-140">**Operator**</span></span>        |                              <span data-ttu-id="94da2-141">选择**==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-141">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="94da2-142">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="94da2-142">**Value**</span></span>          |                <span data-ttu-id="94da2-143">类型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>。**</span><span class="sxs-lookup"><span data-stu-id="94da2-143">Type **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**</span></span>                 |
   |        <span data-ttu-id="94da2-144">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="94da2-144">**Group By**</span></span>        |                             <span data-ttu-id="94da2-145">选择**AND**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-145">Select **AND** from the drop-down list.</span></span>                              |
   |        <span data-ttu-id="94da2-146">**属性**</span><span class="sxs-lookup"><span data-stu-id="94da2-146">**Property**</span></span>        |     <span data-ttu-id="94da2-147">在第一个属性，单击空白框中，然后选择**BTAHL7Schemas.MSH5_1**。</span><span class="sxs-lookup"><span data-stu-id="94da2-147">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span>     |
   |        <span data-ttu-id="94da2-148">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="94da2-148">**Operator**</span></span>        |                              <span data-ttu-id="94da2-149">选择**==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="94da2-149">Select **==** from the drop-down list.</span></span>                              |
   |         <span data-ttu-id="94da2-150">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="94da2-150">**Value**</span></span>          |                                   <span data-ttu-id="94da2-151">类型**Tutorial_ADTSystem**。</span><span class="sxs-lookup"><span data-stu-id="94da2-151">Type **Tutorial_ADTSystem**.</span></span>                                   |

   > [!NOTE]
   >  <span data-ttu-id="94da2-152">为发送端口 Tutorial_sendAck_ADT，BTAHL7 将删除对确认在文件存放位置\<*驱动器*\>： 程序 FilesMicrosoft BizTalk <version> HL7SDKEnd 端到端的快捷键TutorialTutorial_sendAck_ADT。</span><span class="sxs-lookup"><span data-stu-id="94da2-152">For the send port Tutorial_sendAck_ADT, BTAHL7 drops the acknowledgments at the file drop location \<*drive*\>:Program FilesMicrosoft BizTalk <version> Accelerator for HL7SDKEnd-to-End TutorialTutorial_sendAck_ADT.</span></span>  

7. <span data-ttu-id="94da2-153">单击**Apply**，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="94da2-153">Click **Apply**, and then click **OK.**</span></span>  

8. <span data-ttu-id="94da2-154">在管理控制台中，单击**发送端口**，右键单击**Tutorial_sendAck_ADT**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="94da2-154">In the Administration Console, click **Send Ports**, right-click **Tutorial_sendAck_ADT**, and then click **Start**.</span></span>  

   <span data-ttu-id="94da2-155">请继续执行[步骤 6:创建发送端口以将 ^ A03 消息至 RX 系统使用文件适配器](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)。</span><span class="sxs-lookup"><span data-stu-id="94da2-155">Proceed to [Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md).</span></span>