---
title: 创建管道项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b584e3ab-e824-4977-b4ed-4fc197a6cf7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eead267abbb990933e6fd3150d099d07b007526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209709"
---
# <a name="creating-a-pipeline-project"></a><span data-ttu-id="2f1a1-102">创建管道项目</span><span class="sxs-lookup"><span data-stu-id="2f1a1-102">Creating a Pipeline Project</span></span>
<span data-ttu-id="2f1a1-103">若要创建管道项目：</span><span class="sxs-lookup"><span data-stu-id="2f1a1-103">To create a pipeline project:</span></span>  
  
1.  <span data-ttu-id="2f1a1-104">在 Visual Studio 中，创建一个新的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-104">In Visual Studio, create a new BizTalk project.</span></span>  
  
2.  <span data-ttu-id="2f1a1-105">将接收管道项和发送管道项添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-105">Add a receive pipeline item and a send pipeline item to the project.</span></span>  
  
3.  <span data-ttu-id="2f1a1-106">打开 ReceivePipeline.btp 文件。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-106">Open the ReceivePipeline.btp file.</span></span>  
  
4.  <span data-ttu-id="2f1a1-107">在管道设计器中，打开工具箱。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-107">In Pipeline Designer, open the Toolbox.</span></span>  
  
5.  <span data-ttu-id="2f1a1-108">右键单击**工具箱**图面，，然后选择**选择项**。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-108">Right-click the **Toolbox** surface, and then select **Choose Items**.</span></span>  
  
6.  <span data-ttu-id="2f1a1-109">在选择工具箱项窗口中，单击**管道组件**选项卡上，然后选择以下的管道组件：</span><span class="sxs-lookup"><span data-stu-id="2f1a1-109">In the Choose Toolbox Items window, click the **Pipeline Components** tab, and then select the following pipeline components:</span></span>  
  
    -   <span data-ttu-id="2f1a1-110">SwiftMXDisassembler</span><span class="sxs-lookup"><span data-stu-id="2f1a1-110">SwiftMXDisassembler</span></span>  
  
    -   <span data-ttu-id="2f1a1-111">SwiftMXAssembler</span><span class="sxs-lookup"><span data-stu-id="2f1a1-111">SwiftMXAssembler</span></span>  
  
    -   <span data-ttu-id="2f1a1-112">Swift MXRR 编码器组件</span><span class="sxs-lookup"><span data-stu-id="2f1a1-112">Swift MXRR Encoder Component</span></span>  
  
    -   <span data-ttu-id="2f1a1-113">Swift MXRR 解码器组件</span><span class="sxs-lookup"><span data-stu-id="2f1a1-113">Swift MXRR Decoder Component</span></span>  
  
    -   <span data-ttu-id="2f1a1-114">Swift MXRR 相关当事方冲突解决程序组件</span><span class="sxs-lookup"><span data-stu-id="2f1a1-114">Swift MXRR Correlation Party Resolver Component</span></span>  
  
7.  <span data-ttu-id="2f1a1-115">拖动**SwiftMXDisassembler**组件到反汇编程序占位符接收管道中。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-115">Drag the **SwiftMXDisassembler** component into the Disassembler placeholder in the Receive Pipeline.</span></span>  
  
8.  <span data-ttu-id="2f1a1-116">在 SwiftMXDisassembler 组件属性中，设置**BRE 验证**具体取决于是否想要对传入消息启用业务规则验证属性设置为 TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-116">In the SwiftMXDisassembler component properties, set the **BRE Validation** property to TRUE or FALSE depending on whether you want to enable Business Rules Validation on the incoming messages.</span></span> <span data-ttu-id="2f1a1-117">设置**TransportHeaderRequired**具体取决于是否想要提供的消息中传输标头属性设置为 TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-117">Set the **TransportHeaderRequired** property to TRUE or FALSE depending on whether you want to provide transport header in messages.</span></span>  
  
9. <span data-ttu-id="2f1a1-118">将 Swift MXRR 解码器和 Swift MXRR 相关方冲突解决程序组件拖到解码器和方冲突解决程序占位符内接收管道。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-118">Drag the Swift MXRR Decoder and Swift MXRR Correlation Party Resolver component into the Decoder and the Party Resolver placeholder inside the Receive Pipeline.</span></span>  
  
10. <span data-ttu-id="2f1a1-119">选择**MXRR 相关方冲突解决程序**管道中。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-119">Select the **MXRR Correlation Party Resolver** in the pipeline.</span></span> <span data-ttu-id="2f1a1-120">在管道组件属性窗口中，设置**启用 BAM 日志记录对帐**属性设置为 TRUE 或 FALSE，具体取决于是否想要启用 SWIFT 响应的对帐。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-120">In the Pipeline Component Properties window, set the **Enable BAM Logging for Reconciliation** property to TRUE or FALSE, depending on whether you want to enable reconciliation for the SWIFT responses.</span></span>  
  
11. <span data-ttu-id="2f1a1-121">打开**SendPipeline.btp**文件，在管道设计器中，打开**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-121">Open the **SendPipeline.btp** file, In the Pipeline Designer, open the **Toolbox**.</span></span>  
  
12. <span data-ttu-id="2f1a1-122">在工具箱中，拖动**SwiftMXAssembler**到汇编程序占位符内发送管道组件。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-122">In Toolbox, drag the **SwiftMXAssembler** component into the Assembler placeholder inside the Send Pipeline.</span></span>  
  
13. <span data-ttu-id="2f1a1-123">拖动**Swift MXRR 编码器**组件发送管道的编码器占位符。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-123">Drag the **Swift MXRR Encoder** component into the Encoder placeholders of the Send Pipeline.</span></span>  
  
14. <span data-ttu-id="2f1a1-124">选择**MXRR 编码器方冲突解决程序**在管线中，然后在管道组件属性窗口中，设置以下属性。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-124">Select the **MXRR Encoder Party Resolver** in the pipeline, and then in the Pipeline Component Properties window, set the following properties.</span></span>  
  
15. <span data-ttu-id="2f1a1-125">启用**BAM 日志记录对帐**TRUE 或 FALSE，具体取决于是否想要启用 SWIFT 响应的对帐。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-125">Enable **BAM Logging for Reconciliation** to TRUE or FALSE depending on whether you want to enable reconciliation for the SWIFT responses.</span></span>  
  
16. <span data-ttu-id="2f1a1-126">设置**所需的 LAU** TRUE 或 FALSE，具体取决于是否必须启用的消息在 SWIFT 联盟访问 (SAA) 的签名。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-126">Set the **LAU Required** to TRUE or FALSE depending on whether you have to enable the signing of the message at the SWIFT Alliance Access (SAA).</span></span>  
  
17. <span data-ttu-id="2f1a1-127">如果所需的 LAU 属性已设置为 TRUE，然后提供 LAU 密钥第一个部分和 LAU 密钥第二个部分 （值必须是相同的配置 SAA 时提供。）</span><span class="sxs-lookup"><span data-stu-id="2f1a1-127">If the LAU Required property has been has been set to TRUE, then provide LAU Key First Part and LAU Key Second Part (the values have to be the same ones that were provided while configuring the SAA.)</span></span>  
  
18. <span data-ttu-id="2f1a1-128">生成然后部署项目。</span><span class="sxs-lookup"><span data-stu-id="2f1a1-128">Build and then deploy the project.</span></span>