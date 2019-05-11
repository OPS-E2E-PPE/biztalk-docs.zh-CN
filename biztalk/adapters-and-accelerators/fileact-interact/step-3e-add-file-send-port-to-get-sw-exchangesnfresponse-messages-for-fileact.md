---
title: 步骤 3E:添加 FILE 发送端口为 FileAct 存储和转发方案，以捕获 Sw-exchangesnfresponse 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04bad2ab-1ea4-4602-9dee-5b9af9be3b93
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e77a6b8ded2a2a779155df621b3e25267b20370
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365378"
---
# <a name="step-3e-add-a-file-send-port-for-the-fileact-store-and-forward-scenario-to-capture-sw-exchangesnfresponse-messages"></a>步骤 3E:添加 FILE 发送端口为 FileAct 存储和转发方案，以捕获 Sw-exchangesnfresponse 消息
在开始此步骤之前，必须完成[步骤 3D:添加 FILEACT 发送端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)。  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a>若要添加 FILE 发送端口以捕获状态事件：  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。  
  
3.  右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
4.  在中**发送端口属性**窗口中，命名该发送端口，Tutorial_ GetStatusReports。  
  
5.  在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。  
  
6.  在中**FILE 传输属性**对话框中**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ StatusEvents，然后单击**确定**。  
  
7.  在中**发送端口属性**窗口中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**发送处理程序**|从下拉列表中，选择**BizTalkServerApplication**。|  
    |**发送管道**|从下拉列表中，选择**XMLTransmit**。|  
  
8.  在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**属性**|Select BTS.MessageType|  
    |**“运算符”**|选择 = =|  
    |**ReplTest1**|Type Sw-HandleFileEventRequest|  
    |**分组**|或|  
    |**属性**|选择 BTS。 MessageType|  
    |**“运算符”**|选择 = =|  
    |**ReplTest1**|类型 Sw-exchangesnfresponse|