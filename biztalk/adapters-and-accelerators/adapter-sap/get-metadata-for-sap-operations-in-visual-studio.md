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
# <a name="get-metadata-for-sap-operations-in-visual-studio"></a><span data-ttu-id="da706-102">获取 Visual Studio 中的 SAP 操作的元数据</span><span class="sxs-lookup"><span data-stu-id="da706-102">Get Metadata for SAP Operations in Visual Studio</span></span>
<span data-ttu-id="da706-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]提供了两个[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用于帮助您开发使用该适配器的解决方案的组件 — [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da706-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] provides two [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter—the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="da706-104">适配器客户端必须使用这些组件连接到 SAP 系统，然后生成他们想要调用 SAP 项目的元数据。</span><span class="sxs-lookup"><span data-stu-id="da706-104">Adapter clients must use these components to connect to an SAP system and then generate metadata for the SAP artifacts they want to invoke.</span></span>  
  
 <span data-ttu-id="da706-105">所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化的开发：</span><span class="sxs-lookup"><span data-stu-id="da706-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="da706-106">为想要使用它在解决方案中的操作提供的 Microsoft Windows 界面，通过它您可以浏览和搜索。</span><span class="sxs-lookup"><span data-stu-id="da706-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="da706-107">检索由这些目标操作该适配器公开的元数据。</span><span class="sxs-lookup"><span data-stu-id="da706-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="da706-108">转换的元数据，这表示为 Web 服务描述语言 (WSDL) 文档适配器，可以使用你的解决方案 （的 BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示形式中的形式服务模型） 并将其添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="da706-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="da706-109">本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da706-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="da706-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="da706-110">See Also</span></span>  
[<span data-ttu-id="da706-111">开发 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="da706-111">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)