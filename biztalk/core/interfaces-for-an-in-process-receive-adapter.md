---
title: 接收适配器的进程内的接口 |Microsoft Docs
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
ms.openlocfilehash: 1a222f41d28b57053c192db3235e2fa7f4f710ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381732"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a>接收适配器的进程内的接口
消息引擎实例化和配置进程内适配器，并且传入传输代理以便允许适配器访问其功能。 若要启用配置和绑定到传输代理，适配器必须实现以下配置接口：  
  
- **IBTTransport**  
  
- **IBTTransportControl**  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
  （可选） 如果适配器想要接收处理程序信息在初始化过程中它需要实现**IPersistPropertyBag**。  
  
  消息引擎创建的适配器实例，初始化它，并设置的配置接收位置。 消息引擎将属性包传递给适配器**AddReceiveEndpoint**方法调用。 属性包包含接收位置和接收处理程序的配置。 配置存储在数据库中的 XML 样式的属性包形式。 消息引擎读取 XML 并解除冻结从 XML 属性包。 至少一个终结点后 （接收位置） 添加，适配器可以开始提交消息。  
  
> [!NOTE]
>  适配器应不会阻止消息引擎调用如**IBTTransportControl.Initialize**， **ipersistpropertybag.load 这样**，和**IBTTransportConfig.AddReceiveEndpoint**. 执行过多的处理中这些调用将会影响服务启动时间。  
  
 下图显示了接收适配器创建过程中涉及的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")  
工作流的进程内接收适配器  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [接口独立接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [接收适配器的支持批的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [接收适配器的接口的事务性批处理支持](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [同步请求-响应接收适配器的接口](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)