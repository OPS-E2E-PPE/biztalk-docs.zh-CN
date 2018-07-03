---
title: 接收管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd8f03aa-f5c3-49e7-946b-c8c91fe3abc7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a2c1de940fab14aa370dc1358efe36fe702a9d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990302"
---
# <a name="receive-pipeline"></a><span data-ttu-id="4b9c3-102">接收管道</span><span class="sxs-lookup"><span data-stu-id="4b9c3-102">Receive Pipeline</span></span>
<span data-ttu-id="4b9c3-103">此示例提供了一个有效的 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]接收管道，你可以为你的应用程序自定义。</span><span class="sxs-lookup"><span data-stu-id="4b9c3-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4b9c3-104">演示</span><span class="sxs-lookup"><span data-stu-id="4b9c3-104">Demonstrates</span></span>  
 <span data-ttu-id="4b9c3-105">此示例演示如何使用 BTARN 接收管道 (PipelineReceive.btp) 将传入 RNIF 消息加工成等效的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="4b9c3-105">This sample demonstrates how to process an incoming RNIF message into the equivalent XML message using the BTARN receive pipeline (PipelineReceive.btp).</span></span> <span data-ttu-id="4b9c3-106">PipelineReceive.btp 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNPipelines。</span><span class="sxs-lookup"><span data-stu-id="4b9c3-106">PipelineReceive.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="4b9c3-107">它包含以下阶段：</span><span class="sxs-lookup"><span data-stu-id="4b9c3-107">It includes the following stages:</span></span>  
  
- <span data-ttu-id="4b9c3-108">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="4b9c3-108">ReceiveMessageNonRepudiate</span></span>  
  
- <span data-ttu-id="4b9c3-109">RNMimeDecoder（MIME 预处理器/解码器）</span><span class="sxs-lookup"><span data-stu-id="4b9c3-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
- <span data-ttu-id="4b9c3-110">RNDAsm（XML 拆装器）</span><span class="sxs-lookup"><span data-stu-id="4b9c3-110">RNDAsm (XML Disassembler)</span></span>  
  
- <span data-ttu-id="4b9c3-111">RNPartyRes（参与方解析组件）</span><span class="sxs-lookup"><span data-stu-id="4b9c3-111">RNPartyRes (Party Resolution component)</span></span>  
  
- <span data-ttu-id="4b9c3-112">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="4b9c3-112">MessageUpdater</span></span>  
  
  <span data-ttu-id="4b9c3-113">此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="4b9c3-113">For more information about the components of this pipeline, and the message flow in this pipeline, see [BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9c3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b9c3-114">See Also</span></span>  
 <span data-ttu-id="4b9c3-115">[管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="4b9c3-115">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="4b9c3-116">BTARN 接收管道</span><span class="sxs-lookup"><span data-stu-id="4b9c3-116">BTARN Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)