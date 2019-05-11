---
title: 扩展的编码支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41275124cdf0db7329751c5973bbde0685bd49ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255294"
---
# <a name="extended-encoding-support"></a><span data-ttu-id="af4ed-102">扩展的编码支持</span><span class="sxs-lookup"><span data-stu-id="af4ed-102">Extended Encoding Support</span></span>
<span data-ttu-id="af4ed-103">默认情况下，接收 HL7 管道，BTAHL72X，仅支持 ASCII 编码。</span><span class="sxs-lookup"><span data-stu-id="af4ed-103">By default, the HL7 receive pipeline, BTAHL72X, only supports ASCII encoding.</span></span> <span data-ttu-id="af4ed-104">这意味着，具有等效值大于 127 将替换为输入消息中的任何字符"？"。</span><span class="sxs-lookup"><span data-stu-id="af4ed-104">This means that any characters in an input message with an equivalent value greater than 127 are replaced with "?".</span></span> <span data-ttu-id="af4ed-105">这是因为不表示 ASCII 字符集中具有等效值大于 127 个字符。</span><span class="sxs-lookup"><span data-stu-id="af4ed-105">This is because characters with an equivalent value greater than 127 are not represented in the ASCII character set.</span></span>  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] <span data-ttu-id="af4ed-106">为两个新编码提供支持：</span><span class="sxs-lookup"><span data-stu-id="af4ed-106">provides support for two new encodings:</span></span>  
  
- <span data-ttu-id="af4ed-107">西欧语</span><span class="sxs-lookup"><span data-stu-id="af4ed-107">Western European</span></span>  
  
- <span data-ttu-id="af4ed-108">UTF-8</span><span class="sxs-lookup"><span data-stu-id="af4ed-108">UTF-8</span></span>  
  
  <span data-ttu-id="af4ed-109">创建并生成一个自定义管道组件以实现扩展编码的支持。</span><span class="sxs-lookup"><span data-stu-id="af4ed-109">You create and build a custom pipeline component to implement extended encoding support.</span></span> <span data-ttu-id="af4ed-110">自定义管道组件使用 BTAHL7 2.X 拆装器。</span><span class="sxs-lookup"><span data-stu-id="af4ed-110">The custom pipeline component uses the BTAHL7 2.X Disassembler.</span></span> <span data-ttu-id="af4ed-111">创建使用自定义管道来处理消息的接收位置。</span><span class="sxs-lookup"><span data-stu-id="af4ed-111">You create a receive location that uses the custom pipeline to process messages.</span></span> <span data-ttu-id="af4ed-112">若要测试的接收位置和自定义管道，您可以创建使用 BTAHL7 2.XSendPipeline 的发送端口。</span><span class="sxs-lookup"><span data-stu-id="af4ed-112">To test the receive location and custom pipeline, you create a send port that uses the BTAHL7 2.XSendPipeline.</span></span>  
  
### <a name="to-create-a-custom-pipeline"></a><span data-ttu-id="af4ed-113">若要创建自定义管道</span><span class="sxs-lookup"><span data-stu-id="af4ed-113">To create a custom pipeline</span></span>  
  
1. <span data-ttu-id="af4ed-114">在中[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]，添加一个新**空的 BizTalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-114">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], add a new **Empty BizTalk Server Project**.</span></span>  
  
2. <span data-ttu-id="af4ed-115">在解决方案资源管理器，右键单击新项目中，单击**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-115">In Solution Explorer, right-click the new project, click **Add**, and then click **New Item**.</span></span>  
  
3. <span data-ttu-id="af4ed-116">在中**添加新项**对话框框中，添加一个新**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-116">In the **Add New Item** dialog box, add a new **Receive Pipeline**.</span></span>  
  
4. <span data-ttu-id="af4ed-117">从管道工具箱拖动**BTAHL7 2.X 反汇编程序**到管道编辑器并将其拖到放置**拆装**阶段**拖至此处**目标。</span><span class="sxs-lookup"><span data-stu-id="af4ed-117">From the pipeline toolbox, drag the **BTAHL7 2.X Disassembler** to the pipeline editor and drop it onto the **Disassemble** stage **Drop Here** target.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="af4ed-118">如果 BTAHL7 2.7 拆装器不在工具箱中，在工具箱中，右键单击，然后单击**选择项**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-118">If the BTAHL7 2.7 Disassembler is not in the toolbox, right-click in the toolbox, and click **Choose Items**.</span></span> <span data-ttu-id="af4ed-119">在中**选择工具箱项**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTAHL7 2.X 拆装器**复选框，然后依次**确定**.</span><span class="sxs-lookup"><span data-stu-id="af4ed-119">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Component** tab, select the **BTAHL7 2.X Disassembler** check box, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="af4ed-120">中的属性窗格**BTAHL7 2.X 反汇编程序**，从**编码字符集**下拉列表中，选择**西欧语言**或**UTF8**编码。</span><span class="sxs-lookup"><span data-stu-id="af4ed-120">In the Properties pane for the **BTAHL7 2.X Disassembler**, from the **Encoding charset** drop-down list, select **Western European** or **UTF8** encoding.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="af4ed-121">HL7 仅支持 ASCII （默认值）、 西欧和 UTF8 编码。</span><span class="sxs-lookup"><span data-stu-id="af4ed-121">HL7 only supports ASCII (the default), Western European, and UTF8 encoding.</span></span> <span data-ttu-id="af4ed-122">不要选择其他编码选项，因为 HL7 不支持它们。</span><span class="sxs-lookup"><span data-stu-id="af4ed-122">Do not select the other encoding options because HL7 does not support them.</span></span>  
  
