---
title: "了解 BizTalk 适配器的 Siebel eBusiness Applications |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad8aecf0faa0a9a0117feaf91e5fa91203fa63f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a>为 Siebel eBusiness 应用程序了解的 BizTalk Adapter
[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统交互，以面向服务的编程访问。 适配器向客户端提供以下优势：  
  
-   **一致的设计时体验**。 适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。  
  
-   **各种编程选项**。 适配器均提供一种编程模型，包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务，或 BizTalk 支持模型。  
  
-   **跨 Lob 的统一体验**。 适配器上使用的是 WCF 标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获得对任何 LOB 系统的访问的统一体验。  
  
 如前文所述，适配器均构建在之上[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器提供了常见的基础。 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道结合适配器策略与 Microsoft 服务策略。 有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。 文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<安装驱动器 >: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。  
  
 若要执行 Siebel 系统的操作，适配器客户端必须有权公开的 Siebel 系统的业务服务。 Siebel 应用程序将数据公开为业务组件和业务对象。 Siebel*在业务组件*是将一个或多个表中的列到单个结构相关联的逻辑实体。 Siebel*业务对象*通过将在一起的一组相关的业务组件中实现的业务模型。 与[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]，适配器客户端可以外围 Siebel 业务对象和业务组件。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]还包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel 系统为 ADO 接口提供通过扩展 ADO.NET 接口。  
  
 本部分讨论的功能[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Siebel 适配器中的主要功能](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [为 Siebel eBusiness 应用程序的 BizTalk Adapter 限制](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [有关 Siebel 的数据提供程序](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)