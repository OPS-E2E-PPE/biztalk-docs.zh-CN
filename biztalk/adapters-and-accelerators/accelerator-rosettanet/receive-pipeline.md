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
# <a name="receive-pipeline"></a>接收管道
此示例提供了一个有效的 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]接收管道，你可以为你的应用程序自定义。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何使用 BTARN 接收管道 (PipelineReceive.btp) 将传入 RNIF 消息加工成等效的 XML 消息。 PipelineReceive.btp 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNPipelines。 它包含以下阶段：  
  
- ReceiveMessageNonRepudiate  
  
- RNMimeDecoder（MIME 预处理器/解码器）  
  
- RNDAsm（XML 拆装器）  
  
- RNPartyRes（参与方解析组件）  
  
- MessageUpdater  
  
  此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)。  
  
## <a name="see-also"></a>请参阅  
 [管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)