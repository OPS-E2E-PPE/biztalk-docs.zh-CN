---
title: 如何配置 MQSeries 适配器发送和接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MQSeries adapters
- configuring [MQSeries adapters], receive handlers
- MQSeries adapters, send handlers
- MQSeries adapters, receive handlers
- send handlers, MQSeries adapters
- configuring [MQSeries adapters], send handlers
ms.assetid: e1cfc415-50d2-440b-9301-ad69da28ad3e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c97b109146dadd1a5cc90710f00c9c8f6620f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988894"
---
# <a name="how-to-configure-mqseries-adapter-send-and-receive-handlers"></a>如何配置 MQSeries 适配器发送和接收处理程序
你可以配置某些属性的发送和接收处理程序，MQSeries 适配器通过 BizTalk Server 管理控制台。 该过程中所述[如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)建立大部分发送处理程序属性的值。  

## <a name="to-configure-the-send-and-receive-handlers"></a>若要配置发送和接收处理程序  
 请执行以下步骤来配置发送和接收的 MSQeries 适配器处理程序：  

1. 单击**启动**，依次指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，单击此项可展开**平台设置**，然后单击到展开**适配器**。  

3. 在展开的适配器列表中，选择**MQSeries**。 列表发送和接收处理程序绑定到 MQSeries 适配器显示在右窗格中。  

4. 在右窗格中，双击发送或接收处理程序，在右窗格中。  

5. 在中**适配器处理程序属性**对话框中，单击**属性**。  

6. 在中**MQSeries 传输属性**对话框框中，执行以下操作：  


   |           使用此选项            |                                    执行的操作                                    |
   |-------------------------------|----------------------------------------------------------------------------------|
   | **批中最大消息数** | 在批处理中设置的最大消息数。 仅适用于发送处理程序。 |
   |          **Server**           |      运行 MQSeries Server for Windows 的计算机的名称。       |


7. 单击“确定” 。  

   > [!NOTE]
   >  “接收位置”和“发送端口”属性将替代“接收处理程序”和“发送处理程序”的值。 如果“接收位置”或“发送端口”属性未设置值，则适配器将分别采用“接收处理程序”和“发送处理程序”的值。  

8. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)   
 [配置 MQSeries 适配器](../core/configuring-the-mqseries-adapter.md)