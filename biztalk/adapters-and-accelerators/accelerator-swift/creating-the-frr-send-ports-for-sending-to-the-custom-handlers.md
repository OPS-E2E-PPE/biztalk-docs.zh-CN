---
title: "创建 FRR 发送端口将发送到自定义处理程序 |Microsoft 文档"
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
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6326ae6e82e819d3cdf76ecc4d81e2a377ea65
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a>创建 FRR 发送端口将发送到自定义处理程序
若要执行 FIN 响应对帐，你需要创建一系列发送端口，其中每个发送一条消息 （原始消息或响应） 从[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到处理相关的消息的自定义处理程序。  
  
 **摘要**  
  
 创建具有以下属性和组件，按照 BTS 值区分每个发送端口的一系列。筛选器中的操作：  
  
|属性 / 组件|设置|  
|-------------------------|-------------|  
|发送端口|静态单向端口|  
|传输类型|FILE|  
|目标文件夹 (地址 URI)|你想要将消息发送到文件夹|  
|文件名称 (地址 URI)|%MessageID%.txt|  
|发送管道|[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].BizTalk.DefaultPipelines。 PassThruTransmit|  
|筛选器|下表中所示|  
  
 通过 BTS 的值来区分不同的消息的发送端口。发送端口的筛选器中的操作。  
  
### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a>若要添加 FRR 发送端口将发送到自定义处理程序  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态一个 waySend 端口**。  
  
2.  在发送端口属性对话框中，在**名称**框中，键入发送端口，如 FRRCustomHandlersSendPort 的名称。  
  
3.  有关**类型**，选择**文件**。  
  
4.  单击**配置**。  
  
5.  在文件传输属性对话框中，单击**浏览**。  
  
6.  在浏览文件夹对话框中，移动到你想要从发送消息的文件夹。 单击 **“确定”**。  
  
    > [!NOTE]
    >  如果此文件夹不存在，则可以创建使用**新建文件夹**命令。  
  
7.  在**文件名**框中，键入**%MessageID%.txt**，然后单击**确定**。  
  
    > [!NOTE]
    >  你可以创建用于每种类型的消息的不同文件夹。  
  
8.  在发送端口属性对话框中的发送处理程序，验证**BizTalkServerApplication**选择。  
  
9. 有关**发送管道**，选择**PassThruTransmit**。  
  
10. 单击**筛选器**在左窗格中，然后再执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**A4SWIFT_FrrService**。|  
    |**分组**|**And**|  
    |**属性**|选择**BTS。操作**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|BTS 之一的类型。下表中的操作值。|  
  
     有关 BTS。操作中，输入以下值之一：  
  
    |消息类型|BTS。操作值|  
    |------------------|-------------------------|  
    |所有类别 0 到 9 SWIFT FIN 消息类型|**A4SWIFT_FrrSendMTMsg**|  
    |MQ 系列平移/NAN （MQ 系列传输级 ACK/否认）|**A4SWIFT_FrrSendTransport**|  
    |MT010 （未送达警告）|**A4SWIFT_FrrSend010NDW**|  
    |MT011 （传递通知）|**A4SWIFT_FrrSend011Delivered**|  
    |MT012 （发件人通知）|**A4SWIFT_FrrSend012SenderACK**|  
    |MT015 （DNK 或延迟的否认）|**A4SWIFT_FrrSend015DNK**|  
    |MT019 （中止通知）|**A4SWIFT_FrrSend019Abort**|  
    |MTS21_FIN_ACKNAK （发送由 LT (ACK) 的 FIN 消息的确认|**A4SWIFT_FrrSendS21ACK**|  
    |MTS21_FIN_ACKNAK （否定确认发送由 LT （否认） 的 FIN 消息的|**A4SWIFT_FrrSendS21NAK**|  
  
11. 为类别 0 到 9 SWIFT FIN 成功不发送的消息执行以下**筛选器**窗格中：  
  
    > [!NOTE]
    >  **A4SWIFT_FRRFailedReason**应分组中的以下筛选器的属性。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**A4SWIFT_FrrService**。|  
    |**分组**|**And**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**True**。|  
    |**分组**|**And**|  
    |**属性**|选择**BTS。操作**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**A4SWIFT_FrrSendMTMsg**。|  
    |**分组**|**And**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型 *\<NAKErrorCode\>*，如"Y01"。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**TimedOut**。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**TransportError**。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**DelayedNAK**。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**AbortMessage**。|  
  
12. 单击**应用**，然后单击**确定**。  
  
13. 发送端口中，右键单击，然后单击**启动**。  
  
14. 重复步骤 2 至 13 以创建所需的每种消息类型发送端口。