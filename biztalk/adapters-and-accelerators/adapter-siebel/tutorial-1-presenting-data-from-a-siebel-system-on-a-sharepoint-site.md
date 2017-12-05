---
title: "教程 1： 从 SharePoint 站点上的 Siebel 系统提供数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd06f75-75d1-4fad-8f34-51c97c7790e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd82dc1f8328645e59aa8c7b0fc668cbe2509ab6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site"></a><span data-ttu-id="a6b3c-102">教程 1： 从 SharePoint 站点上的 Siebel 系统提供数据</span><span class="sxs-lookup"><span data-stu-id="a6b3c-102">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>
<span data-ttu-id="a6b3c-103">本教程提供了详细的说明[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Microsoft Office SharePoint Server，在 SharePoint 门户网站上显示的业务数据免遭 Siebel 系统。</span><span class="sxs-lookup"><span data-stu-id="a6b3c-103">This tutorial provides detailed instructions on using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server to present business data from a Siebel system on a SharePoint portal.</span></span> <span data-ttu-id="a6b3c-104">若要演示如何使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Office SharePoint Server，我们创建应用程序在 Office SharePoint Server，以检索从 Siebel 存储库使用的客户帐户的列表中[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a6b3c-104">To demonstrate how to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server, we create an application in Office SharePoint Server to retrieve a list of customer accounts from the Siebel repository using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="a6b3c-105">若要从 Siebel 系统中提取此信息，该示例时，将调用的查询方法上**帐户**业务组件。</span><span class="sxs-lookup"><span data-stu-id="a6b3c-105">To extract this information from the Siebel system, the example invokes the Query method on the **Account** business components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6b3c-106">本教程之前，确保已安装使用的所有先决条件[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="a6b3c-106">Before proceeding with the tutorial, make sure you have installed all the prerequisites for using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Office SharePoint Server.</span></span> <span data-ttu-id="a6b3c-107">有关先决条件的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装指南，通常安装在\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="a6b3c-107">For more information about the prerequisites, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation guide, typically installed at \<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6b3c-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="a6b3c-108">In This Section</span></span>  
  
-   [<span data-ttu-id="a6b3c-109">步骤 1：将 Siebel 业务组件操作作为 WCF 服务发布</span><span class="sxs-lookup"><span data-stu-id="a6b3c-109">Step 1: Publish the Siebel Business Component Operations as a WCF Service</span></span>](../../adapters-and-accelerators/adapter-siebel/step-1-publish-the-siebel-business-component-operations-as-a-wcf-service.md)  
  
-   [<span data-ttu-id="a6b3c-110">步骤 2：为 Siebel 业务组件操作创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="a6b3c-110">Step 2: Create an Application Definition File for Siebel Business Component Operations</span></span>](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)  
  
-   [<span data-ttu-id="a6b3c-111">步骤 3：创建 SharePoint 应用程序以从 Siebel 检索数据</span><span class="sxs-lookup"><span data-stu-id="a6b3c-111">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)  
  
-  [<span data-ttu-id="a6b3c-112">步骤 4：测试 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="a6b3c-112">Step 4: Test Your SharePoint Application</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6b3c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6b3c-113">See Also</span></span>  
 [<span data-ttu-id="a6b3c-114">Siebel 适配器教程</span><span class="sxs-lookup"><span data-stu-id="a6b3c-114">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)