---
title: "创建自定义管道处理 JSON 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c85f1a45dceb812fc805a66701653642d0ccb6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-custom-pipelines-to-process-json-messages"></a>创建处理 JSON 消息的自定义管道
> [!NOTE]
>  本教程仅适用于 [!INCLUDE[prague](../includes/prague-md.md)]。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了可用于处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中的 JSON 消息的管道组件。 在此步骤中，我们使用这些管道组件来创建自定义管道，在配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序时使用。  
  
## <a name="create-a-custom-receive-pipeline"></a>创建自定义接收管道  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **接收管道**. 提供将管道名称作为`JSONToXmlReceivePipeline.btp`，然后单击**添加**。  
  
2.  在**解码**阶段添加新**JSON 解码器**。 在屏幕快照中所示的其他阶段以及其他管道组件中，保存更改。  
  
     ![自定义接收管道](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")  
  
## <a name="create-a-custom-send-pipeline"></a>创建自定义发送管道  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **发送管道**. 提供将管道名称作为`XmlToJSONSendPipeline.btp`，然后单击**添加**。  
  
2.  在**编码**阶段添加新**JSON 编码器**。 在屏幕快照中所示的其他阶段以及其他管道组件中，保存更改。  
  
     ![自定义发送管道](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)