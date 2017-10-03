---
title: "教程 2： 员工-采购订单过程使用 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fca0c11aeb1f84a5e9f05a4df4f995b7c2b52e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a>教程 2： 员工-采购订单过程使用 SQL 适配器
在本教程中，你要实现自动化其中将设备的购买部门排序每次新员工加入企业组织的过程。 员工详细信息和购买订单详细信息保留在**员工**和**Purchase_Order**分别，表中的 SQL Server 数据库。 通过更新 SQL Server 数据库中的 Purchase_Order 表并发送一封电子邮件，购买部门将得到通知。 在此过程中，将出现以下操作：  
  
1.  适配器将接收通知每次**员工**更新表。 然后，适配器将通知发送到 BizTalk 业务流程。  
  
2.  BizTalk 业务流程指出是否通知是一条新记录插入到**员工**表。 如果通知适用于任何其他操作上**员工**表，业务流程不执行任何操作。  
  
3.  如果通知为插入操作上**员工**表，通知已添加新的员工记录、 业务流程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]读取新记录的详细信息。  
  
4.  业务流程接收响应，其中包含新添加的员工记录的详细信息。 业务流程地图**Employee_ID**和**代码**中插入操作的请求消息的响应上的字段**Purchase_Order**表。  
  
5.  然后，业务流程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上执行插入操作**Purchase_Order**表。 插入操作的响应作为电子邮件发送到购买部门。  
  
## <a name="about-the-database-objects-used-in-this-sample"></a>有关在此示例中使用的数据库对象  
 本教程使用随示例提供的 SQL 脚本创建的数据库对象。 有关脚本和示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 将在本教程中使用的数据库对象是：  
  
-   **ADAPTER_SAMPLES**数据库。  
  
-   **员工**和**Purchase_Order**表。  
  
-   **UPDATE_EMPLOYEE**存储过程。  
  
 当你运行该示例提供的 SQL 脚本创建所有这些数据库对象。 请确保在开始本教程与之前运行脚本。  
  
## <a name="sample-based-on-this-tutorial"></a>基于本教程的示例  
 示例中， **Employee_PurchaseOrder**，后者基于本教程还提供了与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
 我们建议你完成本教程完全若要了解如何创建使用该适配器，BizTalk 项目，然后查看作为引用示例。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [第 1 课： 生成架构，并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [第 2 课： 接收和筛选器通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [第 3 课： 执行存储的过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [第 4 课： 执行插入操作上采购订单表](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [第 5 课： 部署解决方案](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)