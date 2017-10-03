---
title: "获取 Visual Studio 中的 Siebel 操作的元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: metadata, retrieving for Siebel operations in Visual Studio
ms.assetid: 63643942-6497-4891-ad7d-34b1df9acbc1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30935631052adf4c455e730c476104b54a6a352b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-for-siebel-operations-in-visual-studio"></a>获取 Visual Studio 中的 Siebel 操作的元数据
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]提供了两个[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助你开发使用该适配器的解决方案的组件。  
  
-   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]在 BizTalk Server 项目中可用。 你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]若要为你想要针对 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[开发 BizTalk 应用程序使用在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)。
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]在非 BizTalk 编程项目中可用。 你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成 WCF 客户端类或 WCF 服务回调接口，当你开发使用 WCF 服务模型的解决方案时。 有关开发与 WCF 服务模型的解决方案的详细信息，请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。  
  
 这两种[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化开发：  
  
-   为你想要使用你的解决方案中的操作提供的 Microsoft Windows 界面通过它您可以浏览和搜索。  
  
-   检索由这些目标操作的适配器公开元数据。  
  
-   将转换该元数据，这表示为 Web 服务描述语言 (WSDL) 文档的适配器，到可以 （BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示在解决方案中使用一个窗体服务模型） 并将其添加到你的项目。  
  
 本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  

  
## <a name="see-also"></a>另请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)