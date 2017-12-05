---
title: "发送管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58ca6a63-525a-4b16-932d-6d26e68f6fab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7ee5ad712466df79a4e6961062ea56b73ad248
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="send-pipeline"></a><span data-ttu-id="6d8e4-102">发送管道</span><span class="sxs-lookup"><span data-stu-id="6d8e4-102">Send Pipeline</span></span>
<span data-ttu-id="6d8e4-103">此示例提供一个能够实际应用的 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 发送管道，你可以为自己的应用程序自定义它。</span><span class="sxs-lookup"><span data-stu-id="6d8e4-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6d8e4-104">演示</span><span class="sxs-lookup"><span data-stu-id="6d8e4-104">Demonstrates</span></span>  
 <span data-ttu-id="6d8e4-105">此示例演示如何使用 BTARN 发送管道 (PipelineSend.btp) 将传出 XML 消息加工成等效的 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="6d8e4-105">This sample demonstrates how to process an outgoing XML message into the equivalent RNIF message using the BTARN send pipeline (PipelineSend.btp).</span></span> <span data-ttu-id="6d8e4-106">PipelineSend.btp 位于*\<驱动器\>*: files\microsoft BizTalk\<版本\>RosettaNet\SDK\RNPipelines 快捷键。</span><span class="sxs-lookup"><span data-stu-id="6d8e4-106">PipelineSend.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="6d8e4-107">它包含以下阶段：</span><span class="sxs-lookup"><span data-stu-id="6d8e4-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="6d8e4-108">XML 汇编程序</span><span class="sxs-lookup"><span data-stu-id="6d8e4-108">XML Assembler</span></span>  
  
-   <span data-ttu-id="6d8e4-109">MIME 编码器</span><span class="sxs-lookup"><span data-stu-id="6d8e4-109">MIME Encoder</span></span>  
  
-   <span data-ttu-id="6d8e4-110">发送不可否认的消息</span><span class="sxs-lookup"><span data-stu-id="6d8e4-110">Send message Non-repudiate</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d8e4-111">如果在 Visual Studio 的管道设计器中选择 BTARN 发送管道的上述组件之一，则该组件的属性将不显示在“属性”窗格中。</span><span class="sxs-lookup"><span data-stu-id="6d8e4-111">If you select one of the above components of the BTARN send pipeline in the Pipeline Designer in Visual Studio, the properties for that component will not be displayed in the Properties pane.</span></span> <span data-ttu-id="6d8e4-112">若要显示组件的属性，你必须将组件添加到工具箱中使用**选择工具箱项**工具菜单中的命令; 从发送管道; 中删除现有组件并将从组件到管道设计器中的相应阶段的工具箱。</span><span class="sxs-lookup"><span data-stu-id="6d8e4-112">To display the properties of the component, you must add the component to the Toolbox by using the **Choose Toolbox Items** command in the Tools menu; delete the existing component from the send pipeline; and then add the component from the Toolbox into the appropriate stage in the Pipeline Designer.</span></span> <span data-ttu-id="6d8e4-113">然后，如果你选择该组件，它的属性将显示在“属性”窗格中。</span><span class="sxs-lookup"><span data-stu-id="6d8e4-113">If you then select the component, its properties will be displayed in the Properties pane.</span></span>  
  
 <span data-ttu-id="6d8e4-114">此管道中，并在此管道中的消息流的组件的详细信息，请参阅[BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="6d8e4-114">For more information about the components of this pipeline, and the message flow within this pipeline, see [BTARN Send Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d8e4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d8e4-115">See Also</span></span>  
 <span data-ttu-id="6d8e4-116">[管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="6d8e4-116">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="6d8e4-117">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="6d8e4-117">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)