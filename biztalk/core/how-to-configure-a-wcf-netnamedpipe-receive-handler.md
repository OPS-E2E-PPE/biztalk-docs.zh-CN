---
title: 如何配置 Wcf-netnamedpipe 接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [WCF-NetNamedPipe adapters], global variables
- receive handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], receive handlers
- WCF-NetNamedPipe adapters, global variables
ms.assetid: f7ab2228-1049-40f0-87f7-6330a8f40cfe
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2601bcd6e68f8752699474c4d02295d353064083
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022899"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-handler"></a>如何配置 WCF-NetNamedPipe 接收处理程序
可使用以下过程配置 WCF-NetNamedPipe 接收处理程序。  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-receive-handler"></a>更改 WCF-NetNamedPipe 接收处理程序的全局变量  

1. 在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  

2. 在展开的适配器列表中，单击**Wcf-netnamedpipe**，在右窗格中，右键单击你想要配置，接收处理程序，再单击**属性**。  

3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。  

4. 在中**常规**选项卡上，单击**属性**。 上**接收处理程序**选项卡上，执行以下操作：  


   |        使用此选项         |                                                                                                                         执行的操作                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **最大连接数** | 指定监听程序可以拥有的等待应用程序接受的最大连接数。 在超过此配额值时，将删除新的传入连接，而不是等待接受这些连接。<br /><br /> 默认值为 10。 |


5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [发布 WCF 服务](../core/publishing-wcf-services.md)   
 [配置 WCF-NetNamedPipe 适配器](../core/configuring-the-wcf-netnamedpipe-adapter.md)