---
title: "扩展编码支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a40fa6-d0da-416e-97fb-675ddde3f005
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e36c3baff4ac33f2878295791bb3f6615c1b25d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="extended-encoding-support"></a><span data-ttu-id="d8b85-102">扩展编码的支持</span><span class="sxs-lookup"><span data-stu-id="d8b85-102">Extended Encoding Support</span></span>
<span data-ttu-id="d8b85-103">默认情况下，HL7 接收管道，BTAHL72X，仅支持 ASCII 编码。</span><span class="sxs-lookup"><span data-stu-id="d8b85-103">By default, the HL7 receive pipeline, BTAHL72X, only supports ASCII encoding.</span></span> <span data-ttu-id="d8b85-104">这意味着，具有等效值大于 127 都将替换输入消息中的任何字符"？"。</span><span class="sxs-lookup"><span data-stu-id="d8b85-104">This means that any characters in an input message with an equivalent value greater than 127 are replaced with "?".</span></span> <span data-ttu-id="d8b85-105">这是因为在 ASCII 字符集中未表示具有等效值大于 127 个字符。</span><span class="sxs-lookup"><span data-stu-id="d8b85-105">This is because characters with an equivalent value greater than 127 are not represented in the ASCII character set.</span></span>  
  
 [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]<span data-ttu-id="d8b85-106">为这两个新的编码提供支持：</span><span class="sxs-lookup"><span data-stu-id="d8b85-106"> provides support for two new encodings:</span></span>  
  
-   <span data-ttu-id="d8b85-107">西欧语言</span><span class="sxs-lookup"><span data-stu-id="d8b85-107">Western European</span></span>  
  
-   <span data-ttu-id="d8b85-108">UTF-8</span><span class="sxs-lookup"><span data-stu-id="d8b85-108">UTF-8</span></span>  
  
 <span data-ttu-id="d8b85-109">创建并生成要实现扩展的编码支持的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="d8b85-109">You create and build a custom pipeline component to implement extended encoding support.</span></span> <span data-ttu-id="d8b85-110">自定义管道组件使用 BTAHL7 2.X 反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="d8b85-110">The custom pipeline component uses the BTAHL7 2.X Disassembler.</span></span> <span data-ttu-id="d8b85-111">创建使用自定义管道处理消息的接收位置。</span><span class="sxs-lookup"><span data-stu-id="d8b85-111">You create a receive location that uses the custom pipeline to process messages.</span></span> <span data-ttu-id="d8b85-112">若要测试的接收位置和自定义管道，你可以创建使用 BTAHL7 2.XSendPipeline 发送端口。</span><span class="sxs-lookup"><span data-stu-id="d8b85-112">To test the receive location and custom pipeline, you create a send port that uses the BTAHL7 2.XSendPipeline.</span></span>  
  
### <a name="to-create-a-custom-pipeline"></a><span data-ttu-id="d8b85-113">若要创建的自定义管道</span><span class="sxs-lookup"><span data-stu-id="d8b85-113">To create a custom pipeline</span></span>  
  
1.  <span data-ttu-id="d8b85-114">在[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]，添加新**空 BizTalk 服务器项目**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-114">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], add a new **Empty BizTalk Server Project**.</span></span>  
  
2.  <span data-ttu-id="d8b85-115">在解决方案资源管理器，右键单击新项目，单击**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-115">In Solution Explorer, right-click the new project, click **Add**, and then click **New Item**.</span></span>  
  
3.  <span data-ttu-id="d8b85-116">在**添加新项**对话框框中，添加一个新**接收管道**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-116">In the **Add New Item** dialog box, add a new **Receive Pipeline**.</span></span>  
  
4.  <span data-ttu-id="d8b85-117">从管道工具箱中，将**BTAHL7 2.X 反汇编程序**到管道编辑器拖放到**拆卸**阶段**拖至此处**目标。</span><span class="sxs-lookup"><span data-stu-id="d8b85-117">From the pipeline toolbox, drag the **BTAHL7 2.X Disassembler** to the pipeline editor and drop it onto the **Disassemble** stage **Drop Here** target.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8b85-118">如果 BTAHL7 2.7 反汇编程序不在工具箱中，在工具箱中，右键单击，然后单击**选择项**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-118">If the BTAHL7 2.7 Disassembler is not in the toolbox, right-click in the toolbox, and click **Choose Items**.</span></span> <span data-ttu-id="d8b85-119">在**选择工具箱项**对话框中，在**BizTalk 管道组件**选项卡上，选择**BTAHL7 2.X 反汇编程序**复选框，并依次**确定**.</span><span class="sxs-lookup"><span data-stu-id="d8b85-119">In the **Choose Toolbox Items** dialog box, on the **BizTalk Pipeline Component** tab, select the **BTAHL7 2.X Disassembler** check box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d8b85-120">在为属性窗格中**BTAHL7 2.X 反汇编程序**，从**编码 charset**下拉列表中，选择**西欧**或**UTF8**编码。</span><span class="sxs-lookup"><span data-stu-id="d8b85-120">In the Properties pane for the **BTAHL7 2.X Disassembler**, from the **Encoding charset** drop-down list, select **Western European** or **UTF8** encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8b85-121">HL7 仅支持 ASCII （默认）、 西欧，和 UTF8 编码。</span><span class="sxs-lookup"><span data-stu-id="d8b85-121">HL7 only supports ASCII (the default), Western European, and UTF8 encoding.</span></span> <span data-ttu-id="d8b85-122">由于 HL7 不支持它们，则无法选择其他的编码选项。</span><span class="sxs-lookup"><span data-stu-id="d8b85-122">Do not select the other encoding options because HL7 does not support them.</span></span>  
  
