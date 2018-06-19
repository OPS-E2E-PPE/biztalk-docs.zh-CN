---
title: 接收管道 |Microsoft 文档
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
ms.openlocfilehash: 3d5374c46411e0c4924585647736bfde7f1e4428
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964435"
---
# <a name="receive-pipeline"></a>接收管道
此示例提供一个能够实际应用的 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 接收管道，你可以为自己的应用程序自定义它。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何使用 BTARN 接收管道 (PipelineReceive.btp) 将传入 RNIF 消息加工成等效的 XML 消息。 PipelineReceive.btp 位于*\<驱动器\>*: files\microsoft BizTalk\<版本\>RosettaNet\SDK\RNPipelines 快捷键。 它包含以下阶段：  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder（MIME 预处理器/解码器）  
  
-   RNDAsm（XML 拆装器）  
  
-   RNPartyRes（参与方解析组件）  
  
-   MessageUpdater  
  
 此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)