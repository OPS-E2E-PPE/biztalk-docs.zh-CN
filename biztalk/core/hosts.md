---
title: 主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9785e734579c88a790f2a07a292fef476be5d6d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387523"
---
# <a name="hosts"></a>主机
BizTalk 主机对象表示的零个或多个运行时进程在其中部署服务、 管道和其他项目的逻辑组。 该主机对象还表示已部署的项以物理方式运行的运行时实例 （零个或多个） 的集合。  
  
 创建主机 （逻辑容器） 后，您可以向主机添加物理 BizTalk server （主机实例）。 不能超过一次到同一主机中添加 BizTalk server。 单个主机实例可以添加到多个主机。  
  
 项 — 如适配器处理程序、 接收位置 （包括管道） 和业务流程，包含在 BizTalk 主机可以执行以下功能：  
  
- **接收**。 这些项后选取在接收位置对其进行初始处理的消息。 当主机包含接收项时，如接收位置或管道，它充当安全边界，并在主机内的管道中出现消息解码和解密。  
  
- **发送**。 这些项对其进行最终处理消息之前发送到发送端口发送。 当主机包含发送项，例如发送端口或管道中，主机将充当安全边界，而且消息的签名和加密发生在主机中的管道中。  
  
- **处理**。 这些项来处理基于业务流程中的说明进行操作的消息。  
  
  一个 BizTalk 主机可以包含接收、 发送和处理消息的项。 建议创建不同的主机，为每个函数来创建安全边界，从而有助于管理。 具体而言，建议使用不同的主机，对于处理操作和接收/发送，并且分隔可信任项和不受信任项。  
  
  下图显示了服务器、 主机和主机实例之间的关系。  
  
  ![主机、 主机实例和服务器之间的关系](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
  主机、 主机实例和服务器之间的关系  
  
  有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。  
  
  根据物理配置和托管的适配器类型，有两种类型的主机： 进程内主机和独立主机。  
  
## <a name="in-process-hosts"></a>进程内主机  
 进程内主机表示管理员身份创建、 删除和完全控制使用 Windows Management Instrumentation (WMI) 和 BizTalk 管理控制台中的服务实例。  
  
 进程内主机具有以下特征：  
  
- 您可以登记到进程内主机的任何业务流程。  
  
- 进程内主机可以承载任何发送处理程序。  
  
- 进程内主机可以承载任何除 SOAP 和 HTTP 的接收处理程序：  
  
  -   FILE  
  
  -   FTP  
  
  -   MQSeries  
  
  -   MSMQ  
  
  -   POP3  
  
  -   SQL  
  
  -   Windows SharePoint Services  
  
- 在创建的第一个进程内主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署**默认主机**并不能将其删除。 BizTalk 消息队列适配器将默认主机用于静态处理程序配置。 添加适配器会自动创建接收和发送端口的默认主机。  
  
## <a name="isolated-hosts"></a>独立主机  
 独立主机表示解决方案开发人员以编程方式创建、 删除和控制的服务实例。 管理员使用 WMI 和 BizTalk 管理控制台来配置这些主机 （例如，若要配置主机服务帐户和身份验证信任）。  
  
 独立主机主要主机必须运行正常的 BizTalk Server 运行时进程外部的适配器。 例如，对于外部进程，如 ISAPI 扩展和 ASP.NET 使用到的主机适配器的独立主机。  
  
 独立主机具有以下特征：  
  
-   无法登记到独立主机的业务流程。  
  
-   独立主机不能作为发送处理程序的宿主。  
  
-   独立主机可作为仅与 HTTP/S 和 SOAP 适配器 （独立类型适配器） 相关联的接收处理程序的宿主。  
  
-   独立主机不能作为跟踪的宿主。  
  
-   独立主机不能为默认主机。  
  
-   独立主机的状态始终是**不可用状态**。 BizTalk Server 不访问外部进程的状态信息。  
  
> [!NOTE]
>  主机实例可以共享相同的服务帐户，只要它们共享相同的安全配置 （受信任验证）。  
  
## <a name="trusted-and-untrusted-hosts"></a>受信任和不受信任主机  
 BizTalk Server 将主机标识为受信任验证来指示，受信任的主机排队到 MessageBox 数据库的消息的发件人是一个实体而不受信任主机本身。 受信任验证的主要目的是将管道解析为产品 ID (PID) 并将传递到使用 PID 服务用于授权和出站参与方解析和发件人 Windows 安全 ID 的传输(SSID) 一起使用以便在业务流程操作授权中使用的服务。  
  
## <a name="see-also"></a>请参阅  
 [主机实例](../core/host-instances.md)   
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)  
 [实体](../core/entities.md)