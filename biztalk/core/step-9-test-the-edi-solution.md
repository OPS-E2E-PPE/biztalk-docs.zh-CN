---
title: 步骤 9： 测试 EDI 解决方案 |Microsoft Docs
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
ms.openlocfilehash: ab6da406d2de066f9a1a7f4a99576ca9c2fa14d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979670"
---
# <a name="step-9-test-the-edi-solution"></a><span data-ttu-id="bc473-102">步骤 9： 测试 EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="bc473-102">Step 9: Test the EDI Solution</span></span>
<span data-ttu-id="bc473-103">![步骤 9 的 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="bc473-103">![Step 9 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="bc473-104">在本主题中，您将测试入站处理和查看有关处理信息的 EDI 交换状态报告。</span><span class="sxs-lookup"><span data-stu-id="bc473-104">In this topic you test your inbound processing and view the EDI-Interchange Status Report for processing information.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc473-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="bc473-105">Prerequisites</span></span>  
 <span data-ttu-id="bc473-106">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="bc473-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="testing-the-solution"></a><span data-ttu-id="bc473-107">测试解决方案</span><span class="sxs-lookup"><span data-stu-id="bc473-107">Testing the solution</span></span>  
  
1. <span data-ttu-id="bc473-108">在 Windows 资源管理器中，将移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发工具 Tutorial\ProcessEDI_TestLocations。</span><span class="sxs-lookup"><span data-stu-id="bc473-108">In Windows Explorer, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="bc473-109">复制**SamplePO.txt**文件。</span><span class="sxs-lookup"><span data-stu-id="bc473-109">Copy the **SamplePO.txt** file.</span></span>  
  
2. <span data-ttu-id="bc473-110">粘贴**SamplePO.txt**文件到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bc473-110">Paste the **SamplePO.txt** file into the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM folder.</span></span>  
  
3. <span data-ttu-id="bc473-111">将移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bc473-111">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem folder.</span></span> <span data-ttu-id="bc473-112">确认此文件夹中含有一个 txt 输出文件。</span><span class="sxs-lookup"><span data-stu-id="bc473-112">Confirm that the folder contains an output txt file.</span></span>  
  
4. <span data-ttu-id="bc473-113">打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem 中的输出文件，以及 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations 中的 SamplePO.txt 输入文件。</span><span class="sxs-lookup"><span data-stu-id="bc473-113">Open the output file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem and the SamplePO.txt input file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="bc473-114">验证输出消息中的数据相对应的数据在原始**SamplePO.txt**文件。</span><span class="sxs-lookup"><span data-stu-id="bc473-114">Verify that the data in the output message corresponds to the data in the original **SamplePO.txt** file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bc473-115">可以通过在 Visual Studio 中打开 Inbound4010850_to_OrderFile.btm 文件并检查映射，验证输出文件中的数据是否是从输出文件中的数据转换过来的。</span><span class="sxs-lookup"><span data-stu-id="bc473-115">You can verify that the data in the output file has been transformed from the data in the input file by opening the Inbound4010850_to_OrderFile.btm file in Visual Studio, and checking the mappings.</span></span>  
  
5. <span data-ttu-id="bc473-116">将移动到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="bc473-116">Move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 folder.</span></span> <span data-ttu-id="bc473-117">确认该文件夹包含输出 997 确认 txt 文件，且其中 ST01 数据元素是“997”。</span><span class="sxs-lookup"><span data-stu-id="bc473-117">Confirm that the folder contains an output 997 acknowledgment txt file in which the ST01 data element is "997".</span></span>  
  
6. <span data-ttu-id="bc473-118">在控制台树中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="bc473-118">In the console tree of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **BizTalk Group**.</span></span> <span data-ttu-id="bc473-119">在右窗格的底部，单击**EDI 交换和相关 ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="bc473-119">At the bottom of the right pane, click **EDI Interchange and Correlated ACK Status**.</span></span>  
  
7. <span data-ttu-id="bc473-120">查询表达式中的运算符更改**状态**字段**等于**并更改**值**字段**状态**字段**所有**。</span><span class="sxs-lookup"><span data-stu-id="bc473-120">In the query expression, change the operator for the **Status** field to **Equals** and change the **Value** field for the **Status** field to **All**.</span></span> <span data-ttu-id="bc473-121">删除**交换日期时间字段**（选择行并按键盘上的 DELETE）。</span><span class="sxs-lookup"><span data-stu-id="bc473-121">Delete the **Interchange Date Time field** (select the row and press DELETE on the key board).</span></span>  
  
8. <span data-ttu-id="bc473-122">单击**运行查询**。</span><span class="sxs-lookup"><span data-stu-id="bc473-122">Click **Run Query**.</span></span>  
  
9. <span data-ttu-id="bc473-123">验证是否有两条消息显示在状态报告中，一条为从 THEM (Fabrikam) 到 US (OrderSystem) 的接收方向的消息（850 消息），另一条为从 US (OrderSystem) 到 THEM (Fabrikam) 的发送方向的消息（997 确认）。</span><span class="sxs-lookup"><span data-stu-id="bc473-123">Verify that two messages are displayed in the status report, one in the receive direction from THEM (Fabrikam) to US (OrderSystem) (the 850 message), the other in the send direction from the US (OrderSystem) to THEM (Fabrikam) (the 997 acknowledgment).</span></span>  
  
10. <span data-ttu-id="bc473-124">双击从 THEM 到 US 的消息。</span><span class="sxs-lookup"><span data-stu-id="bc473-124">Double-click the message from THEM to US.</span></span> <span data-ttu-id="bc473-125">在中**交换状态和确认详细信息**对话框框中，验证交换的详细信息是否显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="bc473-125">In the **Interchange status and ACK  details** dialog box, verify that details of the interchange are displayed in the right pane.</span></span>  
  
11. <span data-ttu-id="bc473-126">单击**功能确认**。</span><span class="sxs-lookup"><span data-stu-id="bc473-126">Click **Functional ACK(s)**.</span></span> <span data-ttu-id="bc473-127">验证确认的报告详细信息是否显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="bc473-127">Verify that the report details of the acknowledgment are displayed in the right pane.</span></span>  
  
12. <span data-ttu-id="bc473-128">关闭“交换状态和确认详细信息”对话框。</span><span class="sxs-lookup"><span data-stu-id="bc473-128">Close the Interchange status and ack details dialog box.</span></span>  
  
13. <span data-ttu-id="bc473-129">在中**交换 /ACK 状态**窗格中，右键单击从 THEM 到 US 的消息，然后单击**事务集详细信息**。</span><span class="sxs-lookup"><span data-stu-id="bc473-129">In the **Interchange/ACK Status** pane, right-click the message from THEM to US, and then click **Transaction Set Details**.</span></span> <span data-ttu-id="bc473-130">右键单击中的条目**查询结果**窗格中，，然后单击**查看事务集内容**。</span><span class="sxs-lookup"><span data-stu-id="bc473-130">Right-click the entry in the **Query results** pane, and then click **View Transaction Set Content**.</span></span> <span data-ttu-id="bc473-131">验证事务集数据是否显示在**消息的详细信息**对话框。</span><span class="sxs-lookup"><span data-stu-id="bc473-131">Verify that the transaction set data is displayed in the **Message Details** dialog box.</span></span> <span data-ttu-id="bc473-132">在 Windows 资源管理器中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\ProcessEDI_TestLocations 中的 SamplePO.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="bc473-132">In Windows Explorer, open the SamplePO.txt file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations.</span></span> <span data-ttu-id="bc473-133">验证事务集显示在**消息的详细信息**对话框输入消息，且没有交换和组标头和尾部中是相同的。</span><span class="sxs-lookup"><span data-stu-id="bc473-133">Verify that the transaction set displayed in the **Message Details** dialog box is the same as that in the input message, without the interchange and group headers and trailers.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bc473-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bc473-134">Next Steps</span></span>  
 <span data-ttu-id="bc473-135">您已完成 EDI 接口开发人员教程。</span><span class="sxs-lookup"><span data-stu-id="bc473-135">You have completed the EDI Interface Developer Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc473-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc473-136">See Also</span></span>  
 <span data-ttu-id="bc473-137">[教程 2: EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="bc473-137">[Tutorial 2: EDI Interface Developer Tutorial](../core/tutorial-2-edi-interface-developer-tutorial.md) </span></span>  
 [<span data-ttu-id="bc473-138">步骤 1：EDI 接口开发人员教程的准备工作</span><span class="sxs-lookup"><span data-stu-id="bc473-138">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)