---
title: "Oracle EBS 适配器示例 |Microsoft 文档"
description: "可以用于 BizTalk Server、 WCF 服务模型和 WCF 通道模型的 oracle 企业业务套件 WCF 适配器示例"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12f19f13-3b01-40d6-b12c-811f99841040
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4069b7f5916291544ce76534e04b20af5680d69
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-oracle-ebs-adapter"></a>Oracle EBS 适配器的的示例
示例[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]分为：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
-   WCF 服务模型示例  
  
-   WCF 通道模型示例  
  
-   Microsoft Office SharePoint Server 示例  
  
 这些示例位于[BizTalk 适配器包 2010年: Oracle E-business Suite 适配器示例](https://www.microsoft.com/download/details.aspx?id=6464)。 用于创建接口表、 并发程序、 表和示例中使用的包的 SQL 脚本是包含。 
  
> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 以下列表介绍这些示例。 
  
## <a name="biztalk-server-samples"></a>BizTalk Server 示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|InterfaceTableInsert|演示如何在 Oracle E-business Suite 中使用接口表中插入记录[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|ConcurrentProgram|演示如何以调用在 Oracle E-business Suite 中使用的并发程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|RequestSet|演示如何以调用在 Oracle E-business Suite 中设置的请求[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|MsgContextProperty|演示如何使用公开的消息上下文属性[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]设置应用程序上下文上执行操作项目中使用 Oracle E-business Suite [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|OracleEBS_CompositeOperation|演示如何在 Oracle E-business Suite 使用执行复合操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|OracleNotifyIncremental|演示如何从 Oracle 使用接收"增量"查询通知消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|PollingUsingSelectStatement|演示如何配置一个轮询查询使用 SELECT 语句和接收使用对结果[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|PollingUsingStoredProc|演示如何配置一个轮询查询使用存储的过程和接收使用对结果[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
  
## <a name="wcf-service-model-sasamplesmples"></a>WCF 服务模型 Sasamplesmples  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|ConcProgram_ServiceModel|演示如何调用中使用该适配器的 Oracle E-business Suite 的并发程序。|  
|ExecuteReader|演示如何调用上使用该适配器的 Oracle E-business Suite ExecuteReader 操作。|  
|Interface_Table_Ops|演示如何对表执行操作接口中使用该适配器的 Oracle E-business Suite。|  
|LargeDataTypes_ServiceModel|演示如何使用适配器 Oracle E-business Suite 中执行具有较大的数据类型的列的表操作。|  
|Notification_ServiceModel|演示如何使用适配器 Oracle E-business Suite 后面的数据库从接收通知。|  
|SelectPolling_ServiceModel|演示如何使用 SELECT 语句来轮询 Oracle E-business Suite 使用适配器中的接口表。|  
|StoredProcPolling_ServiceModel|演示如何使用存储的过程来轮询 Oracle E-business Suite 使用适配器中的表。|  
  
## <a name="wcf-channel-model-samples"></a>WCF 通道模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|InsertOperation|演示如何在使用该适配器的 Oracle E-business Suite 中执行对接口表的插入操作。|  
|SelectPolling_ChannelModel|演示如何使用 SELECT 语句来轮询 Oracle E-business Suite 使用适配器中的接口表。|  
  
## <a name="microsoft-office-sharepoint-server-samples"></a>Microsoft Office SharePoint Server 示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|MOSS_Sample|演示如何使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle E-business Suite 项目，创建 Windows Communication Foundation (WCF) 服务，然后使用 WCF 服务在 Microsoft Office SharePoint Server 使用业务数据列表 Web 部件中显示数据。|  
  
## <a name="see-also"></a>另请参阅  
[开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)