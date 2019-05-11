---
title: 服务器命名约定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, naming conventions
- naming conventions, servers
- installation, naming conventions
ms.assetid: 98989c15-51d7-4a67-b054-abe6993a98a6
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a727ca9c817c182055ba6a6580d02f394bdceba7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393320"
---
# <a name="server-naming-conventions"></a>服务器命名约定
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。  
  
 下表描述了本主题中的关系图中的服务器[大型分布式体系结构](../core/large-distributed-architecture.md)，及其功能。  
  
|在关系图中的服务器名称|函数|Description|  
|----------------------------|--------------|-----------------|  
|FW4|防火墙|在 Internet 和外围网络之间的 forefront Threat Management Gateway (TMG) 2010年服务器。|  
|HTTP （接收）|Web 服务器|接收 HTTP 适配器的消息的 web 服务器。 此服务器不具有 BizTalk Server 组件安装;它具有将消息中继到服务接口域的 ASP.NET 页面。 您可以使用反向代理从 FW 4 中继到 FW 3，而不是 ASP.NET 页。 如果使用反向代理，则不需要此服务器。|  
|Exchange （发送/接收）|邮件服务器|BizTalk Server 用于发送和接收 SMTP 消息的邮件服务器。 POP3 适配器读取收到的消息|  
|FTP （发送/接收）|Web 服务器|表示 BizTalk 是从其发送和接收消息的文件传输协议 (FTP) 服务器。 这可以是远程服务器。|  
|SQL|SQL Server|使用 SQL 适配器所使用的 SQL Server 数据库服务器。|  
|文件|文件服务器|从其文件适配器在服务接口域的文件目录的服务器存放和提取文件。|  
|FW3|防火墙|Forefront Threat Management Gateway (TMG) 2010年服务器，用于保护服务接口域从外围网络和公司域。|  
|处理|处理服务器|此服务器处理的消息。 它具有 BizTalk Server 运行时、 业务规则引擎和企业单一登录 (SSO) 服务。 BizTalk 程序集、 主机实例、 业务流程、 架构和映射是此服务器上。 给定的处理服务器可具有不同主机的实例。|  
|接收处理程序<br /><br /> （独立主机）|接收/发送服务器|BizTalk Server，专用于从 HTTP 和 SOAP 适配器接收消息。 给定接收/发送服务器可以具有不同主机的主机实例。|  
|接收处理程序<br /><br /> （进程内主机）|接收/发送服务器|BizTalk Server，专用于从 SQL、 FTP、 EDI、 文件、 POP3 适配器和 BizTalk 消息队列适配器接收消息。 给定接收/发送服务器可以具有不同主机的主机实例。|  
|发送处理程序|接收/发送服务器|BizTalk Server，专用于所有适配器发送消息。 在给定的服务器可以用来发送消息的不同主机的主机实例。|  
|FW2|防火墙|Forefront Threat Management Gateway (TMG) 2010年服务器，用于保护服务域服务接口和公司域 （操作服务）。|  
|跟踪主机|跟踪服务器|具有用于跟踪的 BizTalk 主机的主机实例的服务器。|  
|管理工具|管理服务器|具有 BizTalk Server 运行时、 BizTalk Server 管理控制台中，以及部署工具的服务器。|  
|主密钥服务器|主密钥服务器|管理主密钥的整个环境的 SSO 服务器。 在此计算机上没有其他 BizTalk Server 组件。|  
|FW1|防火墙|Forefront Threat Management Gateway (TMG) 2010年服务器，用于保护数据域、 服务接口域和服务域。|  
|MessageBox 1<br /><br /> MessageBox 2<br /><br /> MessageBox n|数据服务器|包含 MessageBox 数据库的 SQL Server。 您可以为每个 MessageBox 数据库不同的 SQL Server。|  
|SSO|数据服务器|包含企业单一登录用于存储加密的形式的用户 Id 和凭据用于登录到其他系统和以加密形式存储 BizTalk Server 使用的适配器的配置信息表单中的 SSO 数据库的 SQL Server.|  
|日志传送的备份/还原|数据服务器|SQL Server 用于还原由 BizTalk Server 数据库生成的数据库备份。|  
|BizTalk 分析|数据服务器|包含 BizTalk 分析数据库的 analysis Server。|  
  
 下表描述了本主题中的关系图中的其他服务器[具有信息工作者服务的大型分布式结构](../core/large-distributed-architecture-with-information-worker-services.md)主题中的关系图相比及其功能[大分布式体系结构](../core/large-distributed-architecture.md)。  
  
|服务器名称|函数|Description|  
|-----------------|--------------|-----------------|  
|BAM 门户|BAM 门户|包含 BAM 门户的服务器。 业务最终用户使用 BAM 门户来访问 BAM 数据库，以便监视关键性能指标 (Kpi) 和有关其业务流程的其他信息。|  
|通知服务<br /><br /> Windows SharePoint Services 配置<br /><br /> Windows SharePoint Services 内容<br /><br /> BAM 星型架构<br /><br /> BAM 主导入<br /><br /> BAM 存档<br /><br /> BAM 分析 (OLAP)|IW 数据服务器|包含使用业务活动监视的数据库的 SQL Server。 这些数据库，可以使用多个 SQL Server。|  
|IW 客户端|IW 客户端|信息工作者使用为业务活动监视的客户端计算机。|  
  
## <a name="see-also"></a>请参阅  
 [大型分布式体系结构](../core/large-distributed-architecture.md)   
 [具有信息工作者服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)