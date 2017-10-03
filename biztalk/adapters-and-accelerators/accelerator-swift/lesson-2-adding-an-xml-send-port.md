---
title: "第 2 课： 添加 XML 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, XML ports
- XML ports
ms.assetid: 03b2ee43-7874-4ef9-b716-8e16e96d8382
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06b110b911c8cba2dbc643928e8b97e3746935a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-adding-an-xml-send-port"></a>第 2 课： 添加 XML 发送端口
发送端口用于定义要发送的消息的方式。 在本课程中，你可以创建发送端口，以定义应如何发送 XML 消息。  
  
### <a name="to-add-an-xml-send-port"></a>若要添加 XML，将发送端口  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在发送端口属性对话框中，在**名称**框中，键入**MT103_XML_SendPort**。  
  
3.  在**传输**部分中，为**类型**框中，单击下拉列表中，，然后选择**文件**。  
  
4.  单击**配置**类型下拉列表右侧的按钮。  
  
5.  在文件传输属性对话框中，单击**浏览**。  
  
6.  在浏览文件夹对话框中，移动到**\<驱动器 >: \Labs\Outbound**文件夹，，然后单击**确定**。  
  
7.  在文件传输属性对话框中，确保**%MessageID%.xml**中输入**文件名**框中，并依次**确定**。  
  
8.  在发送端口属性对话框中，确保**BizTalkServerApplication**为选择**发送处理程序**框中，且**PassThruTransmit**为选择**发送管道**框。  
  
9. 在左窗格中，单击**筛选器**，然后执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**BTS。ReceivePortName**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**MT103_FlatFile_ReceivePort**。|  
    |**分组**|选择**和**。|  
  
10. 在下一步的属性行中单击，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**False**有效的消息。|  
  
    > [!NOTE]
    >  你添加**"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed = = False"**筛选器表达式子句，以便发送端口将发送仅成功分析和验证消息。 与使用本机接收管道不同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]反汇编程序，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]反汇编程序将挂起失败 （错误） 消息，但改为将其发布到 MessageBox 和标记为失败，使用提升的属性。 A4SWIFT 将附加的 XML 表示形式在发布到 MessageBox 之前收集到在失败消息的错误。  
    > 而不包括"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed = = False"筛选器表达式子句发送端口将发送所有消息： 已通过或失败。 有关失败的消息的订阅的详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。  
  
11. 单击**应用**，然后单击**确定**。  
  
12. 在 BizTalk Server 管理控制台中，在**发送端口**，右键单击**MT103_XML_SendPort**，然后单击**启动**。  
  
 继续执行[模块 6： 部署业务规则](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)。