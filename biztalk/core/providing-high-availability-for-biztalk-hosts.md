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
ms.openlocfilehash: f28c4bb8935da0d98ea59efb2642e13900c3a54a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398436"
---
# <a name="providing-high-availability-for-biztalk-hosts"></a>为 BizTalk 主机提供高可用性
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理高可用性，因为可以策略性地将运行特定区域的功能，如接收消息、 发送消息或处理业务流程的逻辑主机专门提供极大的灵活性。  
  
 BizTalk 主机是 BizTalk Server 组，可承载 BizTalk Server 项，例如适配器处理程序，接收位置 （包括管道） 和业务流程中的逻辑容器。 您通常分组具有类似扩展要求到特定的主机项。 例如，可以将接收到"接收"的主机的位置、 发送端口分到"发送"主机和到"处理"主机的业务流程。  
  
 创建主机 （逻辑容器） 后，您可以配置要在物理上运行的主机的实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 作为 Windows 服务上指定的主机实例运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。 尽管不可能在运行多个实例在同一主机的给定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，您可以通过上单独配置的主机实例运行特定主机的多个实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 此外可以运行不同主机的多个实例的单个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
 BizTalk 主机中包含的项可以执行以下功能：  
  
- **接收**这些项后选取在接收位置对其进行初始处理的消息。 当主机包含接收项时，如接收位置或管道，它充当安全边界，并在主机内的管道中出现消息解码和解密。  
  
- **发送**这些项对其进行最终处理消息之前发送到发送端口发送。 当主机包含发送项，例如发送端口或管道中，主机将充当安全边界，而且消息的签名和加密发生在主机中的管道中。  
  
- **处理**这些项来处理基于业务流程中的说明进行操作的消息。  
  
  虽然单一 BizTalk 主机可以包含接收的项、 发送和处理消息，但它被视为最佳做法来创建不同的主机的每个函数来创建安全边界以及出于管理简易性和可伸缩性。 具体而言，我们建议使用不同的主机，以进行处理，对于接收/发送操作，并且分隔可信任和不可信任项。  
  
  例如，如果收到一条消息，运行业务流程，并发送 10 条消息，你想要将接收和发送功能分隔到两个单独的主机，因为发送项将具有将是接收项的十倍更多流量。 如果收到一条消息，运行业务流程，并发送一条消息，可以将这些项视为一个工作单元并将它们分到一台主机。 或者，可以将它们分到三个不同的主机以提高性能和灵活性。  
  
  BizTalk 主机分为两种类型之一**进程内**或**独立**。 进程内主机运行的内部[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时处理而不会独立的主机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时进程。 可能包含下表列出了每种主机类型的项。  
  
|**主机类型**|**逻辑容器**|  
|-------------------|-------------------------------|  
|进程内|-业务流程<br />适配器发送处理程序<br />适配器接收处理程序不是 HTTP 和 SOAP|  
|隔离|HTTP 和 SOAP 接收处理程序|  
  
 有关主机和主机实例的详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
 若要为 BizTalk 主机提供高可用性，您必须具有两个或多个主机实例的每个主机环境中 (在两个或多[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机)。 整个系统可以通过确保一个主机实例变为不可用，如果正在运行该主机的实例的其他计算机可以恢复的功能有问题或失败的主机实例中，并且每个主机具有多个主机实例继续执行中断降至最低。  
  
## <a name="message-persistence"></a>消息持久性  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 很大程度上依赖于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]以实现高可用性，因为每个主机涉及[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息保存到 BizTalk MessageBox 数据库。 例如，当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]收到传入消息，接收主机其保存到 MessageBox 数据库之前的其他主机检索业务流程处理和发送的消息。  
  
 如果你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案包含业务流程，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将消息路由到的主机执行业务流程 （处理主机），并在业务流程完成后，将消息保存到 MessageBox 数据库。 发送到相应的发送适配器通过外部应用程序之前发送主机从 MessageBox 数据库随后检索消息。  
  
## <a name="separating-the-host-and-database-functions"></a>分隔主机功能和数据库函数  
 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]分隔数据与处理数据，可用于创建高度可用的环境的一个步骤的主机的主机功能 （发送、 接收和处理） 中发生的是[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从数据库函数中发生的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 通过分隔这些功能，可以独立缩放处理、 发送和接收主机功能以及存储数据的数据库。 在运行时和数据库层相关的也就是说，如果增加的数量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的计算机可能需要增加运行的计算机数量[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]处理附加负载。 但是，在数据库层和 BizTalk 层之间没有直接关系。 它们是两个独立的层，您可以单独地扩展它们。  
  
 若要确保主机高度可用而必须执行的操作与不同必须执行哪些操作来使数据库高度可用。 以下各节说明您必须做什么以使接收、 发送和处理主机高度可用。 有关如何实现数据库层的高可用性的详细信息，请参阅[的 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)。  
  
 对于部署其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程多于 SQL Server 进程，可以配置多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用运行 SQL Server 的同一台计算机的计算机。 此配置使用每台计算机上可用的资源。 例如，如果 CPU 或内存使用高 （大于 75%） 上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机但运行在较低 （小于 25%） 运行 SQL Server 的计算机上，您可以向其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机分配工作负荷时提高运行 SQL Server 的计算机上的资源使用率。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [横向扩展接收主机](../core/scaled-out-receiving-hosts.md)  
  
-   [扩展处理主机](../core/scaled-out-processing-hosts.md)  
  
-   [扩展发送主机](../core/scaled-out-sending-hosts.md)  
  
-   [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [企业单一登录的高可用性](../core/high-availability-for-enterprise-single-sign-on.md)