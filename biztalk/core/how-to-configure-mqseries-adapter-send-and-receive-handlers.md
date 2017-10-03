---
title: "如何配置 MQSeries 适配器发送和接收处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive handlers, MQSeries adapters
- configuring [MQSeries adapters], receive handlers
- MQSeries adapters, send handlers
- MQSeries adapters, receive handlers
- send handlers, MQSeries adapters
- configuring [MQSeries adapters], send handlers
ms.assetid: e1cfc415-50d2-440b-9301-ad69da28ad3e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a1e933f62adaf4e17fae5334e65f50610fb6f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a>如何配置 MQSeries 适配器发送和接收处理程序
你可以配置为发送某些属性，接收处理程序通过 BizTalk Server 管理控制台的 MQSeries 适配器。 在过程中所述[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)建立的大部分发送处理程序属性的值。  
  
## <a name="to-configure-the-send-and-receive-handlers"></a>若要配置发送和接收处理程序  
 请按照下列步骤来配置发送和接收 MSQeries 适配器的处理程序：  
  
1.  单击**启动**，指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，单击以展开**平台设置**，然后单击到展开**适配器**。  
  
3.  在展开的适配器列表中，选择**MQSeries**。 列表发送和接收处理程序绑定到 MQSeries 适配器显示在右窗格中。  
  
4.  在右窗格中，双击发送或接收在右窗格中的处理程序。  
  
5.  在**适配器处理程序属性**对话框中，单击**属性**。  
  
6.  在**MQSeries 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**在批处理中的最大消息**|在批处理中设置的最大消息数。 仅适用于发送处理程序。|  
    |**Server**|Windows 正在 MQSeries 服务器的计算机的名称。|  
  
7.  单击 **“确定”**。  
  
    > [!NOTE]
    >  “接收位置”和“发送端口”属性将替代“接收处理程序”和“发送处理程序”的值。 如果“接收位置”或“发送端口”属性未设置值，则适配器将分别采用“接收处理程序”和“发送处理程序”的值。  
  
8.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)   
 [配置 MQSeries 适配器](../core/configuring-the-mqseries-adapter.md)