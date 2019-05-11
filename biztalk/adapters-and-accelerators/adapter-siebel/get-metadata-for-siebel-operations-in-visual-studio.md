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
# <a name="get-metadata-for-siebel-operations-in-visual-studio"></a><span data-ttu-id="1a17c-102">获取 Visual Studio 中的 Siebel 操作的元数据</span><span class="sxs-lookup"><span data-stu-id="1a17c-102">Get Metadata for Siebel Operations in Visual Studio</span></span>
<span data-ttu-id="1a17c-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]提供了两个[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]可用来帮助您开发使用该适配器的解决方案的组件。</span><span class="sxs-lookup"><span data-stu-id="1a17c-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] provides two [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter.</span></span>  
  
- <span data-ttu-id="1a17c-104">[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]是在 BizTalk Server 项目中可用。</span><span class="sxs-lookup"><span data-stu-id="1a17c-104">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is available in BizTalk Server projects.</span></span> <span data-ttu-id="1a17c-105">您使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]为想要面向您的 BizTalk 解决方案中的操作生成消息架构 (Xsd)。</span><span class="sxs-lookup"><span data-stu-id="1a17c-105">You use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate message schemas (XSDs) for operations that you want to target in your BizTalk solution.</span></span> <span data-ttu-id="1a17c-106">有关使用 BizTalk Server 开发解决方案的详细信息，请参阅[使用 Siebel 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="1a17c-106">For more information about developing solutions with BizTalk Server, see [Develop BizTalk applications using the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).</span></span>
  
- <span data-ttu-id="1a17c-107">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]是在非 BizTalk 编程项目中可用。</span><span class="sxs-lookup"><span data-stu-id="1a17c-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] is available in non-BizTalk programming projects.</span></span> <span data-ttu-id="1a17c-108">您使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]开发使用 WCF 服务模型的解决方案时生成 WCF 客户端类或 WCF 服务回调接口。</span><span class="sxs-lookup"><span data-stu-id="1a17c-108">You use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client class or a WCF service callback interface when you develop solutions using the WCF service model.</span></span> <span data-ttu-id="1a17c-109">有关使用 WCF 服务模型开发解决方案的详细信息，请参阅[开发 Siebel 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="1a17c-109">For more information about developing solutions with the WCF service model, see [Develop Siebel applications using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span></span>  
  
  <span data-ttu-id="1a17c-110">这两种[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]组件简化的开发：</span><span class="sxs-lookup"><span data-stu-id="1a17c-110">Both of these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="1a17c-111">为想要使用它在解决方案中的操作提供的 Microsoft Windows 界面，通过它您可以浏览和搜索。</span><span class="sxs-lookup"><span data-stu-id="1a17c-111">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="1a17c-112">检索由这些目标操作该适配器公开的元数据。</span><span class="sxs-lookup"><span data-stu-id="1a17c-112">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="1a17c-113">转换的元数据，这表示为 Web 服务描述语言 (WSDL) 文档适配器，可以使用你的解决方案 （的 BizTalk 项目的 XSD 消息架构或 WCF 服务协定的.NET 对象表示形式中的形式服务模型） 并将其添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="1a17c-113">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="1a17c-114">本部分提供有关如何使用说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1a17c-114">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="1a17c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a17c-115">See Also</span></span>  
[<span data-ttu-id="1a17c-116">开发 Siebel 应用程序</span><span class="sxs-lookup"><span data-stu-id="1a17c-116">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)