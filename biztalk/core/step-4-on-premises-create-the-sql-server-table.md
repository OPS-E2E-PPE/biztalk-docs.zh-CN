---
title: 步骤 4 （本地）：创建 SQL Server 表 |Microsoft Docs
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
ms.openlocfilehash: 67981fed618f9214bf1d07c3140c7685fba3a727
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392514"
---
# <a name="step-4-on-premises-create-the-sql-server-table"></a>步骤 4 （本地）：创建 SQL Server 表
作为业务方案的一部分，由 Contoso 发送到 Northwind 的销售订单消息的消息 X12 必须最后插入中**SalesOrder**表，如果订购数量大于 100。 本主题说明了如何创建**SalesOrder**是用户所在的本地 SQL Server 数据库实例中的表。  
  
### <a name="to-create-the-salesorder-table"></a>若要创建 SalesOrder 表  
  
1.  打开 SQL Server Management Studio 并对数据库运行以下查询你想要创建的表。  
  
2.  运行以下查询以创建**SalesOrder**表：  
  
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
  
3.  验证在目标数据库中创建表。  
  
## <a name="see-also"></a>请参阅  
 [教程 4：创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)