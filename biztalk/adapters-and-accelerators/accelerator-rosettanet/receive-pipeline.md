---
title: "接收管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd8f03aa-f5c3-49e7-946b-c8c91fe3abc7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7461ce357b3fa9cb6216dfce6381876100bb4287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receive-pipeline"></a><span data-ttu-id="6c1d7-102">接收管道</span><span class="sxs-lookup"><span data-stu-id="6c1d7-102">Receive Pipeline</span></span>
<span data-ttu-id="6c1d7-103">此示例提供一个能够实际应用的 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 接收管道，你可以为自己的应用程序自定义它。</span><span class="sxs-lookup"><span data-stu-id="6c1d7-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6c1d7-104">演示</span><span class="sxs-lookup"><span data-stu-id="6c1d7-104">Demonstrates</span></span>  
 <span data-ttu-id="6c1d7-105">此示例演示如何使用 BTARN 接收管道 (PipelineReceive.btp) 将传入 RNIF 消息加工成等效的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="6c1d7-105">This sample demonstrates how to process an incoming RNIF message into the equivalent XML message using the BTARN receive pipeline (PipelineReceive.btp).</span></span> <span data-ttu-id="6c1d7-106">PipelineReceive.btp 位于*\<驱动器 >*: files\microsoft BizTalk\<版本 > RosettaNet\SDK\RNPipelines 快捷键。</span><span class="sxs-lookup"><span data-stu-id="6c1d7-106">PipelineReceive.btp is located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="6c1d7-107">它包含以下阶段：</span><span class="sxs-lookup"><span data-stu-id="6c1d7-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="6c1d7-108">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="6c1d7-108">ReceiveMessageNonRepudiate</span></span>  
  
-   <span data-ttu-id="6c1d7-109">RNMimeDecoder（MIME 预处理器/解码器）</span><span class="sxs-lookup"><span data-stu-id="6c1d7-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
-   <span data-ttu-id="6c1d7-110">RNDAsm（XML 拆装器）</span><span class="sxs-lookup"><span data-stu-id="6c1d7-110">RNDAsm (XML Disassembler)</span></span>  
  
-   <span data-ttu-id="6c1d7-111">RNPartyRes（参与方解析组件）</span><span class="sxs-lookup"><span data-stu-id="6c1d7-111">RNPartyRes (Party Resolution component)</span></span>  
  
-   <span data-ttu-id="6c1d7-112">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="6c1d7-112">MessageUpdater</span></span>  
  
 <span data-ttu-id="6c1d7-113">此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="6c1d7-113">For more information about the components of this pipeline, and the message flow in this pipeline, see [BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c1d7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c1d7-114">See Also</span></span>  
 <span data-ttu-id="6c1d7-115">[管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="6c1d7-115">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="6c1d7-116">BTARN 接收管道</span><span class="sxs-lookup"><span data-stu-id="6c1d7-116">BTARN Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)