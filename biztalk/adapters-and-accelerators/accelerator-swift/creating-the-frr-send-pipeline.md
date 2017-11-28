---
title: "创建 FRR 发送管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87733b6b3a93d2543d26cd6d11b366b84218d207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-send-pipeline"></a><span data-ttu-id="78271-102">创建 FRR 发送管道</span><span class="sxs-lookup"><span data-stu-id="78271-102">Creating the FRR Send Pipeline</span></span>
<span data-ttu-id="78271-103">若要执行 FIN 响应对帐，你需要创建包含 SWIFTAsmFrrMQSeriesHelper 管道组件，除了 SWIFT 汇编程序发送管道。</span><span class="sxs-lookup"><span data-stu-id="78271-103">To perform FIN Response Reconciliation, you need to create a send pipeline that contains the SWIFTAsmFrrMQSeriesHelper pipeline component, in addition to the SWIFT assembler.</span></span>  
  
 <span data-ttu-id="78271-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="78271-104">**Summary**</span></span>  
  
 <span data-ttu-id="78271-105">创建具有以下几个阶段的发送管道：</span><span class="sxs-lookup"><span data-stu-id="78271-105">Create a send pipeline with the following stages:</span></span>  
  
|<span data-ttu-id="78271-106">阶段</span><span class="sxs-lookup"><span data-stu-id="78271-106">Stage</span></span>|<span data-ttu-id="78271-107">组件</span><span class="sxs-lookup"><span data-stu-id="78271-107">Component</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="78271-108">组装阶段</span><span class="sxs-lookup"><span data-stu-id="78271-108">Assemble stage</span></span>|<span data-ttu-id="78271-109">SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="78271-109">SWIFT assembler</span></span>|  
|<span data-ttu-id="78271-110">编码阶段</span><span class="sxs-lookup"><span data-stu-id="78271-110">Encode stage</span></span>|<span data-ttu-id="78271-111">SWIFT Frr MQSeries 发送组件</span><span class="sxs-lookup"><span data-stu-id="78271-111">SWIFT Frr MQSeries Send Component</span></span>|  
  
### <a name="to-create-a-custom-send-pipeline-for-frr"></a><span data-ttu-id="78271-112">若要为 FRR 创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="78271-112">To create a custom send pipeline for FRR</span></span>  
  
1.  <span data-ttu-id="78271-113">在解决方案资源管理器的 Visual Studio 中，右键单击你的管道项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="78271-113">In Solution Explorer of Visual Studio, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="78271-114">在添加新项对话框中，选择**发送管道**从模板窗格。</span><span class="sxs-lookup"><span data-stu-id="78271-114">In the Add New Item dialog box, select **Send Pipeline** from the Templates pane.</span></span>  
  
3.  <span data-ttu-id="78271-115">在**名称**框中，键入接收管道的名称，如**FRRSendPipeline.btp**。</span><span class="sxs-lookup"><span data-stu-id="78271-115">In the **Name** box, type a name for your receive pipeline, such as **FRRSendPipeline.btp**.</span></span> <span data-ttu-id="78271-116">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="78271-116">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="78271-117">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**然后**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="78271-117">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="78271-118">从 BizTalk 管道组件工具箱中，拖动**SWIFT 汇编程序**到**拖至此处**下面框**装配**阶段中的形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="78271-118">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
6.  <span data-ttu-id="78271-119">从 BizTalk 管道组件工具箱中，拖动**SWIFT Frr MQSeries 发送组件**到**拖至此处**下面框**编码**阶段中的形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="78271-119">From the BizTalk Pipeline Components Toolbox, drag **SWIFT Frr MQSeries Send Component** to the **Drop Here** box below the **Encode** stage shape in **BizTalk Pipeline Designer**.</span></span>  
  
7.  <span data-ttu-id="78271-120">在 BizTalk 资源管理器，右键单击你的管道项目，单击**取消部署后再次**，然后单击**是**。</span><span class="sxs-lookup"><span data-stu-id="78271-120">In BizTalk Explorer, right-click your pipeline project, click **Undeploy**, and then click **Yes**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78271-121">在取消部署，然后重新部署管道项目后必须重置任何发送端口或接收在以前部署的项目中使用的管道的位置。</span><span class="sxs-lookup"><span data-stu-id="78271-121">After undeploying and then redeploying your pipeline project, you must reset any send ports or receive locations that use pipelines in the previously deployed project.</span></span>  
  
8.  <span data-ttu-id="78271-122">在解决方案资源管理器，右键单击你的管道项目，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="78271-122">In Solution Explorer, right-click your pipeline project, and then click **Build**.</span></span>  
  
9. <span data-ttu-id="78271-123">已成功生成后，右键单击你的管道项目，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="78271-123">After the build has succeeded, right-click your pipeline project, and then click **Deploy**.</span></span>