---
title: "配置 Siebel 适配器，以将与业务数据集成 Siebel 系统目录和 SharePoint |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49b575e8-5f33-4e6e-a914-95d357671ab5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d02e14b8c996acbfb07f9d422aee70cb0d94fa59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-siebel-adapter-to-integrate-the-siebel-system-with-the-business-data-catalog-and-sharepoint"></a><span data-ttu-id="b65bd-102">配置 Siebel 适配器，以将与业务数据集成 Siebel 系统目录和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="b65bd-102">Configure the Siebel Adapter to Integrate the Siebel System with the Business Data Catalog and SharePoint</span></span>
<span data-ttu-id="b65bd-103">[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]，这将生成特定 LOB 项目的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b65bd-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] includes the [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], which generates a WCF service for specific LOB artifacts.</span></span> <span data-ttu-id="b65bd-104">此 WCF 服务承载在宿主环境如 Microsoft Internet 信息服务 (IIS) 中。</span><span class="sxs-lookup"><span data-stu-id="b65bd-104">This WCF service is hosted in a hosting environment such as Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="b65bd-105">业务数据目录定义编辑器使用的 URL，其中承载该 WCF 服务来获取 Web 服务描述语言 (WSDL) 的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b65bd-105">The Business Data Catalog Definition Editor uses the URL where the WCF service is hosted to get the Web Services Description Language (WSDL) for the WCF service.</span></span> <span data-ttu-id="b65bd-106">使用 WSDL，业务数据目录定义编辑器中提取的 WCF 服务可用的方法。</span><span class="sxs-lookup"><span data-stu-id="b65bd-106">Using the WSDL, the Business Data Catalog Definition Editor extracts the methods available to the WCF service.</span></span> <span data-ttu-id="b65bd-107">这些方法可以用于建立实体和实体之间的关联。</span><span class="sxs-lookup"><span data-stu-id="b65bd-107">These methods can be used to establish entities and the association between the entities.</span></span>  
  
 <span data-ttu-id="b65bd-108">业务数据目录定义编辑器可帮助你创建的应用程序定义文件 （XML 文件），可以使用 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="b65bd-108">The Business Data Catalog Definition Editor helps you create an application definition file (an XML file) that Microsoft Office SharePoint Server can consume.</span></span> <span data-ttu-id="b65bd-109">一旦应用程序定义文件导入 Microsoft Office SharePoint Server 时，你可以创建 Web 部件，为了提供从企业应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="b65bd-109">Once the application definition file is imported to Microsoft Office SharePoint Server, you can create Web Parts to present the information from enterprise applications.</span></span> <span data-ttu-id="b65bd-110">有关详细信息，请参阅"创建 Web 部件"[步骤 3： 创建一个 SharePoint 应用程序检索数据从 Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)中[教程 1： 演示数据从 Siebel 系统 SharePoint 站点上](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)。</span><span class="sxs-lookup"><span data-stu-id="b65bd-110">For more information, see “Creating Web Parts” in [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) in [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
## <a name="tutorial"></a><span data-ttu-id="b65bd-111">教程</span><span class="sxs-lookup"><span data-stu-id="b65bd-111">Tutorial</span></span>  
 <span data-ttu-id="b65bd-112">若要演示如何使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Microsoft Office SharePoint Server，[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]包括提供显示从 SharePoint 站点上的 Siebel 系统的数据的分步说明的教程。</span><span class="sxs-lookup"><span data-stu-id="b65bd-112">To demonstrate how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server, the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] includes a tutorial that provides step-by-step instructions to present data from a Siebel system on a SharePoint site.</span></span> <span data-ttu-id="b65bd-113">请参阅[教程 1： 从 SharePoint 站点上的 Siebel 系统提供数据](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)。</span><span class="sxs-lookup"><span data-stu-id="b65bd-113">See [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b65bd-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b65bd-114">See Also</span></span>  
 [<span data-ttu-id="b65bd-115">使用带有 SharePoint Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="b65bd-115">Use the Siebel Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)