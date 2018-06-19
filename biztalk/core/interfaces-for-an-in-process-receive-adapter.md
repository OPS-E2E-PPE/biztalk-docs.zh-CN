---
title: 进程内的接口接收适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7135471700cf640f61b56506ad159b5c47c7d877
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257645"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a>进程内的接口接收适配器
消息引擎实例化和配置进程内适配器，并且传入传输代理以便允许适配器访问其功能。 若要启用对传输代理的配置和绑定，适配器必须实现以下配置接口：  
  
-   **IBTTransport**  
  
-   **IBTTransportControl**  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
 （可选） 如果适配器想要接收处理程序信息在初始化过程中它需要实现**IPersistPropertyBag**。  
  
 消息引擎将创建适配器的某一实例、初始化该实例并设置接收位置配置。 The Messaging Engine 传送给适配器上的属性包**AddReceiveEndpoint**方法调用。 该属性包包含接收位置和接收处理程序的配置。 该配置以 XML 样式的属性包形式存储于数据库中。 消息引擎读取 XML 并从 XML 解除冻结属性包。 在添加至少一个终结点（接收位置）后，该适配器可以开始提交消息。  
  
> [!NOTE]
>  适配器应不会阻止 Messaging Engine 如调用**IBTTransportControl.Initialize**， **IPersistPropertyBag.Load**，和**IBTTransportConfig.AddReceiveEndpoint**. 执行过多的处理中这些调用将会影响服务启动时间。  
  
 下图显示在创建进程内接收适配器时涉及的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")  
进程内接收适配器的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [一个独立的接口接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [批处理支持的接口接收适配器](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [批处理支持为一个事务性接口接收适配器](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [接口同步请求-响应接收适配器](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)