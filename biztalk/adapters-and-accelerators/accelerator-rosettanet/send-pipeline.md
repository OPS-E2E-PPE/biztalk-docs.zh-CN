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
ms.openlocfilehash: 5700b3adb0769edff4ec820b4d95353383c08e6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968014"
---
# <a name="send-pipeline"></a><span data-ttu-id="9f02e-102">发送管道</span><span class="sxs-lookup"><span data-stu-id="9f02e-102">Send Pipeline</span></span>
<span data-ttu-id="9f02e-103">此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ，可以为你的应用程序自定义发送管道。</span><span class="sxs-lookup"><span data-stu-id="9f02e-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9f02e-104">演示</span><span class="sxs-lookup"><span data-stu-id="9f02e-104">Demonstrates</span></span>  
 <span data-ttu-id="9f02e-105">此示例演示如何使用 BTARN 发送管道 (PipelineSend.btp) 将传出 XML 消息加工成等效的 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="9f02e-105">This sample demonstrates how to process an outgoing XML message into the equivalent RNIF message using the BTARN send pipeline (PipelineSend.btp).</span></span> <span data-ttu-id="9f02e-106">PipelineSend.btp 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNPipelines。</span><span class="sxs-lookup"><span data-stu-id="9f02e-106">PipelineSend.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="9f02e-107">它包含以下阶段：</span><span class="sxs-lookup"><span data-stu-id="9f02e-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="9f02e-108">XML 组装器</span><span class="sxs-lookup"><span data-stu-id="9f02e-108">XML Assembler</span></span>  
  
-   <span data-ttu-id="9f02e-109">MIME 编码器</span><span class="sxs-lookup"><span data-stu-id="9f02e-109">MIME Encoder</span></span>  
  
-   <span data-ttu-id="9f02e-110">发送不可否认的消息</span><span class="sxs-lookup"><span data-stu-id="9f02e-110">Send message Non-repudiate</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f02e-111">如果在 Visual Studio 的管道设计器中选择 BTARN 发送管道的上述组件之一，则该组件的属性将不显示在“属性”窗格中。</span><span class="sxs-lookup"><span data-stu-id="9f02e-111">If you select one of the above components of the BTARN send pipeline in the Pipeline Designer in Visual Studio, the properties for that component will not be displayed in the Properties pane.</span></span> <span data-ttu-id="9f02e-112">若要显示组件的属性，您必须组件向工具箱添加通过使用**选择工具箱项**工具菜单中的命令; 发送管道; 中删除现有的组件以及如何将从组件在管道设计器中的相应阶段到工具箱。</span><span class="sxs-lookup"><span data-stu-id="9f02e-112">To display the properties of the component, you must add the component to the Toolbox by using the **Choose Toolbox Items** command in the Tools menu; delete the existing component from the send pipeline; and then add the component from the Toolbox into the appropriate stage in the Pipeline Designer.</span></span> <span data-ttu-id="9f02e-113">然后，如果你选择该组件，它的属性将显示在“属性”窗格中。</span><span class="sxs-lookup"><span data-stu-id="9f02e-113">If you then select the component, its properties will be displayed in the Properties pane.</span></span>  
  
 <span data-ttu-id="9f02e-114">此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="9f02e-114">For more information about the components of this pipeline, and the message flow within this pipeline, see [BTARN Send Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f02e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f02e-115">See Also</span></span>  
 <span data-ttu-id="9f02e-116">[管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="9f02e-116">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="9f02e-117">BTARN 发送管道</span><span class="sxs-lookup"><span data-stu-id="9f02e-117">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)