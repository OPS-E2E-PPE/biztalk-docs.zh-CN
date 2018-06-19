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
# <a name="step-4-on-premises-create-the-sql-server-table"></a>步骤 4 （在本地）： 创建 SQL Server 表
作为业务方案的一部分，由 Contoso 发送到 Northwind 的销售订单消息的消息 X12 必须最后插入中**SalesOrder**表，如果订购数量大于 100。 本主题将说明了如何创建**SalesOrder**安放在本地 SQL Server 数据库实例中的表。  
  
### <a name="to-create-the-salesorder-table"></a>创建 SalesOrder 表的步骤  
  
1.  打开 SQL Server Management Studio，针对要在其中创建表的数据库运行以下查询。  
  
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
  
3.  验证是否已在目标数据库中创建该表。  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 创建使用 BizTalk Server 2013 的混合应用程序](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)