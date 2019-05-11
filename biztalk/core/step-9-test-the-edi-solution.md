---
title: 步骤 9：测试 EDI 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a44e0f-496c-462f-bf03-1c2f842d13b6
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d07bc0d28bf7d983a70c2f5ec7ee5e0329da714
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244221"
---
# <a name="step-9-test-the-edi-solution"></a><span data-ttu-id="16be9-102">步骤 9：测试 EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="16be9-102">Step 9: Test the EDI Solution</span></span>
<span data-ttu-id="16be9-103">![步骤 9 的 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="16be9-103">![Step 9 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="16be9-104">在本主题将测试入站的处理和查看的处理信息的 EDI 交换状态报告。</span><span class="sxs-lookup"><span data-stu-id="16be9-104">In this topic you test your inbound processing and view the EDI-Interchange Status Report for processing information.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="16be9-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="16be9-105">Prerequisites</span></span>  
 <span data-ttu-id="16be9-106">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="16be9-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="testing-the-solution"></a><span data-ttu-id="16be9-107">测试解决方案</span><span class="sxs-lookup"><span data-stu-id="16be9-107">Testing the solution</span></span>  
  
1. <span data-ttu-id="16be9-108">在 Windows 资源管理器，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations。</span><span class="sxs-lookup"><span data-stu-id="16be9-108">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="16be9-109">复制**SamplePO.txt**文件。</span><span class="sxs-lookup"><span data-stu-id="16be9-109">Copy the **SamplePO.txt** file.</span></span>  
  
2. <span data-ttu-id="16be9-110">粘贴**SamplePO.txt**文件到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM 文件夹。</span><span class="sxs-lookup"><span data-stu-id="16be9-110">Paste the **SamplePO.txt** file into the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM folder.</span></span>  
  
3. <span data-ttu-id="16be9-111">将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 文件夹。</span><span class="sxs-lookup"><span data-stu-id="16be9-111">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem folder.</span></span> <span data-ttu-id="16be9-112">确认文件夹中含有一个 txt 输出文件。</span><span class="sxs-lookup"><span data-stu-id="16be9-112">Confirm that the folder contains an output txt file.</span></span>  
  
4. <span data-ttu-id="16be9-113">打开输出文件中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 和中的 SamplePO.txt 输入的文件[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations。</span><span class="sxs-lookup"><span data-stu-id="16be9-113">Open the output file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem and the SamplePO.txt input file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="16be9-114">验证输出消息中的数据相对应的数据在原始**SamplePO.txt**文件。</span><span class="sxs-lookup"><span data-stu-id="16be9-114">Verify that the data in the output message corresponds to the data in the original **SamplePO.txt** file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="16be9-115">你可以验证，输出文件中的数据已从输入文件中的数据转换通过在 Visual Studio 中打开 Inbound4010850_to_OrderFile.btm 文件并检查映射。</span><span class="sxs-lookup"><span data-stu-id="16be9-115">You can verify that the data in the output file has been transformed from the data in the input file by opening the Inbound4010850_to_OrderFile.btm file in Visual Studio, and checking the mappings.</span></span>  
  
5. <span data-ttu-id="16be9-116">将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 文件夹。</span><span class="sxs-lookup"><span data-stu-id="16be9-116">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 folder.</span></span> <span data-ttu-id="16be9-117">确认该文件夹包含输出 997 确认 txt 文件，在其中 ST01 数据元素是"997"。</span><span class="sxs-lookup"><span data-stu-id="16be9-117">Confirm that the folder contains an output 997 acknowledgment txt file in which the ST01 data element is "997".</span></span>  
  
6. <span data-ttu-id="16be9-118">在控制台树中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="16be9-118">In the console tree of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **BizTalk Group**.</span></span> <span data-ttu-id="16be9-119">在右窗格的底部，单击**EDI 交换和相关 ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="16be9-119">At the bottom of the right pane, click **EDI Interchange and Correlated ACK Status**.</span></span>  
  
7. <span data-ttu-id="16be9-120">查询表达式中的运算符更改**状态**字段**等于**并更改**值**字段**状态**字段**所有**。</span><span class="sxs-lookup"><span data-stu-id="16be9-120">In the query expression, change the operator for the **Status** field to **Equals** and change the **Value** field for the **Status** field to **All**.</span></span> <span data-ttu-id="16be9-121">删除**交换日期时间字段**（选择行并按键盘上的 DELETE）。</span><span class="sxs-lookup"><span data-stu-id="16be9-121">Delete the **Interchange Date Time field** (select the row and press DELETE on the key board).</span></span>  
  
8. <span data-ttu-id="16be9-122">单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="16be9-122">Click **Run Query**.</span></span>  
  
9. <span data-ttu-id="16be9-123">验证两个消息显示在状态报告中，从 THEM (Fabrikam) 到 US (OrderSystem) （850 消息），另一种从 US (OrderSystem) 到 THEM (Fabrikam) （997 确认） 的发送方向接收方向的其中一个。</span><span class="sxs-lookup"><span data-stu-id="16be9-123">Verify that two messages are displayed in the status report, one in the receive direction from THEM (Fabrikam) to US (OrderSystem) (the 850 message), the other in the send direction from the US (OrderSystem) to THEM (Fabrikam) (the 997 acknowledgment).</span></span>  
  
10. <span data-ttu-id="16be9-124">双击从 THEM 到 US 的消息。</span><span class="sxs-lookup"><span data-stu-id="16be9-124">Double-click the message from THEM to US.</span></span> <span data-ttu-id="16be9-125">在中**交换状态和确认详细信息**对话框框中，验证交换的详细信息是否显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="16be9-125">In the **Interchange status and ACK  details** dialog box, verify that details of the interchange are displayed in the right pane.</span></span>  
  
11. <span data-ttu-id="16be9-126">单击**功能确认**。</span><span class="sxs-lookup"><span data-stu-id="16be9-126">Click **Functional ACK(s)**.</span></span> <span data-ttu-id="16be9-127">验证确认的报告详细信息显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="16be9-127">Verify that the report details of the acknowledgment are displayed in the right pane.</span></span>  
  
12. <span data-ttu-id="16be9-128">关闭交换状态和确认详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="16be9-128">Close the Interchange status and ack details dialog box.</span></span>  
  
13. <span data-ttu-id="16be9-129">在中**交换 /ACK 状态**窗格中，右键单击从 THEM 到 US 的消息，然后单击**事务集详细信息**。</span><span class="sxs-lookup"><span data-stu-id="16be9-129">In the **Interchange/ACK Status** pane, right-click the message from THEM to US, and then click **Transaction Set Details**.</span></span> <span data-ttu-id="16be9-130">右键单击中的条目**查询结果**窗格中，，然后单击**查看事务集内容**。</span><span class="sxs-lookup"><span data-stu-id="16be9-130">Right-click the entry in the **Query results** pane, and then click **View Transaction Set Content**.</span></span> <span data-ttu-id="16be9-131">验证事务集数据是否显示在**消息的详细信息**对话框。</span><span class="sxs-lookup"><span data-stu-id="16be9-131">Verify that the transaction set data is displayed in the **Message Details** dialog box.</span></span> <span data-ttu-id="16be9-132">在 Windows 资源管理器中打开中的 SamplePO.txt 文件[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations。</span><span class="sxs-lookup"><span data-stu-id="16be9-132">In Windows Explorer, open the SamplePO.txt file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="16be9-133">验证事务集显示在**消息的详细信息**对话框输入消息，且没有交换和组标头和尾部中是相同的。</span><span class="sxs-lookup"><span data-stu-id="16be9-133">Verify that the transaction set displayed in the **Message Details** dialog box is the same as that in the input message, without the interchange and group headers and trailers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="16be9-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="16be9-134">Next Steps</span></span>  
 <span data-ttu-id="16be9-135">已完成 EDI 接口开发人员教程。</span><span class="sxs-lookup"><span data-stu-id="16be9-135">You have completed the EDI Interface Developer Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16be9-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="16be9-136">See Also</span></span>  
 <span data-ttu-id="16be9-137">[教程 2：EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="16be9-137">[Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md) </span></span>  
 [<span data-ttu-id="16be9-138">步骤 1：EDI 接口开发人员教程的准备工作</span><span class="sxs-lookup"><span data-stu-id="16be9-138">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)