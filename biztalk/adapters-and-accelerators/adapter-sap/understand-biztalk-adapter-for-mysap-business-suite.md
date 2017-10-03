---
title: "了解为 mySAP Business Suite 的 BizTalk Adapter |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 359bbc9d25465cf5c293d24a12ffeb698b11ab02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a>为 mySAP Business Suite 了解 BizTalk 适配器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
-   **一致的设计时体验**。 适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。  
  
-   **各种编程选项**。 适配器均提供一种编程模型包括 Windows Communication Foundation (WCF) 通道模型、 WCF 服务模型、 ADO.NET、 web 服务或支持的 BizTalk 模型。  
  
-   **跨 Lob 的统一体验**。 适配器上使用的是 WCF 标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获得对任何 LOB 系统的访问的统一体验。  
  
 如前文所述，适配器均构建在之上[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器提供了常见的基础。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道结合适配器策略与 Microsoft 服务策略。 有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。 文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<安装驱动器 >: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。  
  
 若要对某个 SAP 系统执行操作，适配器客户端必须有权相关远程函数调用 (文档 Rfc)、 业务应用程序编程接口 (BAPIs) 和 Idoc （或中间的文档）。 SAP / 3 系统公开的业务集成 Rfc、 BAPIs 和 Idoc。 Rfc 是实现特定的业务逻辑的远程函数模块。 从 BizTalk Server 之类的外部应用程序或.NET 应用程序可以调用此逻辑。 BAPIs 都是与通过标准 RFC 接口反过来公开的 SAP 业务对象的方法接口。 Idoc 是一种机制，抽象 SAP 和非 SAP 系统之间的通信的电子数据交换 (EDI) 通信层。 与[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]，你可以访问 Rfc BAPIs，以及 Idoc 公开的 SAP 系统。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，它提供到 SAP 系统 ADO 界面。  
  
 本部分列出的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为 mySAP Business Suite 的 BizTalk Adapter 的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [SAP 适配器中的主要功能](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [为 mySAP Business Suite 的 BizTalk Adapter 限制](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [有关.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a>另请参阅  
[要开始使用用于 mySAP Business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)