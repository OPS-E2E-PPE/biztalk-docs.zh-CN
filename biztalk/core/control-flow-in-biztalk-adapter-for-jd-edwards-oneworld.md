---
title: 控制用于 JD Edwards OneWorld 的 BizTalk 适配器中的流 |Microsoft Docs
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
ms.openlocfilehash: 6f6514a62a90fd2088c494ab2cc7384ceb0b59a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354529"
---
# <a name="control-flow-in-biztalk-adapter-for-jd-edwards-oneworld"></a>用于 JD Edwards OneWorld 的 BizTalk 适配器中的控制流
本主题讨论用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器中的设计时和运行时控制流。  
  
## <a name="design-time-flow"></a>设计时流  
 当适配器打开时 （从传输属性对话框中使用的凭据和系统信息） 时，创建和共用的 JD Edwards OneWorld 应用程序业务函数的一个或多个实例。 当您浏览适配器向导中的命名空间时，显示业务功能的列表。 单击业务函数显示其逻辑方法以及方法签名。  
  
## <a name="run-time-flow"></a>运行时流  
 创建 JD Edwards OneWorld 业务函数实例和组建成池供每个线程。 方法调用提交到一种业务服务，该方法的元数据是使用 JD Edwards OneWorld 应用程序业务函数; 读取但是，如果已缓存的元数据的方法，业务功能，使用缓存的信息并将调用相应方法。 在运行时动态构造 JD Edwards OneWorld 接口层。 它是通过接口层用于 JD Edwards OneWorld 的 BizTalk 适配器支持调用和数据转换。  
  
 用于 JD Edwards OneWorld 的 BizTalk 适配器将映射 JD Edwards OneWorld 应用程序的方法签名的接口的描述允许 BizTalk Server 与这些接口描述进行交互。  
  
 该适配器能够在企业中的应用程序能够通过扩展从一个或多个以下的窗体中的应用程序的功能与 JD Edwards OneWorld 应用程序进行交互：  
  
- 本机数据格式  
  
- 过程  
  
- 方法  
  
- 消息  
  
- 属性  
  
- 应用程序接口  
  
  在运行时，用于 JD Edwards OneWorld 的 BizTalk 适配器生成应用程序接口与 JD Edwards OneWorld 进行交互的客户端应用程序的说明。 适配器可以创建、 删除和根据需要以在应用程序中执行计算并直接调用的方法调用的业务对象。 对 JD Edwards OneWorld 的所有调用都都同步调用。 适配器接收来自 BizTalk Server 的 XML 消息、 将消息封装在 SOAP 信封，并将从 SOAP 消息的调用的数据转换为 Java 类型。  
  
  返回以下类似的过程发送回复：  
  
1.  Java 类型转换成 SOAP 消息中。  
  
2.  SOAP 消息转换为 XML 消息中。  
  
3.  XML 消息提交到 BizTalk Server 进行进一步处理。  
  
### <a name="apartment-threading-of-business-functions"></a>单元线程处理的业务功能  
 JD Edwards OneWorld 业务功能和任何实例，仅可以在其中创建或获取它的线程上使用。 这称为*单元线程处理*。 用于 JD Edwards OneWorld 的 BizTalk 适配器的连接池 framework 管理可用连接的池。  
  
### <a name="connection-pooling"></a>连接池  
 连接池提高调用的性能，方法是让服务器系统之间的连接保持打开状态并重新使用它们而不每次调用后将其关闭。 用于 JD Edwards OneWorld 的 BizTalk 适配器可以连接池内特定登录 Id，但还可以跨所有池保持的连接总数量的关键控制。  
  
 任何新的业务函数实例使用的线程在其创建，并且每次操作后销毁该实例。 对业务功能的所有 JD Edwards OneWorld 调用都是无状态;但是，在操作时，适配器可确保业务功能使用正确的线程上。  
  
## <a name="see-also"></a>请参阅  
 [开发应用程序](../core/developing-applications3.md)   
 [规划和体系结构](../core/planning-and-architecture17.md)