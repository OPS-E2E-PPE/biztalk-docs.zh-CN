---
title: 如何创建 BizTalk Server 宿主环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting environments, creating
- managing [hosts], hosting environments
- hosts, environments
- managing [hosts], creating
- creating, hosting environment
ms.assetid: 6f335139-1121-45ff-88da-5c626b8fff97
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba3829a2fecb32a191b7351833e975bf3770547d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013374"
---
# <a name="how-to-create-a-biztalk-server-hosting-environment"></a>如何创建 BizTalk Server 宿主环境
在创建 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 宿主环境之前，请考虑以下建议：  

- **使用不同的主机的受信任和不受信任的业务流程和接收处理程序**  

   在主机中运行的任何项（例如，业务流程、管道、接收和发送处理程序）都使用同一标识运行，并具有对该主机的工作队列和挂起队列的访问权限。  

   如果由于权限错误导致无法将消息发送到业务流程，则会将该消息放入正在运行发送进程（接收管道或其他业务流程）的主机的挂起队列中。 但是，如果业务流程和发送进程（例如，接收管道）在同一主机中运行，则该业务流程仍可访问挂起队列中的消息。 如果在可信主机中运行不可信业务流程，这可能会危及系统安全。  

   建议在单独的主机中运行不可信业务流程，并使用与 BizTalk 组中的可信主机不同的服务帐户。 有关将主机指定为受信任，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  

- **限制 BizTalk Server 数据库中的数据库和日志大小**  

   BizTalk MessageBox 数据库和 BizTalk 跟踪数据库的增长速度远大于其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库的增长速度。 作为备份和维护程序的一部分，您应经常更新这些数据库。  

   默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中的表没有日志大小限制。 作为备份和维护程序的一部分，建议限制日志大小以防止日志变得过大并可能占用所有磁盘空间。 有关管理的跟踪数据库大小的信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。  

- **使用 SQL Server 群集**  

   为了提供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库的高可用性，建议对存储 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库的 SQL 服务器进行群集。 这将帮助您在其中一个数据库或 SQL Server 出现故障时最大限度地减少停机时间。 有关 SQL Server 群集的详细信息，请参阅 SQL Server 联机丛书中的“故障转移群集体系结构”。  

## <a name="prerequisites"></a>必要條件  
 以下为执行本主题中的过程的前提条件：  

- 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  

- 以下过程中的说明假定您已使用完全安装选项安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 如果不是使用完全安装选项安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则您的系统中可能未安装步骤 1 中列出的某些管理对象。  

### <a name="to-create-a-biztalk-server-hosting-environment"></a>创建 BizTalk Server 宿主环境  

1. 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置创建新的 BizTalk 项目。 了解如何创建一个新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组，请参阅[使用 BizTalk Server 配置的配置组](http://msdn.microsoft.com/library/16beb7bb-091c-4056-8622-cc79c95186e9)。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置可创建以下管理对象：  


   |                   管理对象                    |                                                                                                                                                                                                                                       Description                                                                                                                                                                                                                                       |
   |------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      **BizTalk 管理**数据库 (BizTalkMgmtDb)       |                                                                                                                                                                    此数据库是所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的中央元信息存储区。                                                                                                                                                                     |
   |     **BizTalk MessageBox**数据库 (BizTalkMsgBoxDb)      |           此数据库存储订阅谓词。 它是一个主机平台，存储每个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机的队列和状态表。 MessageBox 数据库还存储消息和消息属性。 有关 MessageBox 数据库的信息，包括添加其他 MessageBox 数据库，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。           |
   |                         **Server**                         | 此为安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以及运行主机实例的计算机。 您从在服务器上创建的主机中创建主机实例。 有关创建主机的详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。 有关创建主机实例的信息，请参阅[如何将主机实例添加](../core/how-to-add-a-host-instance.md)。 |
   |     **BAM 主导入**数据库 (BAMPrimaryImport)     |                                                                                                                                                                                                此数据库是业务活动监视工具从中收集跟踪数据的数据库。                                                                                                                                                                                                 |
   |       **规则引擎**数据库 (BizTalkRuleEngineDb)       |                                                                                                                                                                                       此数据库是业务规则中数据引用策略、规则和词汇的存储库。                                                                                                                                                                                        |
   |        **BizTalk 跟踪**数据库 (BizTalkDTADb)        |                                                                                                                                                       此数据库存储 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 跟踪引擎所跟踪的业务和运行状况监视数据。                                                                                                                                                       |
   |                  **SSO**数据库 (SSODB)                  |                                                                                                                                                                                                                      此数据库存储凭据信息。                                                                                                                                                                                                                       |
   |   **进程内主机**及相应的主机实例    |                                                                                                                                                                        进程内主机在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 进程空间内运行。                                                                                                                                                                        |
   |    **独立主机**及相应的主机实例     |                                                                                                                                                                       独立主机在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装外部运行。                                                                                                                                                                        |
   | HTTP/S、BizTalk 消息队列、文件、SMTP、SOAP 和 SQL |                                                                                                                                                                   配置向导创建的适配器属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。                                                                                                                                                                    |


2. 根据需要，可使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或 WMI 向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中添加组件。 若要扩展解决方案，请添加 MessageBox 数据库、主机和服务器。  

3. 使用 BizTalk 管理控制台或 WMI 在映射的服务器上创建主机实例。 此步骤确定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将在哪些服务器上运行。 随着企业需求的变化，您可以添加服务器，删除服务器以及更改服务器到主机映射。  

## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [主机](../core/hosts.md)   
 [主机实例](../core/host-instances.md)