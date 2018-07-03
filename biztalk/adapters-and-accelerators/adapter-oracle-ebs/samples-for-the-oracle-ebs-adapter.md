---
title: Oracle EBS 适配器示例 |Microsoft Docs
description: 可以使用 BizTalk Server、 WCF 服务模型和 WCF 通道模型使用的 oracle 企业业务套件 WCF 适配器示例
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12f19f13-3b01-40d6-b12c-811f99841040
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4fdffd6d24ce18c38c45a086ea0f6376241d21d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000881"
---
# <a name="samples-for-the-oracle-ebs-adapter"></a>适用于 Oracle EBS 适配器示例
示例[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]分为：  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
- WCF 服务模型示例  
  
- WCF 通道模型示例  
  
- Microsoft Office SharePoint Server 示例  
  
  这些示例目前[BizTalk 适配器包 2010年: Oracle E-business Suite 适配器示例](https://www.microsoft.com/download/details.aspx?id=6464)。 包含用于创建界面表、 并发程序、 表和示例中使用的包的 SQL 脚本。 
  
> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
 以下列表说明的示例。 
  
## <a name="biztalk-server-samples"></a>BizTalk Server 示例  
  
|    示例目录名称     |                                                                                                                                                                        Description                                                                                                                                                                        |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     InterfaceTableInsert     |                                                                                   演示如何在 Oracle E-business Suite 中使用的接口表中插入记录[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                                    |
|      ConcurrentProgram       |                                                                                       演示如何调用并发程序中使用 Oracle E-business Suite [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                                       |
|          RequestSet          |                                                                                          演示如何调用在 Oracle E-business Suite 中设置的请求[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                                           |
|      MsgContextProperty      | 演示如何使用公开的消息上下文属性[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要设置应用程序上下文上执行操作的项目中使用 Oracle E-business Suite [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 |
| OracleEBS_CompositeOperation |                                                                                      演示如何在 Oracle E-business Suite 中使用执行复合操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                                       |
|   OracleNotifyIncremental    |                                                                                   演示如何从 Oracle 使用接收"递增"查询通知消息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                                    |
| PollingUsingSelectStatement  |                                                                            演示如何配置使用的 SELECT 语句轮询查询并接收结果使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                            |
|    PollingUsingStoredProc    |                                                                            演示如何配置使用的存储的过程的轮询查询并接收结果使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。                                                                            |
  
## <a name="wcf-service-model-sasamplesmples"></a>WCF 服务模型 Sasamplesmples  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|ConcProgram_ServiceModel|演示如何调用并发程序使用的适配器 Oracle E-business Suite 中。|  
|ExecuteReader|演示如何调用 ExecuteReader 操作 Oracle E-business Suite 使用适配器。|  
|Interface_Table_Ops|演示如何使用适配器 Oracle E-business Suite 中执行对界面表的操作。|  
|LargeDataTypes_ServiceModel|演示如何使用适配器 Oracle E-business Suite 中执行具有较大的数据类型的列的表的操作。|  
|Notification_ServiceModel|演示如何从 Oracle E-business Suite 使用适配器后的数据库中接收通知。|  
|SelectPolling_ServiceModel|演示如何使用 SELECT 语句来轮询中使用的适配器 Oracle E-business Suite 的接口表。|  
|StoredProcPolling_ServiceModel|演示如何使用存储的过程来轮询使用适配器 Oracle E-business Suite 中的表。|  
  
## <a name="wcf-channel-model-samples"></a>WCF 通道模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|InsertOperation|演示如何使用适配器 Oracle E-business Suite 中执行插入操作在界面表。|  
|SelectPolling_ChannelModel|演示如何使用 SELECT 语句来轮询中使用的适配器 Oracle E-business Suite 的接口表。|  
  
## <a name="microsoft-office-sharepoint-server-samples"></a>Microsoft Office SharePoint Server 示例  
  
| 示例目录名称 |                                                                                                                                                                  Description                                                                                                                                                                   |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      MOSS_Sample      | 演示如何使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]从 Oracle E-business Suite 项目创建 Windows Communication Foundation (WCF) 服务，然后使用 WCF 服务在 Microsoft Office SharePoint Server 使用业务数据列表 Web 部件中显示数据。 |
  
## <a name="see-also"></a>请参阅  
[开发 Oracle E-business Suite 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)