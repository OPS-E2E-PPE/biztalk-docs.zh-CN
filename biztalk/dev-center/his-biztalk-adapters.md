---
title: Host Integration Server 中包含的 BizTalk 适配器 |Microsoft Docs
description: 他包含的主机应用程序、 主机文件、 DB2 和 WebSphere MQ 的 BizTalk 适配器概述
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 138e49965520505c2f45203836af7172dfd56612
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401538"
---
# <a name="biztalk-adapters-for-host-systems"></a>主机系统的的 BizTalk 适配器


## <a name="biztalk-adapter-for-host-applications"></a>主机应用程序的的 BizTalk 适配器

用于主机应用程序的 Microsoft BizTalk 适配器用于 BizTalk Server。 它是 Windows-Initiated 处理命令，从而使对现有 IBM 大型机 zSeries （CICS 和 IMS） 或中型机 iSeries (RPG) 服务器程序高效的客户端访问基于技术中 Microsoft 事务集成器 (TI)。 

TI 设计工具集成使用 Visual Studio 和 BizTalk Server 解决方案，使 IT 开发人员能够定义客户端代理时追求高生产力和创建 XSD 架构。 对于 BizTalk Server 管理员，现有的 TI 管理器，Microsoft 管理控制台 (MMC) 管理单元中，已增强，提高可支持性和支持所需的远程 BizTalk Server 解决方案部署方案。

请参阅[托管应用程序的 BizTalk 适配器](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx)。 

## <a name="biztalk-adapter-for-host-files"></a>主机文件的 BizTalk 适配器
用于主机文件的 Microsoft BizTalk 适配器是支持 IT 部门能够访问并将信息存储在主机文件系统，包括大型机 zSeries VSAM 数据集和中型机 iSeries 物理文件中集成的高级的数据适配器。 

BizTalk Server 解决方案中使用的 visual Studio 设计工具用于定义主机程序描述文件，然后将导出为 XSD 的 BizTalk 适配器一起使用的元数据映射。 配置向导集成到 BizTalk Server 管理工具，允许 IT 专业人员定义的动态发送端口和静态和要求响应接收端口，基于一组简化的 SQL 命令 (SELECT、 INSERT、 UPDATE、 DELETE). 

此 BizTalk 适配器基于 SQL 映射到主机的非关系数据集和成员的主机文件的 Microsoft.NET Framework 数据提供程序。 这使得更易于非编程人员读取和写入文件数据源的主机。

请参阅[主机文件的 BizTalk 适配器](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx)。

## <a name="biztalk-adapter-for-db2"></a>用于 DB2 的 BizTalk 适配器
用于 DB2 的 Microsoft BizTalk 适配器是使 IT 专业人员能够访问存储在远程计算平台、 IBM 大型机 zSeries 和中型机 iSeries (DB2/400)，以及 IBM DB2 的主机上的 IBM DB2 数据库服务器中的重要数据的关系数据库适配器通用数据库 (UDB) 在开放平台上。 

使用标准 SQL 命令以及 BizTalk Server 管理工具中内置的配置向导，IT 专业人员可以创建的读取和写入 DB2 而无需进行数据库编程解决方案。 DB2 适配器，也不能基于 DB2 的 Microsoft.NET Framework 数据提供程序、 支持范围广泛的功能，包括动态发送端口和静态要求响应接收端口。

请参阅[用于 DB2 的 BizTalk 适配器](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx)。

## <a name="biztalk-adapter-for-websphere-mq"></a>适用于 WebSphere MQ 的 BizTalk 适配器
用于 WebSphere MQ （基于客户端） 的 Microsoft BizTalk 适配器使用 IBM WebSphere MQ 客户端 （基本客户端） 和 IBM WebSphere MQ 扩展事务客户端 （扩展客户端） Api 来与远程 MQSeries 队列管理器进行通信。 该适配器，BizTalk Server 可直接与 MQSeries 队列管理器部署在非 Windows 操作系统，而无需部署和管理 WebSphere MQ 服务器的 Windows，若要有效地与交换消息的业务通信企业范围内的应用程序。 

当用于基本客户端，适配器提供了非事务性消息处理保证消息的发送。 它负责在接收端上的应用程序以处理任何重复消息。 当用于扩展客户端，适配器提供了事务性消息处理，以保证一次-和-仅限-传递消息一次。

请参阅[适用于 WebSphere MQ 的 BizTalk 适配器](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx)。
