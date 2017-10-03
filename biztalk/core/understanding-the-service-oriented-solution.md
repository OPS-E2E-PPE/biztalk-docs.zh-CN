---
title: "了解服务面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, background information
- service solutions, about service solutions
- service solution tutorial, about service solution tutorial
- Service Oriented Architecture (SOA)
ms.assetid: 56a2ad90-74bb-489a-ab1d-900f3bea3d64
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8be3a1e7a05c2c60f1ab16c6da4df74dddf7adb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-the-service-oriented-solution"></a>了解服务面向解决方案
面向服务的解决方案提供了设计为服务的信用余额报告应用程序。 该应用程序又使用三个作为服务公开的后端应用程序来获取信用余额所需的信息。  
  
 面向服务的结构 (SOA) 是一种与构建分布式系统部分重叠的方法。 面向服务的方法具有以下几个特征：  
  
-   松散连接。 应用程序的业务逻辑独立于处理服务的逻辑。  
  
-   可发现。 应存在可供应用程序查找服务的机制。  
  
-   契约性。 指向服务的接口实现了用户与服务之间的契约。  
  
 尽管在文献资料中通常将面向服务的方法视为与 Web Services 同义，但两者并不一定是同义词。 Web Services 提供了一种实现面向服务的解决方案的有效方法，但您也可以使用 .NET 远程处理等其他技术来创建服务。  
  
 有关面向服务的体系结构的详细信息，请参阅"服务接口"网址[http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185)和在的"面向服务集成" [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)。  
  
## <a name="reader-guidance"></a>读者指南  
 此解决方案的文档假定你熟悉[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 并假定您了解有关企业应用程序集成和 Web Services 的基本概念。  
  
 此外，若要阅读并遵循开发人员文档，你应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和执行以下任务： 创建项目、 设置引用，调试和测试 BizTalk解决方案。  
  
## <a name="credit-card-reporting-at-woodgrove-bank"></a>Woodgrove Bank 的信用卡报告  
 面向服务的结构解决方案示例是 Woodgrove Bank 的信用卡余额报告服务。 尽管银行都是虚构的该方案不是-方案取决于实际的已部署的客户应用程序。  
  
 在该方案中，对信用卡余额的请求来自两个来源：  
  
-   交互式语音应答 (IVR) 应用程序。  
  
-   交互式客户端，例如网页或自定义客户端应用程序。  
  
 该解决方案通过 MQSeries 接收来自 IVR 应用程序的请求。 它通过使用 HTTP 和 SOAP 的 Web Services 处理来自交互式客户端的请求。  
  
 新的面向服务的结构应用程序通常需要使用采用早期技术的旧版应用程序，同时也需要使用现代应用程序，例如使用 Web Services 的网站。 方案模型此实际要求-IVR 应用程序表示旧的应用程序，客户服务客户端应用程序时，是现代。  
  
 Woodgrove Bank 应用程序使用三个后端原有系统中的数据来响应请求：  
  
-   一个提供信用总限额的应用程序。 此应用程序为大型机上的 SAP 系统。  
  
-   一个用于根据帐户来报告挂起事务总数的挂起事务系统。 此系统为大型机或 AS/400 系统。 该解决方案使用 Web Services 和 Microsoft Host Integration Server (HIS) 与大型机或 AS/400 系统进行通信。  
  
-   一个付款跟踪系统，用于提供对系统进行的最近一次付款。 此付款跟踪系统可以使用 MQSeries 来实现。  
  
 在收集和编译了原有系统中的信息后，该解决方案会将响应发送回源应用程序，从而也将响应发送给客户。  
  
## <a name="business-requirements"></a>业务需求  
 由于信用报告应用程序将实时响应客户请求，因此为了迅速处理这些请求，该应用程序必须具有低延迟时间。 此外，它还必须能够同时处理大量的请求。 该解决方案将使用敏感信息和公共接口，因此安全性十分重要。 最后，还需要确保服务可靠性。  
  
 有关的解决方案如何满足这些要求的信息，请参阅[开发一种服务面向解决方案](../core/developing-a-service-oriented-solution.md)。  
  
## <a name="performance-characteristics"></a>性能特征  
 为了满足上述业务需求，该方案具有以下性能特征：  
  
-   每秒 40 个传入请求的持续吞吐量。  
  
-   每秒 100 个传入请求的峰值吞吐量。  
  
-   在 1000 毫秒内为 90% 的请求提供服务（在 BizTalk Server 内部和外部）。  
  
-   在 2000 毫秒内为 95% 的请求提供服务（在 BizTalk Server 内部和外部）。  
  
-   在 5000 毫秒内为 100% 的请求提供服务（在 BizTalk Server 内部和外部）。  
  
> [!NOTE]
>  这些时间不包括后端系统的延迟时间。  
  
## <a name="three-versions-of-the-solution"></a>解决方案的三个版本  
 该解决方案具有以下三个版本：  
  
-   存根版本使用软件存根替换所有的后端系统。 这些存根模拟后端系统。 使用此版本，可以在单台计算机上快速部署和运行解决方案。  
  
-   适配器版本使用 BizTalk 适配器来连接到后端系统。 此版本是实施解决方案时首先考虑使用的版本。 但是，如果使用适配器向后端系统发送消息，则在获取响应时会有较高的延迟时间。 尽管适配器自身只会造成很短的延迟，但 BizTalk Server 的分布式结构要求适配器与使用 MessageBox 的业务流程主机实例进行通信。 这会导致消息在适配器与该数据库之间往返，从而影响延迟时间。  
  
-   内联版本使用与后端系统直接进行通信的内联代码来替换适配器。 解决方案的内联版本具有最低的延迟时间和最高的吞吐量。  
  
 部署指南为生成和部署该解决方案的上述三个版本提供了指导信息，并且在每个版本中都提供了模拟通过 HIS 连接到挂起事务系统的方法。 有关构建和部署解决方案的信息，请参阅[部署服务面向解决方案](../core/deploying-the-service-oriented-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [面向服务的解决方案](../core/service-oriented-solution.md)