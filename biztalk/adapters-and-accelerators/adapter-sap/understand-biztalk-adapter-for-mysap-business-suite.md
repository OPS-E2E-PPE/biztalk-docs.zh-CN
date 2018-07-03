---
title: 了解用于 mySAP Business Suite 的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 709833ecec71a98e0e09d2cd660b68bf5b647d8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985606"
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a>了解用于 mySAP Business Suite 的 BizTalk 适配器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统进行交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
- **一致的设计时体验**。 适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。  
  
- **不同的编程选项**。 适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型、 WCF 服务模型、 ADO.NET、 web 服务或 BizTalk 支持模型。  
  
- **跨 Lob 的统一体验**。 使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]并因此提供获取访问权的任何 LOB 系统的统一的体验。  
  
  如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。 WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。 WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。 有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。
  
  若要执行 SAP 系统的操作，适配器客户端必须有权相关远程函数调用 (Rfc)、 业务应用程序编程接口 (Bapi) 和 Idoc （或中间文档）。 SAP R/3 系统公开 Rfc 和 Bapi，Idoc 的业务集成。 Rfc 是实现特定的业务逻辑的远程函数模块。 可以从 BizTalk Server 之类的外部应用程序或.NET 应用程序调用此逻辑。 Bapi 是方法的接口连接到 SAP 业务对象，进而通过标准 RFC 接口公开的。 Idoc 是一种机制来抽象 SAP 和非 SAP 系统之间的通信的电子数据交换 (EDI) 通信层。 使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]，可以访问的 Rfc Bapi，以及 Idoc 公开的 SAP 系统。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，其中提供了 SAP 系统的 ADO 接口。  
  
  本部分列出的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [SAP 适配器的主要功能](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [用于 mySAP Business Suite 的 BizTalk 适配器限制](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [关于 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a>请参阅  
[开始使用用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)