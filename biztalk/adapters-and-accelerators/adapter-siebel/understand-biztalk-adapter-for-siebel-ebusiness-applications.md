---
title: 了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d31aee0ae64bdc1c014e72ac5be277283244117
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370375"
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a>了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统进行交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
- **一致的设计时体验**。 适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。  
  
- **不同的编程选项**。 适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务或 BizTalk 支持的模型。  
  
- **跨 Lob 的统一体验**。 使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]并因此提供获取访问权的任何 LOB 系统的统一的体验。  
  
  如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。 WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。 WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。 有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。
  
  若要执行 Siebel 系统的操作，适配器客户端必须具有对业务服务公开的 Siebel 系统的访问。 Siebel 应用程序公开数据作为业务组件和业务对象。 Siebel*业务组件*是将一个或多个表中的列的单个结构相关联的逻辑实体。 Siebel*业务对象*通过将在一起的一组相互关联的业务组件中实现的业务模型。 使用[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]，Siebel 业务对象和业务组件，可能会出现适配器客户端。  
  
  [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]还包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]通过扩展 ADO.NET 接口提供到 Siebel 系统的 ADO 接口。  
  
  本部分讨论的功能[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Siebel 适配器的主要功能](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [用于 Siebel eBusiness 应用程序的 BizTalk 适配器的限制](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [关于 Siebel 的数据提供程序](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)