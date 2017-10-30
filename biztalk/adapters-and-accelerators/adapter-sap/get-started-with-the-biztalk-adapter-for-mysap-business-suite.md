---
title: "要开始使用用于 mySAP Business Suite 的 BizTalk Adapter |Microsoft 文档"
description: "安装自定义的 Rfc，了解有关适配器的信息，请完成上 SAP，单步执行教程，可以使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器 RFC 和 IDOC 任务"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e5607a255f50bf5295d4ea22c9a680d86f38e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a>要开始使用用于 mySAP Business Suite 的 BizTalk Adapter
本部分提供的适配器、 先决条件和主题概述的用户的不熟悉 Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 它讨论的功能[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]和可以在使用该适配器的 SAP 系统执行不同操作。  

## <a name="what-is-an-adapter"></a>什么是适配器？ 
适配器是一个软件组件，使您能够发送和接收消息传入和传出的业务线 (LOB) 系统。 适配器的主要设计目标是便于贸易合作伙伴之间的业务文档的交换。 由于每个业务系统可能符合特定的文档格式和协议，适配器必须使用符合公认的标准和协议，以向用户提供统一的接口的传递机制。  
  
 适配器可以分为两大类：  
  
-   **LOB 适配器**。 提供面向服务的访问 LOB 系统的编程模型，该类型的适配器-例如，为 SAP 或 Siebel 适配器。  
  
-   **数据适配器**。 提供的 access 数据库面向服务的编程模型，该类型的适配器-例如，Oracle 数据库或 SQL Server 的适配器。  
  
 有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] ( [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ( [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ( [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ( [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])，包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] ( [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])，包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])  
  
    > [!NOTE]
    >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不可用于 64 位平台。  
  
 如果你不已知道你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在贵公司，建议你首先探索功能和中所述的适配器的功能[了解用于 mySAP Business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).  
  
## <a name="next-steps"></a>后续步骤  
- [对于 SAP 数据提供程序安装自定义的 Rfc](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [为 mySAP Business Suite 了解 BizTalk 适配器](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [完成上 SAP RFC 和 IDOC 任务](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [SAP 适配器教程](sap-adapter-tutorials.md)  