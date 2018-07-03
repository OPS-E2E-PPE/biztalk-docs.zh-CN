---
title: 获取 Visual Studio 中的 SAP 操作的元数据 |Microsoft Docs
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
ms.openlocfilehash: 0c3eb2a0a0afe6126a622bad1d18bf3fcc198fb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988254"
---
# <a name="get-metadata-for-sap-operations-in-visual-studio"></a>获取 Visual Studio 中的 SAP 操作的元数据
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]提供了两个[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用于帮助您开发使用该适配器的解决方案的组件 — [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 适配器客户端必须使用这些组件连接到 SAP 系统，然后生成他们想要调用 SAP 项目的元数据。  
  
 所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化的开发：  
  
- 为想要使用它在解决方案中的操作提供的 Microsoft Windows 界面，通过它您可以浏览和搜索。  
  
- 检索由这些目标操作该适配器公开的元数据。  
  
- 转换的元数据，这表示为 Web 服务描述语言 (WSDL) 文档适配器，可以使用你的解决方案 （的 BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示形式中的形式服务模型） 并将其添加到你的项目。  
  
  本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
 
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)