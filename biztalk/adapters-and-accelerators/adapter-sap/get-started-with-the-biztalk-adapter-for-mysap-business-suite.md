---
title: 开始使用用于 mySAP Business Suite 的 BizTalk 适配器 |Microsoft Docs
description: 安装自定义 Rfc，了解有关适配器的信息，完成 SAP，单步执行教程，可以使用 BizTalk 适配器包 (BAP) 中的 mySAP 适配器上的 RFC 和 IDOC 任务
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02112b6974a537c9f66cc301014ae16bb4bf326f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967463"
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a>开始使用用于 mySAP Business Suite 的 BizTalk 适配器
本部分中的用户不熟悉 Microsoft 提供的适配器、 先决条件和主题概述[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 它讨论的功能[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]和可以使用该适配器在 SAP 系统执行不同操作。  

## <a name="what-is-an-adapter"></a>什么是适配器？ 
适配器是一个软件组件，可用于发送和接收消息与业务 (LOB) 系统。 适配器的主要设计目标是方便贸易合作伙伴之间业务文档交换。 由于每个业务系统可能需要遵照特定的文档格式和协议，适配器必须使用符合可识别的常用标准和协议来向用户提供统一接口的传送机制。  
  
 适配器可以分为两大类：  
  
- **LOB 适配器**。 此类适配器提供与访问 LOB 系统的面向服务的编程模型 — 例如，对于 SAP 或 Siebel 适配器。  
  
- **数据适配器**。 此类适配器提供面向服务的访问的数据库的编程模型 — 例如，Oracle 数据库或 SQL Server 的适配器。  
  
  有五个适配器中的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] ( [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] ( [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ( [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ( [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])，包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] ( [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])，包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])  
  
  > [!NOTE]
  >  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不适用于 64 位平台。  
  
  如果您不已知道你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在贵公司，建议首先浏览功能和中所述的适配器的功能[理解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).  
  
## <a name="next-steps"></a>后续步骤  
- [为 SAP 数据提供程序安装自定义 RFC](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [了解用于 mySAP Business Suite 的 BizTalk 适配器](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [在 SAP 上完成 RFC 和 IDOC 任务](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [SAP 适配器教程](sap-adapter-tutorials.md)  