6. <span data-ttu-id="af4ed-123">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="af4ed-123">On the **File** menu, click **Save All**.</span></span>  
  
7. <span data-ttu-id="af4ed-124">部署项目。</span><span class="sxs-lookup"><span data-stu-id="af4ed-124">Deploy the project.</span></span>  
  
    <span data-ttu-id="af4ed-125">创建新接收位置以继续。</span><span class="sxs-lookup"><span data-stu-id="af4ed-125">Create a new receive location to continue.</span></span>  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a><span data-ttu-id="af4ed-126">若要创建使用自定义管道的接收位置</span><span class="sxs-lookup"><span data-stu-id="af4ed-126">To create a receive location that uses the custom pipeline</span></span>  
  
1. <span data-ttu-id="af4ed-127">上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-127">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="af4ed-128">在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定为管道程序集 (默认情况下**BizTalk Application 1**)，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-128">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
3. <span data-ttu-id="af4ed-129">在中**接收位置属性**对话框中**接收管道**下拉列表中，选择的自定义名称你创建的管道。</span><span class="sxs-lookup"><span data-stu-id="af4ed-129">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, select the name of the custom pipeline you created.</span></span> <span data-ttu-id="af4ed-130">(这是自定义管道对象，不 BTAHL7 名称 2 倍的管道。)</span><span class="sxs-lookup"><span data-stu-id="af4ed-130">(This is the name of the custom pipeline object, not the BTAHL7 2X pipeline.)</span></span>  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="af4ed-131">若要创建用于测试的接收位置和管道的发送端口</span><span class="sxs-lookup"><span data-stu-id="af4ed-131">To create a send port to test the receive location and pipeline</span></span>  
  
1. <span data-ttu-id="af4ed-132">上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-132">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="af4ed-133">在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定为管道程序集 (默认情况下**BizTalk Application 1**)，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-133">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3. <span data-ttu-id="af4ed-134">在中**发送端口属性**对话框中**发送管道**下拉列表中，选择**BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="af4ed-134">In the **Send Port Properties** dialog box, in the **Send pipeline** drop-down list, select **BTAHL72XSendPipeline**.</span></span>  
  
### <a name="to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="af4ed-135">若要测试的接收位置和管道</span><span class="sxs-lookup"><span data-stu-id="af4ed-135">To test the receive location and pipeline</span></span>  
  
-   <span data-ttu-id="af4ed-136">删除包含特殊字符和保存具有相同的编码到指定接收位置中的位置指定自定义管道中的文件。</span><span class="sxs-lookup"><span data-stu-id="af4ed-136">Drop a file containing special characters and saved with the same encoding you specified in the custom pipeline into the location designated in the receive location.</span></span> <span data-ttu-id="af4ed-137">输出位置上的文件应保留的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="af4ed-137">The file at the output location should preserve the special characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af4ed-138">如果你尝试使用不受支持编码将文件处理 （请记住，支持仅 ASCII、 西欧和 UTF8），并出现错误 ID 在应用程序事件查看器中记录错误：5633.</span><span class="sxs-lookup"><span data-stu-id="af4ed-138">If you attempt to process a file that uses a non-supported encoding (remember that only ASCII, Western European, and UTF8 are supported), an error is logged in the Application Event Viewer with error ID: 5633.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af4ed-139">如果要测试配置为 UTF8 编码的自定义管道，您应将字节顺序标记 (BOM) 字符附加到要传递的消息。</span><span class="sxs-lookup"><span data-stu-id="af4ed-139">If you are testing a custom pipeline configured for UTF8 encoding, you should attach Byte Order Mark (BOM) characters to the message you are passing.</span></span> <span data-ttu-id="af4ed-140">如果要测试配置为西欧语言编码的自定义管道，不附加 BOM 字符。</span><span class="sxs-lookup"><span data-stu-id="af4ed-140">If you are testing a custom pipeline configured for Western European encoding, do not attach BOM characters.</span></span>