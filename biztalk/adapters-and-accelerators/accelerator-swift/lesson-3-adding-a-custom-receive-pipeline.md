---
title: 第 3 课：添加自定义接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating custom pipelines
- custom pipelines
ms.assetid: 1917b8e2-4f1c-4c20-abe4-ea18a406eeeb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f4d7aa1ccb2ee3dc7b76ca081b2de750bdaa6d5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530325"
---
# <a name="lesson-3-adding-a-custom-receive-pipeline"></a><span data-ttu-id="75a62-102">第 3 课：添加自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="75a62-102">Lesson 3: Adding a Custom Receive Pipeline</span></span>
<span data-ttu-id="75a62-103">在本课程中创建自定义接收管道使用 BizTalk 管道设计器。</span><span class="sxs-lookup"><span data-stu-id="75a62-103">In this lesson you create a custom receive pipeline using BizTalk Pipeline Designer.</span></span> <span data-ttu-id="75a62-104">自定义接收管道是一种管道之后适配器收到消息之后，之前对消息运行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]将其发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="75a62-104">A custom receive pipeline is a pipeline that is run on messages after the adapter receives the messages, but before [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] publishes them to the MessageBox database.</span></span>  
  
 <span data-ttu-id="75a62-105">配置自定义管道以使用 SWIFT 反汇编程序 (DASM) 组件。</span><span class="sxs-lookup"><span data-stu-id="75a62-105">You configure the custom pipeline to use the SWIFT disassembler (DASM) component.</span></span> <span data-ttu-id="75a62-106">SWIFT 反汇编程序采用 SWIFT 格式的平面文件并将转换时或分析，为基于 XML 的表示形式，SWIFT 消息的内容的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以使用。</span><span class="sxs-lookup"><span data-stu-id="75a62-106">The SWIFT disassembler takes a SWIFT-formatted flat file and converts, or parses, the content of the SWIFT message into an XML-based representation, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can consume.</span></span>  
  
 <span data-ttu-id="75a62-107">在上一步中添加的 MT103 运行时架构 ([第 2 课：添加项目引用](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) 是用于转换的格式。</span><span class="sxs-lookup"><span data-stu-id="75a62-107">The MT103 runtime schema that you added in the previous step ([Lesson 2: Adding Project References](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-project-references.md)) is the format that you use for the conversion.</span></span>  
  
### <a name="to-create-a-new-custom-receive-pipeline"></a><span data-ttu-id="75a62-108">若要创建新的自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="75a62-108">To create a new custom receive pipeline</span></span>  
  
1. <span data-ttu-id="75a62-109">在解决方案资源管理器中右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="75a62-109">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="75a62-110">在添加新项-SWIFTPipelines 对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**从模板窗格。</span><span class="sxs-lookup"><span data-stu-id="75a62-110">In the Add New Item-SWIFTPipelines dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  
  
3. <span data-ttu-id="75a62-111">在中**名称**框中，键入**MT103ReceivePipeline.btp**。</span><span class="sxs-lookup"><span data-stu-id="75a62-111">In the **Name** box, type **MT103ReceivePipeline.btp**.</span></span>  
  
4. <span data-ttu-id="75a62-112">单击**添加**若要在 BizTalk 管道设计器中打开空白的管道。</span><span class="sxs-lookup"><span data-stu-id="75a62-112">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  
  
   <span data-ttu-id="75a62-113">BizTalk 管道设计器中显示空管道。</span><span class="sxs-lookup"><span data-stu-id="75a62-113">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> <span data-ttu-id="75a62-114">Visual Studio 还会向解决方案资源管理器的新管道 SWIFTPipelines 项目下添加。</span><span class="sxs-lookup"><span data-stu-id="75a62-114">Visual Studio also adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  
  
   <span data-ttu-id="75a62-115">请继续执行[第 4 课：将 SWIFT 汇编程序和反汇编程序添加到工具箱](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md)。</span><span class="sxs-lookup"><span data-stu-id="75a62-115">Proceed to [Lesson 4: Adding the SWIFT Assembler and Disassembler to the Toolbox](../../adapters-and-accelerators/accelerator-swift/lesson-4-adding-the-swift-assembler-and-disassembler-to-the-toolbox.md).</span></span>