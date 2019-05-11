---
title: 了解面向服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, background information
- service solutions, about service solutions
- service solution tutorial, about service solution tutorial
- Service Oriented Architecture (SOA)
ms.assetid: 56a2ad90-74bb-489a-ab1d-900f3bea3d64
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7114ab32084abd45eb6169e1bb4e54bcf3b5f25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292711"
---
# <a name="understanding-the-service-oriented-solution"></a>了解面向服务的解决方案
面向服务的解决方案提供的信用余额报告应用程序设计为服务。 应用程序，反过来，使用三个后端应用程序，作为服务公开，获取信用余额所需的信息。  
  
 面向服务体系结构 (SOA) 是一种方法，与构建分布式的系统部分重叠。 面向服务的方法有几个特性：  
  
- 松散耦合。 应用程序的业务逻辑是独立于处理服务的逻辑。  
  
- 可发现。 应为应用程序以查找该服务的机制。  
  
- 合同。 服务的接口实现的用户和服务之间的约定。  
  
  尽管文献资料通常将面向服务的方法视为与 web services 同义，但它们不一定是同义词。 Web services 提供的极具吸引力的方法来实现面向服务的解决方案，但可以使用其他技术，如.NET 远程处理，以创建服务。  
  
  有关面向服务体系结构的详细信息，请参阅"服务接口"处[ http://go.microsoft.com/fwlink/?LinkId=46185 ](http://go.microsoft.com/fwlink/?LinkId=46185)和"面向服务的集成"， [ http://go.microsoft.com/fwlink/?LinkId=46186 ](http://go.microsoft.com/fwlink/?LinkId=46186)。  
  
## <a name="reader-guidance"></a>读者指南  
 此解决方案的文档假定您熟悉[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 它还假定您了解有关企业应用程序集成和 web 服务的基本概念。  
  
 此外，若要阅读并遵循开发人员文档，应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并熟悉如何执行以下任务： 创建项目、 设置引用以及调试和测试 BizTalk解决方案。  
  
## <a name="credit-card-reporting-at-woodgrove-bank"></a>报告在 Woodgrove Bank 的信用卡  
 面向服务的体系结构解决方案是报告服务的 Woodgrove Bank 的信用卡余额。 尽管银行是虚构的但方案并不是-该方案基于实际的已部署的客户应用程序。  
  
 在方案中，对信用卡余额的请求来自两个方面：  
  
- 交互式语音应答 (IVR) 应用程序。  
  
- Web 页面或自定义客户端应用程序之类的交互式客户端。  
  
  该解决方案接收来自 IVR 应用程序通过 MQSeries 的请求。 它处理来自交互式客户端通过使用 HTTP 和 SOAP 的 web 服务请求。  
  
  新的面向服务应用程序通常需要使用的旧版应用程序使用较旧技术，同时也与现代应用程序，如使用 web 服务的网站的体系结构。 该方案进行建模这一现实世界要求-IVR 应用程序表示旧版应用程序，客户服务客户端应用程序时，是现代。  
  
  Woodgrove Bank 应用程序使用三个后端，从旧系统，用于对请求作出响应的数据：  
  
- 一个提供信用总限额的应用程序。 这是大型机上的 SAP 系统。  
  
- 挂起事务系统报告事务挂起针对帐户的总金额的一个。 此系统为大型机或 AS / 400 系统。 该解决方案使用 web 服务和 Microsoft Host Integration Server (HIS) 与大型机或进行通信 / 400 系统。  
  
- 付款跟踪系统，用于提供对系统所做的最近付款。 可以使用 MQSeries 达到付款跟踪系统。  
  
  收集并编译了原有系统中的信息后, 解决方案将响应发送回原始应用程序，因此，给客户。  
  
## <a name="business-requirements"></a>业务要求  
 由于信用报告应用程序实时响应客户请求，它必须具有较低的延迟，若要快速处理请求。 此外，它还必须能够处理大量的并发请求数。 该解决方案使用敏感信息和一个公共接口，因此安全性十分重要。 最后，该服务必须是可靠。  
  
 有关解决方案如何满足这些要求的信息，请参阅[开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)。  
  
## <a name="performance-characteristics"></a>性能特征  
 为了满足业务要求，该方案具有以下性能特征：  
  
-   每秒 40 个传入请求的持续的吞吐量。  
  
-   每秒 100 个传入请求的峰值吞吐量。  
  
-   90%的请求 （传入和传出 BizTalk Server) 在 1000 毫秒内提供服务。  
  
-   95%的请求 （传入和传出 BizTalk Server) 在 2000 毫秒内提供服务。  
  
-   100%的请求 （传入和传出 BizTalk Server) 在 5000 毫秒内提供服务。  
  
> [!NOTE]
>  这些时间不包括后端系统的延迟时间。  
  
## <a name="three-versions-of-the-solution"></a>三个版本的解决方案  
 有三个版本的解决方案：  
  
- 存根版本将替换所有后端系统使用软件存根。 这些存根模拟后端系统。 此版本提供了部署并运行该解决方案在单台计算机上的快速方法。  
  
- 适配器版本使用 BizTalk 适配器来连接到后端系统。 此版本是如何首先想象来实现此解决方案。 但是，将消息发送到后端系统使用的适配器有明显的延迟在获取响应。 虽然适配器本身无法提供延迟非常低，BizTalk Server 的分布式的结构要求适配器与使用 messagebox 的业务流程主机实例进行通信。 这给数据库带来了往返行程，从而影响延迟时间。  
  
- 内联版本使用直接与后端系统进行通信的内联代码替换适配器。 该解决方案的内联版本具有最低的延迟和最高的吞吐量。  
  
  部署指南为构建和部署的解决方案，所有三个版本，以及提供一种方法，在每个版本中，以模拟通过 HIS 连接到挂起事务系统提供说明。 有关生成和部署解决方案的信息，请参阅[部署面向服务的解决方案](../core/deploying-the-service-oriented-solution.md)。  
  
## <a name="see-also"></a>请参阅  
 [面向服务的解决方案](../core/service-oriented-solution.md)