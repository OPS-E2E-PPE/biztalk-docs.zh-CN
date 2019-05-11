---
title: 创建自定义管道来处理 JSON 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b5600cfa54e5df6ae72c3a5f3bb03a255d4c08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354279"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a>创建自定义管道来处理 JSON 消息
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供可用于处理 JSON 消息中的管道组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。 在此步骤中，我们使用这些管道组件来创建可以在配置时使用的自定义管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。  
  
## <a name="create-a-custom-receive-pipeline"></a>创建自定义接收管道  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **接收管道**. 管道命名为`JSONToXmlReceivePipeline.btp`，然后单击**添加**。  
  
2. 内**解码**阶段将添加新**JSON 解码器**。 中的其他阶段以及其他管道组件，如屏幕截图中中, 所示，并保存更改。  
  
    ![自定义接收管道](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")  
  
## <a name="create-a-custom-send-pipeline"></a>创建自定义发送管道  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **发送管道**. 管道命名为`XmlToJSONSendPipeline.btp`，然后单击**添加**。  
  
2. 内**编码**阶段将添加新**JSON 编码器**。 中的其他阶段以及其他管道组件，如屏幕截图中中, 所示，并保存更改。  
  
    ![自定义发送管道](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)