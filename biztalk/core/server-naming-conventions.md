---
title: "命名约定的服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, naming conventions
- naming conventions, servers
- installation, naming conventions
ms.assetid: 98989c15-51d7-4a67-b054-abe6993a98a6
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a54e61a9ec37754158697a57a3f310d9edb90ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="server-naming-conventions"></a>服务器命名约定
有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。  
  
 下表描述了本主题中的关系图中的服务器[大型分布式体系结构](../core/large-distributed-architecture.md)，及其功能。  
  
|关系图中的服务器名称|函数|Description|  
|----------------------------|--------------|-----------------|  
|FW4|防火墙|Internet 和外围网络之间的 forefront Threat Management Gateway (TMG) 2010年服务器。|  
|HTTP（接收）|Web 服务器|Web 服务器，用于接收 HTTP 适配器的消息。 此服务器未安装 BizTalk Server 组件，但具有可将消息中继到服务接口域的 ASP.NET 页。 您可使用反向代理将消息从 FW 4 中继到 FW 3，而不使用 ASP.NET 页。 如果使用反向代理，则不需要此服务器。|  
|交换（发送/接收）|邮件服务器|邮件服务器，BizTalk Server 使用该服务器发送和接收 SMTP 消息。 POP3 适配器读取收到的消息|  
|FTP（发送/接收）|Web 服务器|表示文件传输协议 (FTP) 服务器，BizTalk 通过该服务器发送和接收消息。 此服务器可为远程服务器。|  
|SQL|SQL Server|包含 SQL 适配器所用的 SQL Server 数据库的服务器。|  
|文件|文件服务器|服务接口域中的文件适配器从中存放和提取文件的文件目录所在的服务器。|  
|FW3|防火墙|保护服务的 forefront Threat Management Gateway (TMG) 2010年服务器接口的域从外围网络和企业域。|  
|处理|处理服务器|此服务器用于处理消息。 它具有 BizTalk Server 运行时、业务规则引擎和企业单一登录 (SSO) 服务。 BizTalk 程序集、主机实例、业务流程、架构和映射均位于此服务器上。 给定的处理服务器可具有不同主机的实例。|  
|接收处理程序<br /><br /> （独立主机）|接收/发送服务器|BizTalk Server，专用于从 HTTP 和 SOAP 适配器接收消息。 给定的接收/发送服务器可具有不同主机的实例。|  
|接收处理程序<br /><br /> （进程内主机）|接收/发送服务器|BizTalk Server，专用于从 SQL 适配器、FTP 适配器、EDI 适配器、文件适配器、POP3 适配器和 BizTalk 消息队列适配器接收消息。 给定的接收/发送服务器可具有不同主机的实例。|  
|发送处理程序|接收/发送服务器|BizTalk Server，专用于发送所有适配器的消息。 给定的服务器可具有用于发送消息的不同主机的实例。|  
|FW2|防火墙|从服务接口和公司的域 （操作服务。） 保护服务域的 forefront Threat Management Gateway (TMG) 2010年服务器|  
|跟踪主机|跟踪服务器|具有用于跟踪的 BizTalk 主机实例的服务器。|  
|管理工具|管理服务器|具有 BizTalk Server 运行时、BizTalk Server 管理控制台和部署工具的服务器。|  
|主密钥服务器|主密钥服务器|用于管理整个环境的主密钥的 SSO 服务器。 此计算机上没有其他 BizTalk Server 组件。|  
|FW1|防火墙|Forefront Threat Management Gateway (TMG) 2010年服务器保护的数据域的服务接口和服务域。|  
|MessageBox 1<br /><br /> MessageBox 2<br /><br /> MessageBox“n”|数据服务器|SQL Server，其中包含 MessageBox 数据库。 可以为每个 MessageBox 数据库使用不同的 SQL Server。|  
|SSO|数据服务器|SQL Server，包含 SSO 数据库，企业单一登录使用该数据库以加密的形式存储用户 ID 和凭据，这些 ID 和凭据用于登录到其他系统以及以加密的形式存储 BizTalk Server 所使用的适配器的配置信息表单。|  
|备份/还原日志传送|数据服务器|SQL Server，用于还原由 BizTalk Server 数据库生成的数据库备份。|  
|BizTalk 分析|数据服务器|分析服务器，包含 BizTalk 分析数据库。|  
  
 下表描述了在关系图中的主题中的其他服务器[大型分布式体系结构与信息辅助服务](../core/large-distributed-architecture-with-information-worker-services.md)相比主题中的关系图及其功能[大分布式体系结构](../core/large-distributed-architecture.md)。  
  
|服务器名称|函数|Description|  
|-----------------|--------------|-----------------|  
|BAM 门户|BAM 门户|包含 BAM 门户的服务器。 业务最终用户使用 BAM 门户来访问 BAM 数据库，以便监视关键性能指标 (KPI) 和有关其业务流程的其他信息。|  
|通知服务<br /><br /> Windows SharePoint Services 配置<br /><br /> Windows SharePoint Services 内容<br /><br /> BAM 星型架构<br /><br /> BAM 主导入<br /><br /> BAM 存档<br /><br /> BAM 分析 (OLAP)|IW 数据服务器|包含业务活动监视所使用的数据库的 SQL Server。 可以为这些数据库使用多个 SQL Server。|  
|IW 客户端|IW 客户端|信息工作者为业务活动监视所使用的客户端计算机。|  
  
## <a name="see-also"></a>另请参阅  
 [大型分布式体系结构](../core/large-distributed-architecture.md)   
 [使用信息辅助服务的大型分布式体系结构](../core/large-distributed-architecture-with-information-worker-services.md)   
 [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)