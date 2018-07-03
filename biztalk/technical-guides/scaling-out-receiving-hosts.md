---
title: 向外扩展接收主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9f78710-93fa-4877-8273-a1634d768d88
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 650042a5de59410f932af260ee6ca2cfc0a56d77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985702"
---
# <a name="scaling-out-receiving-hosts"></a>向外扩展接收主机
若要确保接收主机高度可用，必须具有两个或多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行的每个接收主机实例的计算机。 通过横向扩展接收主机可以增加的大量消息的 BizTalk Server 部署的可用性。 尽管这些部署可能很少处理业务流程，但仍可快速和可靠地路由许多不同类型的消息。  
  
 通过将接收主机与处理业务流程和发送消息的主机分隔开来，您可增强您的环境的安全性和可伸缩性，因为可以独立于其他主机来保护和扩展每个主机。 例如，您可以将两台计算机（主机实例）添加到接收主机，而无需向处理主机或发送主机添加任何计算机。  
  
## <a name="understanding-in-process-and-isolated-receiving-hosts"></a>了解进程内和独立接收主机  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 集成应用程序能够提供业务服务。 集成通常表示为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 （来自应用程序） 的文档、 处理文档，并将已处理的文档发送回应用程序或另一个应用程序。 过程被称为文档事务。  
  
 事务通常会开始监视某些协议通道和接收文档的 BizTalk 适配器。 *适配器*因为它会连接到其他应用程序因此名为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 根据其函数，它可以是一个发送适配器或接收适配器。 大多数默认适配器是一个.NET 组件的接收函数和内置于一个.NET 程序集的发送函数。 基于适配器所驻留的进程内存空间，它为任一进程 （接收） 适配器或独立 （接收） 适配器。 仅可由承载进程内适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程 (BTSNTSvc.exe) 和独立的适配器设计由另一个进程宿主。 例如，HTTP 适配器和 SOAP 适配器由 Internet Information Services (IIS) 进程承载。 它们实质上是 ISAPI 扩展。 但是，所有发送适配器都是进程内适配器。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置可创建两个默认主机-BizTalkServerApplication，调用进程内主机和独立主机名为 BizTalkServerIsolatedHost。 主机提供两个函数： 一个逻辑分组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]因此这些项无法分配到不同的项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]流程和其他控制安全性。 您需要为主机指定 Windows 组。 只有此组中的用户可以将文档发送到托管的适配器*托管实例*分配给此主机。  
  
 每个两个默认主机具有主机实例。 主机实例不具有一个名称，但与主机相关联。 BizTalkServerApplication 主机实例实际上是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务进程 (BTSNTSvc.exe) 上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 组内的计算机。 BizTalkServerIsolatedHost 主机实例不直接绑定到进程。 它是与承载接收适配器的进程相关联。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置还会创建*接收处理程序*为每个默认适配器 SMTP 除外 （SMTP 是一个发送适配器）。 接收处理程序属性之一是主机名。 这就是如何绑定到主机和该主机的主机实例。  
  
 除了适配器、 主机、 主机实例和接收处理程序，你需要配置接收端口之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以开始接收文档。 接收端口包含接收位置。 接收位置有一个接收处理程序属性。 按照逻辑，你可以跟踪到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程处理此接收端口。  
  
 在接收端口配置中，您可以选择指定映射。 在接收位置配置中，必须指定用于文档预处理的管道。 指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程处理接收的文档，预处理到映射文档的文档的所有内容。 这是相同的进程内主机实例和独立主机实例。  
  
## <a name="scaling-out-in-process-receiving-hosts"></a>横向扩展进程内接收承载  
 下图显示了另一台计算机上具有两个主机实例每个接收主机提供高可用性的 BizTalk Server 部署。 注意，在此图中处理和发送主机并不高度可用，因为只有一个主机实例处理分配给主机的 BizTalk 项目。  
  
 ![多个主机接收消息](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 在进行大型部署、与多个贸易合作伙伴打交道以及使用不同的协议时，您可以采用多个接收主机来分担接收功能。 例如，您可以创建一个主机来接收每个适配器的消息，也可以创建不同主机来接收来自不同合作伙伴的消息。 在创建多个接收主机后，您可以创建安全边界来提高您的环境的可管理性和可伸缩性；但是，这并不能确保环境高度可用。 为确保环境高度可用，您必须为创建的每个接收主机创建两个或更多主机实例。 例如，可以创建三种不同接收主机 （A、 B 和 C） 以接收来自三家不同公司的消息。 为确保所有这些主机高度可用，随后还需要在两台或更多计算机中创建所有这些主机的实例。 请注意，您可以在一台计算机上创建每个主机的实例，而不会影响安全边界、可管理性或可伸缩性。  
  
 下图显示了高度可用的包含三台计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与主机环境，专用于接收来自不同公司的消息。  
  
 ![向外扩展接收主机](../technical-guides/media/04bd4234-dc71-49d8-b630-0643390b29f0.gif "04bd4234-dc71-49d8-b630-0643390b29f0")  
  
 为确保此配置的高可用性，每台计算机都运行三个主机实例：三家公司中的每一个家都对应一个实例。 每家公司的主机实例都包含用来与该公司进行通信的接收位置和管道。 在典型操作期间，只要您曾经所需的接收适配器中，前面的横向扩展工作消息传送负载将分布在三个主机实例为每个主机。 如果一台计算机上的主机实例失败，则在其他两台计算机上运行的主机实例将提供冗余，以保持服务可用。  
  
## <a name="scaling-out-isolated-receiving-hosts"></a>缩放出隔离接收主机  
 除了主机实例外缩放并确保接收主机高度可用的过程还取决于在部署中实施的特定适配器。 每个适配器都具有与协议有关的特性，所以在协议不同的情况下规划和部署也会有所不同。 但是，BizTalk Server 可将应用所有适配器的支持，主要通过其他计算机和主机实例相同的高可用性解决方案。  
  
 根据所用的具体协议，某些接收适配器需要采用在多台主机计算机中分布传入消息的附加机制，才能确保高可用性。 例如，使用 HTTP 或 SOAP 适配器 （也称为 Web services 适配器） 的 BizTalk Server 解决方案需要负载均衡器等网络负载平衡 (NLB) 来分布接收工作负荷下, 图中所示。  
  
 ![向外扩展隔离的接收主机](../technical-guides/media/cb38ec25-bfb0-4a55-8464-b7918b6fc746.gif "cb38ec25-bfb0-4a55-8464-b7918b6fc746")  
  
 有关中的最常见的适配器的高可用性指南的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅中的"扩展 BizTalk Server 接收适配器"部分[Scaled-Out 接收主机](http://go.microsoft.com/fwlink/?LinkId=151283)(<http://go.microsoft.com/fwlink/?LinkId=151283>) 在 BizTalk 中Server 帮助。  
  
## <a name="see-also"></a>请参阅  
 [接收主机](../technical-guides/clustering-receiving-hosts.md)   
 [横向扩展处理主机](../technical-guides/scaling-out-processing-hosts.md)   
 [横向扩展发送主机](../technical-guides/scaling-out-sending-hosts.md)