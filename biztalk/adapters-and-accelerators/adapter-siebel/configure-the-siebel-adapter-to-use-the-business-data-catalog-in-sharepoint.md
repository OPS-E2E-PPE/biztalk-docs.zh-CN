---
title: 配置 Siebel 适配器为 Siebel 系统与业务数据目录和 SharePoint |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49b575e8-5f33-4e6e-a914-95d357671ab5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c3bb684dcc526ac57aef91c4797a113ef7bbd0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371875"
---
# <a name="configure-the-siebel-adapter-to-integrate-the-siebel-system-with-the-business-data-catalog-and-sharepoint"></a><span data-ttu-id="550d6-102">配置 Siebel 适配器为 Siebel 系统与业务数据目录和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="550d6-102">Configure the Siebel Adapter to Integrate the Siebel System with the Business Data Catalog and SharePoint</span></span>
<span data-ttu-id="550d6-103">[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]，分别用于执行特定的 LOB 项目的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="550d6-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] includes the [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], which generates a WCF service for specific LOB artifacts.</span></span> <span data-ttu-id="550d6-104">此 WCF 服务承载在宿主环境如 Microsoft Internet 信息服务 (IIS) 中。</span><span class="sxs-lookup"><span data-stu-id="550d6-104">This WCF service is hosted in a hosting environment such as Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="550d6-105">Business Data Catalog Definition Editor 使用 WCF 服务承载的 WCF 服务中获取 Web 服务描述语言 (WSDL) URL。</span><span class="sxs-lookup"><span data-stu-id="550d6-105">The Business Data Catalog Definition Editor uses the URL where the WCF service is hosted to get the Web Services Description Language (WSDL) for the WCF service.</span></span> <span data-ttu-id="550d6-106">使用 WSDL，Business Data Catalog Definition Editor 中提取可用于 WCF 服务的方法。</span><span class="sxs-lookup"><span data-stu-id="550d6-106">Using the WSDL, the Business Data Catalog Definition Editor extracts the methods available to the WCF service.</span></span> <span data-ttu-id="550d6-107">这些方法可以用于建立实体和实体之间的关联。</span><span class="sxs-lookup"><span data-stu-id="550d6-107">These methods can be used to establish entities and the association between the entities.</span></span>  
  
 <span data-ttu-id="550d6-108">Business Data Catalog Definition Editor 可帮助您创建可以使用 Microsoft Office SharePoint Server 应用程序定义文件 （XML 文件）。</span><span class="sxs-lookup"><span data-stu-id="550d6-108">The Business Data Catalog Definition Editor helps you create an application definition file (an XML file) that Microsoft Office SharePoint Server can consume.</span></span> <span data-ttu-id="550d6-109">一旦应用程序定义文件导入到 Microsoft Office SharePoint Server，可以创建 Web 部件，以提供从企业应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="550d6-109">Once the application definition file is imported to Microsoft Office SharePoint Server, you can create Web Parts to present the information from enterprise applications.</span></span> <span data-ttu-id="550d6-110">详细信息，请参阅"创建"Web 部件中[步骤 3:创建 SharePoint 应用程序以从 Siebel 检索数据](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)在[教程 1:从 SharePoint 站点上的 Siebel 系统提供数据](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)。</span><span class="sxs-lookup"><span data-stu-id="550d6-110">For more information, see “Creating Web Parts” in [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md) in [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
## <a name="tutorial"></a><span data-ttu-id="550d6-111">教程</span><span class="sxs-lookup"><span data-stu-id="550d6-111">Tutorial</span></span>  
 <span data-ttu-id="550d6-112">若要演示如何使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用 Microsoft Office SharePoint Server，[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]所含教程提供分步说明，以便提供从 SharePoint 站点上的 Siebel 系统的数据。</span><span class="sxs-lookup"><span data-stu-id="550d6-112">To demonstrate how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server, the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] includes a tutorial that provides step-by-step instructions to present data from a Siebel system on a SharePoint site.</span></span> <span data-ttu-id="550d6-113">请参阅[教程 1:从 SharePoint 站点上的 Siebel 系统提供数据](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)。</span><span class="sxs-lookup"><span data-stu-id="550d6-113">See [Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550d6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="550d6-114">See Also</span></span>  
 [<span data-ttu-id="550d6-115">使用 Siebel 适配器和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="550d6-115">Use the Siebel Adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-siebel-adapter-with-sharepoint.md)