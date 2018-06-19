---
title: 教程 3： 承载在 IIS 中的 Echo 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3044cdea-e9b2-4cc2-b66e-799da1dfc07e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74addb5a69e8f17319a7019167eac1415a3a88d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225181"
---
# <a name="tutorial-3-hosting-the-echo-adapter-in-iis"></a><span data-ttu-id="fb210-102">教程 3： 承载在 IIS 中的 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="fb210-102">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>
<span data-ttu-id="fb210-103">本教程提供分步说明，为承载 Echo 适配器开发[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fb210-103">This tutorial provides step-by-step instructions for hosting the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="fb210-104">更具体地说的步骤说明如何通过使用托管在 Internet 信息服务 (IIS) 的适配器[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fb210-104">More specifically, the steps show how you can host the adapter in Internet Information Services (IIS) by using the [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)].</span></span> <span data-ttu-id="fb210-105">将还使用在 SharePoint 中的业务数据目录功能来调用的承载于 IIS 中的适配器，此 EchoGreetings 操作，然后 Web 部件中显示的结果。</span><span class="sxs-lookup"><span data-stu-id="fb210-105">You will also use the Business Data Catalog feature in SharePoint to call the EchoGreetings operation of the IIS-hosted adapter, and then display the results in a Web Part.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="fb210-106">Echo 适配器的测试代码，安装脚本会在你 BizTalk 安装文件附带`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`或`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`。</span><span class="sxs-lookup"><span data-stu-id="fb210-106">The Echo Adapter, test code, and installation script are included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span> 
  
## <a name="in-this-section"></a><span data-ttu-id="fb210-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="fb210-107">In This Section</span></span>  
  
-   [<span data-ttu-id="fb210-108">步骤 1： 使用适配器服务开发向导来创建 Web 项目</span><span class="sxs-lookup"><span data-stu-id="fb210-108">Step 1: Use the Adapter Service Development Wizard to Create the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)  
  
-   [<span data-ttu-id="fb210-109">步骤 2： 部署 Web 项目</span><span class="sxs-lookup"><span data-stu-id="fb210-109">Step 2: Deploy the Web Project</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
-   [<span data-ttu-id="fb210-110">步骤 3： 创建应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="fb210-110">Step 3: Create an Application Definition File</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
-   [<span data-ttu-id="fb210-111">步骤 4： 创建 Sharepoint 应用程序访问适配器</span><span class="sxs-lookup"><span data-stu-id="fb210-111">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="fb210-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb210-112">See Also</span></span>  
 <span data-ttu-id="fb210-113">[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fb210-113">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
  [<span data-ttu-id="fb210-114">WCF LOB 适配器 SDK 教程</span><span class="sxs-lookup"><span data-stu-id="fb210-114">WCF LOB Adapter SDK Tutorials</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)