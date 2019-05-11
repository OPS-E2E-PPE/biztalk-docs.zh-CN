---
title: 与业务数据目录和 SharePoint 集成 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 311f605d-78b4-41a0-b231-1a00a879f637
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2b5d3db229e7a0d2d4df5a93123576bee478b73
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530665"
---
# <a name="integrate-oracle-e-business-suite-with-the-business-data-catalog-and-sharepoint"></a><span data-ttu-id="b1360-102">将 Oracle 电子商务套件与业务数据目录和 SharePoint 集成</span><span class="sxs-lookup"><span data-stu-id="b1360-102">Integrate Oracle E-Business Suite with the business data catalog and SharePoint</span></span>
<span data-ttu-id="b1360-103">[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]包括[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]，分别用于执行特定的 LOB 项目的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b1360-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] includes the [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)], which generates a WCF service for specific LOB artifacts.</span></span> <span data-ttu-id="b1360-104">此 WCF 服务承载在宿主环境如 Microsoft Internet 信息服务 (IIS) 中。</span><span class="sxs-lookup"><span data-stu-id="b1360-104">This WCF service is hosted in a hosting environment such as Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="b1360-105">Business Data Catalog Definition Editor 使用 WCF 服务承载的 WCF 服务中获取 Web 服务描述语言 (WSDL) URL。</span><span class="sxs-lookup"><span data-stu-id="b1360-105">The Business Data Catalog Definition Editor uses the URL where the WCF service is hosted to get the Web Services Description Language (WSDL) for the WCF service.</span></span> <span data-ttu-id="b1360-106">使用 WSDL，Business Data Catalog Definition Editor 中提取可用于 WCF 服务的方法。</span><span class="sxs-lookup"><span data-stu-id="b1360-106">Using the WSDL, the Business Data Catalog Definition Editor extracts the methods available to the WCF service.</span></span> <span data-ttu-id="b1360-107">这些方法可以用于建立实体和实体之间的关联。</span><span class="sxs-lookup"><span data-stu-id="b1360-107">These methods can be used to establish entities and the association between the entities.</span></span>  
  
 <span data-ttu-id="b1360-108">Business Data Catalog Definition Editor 可帮助您创建可以使用 Microsoft Office SharePoint Server 应用程序定义文件 （XML 文件）。</span><span class="sxs-lookup"><span data-stu-id="b1360-108">The Business Data Catalog Definition Editor helps you create an application definition file (an XML file) that Microsoft Office SharePoint Server can consume.</span></span> <span data-ttu-id="b1360-109">一旦应用程序定义文件导入到 Microsoft Office SharePoint Server，可以创建 Web 部件，以提供从企业应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="b1360-109">Once the application definition file is imported to Microsoft Office SharePoint Server, you can create Web Parts to present the information from enterprise applications.</span></span> <span data-ttu-id="b1360-110">有关详细信息，请参阅步骤 3 中的"创建 Web 部件":创建 SharePoint 应用程序将数据从 Oracle E-business Suite 中检索[教程：从 SharePoint 站点上的 Oracle E-business Suite 中呈现数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。</span><span class="sxs-lookup"><span data-stu-id="b1360-110">For more information, see “Creating Web Parts” in Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite in [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
## <a name="tutorial"></a><span data-ttu-id="b1360-111">教程</span><span class="sxs-lookup"><span data-stu-id="b1360-111">Tutorial</span></span>  
 <span data-ttu-id="b1360-112">若要演示如何使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 Microsoft Office SharePoint Server，[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]所含教程提供了从 SharePoint 站点上的 Oracle E-business Suite 中呈现数据的分步说明。</span><span class="sxs-lookup"><span data-stu-id="b1360-112">To demonstrate how to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server, the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] includes a tutorial that provides step-by-step instructions to present data from Oracle E-Business Suite on a SharePoint site.</span></span> <span data-ttu-id="b1360-113">请参阅[教程：从 SharePoint 站点上的 Oracle E-business Suite 中呈现数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。</span><span class="sxs-lookup"><span data-stu-id="b1360-113">See [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1360-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1360-114">See Also</span></span>  
[<span data-ttu-id="b1360-115">使用包含 SharePoint 的 Oracle E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="b1360-115">Use the Oracle E-Business Suite adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)