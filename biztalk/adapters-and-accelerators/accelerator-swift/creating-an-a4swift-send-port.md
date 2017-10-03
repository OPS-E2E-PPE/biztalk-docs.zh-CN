---
title: "创建 A4SWIFT 发送端口 |Microsoft 文档"
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
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf24cb99643acc869123450ce14fd5050ee7408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-a4swift-send-port"></a>创建 A4SWIFT 发送端口
你必须创建发送端口以启用[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]若要将消息发送到 SWIFT 网络，如下图中所示。 此发送端口将将平面文件消息发送到的出站文件文件夹。 此发送端口用于处理消息修复和新提交功能。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")  
  
 **摘要**  
  
 创建并启动与以下属性和组件的静态单向发送端口：  
  
|属性 / 组件|设置|  
|-------------------------|-------------|  
|发送端口|静态单向端口|  
|传输类型|FILE|  
|目标文件夹 (地址 URI)|你想要从发送消息的文件夹名称|  
|文件名称 （地址 URI）|%MessageID%.txt|  
|筛选器|下表中所述|  
  
### <a name="to-add-the-sent-port"></a>若要添加的发送的端口  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在发送端口属性对话框中，在**名称**框中，键入发送端口的名称。  
  
3.  在**传输**部分中，为**类型**框中，单击下拉列表中，，然后选择**文件**。  
  
4.  单击**配置**类型下拉列表右侧的按钮。  
  
5.  在文件传输属性对话框中，单击**浏览**。  
  
6.  在浏览文件夹对话框中，移动到你想要从发送消息的文件夹。 单击 **“确定”**。  
  
    > [!NOTE]
    >  如果此文件夹不存在，则可以创建使用**新建文件夹**命令。  
  
7.  在**文件名**框中，键入**%MessageID%.txt**，然后单击**确定**。  
  
8.  在**发送端口属性**对话框框中，单击下拉列表**发送管道**框中，，然后选择你自定义发送管道。  
  
9. 在左窗格中，单击**筛选器**，然后执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**BTS。操作**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**A4SWIFT_MRSRCompleted**。|  
    |**分组**|选择**或者。**|  
    |**属性**|选择**BTS。操作**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**A4SWIFT_MRSRFailed**。|  
    |**分组**|选择**或**。|  
    |**属性**|选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|类型**True**。|  
  
10. 单击**应用**，然后单击**确定。**  
  
11. 在**发送端口**窗格中，右击发送端口，然后单击**启动**。