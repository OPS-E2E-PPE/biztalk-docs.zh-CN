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
# <a name="send-pipeline"></a>发送管道
此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ，可以为你的应用程序自定义发送管道。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何使用 BTARN 发送管道 (PipelineSend.btp) 将传出 XML 消息加工成等效的 RNIF 消息。 PipelineSend.btp 位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\RNPipelines。 它包含以下阶段：  
  
-   XML 组装器  
  
-   MIME 编码器  
  
-   发送不可否认的消息  
  
> [!NOTE]
>  如果在 Visual Studio 的管道设计器中选择 BTARN 发送管道的上述组件之一，则该组件的属性将不显示在“属性”窗格中。 若要显示组件的属性，您必须组件向工具箱添加通过使用**选择工具箱项**工具菜单中的命令; 发送管道; 中删除现有的组件以及如何将从组件在管道设计器中的相应阶段到工具箱。 然后，如果你选择该组件，它的属性将显示在“属性”窗格中。  
  
 此管道和此管道中的消息流的组件的详细信息，请参阅[BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)。  
  
## <a name="see-also"></a>请参阅  
 [管道示例](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md)   
 [BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)