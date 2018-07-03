---
title: 步骤 3： 测试使用 SQL 适配器的迁移应用程序 |Microsoft Docs
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
ms.openlocfilehash: 0c2487c6bdf05ae926b8bb962ed9dae6c770298e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973286"
---
# <a name="step-3-test-the-migrated-application-that-uses-the-sql-adapter"></a>步骤 3： 测试迁移应用程序使用 SQL 适配器
![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **完成时间：** 5 分钟  
  
 **目标：** 在此步骤中，您将通过执行插入操作的客户表上测试已迁移应用程序。 若要执行此操作，应删除与使用 vPrev 生成的架构一致的请求消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="prerequisites"></a>必要條件  
  
- 通过将 BizTalk 业务流程中的逻辑端口映射到物理端口在 BizTalk Server 管理控制台中配置的 BizTalk 应用程序。  
  
- 配置 BizTalk 应用程序要用于 Wcf-custom 发送端口基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>若要测试已迁移应用程序  
  
1. 创建请求符合由 vPrev 生成架构的 XML [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 使用出站映射时，WCF 自定义发送端口将此选项以符合架构的基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]并将其发送到 SQL Server 数据库。  
  
   ```  
   <Insert xmlns="http://SQLInsert">  
     <sync>  
       <after>  
         <CustomerTable Name="John" />  
       </after>  
     </sync>  
   </Insert>  
   ```  
  
2. 粘贴到映射到文件的文件夹的请求消息的接收位置。  
  
3. 业务流程使用请求消息，并将其发送到 SQL Server 数据库。 在与基于 WCF 的架构一致的架构中收到从 SQL Server 数据库响应[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 使用入站的映射时，WCF 自定义发送端口将此 vPrev 架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 从 SQL Server 数据库响应保存到其他文件位置定义为业务流程的一部分。 前面的请求消息的响应是：  
  
   ```  
   <?xml version="1.0" encoding="utf-8" ?>   
   <InsertResponse xmlns="http://SQLInsert">  
     <Success>  
       <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">101</long>   
     </Success>  
   </InsertResponse>  
   ```  
  
    在前面的响应中，"101"是标识列插入 Customer 表中的值。  
  
## <a name="see-also"></a>请参阅  
 [教程 1： 将 BizTalk 项目迁移到 SQL 适配器](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)