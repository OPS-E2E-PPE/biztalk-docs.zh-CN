---
title: 适配器宿主模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf9a8e6b-8c8d-47ec-b2a3-aed58206121d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f6603c07bc74cb904ad3eb88f50a3c7d2c60d09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361430"
---
# <a name="adapter-hosting-model"></a>适配器宿主模型
一般情况下 BizTalk 适配器的宿主 BizTalk 服务 Btsntsvc.exe。 这意味着，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理适配器的生存期。 还有一些情况下，如下所述，其他进程管理适配器。  
  
## <a name="in-process-adapters"></a>进程内适配器  
 由适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]称为进程内适配器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行以下操作适用于这些适配器：  
  
- 实例化适配器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已启动  
  
- 在初始化期间传递到适配器的适配器的传输代理  
  
- 适配器的请求提供服务  
  
- 终止在关闭的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在运行时将处理程序配置和终结点配置信息传递给适配器。 指定配置的其他方面，例如服务时段，用于定义在此期间启用适配器以处理请求的特定时间段。  
  
  BizTalk 服务可能会被手动关闭使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或通过使用服务控制管理器。 如果连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库会自动丢失该服务将回收其自身。  
  
  在典型的宿主模型中，接收端适配器和发送端适配器与 BizTalk 服务，以及消息引擎和业务流程引擎在同一进程中托管。 托管模型非常灵活，以便接收、 发送和业务流程的主机和的这些组合的分离。 在下图中，主机在同一进程中的所有三个执行。  
  
  由于宿主模型富于它重要开发适配器要记住发送时，接收适配器可能不会配置在同一主机中。 它们甚至可能配置为在不同计算机上运行。  
  
  ![](../core/media/regularadapterhostingmodel.gif "RegularAdapterHostingModel")  
  进程内适配器宿主模型  
  
## <a name="isolated-adapters"></a>独立的适配器  
 有托管 BizTalk 服务中接收适配器时的情况下不可能。 例如，Internet 信息服务 (IIS) 进程模型是由 IIS 管理 ASP.NET 应用程序和 ISAPI 扩展的生存期。 BizTalk SOAP 适配器必须运行在同一进程空间中作为 IIS 中，从而使其不可能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来控制 SOAP 适配器的任何实例的生存期。  
  
 对于这些类型的适配器没有另一个宿主模型可供即独立接收适配器或简称独立的适配器。 没有独立的发送适配器的概念。  
  
 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不能创建一个独立的适配器，适配器必须获取其自己的传输代理并传输代理注册自身。  
  
 下图说明了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]托管体系结构。 为了提升性能，独立主机结构尽量免除任何不必要的进程间通信。 由于独立的适配器和 BizTalk 消息引擎堆栈位于相同的过程中，没有任何进程间通信时该适配器调用消息引擎。 在该方案中，消息引擎和数据库之间是唯一的进程间通信，这是不可避免的。  
  
 ![](../core/media/isolatedadapters.gif "IsolatedAdapters")  
独立的适配器宿主模型  
  
## <a name="see-also"></a>请参阅  
 [适配器框架概述](../core/what-is-the-adapter-framework.md)