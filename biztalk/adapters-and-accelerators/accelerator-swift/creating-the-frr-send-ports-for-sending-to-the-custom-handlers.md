---
title: 创建 FRR 发送端口将发送到自定义处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeddd040dd3cfb0c423eea149a81a1395a468087
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378387"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a>创建 FRR 发送端口将发送到自定义处理程序
若要执行 FIN 响应对帐，需要创建一系列的发送端口，其中每个将发送一条消息 （原始消息或响应） 从[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到的自定义处理程序处理相关的消息。  

 **摘要**  

 创建具有以下属性和组件，BTS 值进行区分每个发送端口的一系列。在筛选器中的操作：  


|        属性 / 组件        |                                             设置                                              |
|----------------------------------|--------------------------------------------------------------------------------------------------|
|            发送端口             |                                       静态单向端口                                        |
|          传输类型          |                                               FILE                                               |
| 目标文件夹 (地址 URI) |                         你想要发送到的文件夹                          |
|     文件名 (地址 URI)      |                                         %MessageID%.txt                                          |
|          发送管道           | Microsoft。BizTalk.DefaultPipelines。 PassThruTransmit |
|             筛选器              |                                   下表中所示                                   |

 通过 BTS 的值来区分不同的消息的发送端口。发送端口的筛选器中的操作。  

### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a>若要添加用于将发送到自定义处理程序的 FRR 发送端口  

1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态一个 waySend 端口**。  

2.  在发送端口属性对话框中，在**名称**框中，键入发送端口，例如 FRRCustomHandlersSendPort 的名称。  

3.  有关**类型**，选择**文件**。  

4.  单击**配置**。  

5.  在 FILE 传输属性对话框中，单击**浏览**。  

6.  在浏览文件夹对话框中，转至你想要从发送消息的文件夹。 单击“确定” 。  

    > [!NOTE]
    >  如果此文件夹不存在，则可以创建使用其**建立新文件夹**命令。  

7.  在中**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。  

    > [!NOTE]
    >  可以创建每种类型的消息的不同文件夹。  

8.  在发送端口属性对话框中，对于发送处理程序，验证是否**BizTalkServerApplication**处于选中状态。  

9. 有关**发送管道**，选择**PassThruTransmit**。  

10. 单击**筛选器**中左窗格中，然后执行以下操作：  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型**A4SWIFT_FrrService**。|  
    |**分组**|**And**|  
    |**属性**|选择**BTS。操作**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|一个 BTS 的类型。下表中的操作值。|  

     为 BTS。操作中，输入以下值之一：  

    |消息类型|BTS。操作值|  
    |------------------|-------------------------|  
    |所有类别 0 到 9 SWIFT FIN 消息类型|**A4SWIFT_FrrSendMTMsg**|  
    |MQ 系列平移/NAN (MQ Series 传输级 ACK/NAK)|**A4SWIFT_FrrSendTransport**|  
    |MT010 （未送达警告）|**A4SWIFT_FrrSend010NDW**|  
    |MT011 （送达通知）|**A4SWIFT_FrrSend011Delivered**|  
    |MT012 （发件人通知）|**A4SWIFT_FrrSend012SenderACK**|  
    |MT015 （DNK 或延迟的 NAK）|**A4SWIFT_FrrSend015DNK**|  
    |MT019 （中止通知）|**A4SWIFT_FrrSend019Abort**|  
    |MTS21_FIN_ACKNAK （发送由 LT (ACK) 的 FIN 消息确认|**A4SWIFT_FrrSendS21ACK**|  
    |MTS21_FIN_ACKNAK （否定确认发送由 LT (NAK) 的 FIN 消息|**A4SWIFT_FrrSendS21NAK**|  

11. 对于未成功发送，类别 0 到 9 SWIFT FIN 消息执行以下**筛选器**窗格：  

    > [!NOTE]
    >  **A4SWIFT_FRRFailedReason**应分组下面的筛选器中的属性。  

    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型**A4SWIFT_FrrService**。|  
    |**分组**|**And**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型 **，则返回 True**。|  
    |**分组**|**And**|  
    |**属性**|选择**BTS。操作**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型**A4SWIFT_FrrSendMTMsg**。|  
    |**分组**|**And**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型 *\<NAKErrorCode\>*，如"Y01"。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型**TimedOut**。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型**TransportError**。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型**DelayedNAK**。|  
    |**分组**|**Or**|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。|  
    |**“运算符”**|选择 ==。|  
    |**ReplTest1**|类型**AbortMessage**。|  

12. 单击**Apply**，然后单击**确定**。  

13. 右键单击该发送端口，然后依次**启动**。  

14. 重复步骤 2 到 13，创建所需的每种消息类型的发送端口。