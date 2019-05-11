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
ms.openlocfilehash: 211817d704faec2f936f33a04944360804b52e14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282472"
---
# <a name="receive-pipeline"></a><span data-ttu-id="bcfec-102">接收管道</span><span class="sxs-lookup"><span data-stu-id="bcfec-102">Receive Pipeline</span></span>
<span data-ttu-id="bcfec-103">此示例提供了一个有效的 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]接收管道，你可以为你的应用程序自定义。</span><span class="sxs-lookup"><span data-stu-id="bcfec-103">This sample provides a working Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bcfec-104">演示</span><span class="sxs-lookup"><span data-stu-id="bcfec-104">Demonstrates</span></span>  
 <span data-ttu-id="bcfec-105">此示例演示如何将传入 RNIF 消息加工成等效的 XML 消息使用 BTARN 接收管道 (PipelineReceive.btp)。</span><span class="sxs-lookup"><span data-stu-id="bcfec-105">This sample demonstrates how to process an incoming RNIF message into the equivalent XML message using the BTARN receive pipeline (PipelineReceive.btp).</span></span> <span data-ttu-id="bcfec-106">PipelineReceive.btp 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNPipelines。</span><span class="sxs-lookup"><span data-stu-id="bcfec-106">PipelineReceive.btp is located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="bcfec-107">它包括以下阶段：</span><span class="sxs-lookup"><span data-stu-id="bcfec-107">It includes the following stages:</span></span>  
  
- <span data-ttu-id="bcfec-108">ReceiveMessageNonRepudiate</span><span class="sxs-lookup"><span data-stu-id="bcfec-108">ReceiveMessageNonRepudiate</span></span>  
  
- <span data-ttu-id="bcfec-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span><span class="sxs-lookup"><span data-stu-id="bcfec-109">RNMimeDecoder (MIME Preprocessor/Decoder)</span></span>  
  
- <span data-ttu-id="bcfec-110">RNDAsm （XML 拆装器）</span><span class="sxs-lookup"><span data-stu-id="bcfec-110">RNDAsm (XML Disassembler)</span></span>  
  
- <span data-ttu-id="bcfec-111">RNPartyRes （参与方解析组件）</span><span class="sxs-lookup"><span data-stu-id="bcfec-111">RNPartyRes (Party Resolution component)</span></span>  
  
- <span data-ttu-id="bcfec-112">MessageUpdater</span><span class="sxs-lookup"><span data-stu-id="bcfec-112">MessageUpdater</span></span>  
  
  <span data-ttu-id="bcfec-113">此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="bcfec-113">For more information about the components of this pipeline, and the message flow in this pipeline, see [BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcfec-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcfec-114">See Also</span></span>  
 <span data-ttu-id="bcfec-115">[管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="bcfec-115">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="bcfec-116">BTARN 接收管道</span><span class="sxs-lookup"><span data-stu-id="bcfec-116">BTARN Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)