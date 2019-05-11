---
title: 如何配置 Wcf-nettcp 发送处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84506c0d5045fca3f8c914e80bf062edf270eaa5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342106"
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a>如何配置 WCF-NetTcp 发送处理程序
使用以下过程配置 Wcf-nettcp 发送处理程序。  

### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a>若要更改全局变量的 Wcf-nettcp 发送处理程序  

1. 在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  

2. 在展开的适配器列表中，单击**WCF NetTcp**，在右窗格中，右键单击你想要配置，发送处理程序，再单击**属性**。  

3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择发送处理程序将关联的主机。  

4. 上**常规**选项卡上，单击**属性**。 上**发送处理程序**选项卡上，执行以下操作。  


   |        使用此选项         |                                                                                                                                                                                                                                                                          执行的操作                                                                                                                                                                                                                                                                          |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **最大连接数** | 指定的最大连接池中缓存的每个终结点的出站连接数。 这将限制为每个唯一的远程终结点缓存的连接数。 应设置此值大于最大期望缓存的任何唯一远程终结点的连接数。 如果活动出站连接数超过此最大值，则服务可能无法响应运行在此发送处理程序下的 Wcf-nettcp 发送端口。<br /><br /> 默认值为 10。 |


5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [使用 WCF 服务](../core/consuming-wcf-services.md)   
 [配置 WCF-NetTcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md)