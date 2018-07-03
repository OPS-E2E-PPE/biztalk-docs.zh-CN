---
title: 为 BizTalk 主机提供高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- planning, hosts
- hosts, high availability
- messages, routing
- deploying, high availability
- high availability, hosts
- hosts
- hosts, planning
- MessageBox database
ms.assetid: 9583b85c-7cad-4016-8065-5ca7de3f4359
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68ed85354a3f98aa8fbd08d82e5dd942e6751605
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004806"
---
# <a name="providing-high-availability-for-biztalk-hosts"></a>为 BizTalk 主机提供高可用性
由于您可以策略性地将逻辑主机专门用于运行特定方面的功能，如接收消息、发送消息或处理业务流程，所以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可灵活处理高可用性方面的问题。  
  
 BizTalk 主机是 BizTalk Server 组中的逻辑容器，该容器可以容纳不同的 BizTalk Server 项，例如适配器处理程序、接收位置（包括管道）和业务流程等。 通常，您可将具有类似扩展要求的项分到特定的主机中。 例如，可以将接收位置分到“接收”主机中，将发送端口分到“发送”主机中，将业务流程分到“处理”主机。  
  
 在创建了主机（逻辑容器）之后，可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组中的物理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上配置主机实例。 主机实例在指定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上作为 Windows 服务运行。 虽然不能在给定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上运行同一主机的多个实例，但通过在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组中的单独 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上配置主机实例，可以运行特定主机的多个实例。 您还可以在单一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上运行不同主机的多个实例。  
  
 BizTalk 主机中包含的项可以执行以下功能：  
  
- **接收**这些项后选取在接收位置对其进行初始处理的消息。 当主机包含接收项（例如接收位置或管道）时，该主机将充当安全边界，而且消息的解码和解密都将发生在主机内的管道中。  
  
- **发送**这些项对其进行最终处理消息之前发送到发送端口发送。 当主机包含发送项（例如发送端口或管道）时，该主机将充当安全边界，而且消息的签名和加密都将发生在主机内的管道中。  
  
- **处理**这些项来处理基于业务流程中的说明进行操作的消息。  
  
  虽然单一 BizTalk 主机可以包含接收、发送和处理消息的项目，但为了创建安全边界以及出于管理简易性和可伸缩性原因，最佳做法是为每个功能创建不同的主机。 特别是，建议对于处理操作和接收/发送操作分别使用不同的主机，并且分隔可信任项和不可信任项。  
  
  例如，如果您接收一条消息，运行业务流程，然后发送十条消息，则需要将接收功能和发送功能分隔到两个单独的主机中，因为发送项的流量将是接收项的十倍。 如果您接收一条消息，运行业务流程，然后发送一条消息，则可以将这些项视为一个工作单位，并将它们分到单个主机中。 或者，可以将它们分到三个不同的主机中，以提高性能和灵活性。  
  
  BizTalk 主机分为两种类型之一**进程内**或**独立**。 进程内主机在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时进程内运行，而独立的主机不在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时进程中运行。 下表分别列出了这两种主机类型可能包含的项：  
  
|**主机类型**|**逻辑容器**|  
|-------------------|-------------------------------|  
|进程内|-业务流程<br />适配器发送处理程序<br />适配器接收处理程序不是 HTTP 和 SOAP|  
|隔离|HTTP 和 SOAP 接收处理程序|  
  
 有关主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
 为确保 BizTalk 主机的高可用性，您的环境（包含两台或更多 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机）中的每个主机必须具有两个或更多主机实例。 通过为每个主机创建多个主机实例，可以确保在一个主机实例不可用时，运行该主机的实例的其他计算机可恢复有问题或失败的主机实例的功能，并确保整个系统可以继续工作，最大程度地减少中断时间。  
  
## <a name="message-persistence"></a>消息持久性  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的高可用性在很大程度上依赖于 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，因为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中涉及的每个主机都将消息保存到 BizTalk MessageBox 数据库。 例如，当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]收到传入消息，接收主机其保存到 MessageBox 数据库之前的其他主机检索业务流程处理和发送的消息。  
  
 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案包含业务流程，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将消息路由到执行业务程序的主机（处理主机），并在业务流程完成后将消息保存到 MessageBox 数据库中。 随后，发送主机将从 MessageBox 数据库中检索消息，再通过相应的发送适配器将该消息发送到外部应用程序。  
  
## <a name="separating-the-host-and-database-functions"></a>分隔主机功能和数据库功能  
 由于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以分隔数据与处理数据的主机，因此您可以将在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中执行的主机功能（发送、接收和处理）与在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 中执行的数据库功能分开，以创建高可用性环境。 通过分隔这些功能，您可以独立地扩展处理、发送和接收主机功能以及存储数据的数据库。 运行时层与数据库层是相关的，即，如果增加 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的数目，就很可能需要增加运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的计算机的数目才能处理附加负载。 但是，在数据库层和 BizTalk 层之间并没有直接关系。 它们是两个独立的层，您可以单独地扩展它们。  
  
 确保主机高度可用所要执行的操作不同于确保数据库高度可用所要执行的操作。 以下部分说明了确保接收主机、发送主机和处理主机高度可用所要执行的操作。 有关如何实现数据库层的高可用性的详细信息，请参阅[的 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)。  
  
 对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程多于 SQL Server 进程的部署，您可以配置多台 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机来使用运行 SQL Server 的同一计算机。 此配置可使用每台计算机上可用的资源。 例如，如果 CPU 或内存在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机上的使用率很高（大于 75%），而在运行 SQL Server 的计算机上使用率很低（小于 25%），则您可以向其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机分配工作负荷，同时提高运行 SQL Server 的计算机的资源使用率。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [横向扩展接收主机](../core/scaled-out-receiving-hosts.md)  
  
-   [扩展处理主机](../core/scaled-out-processing-hosts.md)  
  
-   [扩展发送主机](../core/scaled-out-sending-hosts.md)  
  
-   [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)