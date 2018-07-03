---
title: 创建 FRR 发送管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d16003e489944016a7b840b870d33d8ebcf671d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005742"
---
# <a name="creating-the-frr-send-pipeline"></a><span data-ttu-id="27f18-102">创建 FRR 发送管道</span><span class="sxs-lookup"><span data-stu-id="27f18-102">Creating the FRR Send Pipeline</span></span>
<span data-ttu-id="27f18-103">若要执行 FIN 响应对帐，您需要创建包含 SWIFT 汇编程序之外的 SWIFTAsmFrrMQSeriesHelper 管道组件的发送管道。</span><span class="sxs-lookup"><span data-stu-id="27f18-103">To perform FIN Response Reconciliation, you need to create a send pipeline that contains the SWIFTAsmFrrMQSeriesHelper pipeline component, in addition to the SWIFT assembler.</span></span>  

 <span data-ttu-id="27f18-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="27f18-104">**Summary**</span></span>  

 <span data-ttu-id="27f18-105">创建发送管道具有以下阶段：</span><span class="sxs-lookup"><span data-stu-id="27f18-105">Create a send pipeline with the following stages:</span></span>  

|<span data-ttu-id="27f18-106">阶段</span><span class="sxs-lookup"><span data-stu-id="27f18-106">Stage</span></span>|<span data-ttu-id="27f18-107">组件</span><span class="sxs-lookup"><span data-stu-id="27f18-107">Component</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="27f18-108">组装阶段</span><span class="sxs-lookup"><span data-stu-id="27f18-108">Assemble stage</span></span>|<span data-ttu-id="27f18-109">SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="27f18-109">SWIFT assembler</span></span>|  
|<span data-ttu-id="27f18-110">编码阶段</span><span class="sxs-lookup"><span data-stu-id="27f18-110">Encode stage</span></span>|<span data-ttu-id="27f18-111">SWIFT 的 Frr MQSeries 发送组件</span><span class="sxs-lookup"><span data-stu-id="27f18-111">SWIFT Frr MQSeries Send Component</span></span>|  

### <a name="to-create-a-custom-send-pipeline-for-frr"></a><span data-ttu-id="27f18-112">若要为 FRR 创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="27f18-112">To create a custom send pipeline for FRR</span></span>  

1. <span data-ttu-id="27f18-113">在解决方案资源管理器的 Visual Studio 中，右键单击管道项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="27f18-113">In Solution Explorer of Visual Studio, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="27f18-114">在添加新项对话框中，选择**发送管道**从模板窗格。</span><span class="sxs-lookup"><span data-stu-id="27f18-114">In the Add New Item dialog box, select **Send Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="27f18-115">在中**名称**框中，键入你的接收管道的名称，如**FRRSendPipeline.btp**。</span><span class="sxs-lookup"><span data-stu-id="27f18-115">In the **Name** box, type a name for your receive pipeline, such as **FRRSendPipeline.btp**.</span></span> <span data-ttu-id="27f18-116">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="27f18-116">Click **Add**.</span></span>  

4. <span data-ttu-id="27f18-117">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**，然后**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="27f18-117">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

5. <span data-ttu-id="27f18-118">从 BizTalk 管道组件工具箱拖动**SWIFT 汇编程序**到**在此处放置**下面的框**组装**阶段中的形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="27f18-118">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  

6. <span data-ttu-id="27f18-119">从 BizTalk 管道组件工具箱拖动**SWIFT 的 Frr MQSeries 发送组件**到**在此处放置**下面的框**编码**阶段中的形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="27f18-119">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Frr MQSeries Send Component** to the **Drop Here** box below the **Encode** stage shape in **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="27f18-120">在 BizTalk 浏览器中，右键单击管道项目，单击**Undeploy**，然后单击**是**。</span><span class="sxs-lookup"><span data-stu-id="27f18-120">In BizTalk Explorer, right-click your pipeline project, click **Undeploy**, and then click **Yes**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="27f18-121">取消部署，然后重新部署管道项目之后, 必须重置任何发送端口或接收管道使用以前部署的项目中的位置。</span><span class="sxs-lookup"><span data-stu-id="27f18-121">After undeploying and then redeploying your pipeline project, you must reset any send ports or receive locations that use pipelines in the previously deployed project.</span></span>  

8. <span data-ttu-id="27f18-122">在解决方案资源管理器，右键单击管道项目，然后依次**生成**。</span><span class="sxs-lookup"><span data-stu-id="27f18-122">In Solution Explorer, right-click your pipeline project, and then click **Build**.</span></span>  

9. <span data-ttu-id="27f18-123">已成功生成后，右键单击管道项目，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="27f18-123">After the build has succeeded, right-click your pipeline project, and then click **Deploy**.</span></span>
