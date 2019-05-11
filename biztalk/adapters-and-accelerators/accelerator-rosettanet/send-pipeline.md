---
title: 发送管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58ca6a63-525a-4b16-932d-6d26e68f6fab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acd13510e9052f1f14f38f30cf263949f65bf5fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281887"
---
# <a name="send-pipeline"></a><span data-ttu-id="bf8a2-102">发送管道</span><span class="sxs-lookup"><span data-stu-id="bf8a2-102">Send Pipeline</span></span>
<span data-ttu-id="bf8a2-103">此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ，可以为你的应用程序自定义发送管道。</span><span class="sxs-lookup"><span data-stu-id="bf8a2-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bf8a2-104">演示</span><span class="sxs-lookup"><span data-stu-id="bf8a2-104">Demonstrates</span></span>  
 <span data-ttu-id="bf8a2-105">此示例演示如何将传出 XML 消息处理成等效的 RNIF 消息使用 BTARN 发送管道 (PipelineSend.btp)。</span><span class="sxs-lookup"><span data-stu-id="bf8a2-105">This sample demonstrates how to process an outgoing XML message into the equivalent RNIF message using the BTARN send pipeline (PipelineSend.btp).</span></span> <span data-ttu-id="bf8a2-106">PipelineSend.btp 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNPipelines。</span><span class="sxs-lookup"><span data-stu-id="bf8a2-106">PipelineSend.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="bf8a2-107">它包括以下阶段：</span><span class="sxs-lookup"><span data-stu-id="bf8a2-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="bf8a2-108">XML 组装器</span><span class="sxs-lookup"><span data-stu-id="bf8a2-108">XML Assembler</span></span>  
  
-   <span data-ttu-id="bf8a2-109">MIME 编码器</span><span class="sxs-lookup"><span data-stu-id="bf8a2-109">MIME Encoder</span></span>  
  
-   <span data-ttu-id="bf8a2-110">发送否认消息</span><span class="sxs-lookup"><span data-stu-id="bf8a2-110">Send message Non-repudiate</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf8a2-111">如果您选择 BTARN 的上述组件之一发送管道在管道设计器在 Visual Studio 中，该组件的属性将不会显示在属性窗格。</span><span class="sxs-lookup"><span data-stu-id="bf8a2-111">If you select one of the above components of the BTARN send pipeline in the Pipeline Designer in Visual Studio, the properties for that component will not be displayed in the Properties pane.</span></span> <span data-ttu-id="bf8a2-112">若要显示组件的属性，您必须组件向工具箱添加通过使用**选择工具箱项**工具菜单中的命令; 发送管道; 中删除现有的组件以及如何将从组件在管道设计器中的相应阶段到工具箱。</span><span class="sxs-lookup"><span data-stu-id="bf8a2-112">To display the properties of the component, you must add the component to the Toolbox by using the **Choose Toolbox Items** command in the Tools menu; delete the existing component from the send pipeline; and then add the component from the Toolbox into the appropriate stage in the Pipeline Designer.</span></span> <span data-ttu-id="bf8a2-113">如果您然后选择的组件，将在属性窗格中显示其属性。</span><span class="sxs-lookup"><span data-stu-id="bf8a2-113">If you then select the component, its properties will be displayed in the Properties pane.</span></span>  
  
 <span data-ttu-id="bf8a2-114">此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="bf8a2-114">For more information about the components of this pipeline, and the message flow within this pipeline, see [BTARN Send Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf8a2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf8a2-115">See Also</span></span>  
 <span data-ttu-id="bf8a2-116">[管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="bf8a2-116">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="bf8a2-117">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="bf8a2-117">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)