---
title: "步骤 3： 测试到 Oracle 数据库适配器迁移的应用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 495efc4f-9d9e-450f-a03a-628bb54e658f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 144313f742bd4256319ff35435a401b4228093dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-migrated-application-to-oracle-database-adapter"></a>步骤 3： 测试到 Oracle 数据库适配器已迁移的应用程序
![步骤 3 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：**在此步骤中，将通过执行插入操作上 SCOTT 测试已迁移的应用程序。CUSTOMER 表。 若要执行此操作，你可以删除与生成使用 vPrev Oracle 数据库适配器的架构一致的请求消息。  
  
## <a name="prerequisites"></a>先决条件  
  
-   通过将 BizTalk 业务流程中的逻辑端口映射到在 BizTalk Server 管理控制台中的物理端口来配置 BizTalk 应用程序。  
  
-   配置 BizTalk 应用程序使用 WCF 自定义发送端口进行基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>测试已迁移应用程序  
  
1.  从 Oracle_Migration 文件夹中，将复制 OracleInsert.xml 请求消息。 此请求消息符合 vPrev Oracle 数据库适配器所生成的架构。 使用出站映射，WCF 自定义发送端口将这以符合为基于 WCF 的架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]并将其发送到 Oracle 数据库。  
  
    ```  
    \<ns0:Insert xmlns:ns0="http://schemas.microsoft.com/[OracleDb://ADAPTER/SCOTT/Tables/CUSTOMER]">  
      \<ns0:Rows>  
        \<ns0:InsertRecord>  
          \<ns0:NAME>Customer_1\</ns0:NAME>  
          \<ns0:STREET>Street_1\</ns0:STREET>  
          \<ns0:CITY>City_1\</ns0:CITY>  
        \</ns0:InsertRecord>  
        \<ns0:InsertRecord>  
          \<ns0:NAME>Customer_2\</ns0:NAME>  
          \<ns0:STREET>Street_2\</ns0:STREET>  
          \<ns0:CITY>City_2\</ns0:CITY>  
        \</ns0:InsertRecord>  
      \</ns0:Rows>  
    \</ns0:Insert>  
    ```  
  
2.  粘贴到文件映射到的文件夹的请求消息接收位置。  
  
3.  业务流程使用请求消息，并将其发送到 Oracle 数据库。 从 Oracle 数据库响应接收中的基于 WCF 的架构的架构符合[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 使用入站的映射，WCF 自定义发送端口将这 vPrev Oracle 数据库适配器的架构。 从 Oracle 数据库的响应保存到定义为业务流程的一部分的其他文件位置。 前面的请求消息的响应是：  
  
    ```  
    \<?xml version="1.0" encoding="utf-8"?>  
    \<ns0:InsertResponse xmlns:ns0="http://schemas.microsoft.com/[OracleDb://ADAPTER/SCOTT/Tables/CUSTOMER]">\</ns0:InsertResponse>  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [教程： 迁移 BizTalk 项目](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)