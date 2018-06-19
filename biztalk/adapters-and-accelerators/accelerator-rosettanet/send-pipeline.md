---
title: 发送管道 |Microsoft 文档
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
ms.openlocfilehash: 1b7ee5ad712466df79a4e6961062ea56b73ad248
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964059"
---
# <a name="send-pipeline"></a>发送管道
此示例提供一个能够实际应用的 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 发送管道，你可以为自己的应用程序自定义它。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何使用 BTARN 发送管道 (PipelineSend.btp) 将传出 XML 消息加工成等效的 RNIF 消息。 PipelineSend.btp 位于*\<驱动器\>*: files\microsoft BizTalk\<版本\>RosettaNet\SDK\RNPipelines 快捷键。 它包含以下阶段：  
  
-   XML 汇编程序  
  
-   MIME 编码器  
  
-   发送不可否认的消息  
  
> [!NOTE]
>  如果在 Visual Studio 的管道设计器中选择 BTARN 发送管道的上述组件之一，则该组件的属性将不显示在“属性”窗格中。 若要显示组件的属性，你必须将组件添加到工具箱中使用**选择工具箱项**工具菜单中的命令; 从发送管道; 中删除现有组件并将从组件到管道设计器中的相应阶段的工具箱。 然后，如果你选择该组件，它的属性将显示在“属性”窗格中。  
  
 此管道中，并在此管道中的消息流的组件的详细信息，请参阅[BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)