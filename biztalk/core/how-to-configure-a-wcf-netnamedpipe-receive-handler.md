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
ms.openlocfilehash: e6a56fbeca1e2e6d362cef94dd6aa68161152b4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342225"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-handler"></a>如何配置 WCF-NetNamedPipe 接收处理程序
使用以下过程来配置 Wcf-netnamedpipe 接收处理程序。  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-receive-handler"></a>若要更改全局变量为 Wcf-netnamedpipe 接收处理程序  

1. 在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  

2. 在展开的适配器列表中，单击**Wcf-netnamedpipe**，在右窗格中，右键单击你想要配置，接收处理程序，再单击**属性**。  

3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。  

4. 在中**常规**选项卡上，单击**属性**。 上**接收处理程序**选项卡上，执行以下操作：  


   |        使用此选项         |                                                                                                                         执行的操作                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **最大连接数** | 指定的最大侦听器可以拥有等待接受的应用程序的连接数。 当超过此配额值时，会删除新的传入连接而不是等待接受。<br /><br /> 默认值为 10。 |


5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [发布 WCF 服务](../core/publishing-wcf-services.md)   
 [配置 WCF-NetNamedPipe 适配器](../core/configuring-the-wcf-netnamedpipe-adapter.md)