---
title: 教程 2:员工-采购订单流程使用 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2e0968743f88c9ae7d5b5ca683f0fb46d81f5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367489"
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a>教程 2:员工-采购订单流程使用 SQL 适配器
在本教程中，将自动在其中放置设备的采购部门订购每次新员工加入组织的过程。 在中维护员工详细信息和采购订单详细信息**员工**并**Purchase_Order**表分别，SQL Server 数据库中。 通过更新 SQL Server 数据库中的 Purchase_Order 表并发送一封电子邮件，采购部门将得到通知。 在进程中，执行下列操作：  
  
1. 适配器接收的通知每次**员工**更新表。 然后，适配器向 BizTalk 业务流程发送通知。  
  
2. BizTalk 业务流程计算出通知是一条新记录插入到**员工**表。 如果通知是任何其他操作上**员工**表中，业务流程不会执行任何操作。  
  
3. 如果通知是插入操作上**员工**表中，通知已添加一个新雇员记录，该业务流程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]读取新记录的详细信息。  
  
4. 业务流程收到响应，其中包含新添加的员工记录的详细信息。 业务流程映射**Employee_ID**并**指定**插入操作的请求消息的响应中字段上**Purchase_Order**表。  
  
5. 该业务流程将使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上执行插入操作**Purchase_Order**表。 插入操作的响应作为电子邮件发送给采购部门。  
  
## <a name="about-the-database-objects-used-in-this-sample"></a>在此示例中使用的数据库对象  
 本教程使用示例随附的 SQL 脚本创建的数据库对象。 有关脚本和示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。 将在本教程中使用的数据库对象包括：  
  
- **ADAPTER_SAMPLES**数据库。  
  
- **员工**并**Purchase_Order**表。  
  
- **UPDATE_EMPLOYEE**存储过程。  
  
  在运行 SQL 脚本的示例时创建所有这些数据库对象。 请确保在开始本教程之前运行脚本。  
  
## <a name="sample-based-on-this-tutorial"></a>基于本教程的示例  
 示例中， **Employee_PurchaseOrder**，后者基于本教程还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
 我们建议你完成本教程中，完全以了解如何创建使用该适配器的 BizTalk 项目，然后查看作为参考示例。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [第 1 课：生成架构并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [第 2 课：接收和筛选通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [第 3 课：执行存储过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [第 4 课：在采购订单表中执行插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [第 5 课：部署解决方案](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)