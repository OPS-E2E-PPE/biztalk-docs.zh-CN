---
title: 第 6 课： 创建自定义发送管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom pipelines
- send pipelines, custom pipelines
ms.assetid: 73a3a546-1e43-4b93-87d3-9bfb32685a57
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a82801b0084f2d1b82a2c25cfc0fa2a9f8f1376c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210157"
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a><span data-ttu-id="95eb2-102">第 6 课： 创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="95eb2-102">Lesson 6: Creating a Custom Send Pipeline</span></span>
<span data-ttu-id="95eb2-103">在本课程中，你可以创建自定义发送管道使用 BizTalk 管道设计器。</span><span class="sxs-lookup"><span data-stu-id="95eb2-103">In this lesson, you create a custom send pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="95eb2-104">发送管道是你在之前的消息运行的管道[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息发送到其目标。</span><span class="sxs-lookup"><span data-stu-id="95eb2-104">A send pipeline is a pipeline you run on messages before [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sends the messages to their destination.</span></span>  
  
 <span data-ttu-id="95eb2-105">配置自定义管道将该 SWIFT 汇编程序 (ASM) 组件。</span><span class="sxs-lookup"><span data-stu-id="95eb2-105">You configure the custom pipeline to use the SWIFT assembler (ASM) component.</span></span> <span data-ttu-id="95eb2-106">ASM 采用 XML 格式的消息和将转换或序列化到 SWIFT 平面文件的内容。</span><span class="sxs-lookup"><span data-stu-id="95eb2-106">The ASM takes an XML-formatted message and converts or serializes the content into a SWIFT flat file.</span></span> <span data-ttu-id="95eb2-107">此转换基于中创建的 MT103 架构[第 3 课： 添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="95eb2-107">This conversion is based upon the MT103 schema you created in [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>  
  
### <a name="to-create-a-custom-send-pipeline"></a><span data-ttu-id="95eb2-108">若要创建自定义，将发送管道</span><span class="sxs-lookup"><span data-stu-id="95eb2-108">To create a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="95eb2-109">在解决方案资源管理器，右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="95eb2-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="95eb2-110">在添加新项-SWIFTPipelines 对话框中，确认**管道文件**是否选择在类别窗格中，然后选择**发送管道**从模板窗格。</span><span class="sxs-lookup"><span data-stu-id="95eb2-110">In the Add New Item-SWIFTPipelines dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="95eb2-111">在**名称**框中，键入**MT103SendPipeline.btp**。</span><span class="sxs-lookup"><span data-stu-id="95eb2-111">In the **Name** box, type **MT103SendPipeline.btp**.</span></span>  
  
4.  <span data-ttu-id="95eb2-112">单击**添加**以 BizTalk 管道设计器中打开空白的管道。</span><span class="sxs-lookup"><span data-stu-id="95eb2-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95eb2-113">在 BizTalk 管道设计器中显示空的管道。</span><span class="sxs-lookup"><span data-stu-id="95eb2-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="95eb2-114">将新管道 SWIFTPipelines 项目下添加到解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="95eb2-114"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
 <span data-ttu-id="95eb2-115">继续执行[第 7 课： 添加自定义 SWIFT 汇编程序发送管道](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="95eb2-115">Proceed to [Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).</span></span>