---
title: "步骤 5： 测试解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ce7edd1c1f1f8a063e2787cc2acecb3b57cca2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-test-the-solution"></a>步骤 5： 测试解决方案
此解决方案旨在自动执行的将通知发送到过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，每次新机会的关闭时在 Salesforce 中通过设置作为机会的阶段**关闭获胜**。 收到通知后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将查询发送到 Salesforce 以检索与商机，相关的产品详细信息，然后将响应来自 Salesforce 插入名的 SQL Server 数据库表**OrderDetails**. 因此，若要测试此解决方案，我们将更新的阶段的机会**关闭获胜**以及结果是，必须获取相关的记录在 Orders 数据库中的 OrderDetails 表中插入。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  使用 Salesforce 开发人员登录凭据登录到 `https://login.salesforce.com/?lt=de`。  
  
2.  在导航栏中，单击**机会**，然后单击**客户 1 的机会**。 你创建了在这个机会[步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。  
  
3.  在**机会详细信息**部分中，记下的关联产品的**产品 （标准）**部分。 你在此部分中输入的值最终将插入到 SQL Server 数据库中。 下**机会详细信息**部分中，单击**编辑**按钮和更改的值**阶段**字段**关闭获胜**。 单击 **“保存”**。  
  
     ![编辑现有机会](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")  
  
4.  在 SQL Server Management Studio，在上运行查询**OrderDetails**表以选择所有行。  
  
     ![SQL 查询输出](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")  
  
     请注意，它将列出在你更改了其阶段的机会中列出的产品。  
  
     ![将产品添加到有机会](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
 你可以看到记录进入**OrderDetails**表对应于在 Salesforce 中创建的一组给定的产品的销售机会。 你可以通过创建新的机会并将新产品与该机会相关联来重复这些步骤。