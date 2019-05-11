---
title: 如何配置 Wcf-nettcp 接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, global variables
- receive handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], global variables
- configuring [WCF-NetTcp adapters], receive handlers
ms.assetid: a4a283d1-21de-4d6b-9cb5-f2f9f823903b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48133eaa50fed0062b17d9e3b25fe180d7495f89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342196"
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a>如何配置 WCF-NetTcp 接收处理程序
使用以下过程配置 Wcf-nettcp 接收处理程序。  

### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a>若要更改全局变量的 Wcf-nettcp 接收处理程序  

1. 在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  

2. 在展开的适配器列表中，单击**WCF NetTcp**，在右窗格中，右键单击你想要配置，接收处理程序，再单击**属性**。  

3. 在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。  

4. 在中**常规**选项卡上，单击**属性**，然后在**接收处理程序**选项卡上，执行以下操作。  


   |        使用此选项         |                                                                                                                         执行的操作                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **最大连接数** | 指定的最大侦听器可以拥有等待接受的应用程序的连接数。 当超过此配额值时，会删除新的传入连接而不是等待接受。<br /><br /> 默认值为 10。 |


5. 单击“确定” 。  

## <a name="see-also"></a>请参阅  
 [配置 Wcf-nettcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md)   
 [发布 WCF 服务](../core/publishing-wcf-services.md)