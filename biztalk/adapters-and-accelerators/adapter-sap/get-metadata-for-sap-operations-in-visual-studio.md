---
title: 获取 Visual Studio 中的 SAP 操作的元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving for SAP operations in Visual Studio
ms.assetid: 1be5934a-a5d4-4734-8bea-fb8274f59c71
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c786ea9b1acbc3ed88c79187725697ce279ea5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-for-sap-operations-in-visual-studio"></a>获取 Visual Studio 中的 SAP 操作的元数据
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]提供了两个[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助你开发使用该适配器的解决方案的组件- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 适配器客户端必须使用这些组件连接到 SAP 系统，然后生成他们想要调用的 SAP 项目的元数据。  
  
 所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化开发：  
  
-   为你想要使用你的解决方案中的操作提供的 Microsoft Windows 界面通过它您可以浏览和搜索。  
  
-   检索由这些目标操作的适配器公开元数据。  
  
-   将转换该元数据，这表示为 Web 服务描述语言 (WSDL) 文档的适配器，到可以 （BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示在解决方案中使用一个窗体服务模型） 并将其添加到你的项目。  
  
 本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
 
  
## <a name="see-also"></a>另请参阅  
[开发您的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)