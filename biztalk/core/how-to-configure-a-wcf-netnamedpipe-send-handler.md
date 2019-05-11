---
title: 如何配置 Wcf-netnamedpipe 发送处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, global adapters
- configuring [WCF-NetNamedPipe adapters], global adapters
- send handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], send handlers
ms.assetid: 1f281649-d09f-44eb-8af5-1f83233fab60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69941385bdadc3670a88fd48c37fb77e22657752
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342220"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-handler"></a>如何配置 WCF-NetNamedPipe 发送处理程序
使用以下过程来配置 Wcf-netnamedpipe 发送处理程序。  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-send-handler"></a>若要更改全局变量为 Wcf-netnamedpipe 发送处理程序  

1. 在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  

2. 在展开的适配器列表中，单击**Wcf-netnamedpipe**，在右窗格中，右键单击你想要配置，发送处理程序，再单击**属性**。  

3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择发送处理程序将关联的主机。  

4. 在中**常规**选项卡上，单击**属性**。 上**发送处理程序**选项卡上，执行以下操作：  


   |        使用此选项         |                                                                                                                                                                                                                                                                             执行的操作                                                                                                                                                                                                                                                                             |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **最大连接数** | 指定的最大连接池中缓存的每个终结点的出站连接数。 这将限制为每个唯一的远程终结点缓存的连接数。 应设置此值大于最大期望缓存的任何唯一远程终结点的连接数。 如果活动出站连接数超过此最大值，则服务可能无法响应运行在此发送处理程序下的 Wcf-netnamedpipe 发送端口。<br /><br /> 默认值为 10。 |


5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [使用 WCF 服务](../core/consuming-wcf-services.md)   
 [配置 WCF-NetNamedPipe 适配器](../core/configuring-the-wcf-netnamedpipe-adapter.md)