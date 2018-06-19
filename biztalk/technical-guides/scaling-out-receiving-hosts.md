---
title: 向外扩展接收主机 |Microsoft 文档
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
ms.openlocfilehash: 8f0a58d7dfa022c3921abb5b426dacdf387095c2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010142"
---
# <a name="scaling-out-receiving-hosts"></a>向外扩展接收主机
若要使接收主机高度可用，必须具有两个或多[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]正在运行的每个接收的主机实例的计算机。 通过向外扩展接收主机可以增加的消息传送密集型 BizTalk Server 部署的可用性。 尽管这些部署可能很少处理业务流程，但仍可快速和可靠地路由许多不同类型的消息。  
  
 通过将接收主机与处理业务流程和发送消息的主机分隔开来，您可增强您的环境的安全性和可伸缩性，因为可以独立于其他主机来保护和扩展每个主机。 例如，您可以将两台计算机（主机实例）添加到接收主机，而无需向处理主机或发送主机添加任何计算机。  
  
## <a name="understanding-in-process-and-isolated-receiving-hosts"></a>了解在过程和独立接收主机  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]集成应用程序能够提供业务服务。 集成通常表示为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 （从应用程序） 文档、 处理文档，并将处理的文档发送回应用程序或其他应用程序。 过程被称为文档事务。  
  
 使用 BizTalk 适配器监视特定协议通道和接收文档通常启动事务。 *适配器*因此称作，因为它连接到其他应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 根据其函数，它可以是发送适配器或接收适配器。 默认适配器的大部分都是使用接收函数和内置于一个.NET 程序集的 send 函数的一个.NET 组件。 基于适配器所在的进程内存空间，它是任一进程 （接收） 适配器或隔离 （接收） 适配器。 仅可由承载进程内适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程 (BTSNTSvc.exe)，并隔离的适配器旨在由另一个进程。 例如，HTTP 适配器和 SOAP 适配器位于通过 Internet 信息服务 (IIS) 进程。 它们是实质上是 ISAPI 扩展。 另一方面，所有发送适配器是进程内适配器。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置会创建两个默认主机-进程内主机是 BizTalkServerApplication，并且独立的主机中调用 BizTalkServerIsolatedHost。 主机提供两个函数： 一个逻辑分组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项因此这些项无法分配到不同[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程，以及其他控制安全性。 你需要为主机指定 Windows 组。 只有此组中的用户可以将文档发送到由承载适配器*托管实例*分配给此主机。  
  
 每两个默认主机都有一个主机实例。 主机实例不具有一个名称，而是与主机关联。 BizTalkServerApplication 主机实例实际上是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上服务进程 (BTSNTSvc.exe) [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk 组中的计算机。 BizTalkServerIsolatedHost 主机实例未直接绑定到一个进程。 它是与承载接收适配器的进程相关联。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置还会创建*接收处理者*为每个默认适配器 SMTP 除外 （SMTP 是发送适配器）。 接收处理程序属性之一是主机名。 这就是如何绑定到主机和该主机的主机实例。  
  
 除了适配器、 主机、 主机实例和接收处理程序，你需要配置之前接收端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以开始接收文档。 接收端口包含接收位置。 接收位置有一个接收处理程序属性。 逻辑，你可以跟踪到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程处理此接收端口。  
  
 在接收端口配置中，（可选） 指定映射。 在接收位置配置中，你必须指定用于文档预处理的管道。 指定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程处理接收到预处理到映射文档的文档的文档的所有内容。 这是相同的进程内主机实例和独立的主机实例。  
  
## <a name="scaling-out-in-process-receiving-hosts"></a>向外扩展进程内接收承载  
 下图显示通过其他计算机上有两个主机实例每个接收的主机提供高可用性的 BizTalk Server 部署。 请注意，在此图中处理和发送主机不是高可用，因为只有一个处理的 BizTalk 项分配给主机的主机实例。  
  
 ![用于接收消息的多个主机](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 在进行大型部署、与多个贸易合作伙伴打交道以及使用不同的协议时，您可以采用多个接收主机来分担接收功能。 例如，您可以创建一个主机来接收每个适配器的消息，也可以创建不同主机来接收来自不同合作伙伴的消息。 在创建多个接收主机后，您可以创建安全边界来提高您的环境的可管理性和可伸缩性；但是，这并不能确保环境高度可用。 为确保环境高度可用，您必须为创建的每个接收主机创建两个或更多主机实例。 例如，你可以创建三个不同接收主机 （A、 B 和 C） 从三个不同公司接收消息。 为确保所有这些主机高度可用，随后还需要在两台或更多计算机中创建所有这些主机的实例。 请注意，您可以在一台计算机上创建每个主机的实例，而不会影响安全边界、可管理性或可伸缩性。  
  
 下图显示了高度可用的包含三台计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境与主机专用于不同公司从接收消息。  
  
 ![向外扩展接收主机](../technical-guides/media/04bd4234-dc71-49d8-b630-0643390b29f0.gif "04bd4234-dc71-49d8-b630-0643390b29f0")  
  
 为确保此配置的高可用性，每台计算机都运行三个主机实例：三家公司中的每一个家都对应一个实例。 每家公司的主机实例都包含用来与该公司进行通信的接收位置和管道。 在典型操作期间，只要执行了必要的工作，以向外扩展前面的接收适配器中，消息传递负载分布于三个宿主实例对于每个主机。 如果一台计算机上的主机实例失败，则在其他两台计算机上运行的主机实例将提供冗余，以保持服务可用。  
  
## <a name="scaling-out-isolated-receiving-hosts"></a>缩放缩小隔离接收主机  
 除了主机实例，缩放和为接收主机提供高可用性的过程又依赖于在你部署中实施的特定适配器。 每个适配器都具有与协议有关的特性，所以在协议不同的情况下规划和部署也会有所不同。 但是，BizTalk Server 可让你将应用所有适配器的支持，主要通过其他计算机和主机实例相同的高可用性解决方案。  
  
 根据所用的具体协议，某些接收适配器需要采用在多台主机计算机中分布传入消息的附加机制，才能确保高可用性。 例如，使用 HTTP 或 SOAP 适配器 （也称为 Web 服务适配器） 的 BizTalk Server 解决方案需要负载平衡器如网络负载平衡 (NLB) 分配接收工作负荷下, 图中所示。  
  
 ![向外扩展独立接收主机](../technical-guides/media/cb38ec25-bfb0-4a55-8464-b7918b6fc746.gif "cb38ec25-bfb0-4a55-8464-b7918b6fc746")  
  
 有关中的最常见适配器的高可用性准则的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅中的"缩放 BizTalk Server 接收适配器"部分[Scaled-Out 接收主机](http://go.microsoft.com/fwlink/?LinkId=151283)(http://go.microsoft.com/fwlink /？LinkId = 151283) 在 BizTalk Server 帮助中。  
  
## <a name="see-also"></a>另请参阅  
 [群集接收主机](../technical-guides/clustering-receiving-hosts.md)   
 [向外扩展处理主机](../technical-guides/scaling-out-processing-hosts.md)   
 [横向扩展发送主机](../technical-guides/scaling-out-sending-hosts.md)