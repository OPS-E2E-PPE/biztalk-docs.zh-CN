---
title: 步骤 4 （在本地）： 创建 SQL Server 表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e253ac-8707-484f-8461-f098cc7ec7d8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a6934a98ccd101003519486388b09504b5f0ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277261"
---
# <a name="step-4-on-premises-create-the-sql-server-table"></a><span data-ttu-id="d4961-102">步骤 4 （在本地）： 创建 SQL Server 表</span><span class="sxs-lookup"><span data-stu-id="d4961-102">Step 4 (On Premises): Create the SQL Server Table</span></span>
<span data-ttu-id="d4961-103">作为业务方案的一部分，由 Contoso 发送到 Northwind 的销售订单消息的消息 X12 必须最后插入中**SalesOrder**表，如果订购数量大于 100。</span><span class="sxs-lookup"><span data-stu-id="d4961-103">As part of the business scenario, the message X12 sales order message sent by Contoso to Northwind must finally be inserted in a **SalesOrder** table, if the quantity ordered is greater than 100.</span></span> <span data-ttu-id="d4961-104">本主题将说明了如何创建**SalesOrder**安放在本地 SQL Server 数据库实例中的表。</span><span class="sxs-lookup"><span data-stu-id="d4961-104">This topic provides instructions on how to create the **SalesOrder** table within a SQL Server database instance that is housed on-premises.</span></span>  
  
### <a name="to-create-the-salesorder-table"></a><span data-ttu-id="d4961-105">创建 SalesOrder 表的步骤</span><span class="sxs-lookup"><span data-stu-id="d4961-105">To create the SalesOrder table</span></span>  
  
1.  <span data-ttu-id="d4961-106">打开 SQL Server Management Studio，针对要在其中创建表的数据库运行以下查询。</span><span class="sxs-lookup"><span data-stu-id="d4961-106">Open SQL Server Management Studio and run the following query against the database where you want to create the table.</span></span>  
  
2.  <span data-ttu-id="d4961-107">运行以下查询以创建**SalesOrder**表：</span><span class="sxs-lookup"><span data-stu-id="d4961-107">Run the following query to create the **SalesOrder** table:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[SalesOrder] (  
        [SalesOrderID] int IDENTITY(1,1) NOT NULL,  
        [PartNum] int  NOT NULL,  
        [DateRequested] datetime  NULL,  
        [CompanyCode] varchar(3)  NOT NULL,  
        [Qty] int  NOT NULL,  
        [UnitAskPrice] float  NULL,  
        [ShipDate] datetime  NOT NULL,  
        [SellToAddress] varchar(255)  NULL,  
        [BillToAddress] varchar(255)  NOT NULL,  
        [PartnerContact] varchar(128)  NULL,  
        [CustomerComments] varchar(500)  NULL,  
        [RFQStatuesId] smallint  NULL  
    );  
    GO  
    ```  
  
3.  <span data-ttu-id="d4961-108">验证是否已在目标数据库中创建该表。</span><span class="sxs-lookup"><span data-stu-id="d4961-108">Verify that the table is created in the target database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4961-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4961-109">See Also</span></span>  
 [<span data-ttu-id="d4961-110">教程 4： 创建使用 BizTalk Server 2013 的混合应用程序</span><span class="sxs-lookup"><span data-stu-id="d4961-110">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)