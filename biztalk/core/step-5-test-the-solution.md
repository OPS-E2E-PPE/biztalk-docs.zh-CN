---
title: 步骤 5： 测试解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33a51cda93a1c2cdd6f5a70ebd62bf1d9ce05a7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020848"
---
# <a name="step-5-test-the-solution"></a>步骤 5： 测试解决方案
此解决方案的目的是将通知发送到进程的自动化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，每次在 Salesforce 中通过设置为机会的阶段关闭新机会时**已结束-赢得**。 收到通知后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将查询发送到 Salesforce 以检索与机会相关的产品详细信息，然后将来自 Salesforce 的响应插入到名为的 SQL Server 数据库表**OrderDetails**. 因此，若要测试此解决方案，我们将更新的机会的阶段**已结束-赢得**和结果，必须在订单数据库中的 OrderDetails 表中插入相关记录。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1. 使用 Salesforce 开发人员登录凭据登录到 `https://login.salesforce.com/?lt=de`。  
  
2. 在导航栏中，单击**机会**，然后单击**客户 1**。 已创建在这个机会[步骤 2： 设置 Salesforce 系统](../core/step-2-set-up-the-salesforce-system.md)。  
  
3. 在中**机会详细信息**部分中，记下中的关联产品**产品 （标准）** 部分。 你在此部分中输入的值最终将插入到 SQL Server 数据库中。 下**机会详细信息**部分中，单击**编辑**按钮，然后更改的值**阶段**字段**已结束-赢得**。 单击 **“保存”**。  
  
    ![编辑现有机会](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")  
  
4. 在 SQL Server Management Studio 中，运行查询**OrderDetails**表来选择所有行。  
  
    ![SQL 查询输出](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")  
  
    请注意，它将列出在你更改了其阶段的机会中列出的产品。  
  
    ![向机会添加产品](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
   您可以看到中输入的记录**OrderDetails**表对应于在 Salesforce 中创建的一组给定的产品的销售机会。 你可以通过创建新的机会并将新产品与该机会相关联来重复这些步骤。