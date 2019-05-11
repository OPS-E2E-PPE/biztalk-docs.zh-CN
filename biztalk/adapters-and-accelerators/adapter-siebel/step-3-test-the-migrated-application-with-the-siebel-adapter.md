---
title: 步骤 3：测试与 Siebel 适配器迁移应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 651ee1b2-52da-497a-84a5-67f1436cc3e6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eaed7d5beb9fffe30f435fa0a1fff0c0349f4e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370546"
---
# <a name="step-3-test-the-migrated-application-with-the-siebel-adapter"></a>步骤 3：测试迁移应用程序使用 Siebel 适配器
![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，将通过执行插入操作帐户业务组件上的测试已迁移应用程序。 若要执行此操作，则删除与使用 vPrev Siebel 适配器生成的架构一致的请求消息。  
  
## <a name="prerequisites"></a>先决条件  
  
- 通过将 BizTalk 业务流程中的逻辑端口映射到物理端口在 BizTalk Server 管理控制台中配置的 BizTalk 应用程序。  
  
- 配置 BizTalk 应用程序要用于 Wcf-custom 发送端口基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>若要测试已迁移应用程序  
  
1. 从 Siebel_BussComp_Migration 文件夹中，将复制 AccountInsert.xml 请求消息。 此请求消息符合 vPrev Siebel 适配器生成的架构。 使用出站映射时，WCF 自定义发送端口将此选项以符合架构的基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]并将其发送到 Siebel 系统。  
  
   ```  
   <Insert xmlns="http://schemas.microsoft.com/[Siebel://Business Objects/Account/Account]">  
     <AccountInsertRecordSet>  
       <AccountInsertRecord xmlns="http://schemas.microsoft.com/Business_Objects">  
         <Currency_Code>USD</Currency_Code>  
         <Customer_Account_Group>Sold-To-Party</Customer_Account_Group>  
         <Location>Location_1</Location>  
         <Main_Phone_Number>012345678</Main_Phone_Number>  
         <Name>John_Smith</Name>  
         <Party_Name>Party_Name_1</Party_Name>  
         <Primary_Address_Id></Primary_Address_Id>  
       </AccountInsertRecord>  
     </AccountInsertRecordSet>  
   </Insert>  
   ```  
  
2. 粘贴到文件映射到的文件夹的请求消息的接收位置。  
  
3. 业务流程使用请求消息，并将其发送到 Siebel 系统。 中的基于 WCF 的架构的架构符合收到来自 Siebel 系统的响应[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 使用入站的映射时，WCF 自定义发送端口将此 vPrev Siebel 适配器的架构。 来自 Siebel 系统的响应保存到其他文件位置定义为业务流程的一部分。 前面的请求消息的响应是：  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:InsertResponse xmlns:ns0="http://schemas.microsoft.com/[Siebel://Business Objects/Account/Account]" xmlns:exposed="http://schemas.microsoft.com" xmlns:Business_Objects="http://schemas.microsoft.com/Business_Objects">  
     <ns0:RowIDList>  
       <exposed:String>1-8EWWZ</exposed:String>  
     </ns0:RowIDList>  
   </ns0:InsertResponse>  
   ```  
  
## <a name="see-also"></a>请参阅  
 [教程 2：在 Siebel 的 BizTalk 项目迁移](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)