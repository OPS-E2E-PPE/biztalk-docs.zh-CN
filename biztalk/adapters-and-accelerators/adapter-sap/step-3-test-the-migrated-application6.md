---
title: 步骤 3：测试已迁移的 Application6 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (RFC)
- migration
ms.assetid: 1b1ee59c-a5a3-442d-af2c-0fc4817f3063
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ab38d728eeb5c947dbda1fd38706d0ac5257002
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372782"
---
# <a name="step-3-test-the-migrated-application"></a>步骤 3：测试已迁移应用程序
![第 3 部分，共 3 步](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，将通过调用 SD_RFC_CUSTOMER_GET RFC 测试已迁移应用程序。 若要执行此操作，则删除与使用 vPrev SAP 适配器生成的架构一致的请求消息。  
  
## <a name="prerequisites"></a>先决条件  
  
- 通过将 BizTalk 业务流程中的逻辑端口映射到物理端口在 BizTalk Server 管理控制台中配置的 BizTalk 应用程序。  
  
- 配置 BizTalk 应用程序要用于 Wcf-custom 发送端口基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="to-test-the-migrated-application"></a>若要测试已迁移应用程序  
  
1. 从 SAP_RFC_Migration 文件夹中，将复制 Input.xml 请求消息。 此请求消息符合 vPrev SAP 适配器生成的架构。 使用出站映射时，WCF 自定义发送端口将此选项以符合架构的基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]并将其发送到 SAP 系统。  
  
   ```  
   <ns0:SD_RFC_CUSTOMER_GET_Request xmlns:ns0="http://schemas.microsoft.com/BizTalk/2003">  
     <KUNNR>0000001390</KUNNR>  
     <NAME1/>  
     <CUSTOMER_T/>  
   </ns0:SD_RFC_CUSTOMER_GET_Request>  
   ```  
  
2. 粘贴到映射到文件的文件夹的请求消息的接收位置。  
  
3. 业务流程使用请求消息，并将其发送到 SAP 系统。 中的基于 WCF 的架构的架构符合收到来自 SAP 系统的响应[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 使用入站的映射时，WCF 自定义发送端口将此 vPrev SAP 适配器的架构。 从 SAP 系统的响应保存到其他文件位置定义为业务流程的一部分。 在前面的请求消息的响应是：  
  
   ```  
   <?xml version="1.0" encoding="utf-8" ?>   
   <ns0:SD_RFC_CUSTOMER_GET_Response xmlns:ns0="http://schemas.microsoft.com/BizTalk/2003">  
     <CUSTOMER_T>  
       <KUNNR>0000001390</KUNNR>   
       <ANRED>Firma</ANRED>   
       <NAME1>Contoso, Ltd.</NAME1>   
       <PFACH />   
       <STRAS>Strasse 4567</STRAS>   
       <PSTLZ>50000</PSTLZ>   
       <ORT01>Aachen</ORT01>   
       <TELF1>0123-45678</TELF1>   
       <TELFX>0123-56789</TELFX>   
     </CUSTOMER_T>  
   </ns0:SD_RFC_CUSTOMER_GET_Response>  
   ```  
  
## <a name="see-also"></a>请参阅  
 [教程 2：迁移 SAP RFC BizTalk 项目](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)