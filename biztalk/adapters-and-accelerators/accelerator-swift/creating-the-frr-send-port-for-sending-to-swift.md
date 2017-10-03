---
title: "创建 FRR 发送端口将发送到 SWIFT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cbda5d505f17f2dd7462cb0b16868a340f625c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a>创建用于将发送到 SWIFT FRR 发送端口
若要执行 FIN 响应对帐，你需要创建发送一条消息从发送端口[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 SWIFT 网络。  
  
 **摘要**  
  
 创建具有以下属性和组件发送端口：  
  
|属性 / 组件|设置|  
|-------------------------|-------------|  
|发送端口|静态单向端口|  
|传输类型|MQSeries|  
|队列定义 (MQSeries)|MQSeries 服务器队列管理器队列|  
|发送管道|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 FRR 创建的发送管道|  
|筛选器|下表中所示|  
  
### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a>若要添加自定义发送端口将发送到 SWIFT  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态一个 waySend 端口**。  
  
2.  在发送端口属性对话框中，在**名称**框中，键入发送端口，如 FRRSWIFTSendPort 的名称。  
  
3.  有关**类型**，选择**MQSeries**。  
  
4.  单击**配置**。  
  
5.  在 MQSeries 传输属性对话框中，单击**队列定义**，然后单击省略号 （） 按钮。  
  
6.  在队列定义对话框中，输入 MQSeries 服务器、 队列管理器和队列。 单击 **“确定”**。  
  
7.  在 MQSeries 传输属性对话框中，验证的属性是根据需要。 单击 **“确定”**。  
  
    > [!NOTE]
    >  有关 MQSeries 传输属性的详细信息，请参阅 MQSeries 文档。  
  
8.  在发送端口属性对话框中，为**发送处理程序**，验证是否已选中 BizTalkServerApplication。  
  
9. 有关**发送管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 FRR 创建的发送管道。  
  
10. 单击**筛选器**在左窗格中，然后再执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**False**。|  
    |**分组**|选择**和**。|  
    |**属性**|类型**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**True**。|  
  
11. 单击**应用**，然后单击**确定**。  
  
12. 发送端口中，右键单击，然后单击**启动**。