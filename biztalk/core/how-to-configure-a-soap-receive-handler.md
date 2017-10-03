---
title: "如何配置 SOAP 接收处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SOAP adapters], receive handlers
- SOAP adapters, receive handlers
- receive handlers, SOAP adapters
ms.assetid: e1174381-f36c-4131-83b7-26bfa879802e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4054635a8ffa4e019f7db9513e5e20e997f7e291
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-soap-receive-handler"></a>如何配置 SOAP 接收处理程序
你可以配置 SOAP 接收处理程序设置通过使用 BizTalk Server 管理控制台。 如果你配置使用 BizTalk Server 管理控制台的适配器，不需要处理程序替代属性在 BizTalk 资源管理器中设置。  
  
### <a name="to-change-global-variables-for-the-soap-receive-handler"></a>若要更改全局变量 SOAP 接收处理程序  
  
1.  在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，单击**SOAP**，而是在右窗格中，右键单击你想要配置，接收处理程序，然后单击**属性**。  
  
3.  在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之相关联，该主机，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [配置 SOAP 适配器](../core/configuring-the-soap-adapter.md)   
 [使用 Web 服务](../core/consuming-web-services.md)