6.  <span data-ttu-id="d8b85-123">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="d8b85-123">On the **File** menu, click **Save All**.</span></span>  
  
7.  <span data-ttu-id="d8b85-124">部署该项目。</span><span class="sxs-lookup"><span data-stu-id="d8b85-124">Deploy the project.</span></span>  
  
     <span data-ttu-id="d8b85-125">创建一个新接收位置以继续。</span><span class="sxs-lookup"><span data-stu-id="d8b85-125">Create a new receive location to continue.</span></span>  
  
### <a name="to-create-a-receive-location-that-uses-the-custom-pipeline"></a><span data-ttu-id="d8b85-126">若要创建使用自定义管道接收位置</span><span class="sxs-lookup"><span data-stu-id="d8b85-126">To create a receive location that uses the custom pipeline</span></span>  
  
1.  <span data-ttu-id="d8b85-127">上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-127">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d8b85-128">在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定管道程序集 (默认情况下， **BizTalk 应用程序 1**)，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-128">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
3.  <span data-ttu-id="d8b85-129">在**接收位置属性**对话框中，在**接收管道**下拉列表中，选择自定义的名称管道你创建。</span><span class="sxs-lookup"><span data-stu-id="d8b85-129">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, select the name of the custom pipeline you created.</span></span> <span data-ttu-id="d8b85-130">(这是自定义管道对象，不 BTAHL7 名称 2 X 管道。)</span><span class="sxs-lookup"><span data-stu-id="d8b85-130">(This is the name of the custom pipeline object, not the BTAHL7 2X pipeline.)</span></span>  
  
### <a name="to-create-a-send-port-to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="d8b85-131">若要创建要测试的接收位置和管道发送端口</span><span class="sxs-lookup"><span data-stu-id="d8b85-131">To create a send port to test the receive location and pipeline</span></span>  
  
1.  <span data-ttu-id="d8b85-132">上**启动**菜单上，单击**程序**，指向[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-132">On the **Start** menu, click **Programs**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d8b85-133">在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，展开应用程序指定管道程序集 (默认情况下， **BizTalk 应用程序 1**)，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-133">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand the application you designated for your pipeline assembly (by default, **BizTalk Application 1**), right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="d8b85-134">在**发送端口属性**对话框中，在**发送管道**下拉列表中，选择**BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="d8b85-134">In the **Send Port Properties** dialog box, in the **Send pipeline** drop-down list, select **BTAHL72XSendPipeline**.</span></span>  
  
### <a name="to-test-the-receive-location-and-pipeline"></a><span data-ttu-id="d8b85-135">若要测试的接收位置和管道</span><span class="sxs-lookup"><span data-stu-id="d8b85-135">To test the receive location and pipeline</span></span>  
  
-   <span data-ttu-id="d8b85-136">删除包含特殊字符，且使用相同的编码到在接收位置中指定的位置指定自定义管道中保存的文件。</span><span class="sxs-lookup"><span data-stu-id="d8b85-136">Drop a file containing special characters and saved with the same encoding you specified in the custom pipeline into the location designated in the receive location.</span></span> <span data-ttu-id="d8b85-137">输出位置上的文件应保留的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="d8b85-137">The file at the output location should preserve the special characters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8b85-138">如果你尝试处理使用不受支持编码的文件 （请记住，支持仅 ASCII、 西欧和 UTF8），一个错误记录在应用程序事件查看器，并出现错误 ID: 5633。</span><span class="sxs-lookup"><span data-stu-id="d8b85-138">If you attempt to process a file that uses a non-supported encoding (remember that only ASCII, Western European, and UTF8 are supported), an error is logged in the Application Event Viewer with error ID: 5633.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8b85-139">如果你要测试配置为 UTF8 编码的自定义管道，你应该附加到您要传递的消息的字节顺序标记 (BOM) 字符。</span><span class="sxs-lookup"><span data-stu-id="d8b85-139">If you are testing a custom pipeline configured for UTF8 encoding, you should attach Byte Order Mark (BOM) characters to the message you are passing.</span></span> <span data-ttu-id="d8b85-140">如果你要测试配置为西欧字符编码的自定义管道，不要将连接 BOM 字符。</span><span class="sxs-lookup"><span data-stu-id="d8b85-140">If you are testing a custom pipeline configured for Western European encoding, do not attach BOM characters.</span></span>