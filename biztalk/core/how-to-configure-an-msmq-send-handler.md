---
title: "如何配置 MSMQ 发送处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feacaec9d2794cf8806fa5156fe64b7290699faa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-msmq-send-handler"></a>如何配置 MSMQ 发送处理程序
使用下面的步骤可以更改 MSMQ 发送处理程序的全局变量。  
  
> [!NOTE]
>  每个主机只能有一个关联的发送处理程序。  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a>通过使用 BizTalk Server 管理控制台更改 MSMQ 发送处理程序的全局变量  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**MSMQ**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择的主机发送处理程序将与之相关联，并依次**属性**。  
  
4.  在**MSMQ 传输属性**对话框框中，输入一个值**批大小**。  
  
     MSMQ 发送处理程序会将消息发送到使用指定的目标队列**批大小**参数。 默认值**批大小**值为 5。  
  
5.  单击**确定**单击**确定**以关闭**适配器处理程序属性**对话框。