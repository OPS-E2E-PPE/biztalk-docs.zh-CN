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
ms.openlocfilehash: de4183a91d2e10eaaefd2f6298a66b05b74eb9c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340118"
---
# <a name="how-to-create-a-biztalk-server-hosting-environment"></a>如何创建 BizTalk Server 宿主环境
在创建之前你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]承载环境中，请考虑以下建议：  

- **使用不同的主机的受信任和不受信任的业务流程和接收处理程序**  

   为在主机中运行的任何项 （例如，业务流程、 管道、 接收和发送处理程序） 在同一标识下运行，并为该主机有权访问的工作和已挂起的队列。  

   如果无法在消息送达由于权限错误导致业务流程，将消息放在主机的挂起队列中运行发送进程 （接收管道或另一个业务流程） 的位置。 但是，如果在同一主机中运行业务流程和发送进程 （例如，接收管道），该业务流程仍可以访问挂起队列中的消息。 如果在受信任的主机中运行不可信业务流程，这可能可能破坏您系统。  

   我们建议在单独的主机，使用不同的服务帐户比 BizTalk 组中受信任的主机中运行不可信业务流程。 有关将主机指定为受信任，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  

- **限制 BizTalk Server 数据库中的数据库和日志大小**  

   BizTalk MessageBox 数据库和 BizTalk 跟踪数据库的增长速度快于另[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 作为备份和维护程序的一部分，则应频繁地更新这些数据库。  

   默认情况下中的表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库没有日志大小限制。 作为备份和维护程序的一部分，我们建议限制日志大小，以防止日志变得过大并可能使用的所有磁盘空间。 有关管理的跟踪数据库大小的信息，请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)。  

- **使用 SQL Server 群集**  

   若要提供的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，我们建议 SQL 服务器进行群集其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库存储。 这将有助于尽量减少停机时间，如果其中一个数据库或 SQL Server 失败。 有关 SQL Server 群集的详细信息，请参阅"故障转移群集体系结构"SQL Server 联机丛书中。  

## <a name="prerequisites"></a>先决条件  
 在本主题中执行该过程的先决条件如下：  

- 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

- 以下过程中的说明假定您已安装了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与完全安装选项。 如果未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用完全安装选项时，某些步骤 1 中列出的管理对象可能无法在系统上。  

### <a name="to-create-a-biztalk-server-hosting-environment"></a>若要创建 BizTalk Server 宿主环境  

1. 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置来创建新的 BizTalk 组。 了解如何创建一个新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组，请参阅[使用 BizTalk Server 配置的配置组](http://msdn.microsoft.com/library/16beb7bb-091c-4056-8622-cc79c95186e9)。  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置可创建以下管理对象：  


   |                   管理对象                    |                                                                                                                                                                                                                                       Description                                                                                                                                                                                                                                       |
   |------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      **BizTalk 管理**数据库 (BizTalkMgmtDb)       |                                                                                                                                                                    此数据库是所有的中央元信息存储区[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s。                                                                                                                                                                     |
   |     **BizTalk MessageBox**数据库 (BizTalkMsgBoxDb)      |           此数据库存储订阅谓词。 它是一个主机平台，并为每个保留的队列和状态表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机。 MessageBox 数据库还存储消息和消息属性。 有关 MessageBox 数据库的信息，包括添加其他 MessageBox 数据库，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。           |
   |                         **Server**                         | 这是在其上的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装和配置，以及运行主机实例。 从一个服务器上创建的主机创建主机实例。 有关创建主机的详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。 有关创建主机实例的信息，请参阅[如何将主机实例添加](../core/how-to-add-a-host-instance.md)。 |
   |     **BAM 主导入**数据库 (BAMPrimaryImport)     |                                                                                                                                                                                                这是业务活动监视工具从中收集跟踪数据的数据库。                                                                                                                                                                                                 |
   |       **规则引擎**数据库 (BizTalkRuleEngineDb)       |                                                                                                                                                                                       此数据库是策略、 规则和业务规则中的数据引用的词汇的存储库。                                                                                                                                                                                        |
   |        **BizTalk 跟踪**数据库 (BizTalkDTADb)        |                                                                                                                                                       此数据库存储业务数据和跟踪的运行状况监视数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪引擎。                                                                                                                                                       |
   |                  **SSO**数据库 (SSODB)                  |                                                                                                                                                                                                                      此数据库存储的凭据信息。                                                                                                                                                                                                                       |
   |   **进程内主机**及相应的主机实例    |                                                                                                                                                                        进程内主机的范围内操作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进程空间。                                                                                                                                                                        |
   |    **独立主机**及相应的主机实例     |                                                                                                                                                                       独立的主机外部运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。                                                                                                                                                                        |
   | HTTP/S、 BizTalk 消息队列、 文件、 SMTP、 SOAP 和 SQL |                                                                                                                                                                   配置向导创建的适配器属于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。                                                                                                                                                                    |


2. 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 WMI 来将组件添加到你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]按需环境。 若要横向扩展你的解决方案，请添加 MessageBox 数据库、 主机和服务器。  

3. 使用 BizTalk 管理控制台或 WMI 在映射的服务器上创建主机实例。 此步骤将确定哪些服务器上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将运行。 在企业中的需求更改时，可以将服务器添加、 删除服务器，并更改服务器到主机映射。  

## <a name="see-also"></a>请参阅  
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [主机](../core/hosts.md)   
 [主机实例](../core/host-instances.md)