---
title: 第 6 课：创建自定义发送管道 |Microsoft Docs
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
ms.openlocfilehash: 536119606e7010b22e603585e5d410e3550ae41c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530293"
---
# <a name="lesson-6-creating-a-custom-send-pipeline"></a><span data-ttu-id="93941-102">第 6 课：创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="93941-102">Lesson 6: Creating a Custom Send Pipeline</span></span>
<span data-ttu-id="93941-103">在本课中，您可以创建自定义发送管道使用 BizTalk 管道设计器。</span><span class="sxs-lookup"><span data-stu-id="93941-103">In this lesson, you create a custom send pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="93941-104">发送管道是一个管道，对消息之前运行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息发送到其目标。</span><span class="sxs-lookup"><span data-stu-id="93941-104">A send pipeline is a pipeline you run on messages before [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sends the messages to their destination.</span></span>  
  
 <span data-ttu-id="93941-105">配置自定义管道以使用 SWIFT 汇编程序 (ASM) 组件。</span><span class="sxs-lookup"><span data-stu-id="93941-105">You configure the custom pipeline to use the SWIFT assembler (ASM) component.</span></span> <span data-ttu-id="93941-106">ASM 采用 XML 格式的消息并将转换或将内容序列化到 SWIFT 的平面文件。</span><span class="sxs-lookup"><span data-stu-id="93941-106">The ASM takes an XML-formatted message and converts or serializes the content into a SWIFT flat file.</span></span> <span data-ttu-id="93941-107">此转换基于中创建的 MT103 架构[第 3 课：添加自定义接收管道](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="93941-107">This conversion is based upon the MT103 schema you created in [Lesson 3: Adding a Custom Receive Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-a-custom-receive-pipeline.md).</span></span>  
  
### <a name="to-create-a-custom-send-pipeline"></a><span data-ttu-id="93941-108">若要创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="93941-108">To create a custom send pipeline</span></span>  
  
1. <span data-ttu-id="93941-109">在解决方案资源管理器中右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="93941-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="93941-110">在添加新项-SWIFTPipelines 对话框中，验证是否**管道文件**所选的类别窗格中，并选择**发送管道**从模板窗格。</span><span class="sxs-lookup"><span data-stu-id="93941-110">In the Add New Item-SWIFTPipelines dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  
  
3. <span data-ttu-id="93941-111">在中**名称**框中，键入**MT103SendPipeline.btp**。</span><span class="sxs-lookup"><span data-stu-id="93941-111">In the **Name** box, type **MT103SendPipeline.btp**.</span></span>  
  
4. <span data-ttu-id="93941-112">单击**添加**若要在 BizTalk 管道设计器中打开空白的管道。</span><span class="sxs-lookup"><span data-stu-id="93941-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="93941-113">BizTalk 管道设计器中显示空管道。</span><span class="sxs-lookup"><span data-stu-id="93941-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] <span data-ttu-id="93941-114">将新的管道添加到解决方案资源管理器中，SWIFTPipelines 项目下。</span><span class="sxs-lookup"><span data-stu-id="93941-114">adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
   <span data-ttu-id="93941-115">请继续执行[第 7 课：将 SWIFT 汇编程序添加到自定义发送管道](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="93941-115">Proceed to [Lesson 7: Adding the SWIFT Assembler to a Custom Send Pipeline](../../adapters-and-accelerators/accelerator-swift/lesson-7-adding-the-swift-assembler-to-a-custom-send-pipeline.md).</span></span>