---
title: SQL 适配器示例 |Microsoft 文档
description: 可以用于 BizTalk Server、 WCF 服务模型和 WCF 通道模型的 SQL WCF 适配器示例
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
ms.openlocfilehash: 0729b18dc900800ed39ccae31acfdd37b38b4573
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013940"
---
# <a name="samples-for-the-sql-adapter"></a>有关 SQL 适配器的示例

示例[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]分为：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 示例  
  
-   WCF 服务模型示例  
  
-   WCF 通道模型示例  
  
这些示例位于[BizTalk 适配器包 2010年: SQL 适配器示例](https://www.microsoft.com/download/details.aspx?id=22455)。 包含表，在示例中，例如，数据库，使用用于创建对象的 SQL 脚本和过程。 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
以下列表介绍这些示例。
  
## <a name="biztalk-server-samples"></a>BizTalk Server 示例  
  
|示例目录名称|Description|  
|---------------------------|-----------------|  
|ExecuteStoredProcedure|演示如何调用存储的过程在 SQL Server 数据库中使用的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|SelectTable|演示如何执行上使用的适配器的 SQL Server 数据库表选择操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|CompositeOperations|演示如何执行 SQL Server 数据库使用的适配器上的复合操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|TypedPolling|演示如何在 SQL Server 数据库使用的适配器上执行强类型轮询[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|FILESTREAMOperation|演示如何执行上使用的适配器的 SQL Server 2008 数据库的 FILESTREAM 操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|IncrementalNotification|演示如何从 SQL Server 数据库使用的适配器接收增量通知[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。|  
|Employee_PurchaseOrder|示例基于[教程 2： 员工-采购订单过程使用 SQL 适配器](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。|  
  
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
[开发 SQL 应用程序](develop-your-sql-applications.md)