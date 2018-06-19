---
title: 步骤 3： 测试迁移使用的应用程序的 SQL 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 929ce2f3-94ed-4e12-b629-e229769f825a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32314638b3352dccb2c30eb0b99a4d328d22b092
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964019"
---
# <a name="step-3-test-the-migrated-application-that-uses-the-sql-adapter"></a>步骤 3： 测试迁移使用的应用程序的 SQL 适配器
![步骤 3 / 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，将测试已迁移应用程序，通过执行对 Customer 表的插入操作。 若要执行此操作，你可以删除符合架构使用 vPrev 生成的请求消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="prerequisites"></a>先决条件  
  
-   通过将 BizTalk 业务流程中的逻辑端口映射到在 BizTalk Server 管理控制台中的物理端口来配置 BizTalk 应用程序。  
  
-   配置 BizTalk 应用程序使用 WCF 自定义发送端口进行基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>测试已迁移应用程序  
  
1.  创建请求符合 vPrev 所生成的架构的 XML [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 使用出站映射，WCF 自定义发送端口将这以符合为基于 WCF 的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]并将其发送到 SQL Server 数据库。  
  
    ```  
    <Insert xmlns="http://SQLInsert">  
      <sync>  
        <after>  
          <CustomerTable Name="John" />  
        </after>  
      </sync>  
    </Insert>  
    ```  
  
2.  粘贴到映射到文件的文件夹的请求消息接收位置。  
  
3.  业务流程使用请求消息，并将其发送到 SQL Server 数据库。 在与基于 WCF 的架构一致的架构中接收从 SQL Server 数据库响应[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 使用入站的映射，WCF 自定义发送端口将这 vPrev 的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 从 SQL Server 数据库响应保存到定义为业务流程的一部分的其他文件位置。 前面的请求消息的响应是：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <InsertResponse xmlns="http://SQLInsert">  
      <Success>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">101</long>   
      </Success>  
    </InsertResponse>  
    ```  
  
     在前面的响应中，"101"是标识列插入 Customer 表中的值。  
  
## <a name="see-also"></a>另请参阅  
 [教程 1： 将 BizTalk 项目迁移到 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)