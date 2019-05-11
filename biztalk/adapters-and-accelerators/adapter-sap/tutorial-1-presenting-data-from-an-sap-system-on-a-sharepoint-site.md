---
title: 教程 1:从 SharePoint 站点上的 SAP 系统提供的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MOSS, creating an application in
- Microsoft Office SharePoint Server
- MOSS
- Microsoft Office SharePoint Server, creating an application in
ms.assetid: 6e31c365-446c-4fe1-8538-fa6c869eed63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5365f75982677124e8cd529ffa78b76c66dd2358
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372392"
---
# <a name="tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site"></a><span data-ttu-id="6756b-102">教程 1:从 SharePoint 站点上的 SAP 系统提供的数据</span><span class="sxs-lookup"><span data-stu-id="6756b-102">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>
<span data-ttu-id="6756b-103">本教程提供了详细的说明[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Microsoft Office SharePoint Server 在 SharePoint 门户网站上显示从 SAP 系统的业务数据。</span><span class="sxs-lookup"><span data-stu-id="6756b-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft Office SharePoint Server to present business data from an SAP system on a SharePoint portal.</span></span> <span data-ttu-id="6756b-104">若要演示如何使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Office SharePoint Server，在任何企业中考虑两个最常见的实体： 客户和销售订单。</span><span class="sxs-lookup"><span data-stu-id="6756b-104">To demonstrate how to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server, consider the two most common entities in any business: customers and sales orders.</span></span> <span data-ttu-id="6756b-105">在此示例中，在使用的 Office SharePoint Server 中创建的应用程序[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6756b-105">In this example, an application is created in Office SharePoint Server, which uses the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to do the following:</span></span>  
  
- <span data-ttu-id="6756b-106">从基于搜索字符串上的 SAP 系统中检索客户列表。</span><span class="sxs-lookup"><span data-stu-id="6756b-106">Retrieve a list of customers from the SAP system based on a search string.</span></span>  
  
- <span data-ttu-id="6756b-107">客户从列表和存在的详细信息选择一个客户。</span><span class="sxs-lookup"><span data-stu-id="6756b-107">Select a customer from the list and present details for the customer.</span></span>  
  
- <span data-ttu-id="6756b-108">检索所选客户的销售订单。</span><span class="sxs-lookup"><span data-stu-id="6756b-108">Retrieve the sales orders for the selected customer.</span></span>  
  
  <span data-ttu-id="6756b-109">若要从 SAP 系统中提取客户数据，该示例使用 SD_RFC_CUSTOMER_GET RFC。</span><span class="sxs-lookup"><span data-stu-id="6756b-109">To extract customer data from an SAP system, the example uses the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="6756b-110">若要提取特定客户的销售订单有关的信息，它使用 BAPI_SALESORDER_GETLIST RFC。</span><span class="sxs-lookup"><span data-stu-id="6756b-110">To extract information about sales orders for a specific customer, it uses the BAPI_SALESORDER_GETLIST RFC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6756b-111">某些版本的 SAP 系统公开而不是 SD_RFC_CUSTOMER_GET RFC_CUSTOMER_GET RFC。</span><span class="sxs-lookup"><span data-stu-id="6756b-111">Some versions of the SAP system expose an RFC_CUSTOMER_GET RFC instead of SD_RFC_CUSTOMER_GET.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="6756b-112">本教程前，请确保已安装使用的所有先决条件[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用 Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="6756b-112">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="6756b-113">有关先决条件的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南中，通常安装在 c: / Program Files/Microsoft  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] /记录。</span><span class="sxs-lookup"><span data-stu-id="6756b-113">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at C:/Program Files/Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]/Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6756b-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="6756b-114">In This Section</span></span>  
  
-   [<span data-ttu-id="6756b-115">步骤 1：将 SAP 项目作为 WCF 服务发布</span><span class="sxs-lookup"><span data-stu-id="6756b-115">Step 1: Publish the SAP Artifacts as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="6756b-116">步骤 2：为 SAP 项目创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="6756b-116">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)  
  
-   [<span data-ttu-id="6756b-117">步骤 3：创建 SharePoint 应用程序以从 SAP 检索数据</span><span class="sxs-lookup"><span data-stu-id="6756b-117">Step 3: Create a SharePoint Application to Retrieve Data from SAP</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)  
  
-   [<span data-ttu-id="6756b-118">步骤 4：测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="6756b-118">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)  
  
## <a name="see-also"></a><span data-ttu-id="6756b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6756b-119">See Also</span></span>  
 [<span data-ttu-id="6756b-120">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="6756b-120">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)