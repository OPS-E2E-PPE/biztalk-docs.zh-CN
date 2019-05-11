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
# <a name="send-pipeline"></a>发送管道
此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ，可以为你的应用程序自定义发送管道。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何将传出 XML 消息处理成等效的 RNIF 消息使用 BTARN 发送管道 (PipelineSend.btp)。 PipelineSend.btp 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNPipelines。 它包括以下阶段：  
  
-   XML 组装器  
  
-   MIME 编码器  
  
-   发送否认消息  
  
> [!NOTE]
>  如果您选择 BTARN 的上述组件之一发送管道在管道设计器在 Visual Studio 中，该组件的属性将不会显示在属性窗格。 若要显示组件的属性，您必须组件向工具箱添加通过使用**选择工具箱项**工具菜单中的命令; 发送管道; 中删除现有的组件以及如何将从组件在管道设计器中的相应阶段到工具箱。 如果您然后选择的组件，将在属性窗格中显示其属性。  
  
 此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)。  
  
## <a name="see-also"></a>请参阅  
 [管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)