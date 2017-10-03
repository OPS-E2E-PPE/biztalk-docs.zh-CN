---
title: "有关 SQL 适配器的示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2438696-bc51-46df-81ca-00c17a52736e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0e5f82bee9e13d9e19633f2c8ac6b62ce19e27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="samples-for-the-sql-adapter"></a>有关 SQL 适配器的示例
示例[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]分为：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
-   WCF 服务模型示例  
  
-   WCF 通道模型示例  
  
 这些示例都位于[BizTalk 开发人员中心](https://msdn.microsoft.com/biztalk/biztalk-codesamples)。 用于创建在示例中，例如数据库、 表、 过程等，所使用的对象的 SQL 脚本，还提供以及这些示例。  
  
 以下列表包含的名称和描述的示例[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="biztalk-server-samples"></a>BizTalk Server 示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|ExecuteStoredProcedure|演示如何调用存储的过程在 SQL Server 数据库中使用的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|SelectTable|演示如何执行上使用的适配器的 SQL Server 数据库表选择操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|CompositeOperations|演示如何执行 SQL Server 数据库使用的适配器上的复合操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|TypedPolling|演示如何在 SQL Server 数据库使用的适配器上执行强类型轮询[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|FILESTREAMOperation|演示如何执行上使用的适配器的 SQL Server 2008 数据库的 FILESTREAM 操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|IncrementalNotification|演示如何从 SQL Server 数据库使用的适配器接收增量通知[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|Employee_PurchaseOrder|示例基于[教程 2： 员工-采购订单过程使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。|  
  
## <a name="wcf-service-model-samples"></a>WCF 服务模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|EmployeeBasicOps|演示如何执行插入、 选择、 更新和删除使用该适配器的 SQL Server 数据库上的操作。|  
|ExecuteReader|演示如何调用 ExecuteReader 操作使用该适配器的 SQL Server 数据库上。|  
|Execute_StoredProc|演示如何调用使用适配器的 SQL Server 数据库中的存储的过程。|  
|Execute_TypedStoredProcedure|演示如何调用中使用该适配器的 SQL Server 数据库的强类型的存储的过程。|  
|Records_FILESTREAM_Op|演示如何更新使用适配器的 SQL Server 数据库表中的 FILESTREAM 数据。|  
|ScalarFunction_ServiceModel|演示如何调用中使用该适配器的 SQL Server 数据库的标量函数。|  
|TableFunction_ServiceModel|演示如何调用中使用该适配器的 SQL Server 数据库表值函数。|  
|Polling_ServiceModel|演示如何从 SQL Server 数据库使用适配器接收基于轮询的数据更改消息。|  
|TypedPolling_ServiceModel|演示如何从 SQL Server 数据库使用适配器接收强类型基于轮询的数据更改消息。|  
|Notification_ServiceModel|演示如何从 SQL Server 数据库使用适配器接收查询通知。|  
  
## <a name="wcf-channel-model-samples"></a>WCF 通道模型示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|EmployeeInsertOp|演示如何执行插入操作使用该适配器的 SQL Server 数据库上。|  
|Polling_ChannelModel|演示如何从 SQL Server 数据库使用适配器接收基于轮询的数据更改消息。|  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)