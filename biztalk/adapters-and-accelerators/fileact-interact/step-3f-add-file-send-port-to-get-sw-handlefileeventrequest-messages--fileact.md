---
title: '单步 3F: FileAct 实时方案，以捕获软件 HandleFileEventRequest 消息的文件发送端口添加 |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b7594b0-0443-41b7-ae04-55b2cc8bf90e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1d70c338696f1c4455161a88c8d2988e0ea0ccb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225525"
---
# <a name="step-3f-add-a-file-send-port-for-the-fileact-real-time-scenario-to-capture-sw-handlefileeventrequest-messages"></a>单步 3F： 添加 FileAct 实时方案，以捕获软件 HandleFileEventRequest 消息文件发送端口
在开始此步骤之前，必须完成[步骤 3E: FileAct 实时方案将文件发送端口添加到捕获 Sw:ExchangeFileResponse 消息](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a>若要添加捕获状态事件的文件发送端口：  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
4.  在**发送端口属性**窗口中，名称发送端口 Tutorial_ GetStatusReports。  
  
5.  在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ StatusEvents，然后单击**确定**。  
  
7.  在**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中选择**XMLTransmit**。|  
  
8.  在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|选择 BTS。 MessageType|  
    |**运算符**|选择 = =|  
    |**值**|类型软件 HandleFileEventRequest|  
    |**分组**|或|  
    |**属性**|选择 BTS。 MessageType|  
    |**运算符**|选择 = =|  
    |**值**|类型软件 ExchangeSnFResponse|