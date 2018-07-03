---
title: SQL 适配器示例 |Microsoft Docs
description: 可以使用 BizTalk Server、 WCF 服务模型和 WCF 通道模型使用的 SQL WCF 适配器示例
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2438696-bc51-46df-81ca-00c17a52736e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f7ff1e686fd8de344c4de4513fbda84003c69a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982630"
---
# <a name="samples-for-the-sql-adapter"></a>SQL 适配器示例

示例[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]分为：  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
- WCF 服务模型示例  
  
- WCF 通道模型示例  
  
这些示例目前[BizTalk 适配器包 2010年: SQL 适配器示例](https://www.microsoft.com/download/details.aspx?id=22455)。 包含表，在示例中，例如，数据库，用于创建对象的 SQL 脚本和过程。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
以下列表说明的示例。
  
## <a name="biztalk-server-samples"></a>BizTalk Server 示例  
  
|  示例目录名称  |                                                                                          Description                                                                                          |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ExecuteStoredProcedure  |      演示如何调用存储的过程在 SQL Server 数据库中使用的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。      |
|       SelectTable       |  演示如何执行针对 SQL Server 数据库表使用的适配器的选择操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  |
|   CompositeOperations   |    演示如何执行复合操作使用的适配器的 SQL Server 数据库上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。    |
|      TypedPolling       |   演示如何使用的适配器的 SQL Server 数据库上执行强类型轮询[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。   |
|   FILESTREAMOperation   | 演示如何执行 FILESTREAM 操作上使用的适配器的 SQL Server 2008 数据库[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 |
| IncrementalNotification | 演示如何从 SQL Server 数据库使用的适配器接收增量通知[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 |
| Employee_PurchaseOrder  |                  示例基于[教程 2： 员工-采购订单流程使用 SQL 适配器](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。                  |
  
## <a name="wcf-service-model-samples"></a>WCF 服务模型示例   
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|EmployeeBasicOps|演示如何执行 Insert、 Select、 Update 和删除 SQL Server 数据库使用的适配器上的操作。|  
|ExecuteReader|演示如何调用 ExecuteReader 操作使用的适配器的 SQL Server 数据库。|  
|Execute_StoredProc|演示如何调用中使用的适配器的 SQL Server 数据库的存储的过程。|  
|Execute_TypedStoredProcedure|演示如何调用中使用适配器的 SQL Server 数据库的强类型化的存储的过程。|  
|Records_FILESTREAM_Op|演示如何更新使用的适配器的 SQL Server 数据库表中的 FILESTREAM 数据。|  
|ScalarFunction_ServiceModel|演示如何调用标量函数中使用的适配器的 SQL Server 数据库。|  
|TableFunction_ServiceModel|演示如何调用表值函数中使用的适配器的 SQL Server 数据库。|  
|Polling_ServiceModel|演示如何从 SQL Server 数据库使用的适配器接收基于轮询的数据更改消息。|  
|TypedPolling_ServiceModel|演示如何从 SQL Server 数据库使用的适配器接收强类型基于轮询的数据更改消息。|  
|Notification_ServiceModel|演示如何从 SQL Server 数据库使用的适配器接收查询通知。|  
  
## <a name="wcf-channel-model-samples"></a>WCF 通道模型示例 
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|EmployeeInsertOp|演示如何执行插入操作上使用该适配器的 SQL Server 数据库。|  
|Polling_ChannelModel|演示如何从 SQL Server 数据库使用的适配器接收基于轮询的数据更改消息。|  
  
## <a name="see-also"></a>请参阅  
[开发 SQL 应用程序](develop-your-sql-applications.md)