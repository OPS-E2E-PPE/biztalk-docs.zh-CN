---
title: 获取 Visual Studio 中的 Siebel 操作的元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving for Siebel operations in Visual Studio
ms.assetid: 63643942-6497-4891-ad7d-34b1df9acbc1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98e8b4af57d575ca23b1561d052d71f5f8dbf4f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371575"
---
# <a name="get-metadata-for-siebel-operations-in-visual-studio"></a>获取 Visual Studio 中的 Siebel 操作的元数据
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]提供了两个[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助您开发使用该适配器的解决方案的组件。  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]是在 BizTalk Server 项目中可用。 您使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。 有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[使用 Siebel 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)。
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]是在非 BizTalk 编程项目中可用。 您使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]开发使用 WCF 服务模型的解决方案时生成 WCF 客户端类或 WCF 服务回调接口。 有关使用 WCF 服务模型开发解决方案的详细信息，请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。  
  
  这两种[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化的开发：  
  
- 为想要使用它在解决方案中的操作提供的 Microsoft Windows 界面，通过它您可以浏览和搜索。  
  
- 检索由这些目标操作该适配器公开的元数据。  
  
- 转换的元数据，这表示为 Web 服务描述语言 (WSDL) 文档适配器，可以使用你的解决方案 （的 BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示形式中的形式服务模型） 并将其添加到你的项目。  
  
  本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  

  
## <a name="see-also"></a>请参阅  
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)