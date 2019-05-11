---
title: 运行中群集 Host1 的适配器处理程序的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- receive adapters, clustering
- clustering, POP3 adapters
- FTP adapters, clustering
- clustering, receive adapters
- NLB system
- MSMQ send handler
- MSMQ receive handler
- clustering, FTP adapters
- handlers [adapters], best practices
- hosts, clustering
- MSMQ adapters
- clustering, MSMQ adapters
- adapters, best practices
- adapters, handlers
- POP3 adapters, clustering
- MSMQ adapters, clustering
- clustering
ms.assetid: ee66663c-4f4d-4515-9df1-aacf4fc72be4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6ac819e5255a423427e0e8c10235f73ab1ced5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390388"
---
# <a name="considerations-for-running-adapter-handlers-within-a-clustered-host"></a>运行在群集主机内的适配器处理程序的注意事项
BizTalk 主机群集支持，可用于为以下集成的 BizTalk 适配器提供高可用性： FTP 适配器、 SFTP 适配器、 MSMQ 适配器和 POP3 适配器。 主机群集支持还提供，以便运行为目的的按序送达的适配器的单个实例的高可用性。  
  
 所有 BizTalk 适配器处理程序可以在群集主机中运行，但没有任何好处除群集主机中运行适配器处理程序，如下所述。 如果您的处理要求不包括任何下面描述的方案，则应在群集主机中不运行适配器处理程序。  
  
## <a name="running-the-ftp-or-sftp-adapter-receive-handler-within-a-clustered-biztalk-host"></a>运行 FTP 或 SFTP 适配器接收处理程序在群集 BizTalk 主机内  
 对于大多数集成的适配器，高可用性可以通过创建多个适配器处理程序在 BizTalk 上运行的 BizTalk server 的主机实例上不同[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 组内的服务器。 FTP 或 SFTP 适配器接收处理程序不应但是，将配置为同时在多个 BizTalk 主机实例中运行。 提出此建议是因为 FTP 或 SFTP 接收适配器使用 FTP 或 SFTP 协议从目标系统检索文件。 FTP 或 SFTP 协议不会锁定文件，以确保不会同时检索同一文件的多个副本正在运行的多个实例的 FTP 或 SFTP 接收适配器时。  
  
 若要确保高可用性为 FTP 或 SFTP 接收适配器，应配置 FTP 或 SFTP 接收适配器已群集的 BizTalk 主机实例中运行。  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>在群集 BizTalk 主机内运行 MSMQ 适配器处理程序  
 若要确保 MSMQ 适配器的高可用性并确保消息由 MSMQ 适配器发送或接收的事务一致性，应执行以下操作：  
  
1. 在 Windows 群集组中的群集资源配置消息队列 (MSMQ) 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
2. 将群集的 MSMQ 服务添加到的资源依赖关系列表中，为群集的 BizTalk 主机。 这可确保在群集的 BizTalk 主机始终开始之后发生故障转移群集的 MSMQ 服务。  
  
3. 配置 MSMQ 适配器发送和接收处理程序已配置为群集 MSMQ 资源所在的群集组中的群集资源的 BizTalk 主机实例中。  
  
   由于以下原因建议使用以下步骤：  
  
   **MSMQ 适配器接收处理程序**– MSMQ 4.0 (Windows Server 2008) 之前的 MSMQ 版本不支持远程事务性读取，支持仅本地事务读取。 在这种情况下，MSMQ 适配器接收处理程序必须是本地群集的消息队列服务，以完成本地事务读取使用 MSMQ 适配器的主机实例中运行。  
  
> [!IMPORTANT]
>  MSMQ 适配器接收处理程序要求在接收处理程序主机实例运行的同一台计算机上正在运行消息队列服务的本地非群集实例。  
  
 **MSMQ 适配器发送处理程序**-若要确保所做的 MSMQ 适配器，使用 MSMQ 适配器发送处理程序的传出队列的事务发送的一致性，以便如果 MSMQ 服务的传出队列失败则可能应具备高可用性已恢复。 在群集组中配置群集的消息 Queuingresource 和 MSMQ 适配器处理程序将确保使用 MSMQ 适配器发送处理程序的传出队列具有高可用性。 在的消息队列服务失败，这将降低消息丢失的可能性。  
  
> [!NOTE]
>  MSMQ 接收位置是否**仅**接收来自远程 MSMQ 服务器上的 MSMQ 队列，则可以通过运行 MSMQ 实现高可用性 BizTalk 组中接收多个 BizTalk 计算机上的主机。  若要为 MSMQ 提供高可用性，必须确保远程 MSMQ 服务器正在使用中 Windows 故障转移群集。  如果使用的事务性队列，必须运行远程 MSMQ 服务器 MSMQ 4.0 (Windows Server 2008) 或更高版本。  
  
## <a name="running-the-pop3-adapter-receive-handler-within-a-clustered-biztalk-host"></a>运行 POP3 适配器接收处理程序在群集 BizTalk 主机内  
 POP3 适配器接收处理程序不需要将配置为群集的 BizTalk 主机中运行，除非适配器从中进行读取的 POP3 服务器允许对同一邮箱进行多个并发连接。 如果 POP3 适配器连接到的 POP3 服务器允许对其邮箱，多个并发连接，则我们建议您确保高可用性通过配置单个 POP3 适配器的 POP3 适配器接收处理程序为 BizTalk 主机中运行已群集的实例。 提出此建议以确保不会同时检索同一电子邮件的多个副本正在运行的多个实例的 POP3 接收适配器时。  
  
## <a name="running-a-receive-adapter-that-supports-ordered-delivery-with-a-clustered-biztalk-host"></a>运行支持群集的 BizTalk 主机使用按序送达的接收适配器  
 MSMQ 和 MQSeries 集成的适配器能够将文档提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收的顺序。 正确实现此功能需要单个实例的这些接收适配器在任何给定时间运行。 若要为这些适配器的单个实例提供高可用性，应将它们配置为在群集 BizTalk 主机实例中运行。