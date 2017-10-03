---
title: "如何配置 WCF NetTcp 发送处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], send handlers
- WCF-NetTcp adapters, global variables
- configuring [WCF-NetTcp adapters], global variables
ms.assetid: c60fe03d-7e11-4e08-9a24-8ff443eee9c1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02451dba6755e4db0c10d7cce20141468a67694f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-nettcp-send-handler"></a>如何配置 WCF-NetTcp 发送处理程序
可使用以下过程配置 WCF-NetTcp 发送处理程序。  
  
### <a name="to-change-global-variables-for-a-wcf-nettcp-send-handler"></a>更改 WCF-NetTcp 发送处理程序的全局变量  
  
1.  在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**WCF NetTcp**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择发送处理程序将与之关联的主机。  
  
4.  上**常规**选项卡上，单击**属性**。 上**发送处理程序**选项卡上，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**最大连接数**|为在连接池中缓存的各终结点指定最大出站连接数。 这将限制为每个唯一的远程终结点缓存的连接数。 对于每个唯一的远程终结点，你应该将此值设置为一个大于最大期望缓存连接数的值。 如果活动的出站连接的数目超过此最大值，则服务可能不响应运行在此发送处理程序下的 WCF-NetTcp 发送端口。<br /><br /> 默认值为 10。|  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [使用 WCF 服务](../core/consuming-wcf-services.md)   
 [配置 WCF NetTcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md)