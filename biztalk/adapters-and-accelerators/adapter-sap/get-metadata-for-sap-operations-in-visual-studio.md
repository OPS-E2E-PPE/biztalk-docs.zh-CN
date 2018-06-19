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
ms.locfileid: "22216117"
---
# <a name="get-metadata-for-sap-operations-in-visual-studio"></a><span data-ttu-id="bc92e-102">获取 Visual Studio 中的 SAP 操作的元数据</span><span class="sxs-lookup"><span data-stu-id="bc92e-102">Get Metadata for SAP Operations in Visual Studio</span></span>
<span data-ttu-id="bc92e-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]提供了两个[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助你开发使用该适配器的解决方案的组件- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bc92e-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] provides two [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter—the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="bc92e-104">适配器客户端必须使用这些组件连接到 SAP 系统，然后生成他们想要调用的 SAP 项目的元数据。</span><span class="sxs-lookup"><span data-stu-id="bc92e-104">Adapter clients must use these components to connect to an SAP system and then generate metadata for the SAP artifacts they want to invoke.</span></span>  
  
 <span data-ttu-id="bc92e-105">所有这些[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化开发：</span><span class="sxs-lookup"><span data-stu-id="bc92e-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
-   <span data-ttu-id="bc92e-106">为你想要使用你的解决方案中的操作提供的 Microsoft Windows 界面通过它您可以浏览和搜索。</span><span class="sxs-lookup"><span data-stu-id="bc92e-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
-   <span data-ttu-id="bc92e-107">检索由这些目标操作的适配器公开元数据。</span><span class="sxs-lookup"><span data-stu-id="bc92e-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
-   <span data-ttu-id="bc92e-108">将转换该元数据，这表示为 Web 服务描述语言 (WSDL) 文档的适配器，到可以 （BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示在解决方案中使用一个窗体服务模型） 并将其添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="bc92e-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
 <span data-ttu-id="bc92e-109">本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bc92e-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="bc92e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc92e-110">See Also</span></span>  
[<span data-ttu-id="bc92e-111">开发您的 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="bc92e-111">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)