---
title: 教程：从 SharePoint 站点上的 Oracle E-business Suite 中呈现的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1272b76c-29a1-4912-9c2d-8a4cf43df59d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cf80a137a9826328dbf17070119efe8b5398651
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374388"
---
# <a name="tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site"></a><span data-ttu-id="d8bd5-102">教程：从 SharePoint 站点上的 Oracle E-business Suite 的呈现数据</span><span class="sxs-lookup"><span data-stu-id="d8bd5-102">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>
<span data-ttu-id="d8bd5-103">本教程提供了详细的说明[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 Microsoft Office SharePoint Server 在 SharePoint 门户网站上，从 Oracle E-business Suite 中显示数据。</span><span class="sxs-lookup"><span data-stu-id="d8bd5-103">This tutorial provides detailed instructions on using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server to present data from Oracle E-Business Suite on a SharePoint portal.</span></span> <span data-ttu-id="d8bd5-104">它还演示了如何在 Microsoft Office SharePoint Server，您可以从 SharePoint 门户网站上配置 Oracle E-business Suite 项目执行全文搜索中配置的搜索应用程序。</span><span class="sxs-lookup"><span data-stu-id="d8bd5-104">It also demonstrates how to configure a search application in the Microsoft Office SharePoint Server that allows you to do a full-text search from a SharePoint portal on the configured Oracle E-Business Suite artifact.</span></span>  
  
 <span data-ttu-id="d8bd5-105">若要演示如何执行此操作，请考虑存储有关员工的信息的 Oracle E-business Suite 中的示例接口表。</span><span class="sxs-lookup"><span data-stu-id="d8bd5-105">To demonstrate how to do so, consider a sample interface table in Oracle E-Business Suite that stores information about employees.</span></span> <span data-ttu-id="d8bd5-106">在本教程中，在从基于搜索字符串使用 Oracle E-business Suite 中检索客户列表的 Microsoft Office SharePoint Server 中创建的应用程序：</span><span class="sxs-lookup"><span data-stu-id="d8bd5-106">In this tutorial, an application is created in Microsoft Office SharePoint Server that retrieve a list of customers from Oracle E-Business Suite based on a search string using:</span></span>  
  
-   <span data-ttu-id="d8bd5-107">Microsoft Office SharePoint Server 中业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="d8bd5-107">A Business Data List Web Part in Microsoft Office SharePoint Server</span></span>  
  
-   <span data-ttu-id="d8bd5-108">Microsoft Office SharePoint Server 中的搜索功能</span><span class="sxs-lookup"><span data-stu-id="d8bd5-108">The search feature in Microsoft Office SharePoint Server</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8bd5-109">本教程前，请确保已安装使用的所有先决条件[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="d8bd5-109">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="d8bd5-110">有关先决条件的信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南中，通常安装在 C:\Program Files\Microsoft BizTalk 适配器 Pack\Documents。</span><span class="sxs-lookup"><span data-stu-id="d8bd5-110">For information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at C:\Program Files\Microsoft BizTalk Adapter Pack\Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8bd5-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="d8bd5-111">In This Section</span></span>  
  
-   [<span data-ttu-id="d8bd5-112">步骤 1：使用 Oracle E-business 适配器创建和发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="d8bd5-112">Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)  
  
-   [<span data-ttu-id="d8bd5-113">步骤 2：为 Oracle E-business Suite 项目创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="d8bd5-113">Step 2: Create an Application Definition File for the Oracle E-Business Suite Artifacts</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)  
  
-   [<span data-ttu-id="d8bd5-114">步骤 3：创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据</span><span class="sxs-lookup"><span data-stu-id="d8bd5-114">Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
  
-   [<span data-ttu-id="d8bd5-115">步骤 4：测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="d8bd5-115">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)