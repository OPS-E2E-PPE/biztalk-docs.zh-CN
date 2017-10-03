---
title: "主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host instances, servers
- hosts, isolated
- host instances, relationships
- hosts, in-process hosts
- servers, hosts
- hosts, host instances
- hosts, relationships
- In-Process BizTalk Host groups
- hosts, about hosts
- hosts, untrusted
- host instances, hosts
- hosts, servers
- hosts
- servers, host instances
- Isolated Host Users group
- hosts, trusted
ms.assetid: d96537e0-e679-407a-8870-34a663acfed9
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a1c61995bca06203208c057762db7f737afd6eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hosts"></a>主机
BizTalk 主机对象表示在其中部署服务、管道和其他项目的零个或多个运行时进程的逻辑组。 主机对象还表示运行时实例（零个或多个）的集合，是运行部署项的物理位置。  
  
 在创建主机（逻辑容器）后，您可以向主机添加物理 BizTalk Server（主机实例）。 不能向同一主机多次添加 BizTalk Server。 可将单个主机实例添加到多个主机上。  
  
 项-适配器处理程序，如接收位置 （包括管道） 和业务流程-BizTalk 中包含的主机可以执行以下功能：  
  
-   **接收**。 在接收位置中提取消息后，这些项对其进行初始处理。 当主机包含接收项（例如接收位置或管道）时，该主机将充当安全边界，而且消息的解码和解密都将发生在主机内的管道中。  
  
-   **发送**。 在将消息发送给发送端口前，这些项对其进行最终处理。 当主机包含发送项（例如发送端口或管道）时，该主机将充当安全边界，而且消息的签名和加密都将发生在主机内的管道中。  
  
-   **处理**。 这些项将根据业务流程中的指令来处理消息。  
  
 一个 BizTalk 主机可以包含接收、发送和处理消息的项。 建议为每个功能创建不同的主机，以创建安全边界，从而有助于管理。 特别是，建议对于处理操作和接收/发送分别使用不同的主机，并且分隔可信任项和不可信任项。  
  
 下图显示了服务器、主机和主机实例之间的关系：  
  
 ![主机、 主机实例和服务器关系](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
主机、 主机实例和服务器之间的关系  
  
 有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。  
  
 根据物理配置和承载适配器的类型，有两种类型的主机：进程内主机和独立主机。  
  
## <a name="in-process-hosts"></a>进程内主机  
 进程内主机表示管理员使用 Windows 管理规范 (WMI) 和 BizTalk 管理控制台创建、删除和完全控制的服务实例。  
  
 进程内主机具有以下特性：  
  
-   可以将任何业务流程登记到进程内主机中。  
  
-   进程内主机可以作为任何发送处理程序的宿主。  
  
-   进程内主机可以作为除 SOAP 和 HTTP 以外的任何接收处理程序的宿主：  
  
    -   FILE  
  
    -   FTP  
  
    -   MQSeries  
  
    -   MSMQ  
  
    -   POP3  
  
    -   SQL  
  
    -   Windows SharePoint Services  
  
-   在中创建第一个进程内主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署**默认主机**并且不能删除它。 BizTalk 消息队列适配器将默认主机用于静态处理程序配置。 添加适配器会自动创建默认主机的接收和发送端口。  
  
## <a name="isolated-hosts"></a>独立主机  
 独立主机表示解决方案开发人员以编程的方式创建、删除和控制的服务实例。 管理员使用 WMI 和 BizTalk 管理控制台来配置这些主机（例如，配置主机服务帐户和受信任验证）。  
  
 独立主机主要作为必须运行于常规 BizTalk Server 运行时进程之外的适配器的宿主。 例如，使用独立主机作为外部进程（如 ISAPI 扩展和 ASP.NET）适配器的宿主。  
  
 独立主机具有以下特性：  
  
-   您不能将业务流程登记到独立主机中。  
  
-   独立主机不能作为发送处理程序的宿主。  
  
-   独立主机仅能作为与 HTTP/S 和 SOAP 适配器（独立类型适配器）相关联的接收处理程序的宿主。  
  
-   独立主机不能作为跟踪的宿主。  
  
-   独立主机不能为默认主机。  
  
-   隔离主机的状态始终是**状态不可用**。 BizTalk Server 不访问外部进程的状态信息。  
  
> [!NOTE]
>  只要主机实例共享相同的安全配置（受信任验证），它们就可以共享相同的服务帐户。  
  
## <a name="trusted-and-untrusted-hosts"></a>可信任主机和不可信任主机  
 BizTalk Server 将主机标识为受信任验证来表明受信任主机排队到 MessageBox 数据库的消息的发件人是一个实体而不是受信任主机本身。 受信任验证的主要用途是将管道解析为产品 ID (PID)，并将该 PID 传递到需要该 ID 的服务，以用于授权和出站参与方解析，以及将发件人 Windows 安全 ID (SSID) 传输到需要该 ID 的服务，以用于业务流程操作授权。  
  
## <a name="see-also"></a>另请参阅  
 [主机实例](../core/host-instances.md)   
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)  
 [实体](../core/entities.md)