---
title: 控制流中的 BizTalk Adapter 博士 Edwards OneWorld |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection pooling
- control flows
- apartment threading
- apartment threading, business functions
ms.assetid: 1ec865d0-2257-453b-9230-1f3787ebac38
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fc5a8be6516b61c4049242952967ce939513e9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237973"
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a>控制 JD Edwards OneWorld 的 BizTalk 适配器中的流
本主题讨论了适用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器中的设计时间和运行时间控制流。  
  
## <a name="design-time-flow"></a>设计时流  
 打开适配器时（使用“传输属性”对话框中的凭据和系统信息），将创建并轮询一个或多个 JD Edwards OneWorld 应用程序业务函数实例。 浏览适配器向导中的命名空间时，显示业务功能的列表。 单击业务函数显示其逻辑的方法以及方法签名。  
  
## <a name="run-time-flow"></a>运行时流  
 将创建并放入池中为每个线程博士 Edwards OneWorld 业务功能的实例。 当方法调用提交至业务服务时，使用博士 Edwards OneWorld 应用程序业务函数; 读取方法的元数据但是，如果已缓存方法的元数据，业务功能将使用缓存的信息，然后将相应的方法调用。 在运行时，动态构造博士 Edwards OneWorld 接口层。 它是通过接口层用于博士 Edwards OneWorld 的 BizTalk Adapter 支持调用和数据转换。  
  
 用于博士 Edwards OneWorld 的 BizTalk Adapter 将映射博士 Edwards OneWorld 应用程序，调用的方法签名的接口说明允许 BizTalk Server 与这些接口说明进行交互。  
  
 适配器使企业中的应用程序可以通过扩展从一个或多个以下的窗体中的应用程序的功能与博士 Edwards OneWorld 应用程序进行交互：  
  
-   本机数据格式  
  
-   过程  
  
-   方法  
  
-   消息  
  
-   属性  
  
-   应用程序接口  
  
 在运行时，用于博士 Edwards OneWorld 的 BizTalk Adapter 生成与博士 Edwards OneWorld 交互的客户端应用程序的应用程序接口的描述。 该适配器可以创建、 删除和调用业务对象，如需要应用程序中执行计算并直接调用方法。 所有调入博士 Edwards OneWorld 都是同步调用。 适配器从 BizTalk Server 接收的 XML 消息，将消息放入 SOAP 信封，将从 SOAP 消息进行的调用的数据转换为 Java 类型。  
  
 回复发送回遵循类似的过程：  
  
1.  Java 类型被转换为 SOAP 消息。  
  
2.  SOAP 消息转换为 XML 消息。  
  
3.  XML 消息进行进一步处理提交给 BizTalk Server。  
  
### <a name="apartment-threading-of-business-functions"></a>单元线程处理的业务函数  
 博士 Edwards OneWorld 业务功能和任何实例，仅可在其中创建或获取线程上。 这称为*单元线程处理*。 博士 Edwards OneWorld 的 BizTalk 适配器的连接池 framework 管理的池的可用连接。  
  
### <a name="connection-pooling"></a>连接池  
 连接池可以调用的性能提高通过使与服务器系统的连接打开并重新使用它们而不每次调用后将其关闭。 博士 Edwards OneWorld 的 BizTalk 适配器可以在特定的登录 Id，连接池，同时仍然跨所有池保留的连接总数的关键控件。  
  
 任何新的业务函数实例使用的线程创建，且每次操作后销毁实例。 对业务功能的所有博士 Edwards OneWorld 调用都是无状态;但是，在操作时，适配器可以确保业务功能使用正确线程上。  
  
## <a name="see-also"></a>另请参阅  
 [开发应用程序](../core/developing-applications3.md)   
 [规划和体系结构](../core/planning-and-architecture17.md)