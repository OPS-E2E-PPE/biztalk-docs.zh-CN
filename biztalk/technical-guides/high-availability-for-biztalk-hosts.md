---
title: "BizTalk 主机的高可用性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3153f7f7-7e82-4b0c-9b48-e9f871de285d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29636a63f7847017b233275ee3dd7c2c389c43be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="high-availability-for-biztalk-hosts"></a>BizTalk 主机的高可用性
BizTalk Server 提供极其灵活地寻址高可用性，因为你可以将多个巧妙布局专用逻辑主机运行的功能，如接收和发送消息或处理的业务流程，可以在物理上是特定区域部署到多个服务器。  
  
 BizTalk 主机是中的逻辑容器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组可以存放[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项如适配器发送处理程序 （包括管道）、 接收位置和业务流程。 通常，您可将具有类似扩展属性的项分到特定的主机中。  
  
 创建主机后，可以将其部署到物理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为主机实例的计算机。 作为 Windows 服务，BTSNTSvc.exe （或 64 位主机实例的 BTSNTSvc64.exe） 上指定的主机实例运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 对于每个主机，你可以仅一个实例对特定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 但是，你可以在一个或多个特定主机的实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，可以具有不同的主机的实例对特定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
 BizTalk 主机中包含的项可以执行以下功能：  
  
-   **接收**。 在接收位置中提取消息后，这些项对其进行初始处理。 当主机包含接收的项，如接收位置 （带有管道），在对主机中管道中会出现解码和解密该消息。  
  
-   **发送**。 在将消息发送给发送端口前，这些项对其进行最终处理。 当主机包含发送的项，例如发送端口，消息签名和加密将出现在对主机中的管道。  
  
-   **处理**。 这些项来处理基于在业务流程中的说明进行操作的消息。  
  
 一个 BizTalk 主机可以包含接收、发送和处理消息的项。 更易于管理和可伸缩性，我们建议你创建不同的主机指定为每个函数。 具体而言，我们建议你使用不同的主机，用于处理和接收/发送操作。  
  
 例如，如果您接收一条消息，运行业务流程，然后发送十条消息，则需要将接收功能和发送功能分隔到两个单独的主机中，因为发送项的流量将是接收项的十倍。 如果您接收一条消息，运行业务流程，然后发送一条消息，则可以将这些项视为一个工作单位，并将它们分到单个主机中。 或者，您可以将它们分到三个不同的主机中，以提高性能和灵活性，尽管这同时也增加了管理成本。  
  
 BizTalk 主机是两种类型之一*进程内*或*Isolated*。 进程内主机运行的内部[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时进程 （BTSNTSvc.exe 或 BTSNTSvc64.exe） 和独立的主机在不运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时进程。 用于隔离接收适配器，才会在接收端上使用独立的主机。 下表分别列出了这两种主机类型可能包含的项：  
  
|主机类型|逻辑容器包含|  
|---------------|---------------------------|  
|进程内|-业务流程<br />-适配器发送处理程序<br />中的进程适配器接收处理程序|  
|隔离|-HTTP、 SOAP 接收处理程序<br />-任何其他独立的适配器接收处理程序|  
  
 有关管理 BizTalk 主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](http://go.microsoft.com/fwlink/?LinkID=154191)(http://go.microsoft.com/fwlink/?LinkID=154191) BizTalk Server 帮助中。  
  
 若要为 BizTalk 主机提供高可用性，你必须拥有两个或多个主机实例 （在两个或多个计算机） 上的每个主机你的环境。 通过为你确保，如果一个主机实例变为不可用，主机实例正在运行的同一主机的实例的其他计算机上每个主机可以恢复的函数有问题或失败的主机实例中，让多个主机实例和总体系统可以继续使用很少发生中断执行。  
  
## <a name="disadvantages-of-additional-hosts"></a>其他主机的缺点  
 尽管有创建额外的主机实例的好处，还有潜在缺点如果创建过多的主机实例。 每个主机实例是一个 Windows 服务 （BTSNTSvc.exe 或 BTSNTSvc64.exe），它生成额外的负载，针对 MessageBox 数据库，并会占用计算机资源，例如 CPU、 内存和线程。 除此之外，您有不配置太多额外的主机实例的以下原因：  
  
-   几个性能计数器报告每个主机具有太多粒度。 这将影响的管理员将需要遍历大量数据的可用性。 这对管理员的总体视图有负面影响。  
  
-   每个主机会占用相当多的内存，可能会导致的限制的情况和性能降低。  
  
-   如果主机已收到连续执行轮询的适配器，每个主机将轮询数据库在短时间内，从而导致性能下降。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [横向扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md)  
  
-   [接收主机](../technical-guides/clustering-receiving-hosts.md)  
  
-   [横向扩展处理主机](../technical-guides/scaling-out-processing-hosts.md)  
  
-   [横向扩展发送主机](../technical-guides/scaling-out-sending-hosts.md)  
  
## <a name="see-also"></a>另请参阅  
 [配置主机和主机实例](../technical-guides/configuring-hosts-and-host-instances.md)   
 [配置专用的跟踪主机](../technical-guides/configuring-a-dedicated-tracking-host.md)   
 [规划高 Availability2](../technical-guides/planning-for-high-availability2.md)   
 [数据库的高可用性](../technical-guides/high-availability-for-databases.md)   
 [主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)