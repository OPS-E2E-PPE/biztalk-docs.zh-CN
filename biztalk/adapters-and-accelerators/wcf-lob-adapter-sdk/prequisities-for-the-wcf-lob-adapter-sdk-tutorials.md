---
title: "有关 WCF LOB 适配器 SDK 教程 Prequisities |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7d47ac1-1605-4c6d-a331-8583771dca28
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e16ba0911026508a40f234456c0b5d379f69bc4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prequisities-for-the-wcf-lob-adapter-sdk-tutorials"></a><span data-ttu-id="26f46-102">有关 WCF LOB 适配器 SDK 教程 Prequisities</span><span class="sxs-lookup"><span data-stu-id="26f46-102">Prequisities for the WCF LOB Adapter SDK tutorials</span></span>
<span data-ttu-id="26f46-103">本部分提供有关你应该熟悉以充分利用教程，以及完成它们所需的软件的概念的详细信息。</span><span class="sxs-lookup"><span data-stu-id="26f46-103">This section provides details about the concepts you should be familiar with to get the most out of the tutorials, as well as the software required to complete them.</span></span>  
  
## <a name="what-to-install"></a><span data-ttu-id="26f46-104">安装的内容</span><span class="sxs-lookup"><span data-stu-id="26f46-104">What to Install</span></span>  
 <span data-ttu-id="26f46-105">若要开始本教程，你必须在计算机上安装以下软件。</span><span class="sxs-lookup"><span data-stu-id="26f46-105">To start the tutorials, you must have the following software installed on your computer.</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]
  
-   <span data-ttu-id="26f46-106">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="26f46-106">Internet Information Services (IIS)</span></span>  
  
-   [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]
  
-   [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="26f46-107">（适用于你的 BizTalk Server 安装文件，并命名 ASDK_x64 和 ASDK_x86）</span><span class="sxs-lookup"><span data-stu-id="26f46-107"> (available with your BizTalk Server installation files, and named ASDK_x64 and ASDK_x86)</span></span>  
  
 <span data-ttu-id="26f46-108">若要完成本教程 3，你必须在计算机上安装以下软件。</span><span class="sxs-lookup"><span data-stu-id="26f46-108">To complete Tutorial 3, you must have the following software installed on your computer.</span></span>  
  
-   <span data-ttu-id="26f46-109">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="26f46-109">Microsoft SharePoint</span></span>  
  
-   <span data-ttu-id="26f46-110">Microsoft SharePoint SDK</span><span class="sxs-lookup"><span data-stu-id="26f46-110">Microsoft SharePoint SDK</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="26f46-111">不要在生产环境中执行这些教程。</span><span class="sxs-lookup"><span data-stu-id="26f46-111">Do not perform these tutorials in your production environment.</span></span>  
  
<span data-ttu-id="26f46-112">已完成的 Echo 适配器是在你 BizTalk 安装文件附带`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`或`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`。</span><span class="sxs-lookup"><span data-stu-id="26f46-112">The completed Echo Adapter is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="26f46-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="26f46-113">Prerequisites</span></span>  
 <span data-ttu-id="26f46-114">本教程假定你熟悉以下：</span><span class="sxs-lookup"><span data-stu-id="26f46-114">The tutorials assume that you are familiar with the following:</span></span>  
  
-   <span data-ttu-id="26f46-115">面向对象的软件设计和开发</span><span class="sxs-lookup"><span data-stu-id="26f46-115">Object-oriented software design and development</span></span>  
  
-   <span data-ttu-id="26f46-116">Windows Communication Foundation (WCF)，具体而言，渠道模型编程和服务模型编程</span><span class="sxs-lookup"><span data-stu-id="26f46-116">Windows Communication Foundation (WCF), specifically, channel model programming and service model programming</span></span>  
  
-   <span data-ttu-id="26f46-117">XSD、 XML、 WSDL 和 Web 服务描述语言 (WSDL) 和一个 API 之间的关系</span><span class="sxs-lookup"><span data-stu-id="26f46-117">XSD, XML, WSDL, and the relationship between Web Services Description Language (WSDL) and an API</span></span>  
  
-   <span data-ttu-id="26f46-118">C# 编程语言</span><span class="sxs-lookup"><span data-stu-id="26f46-118">C# programming language</span></span>  
  
-   <span data-ttu-id="26f46-119">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="26f46-119">.NET Framework</span></span>  
  
 <span data-ttu-id="26f46-120">在开始之前教程，很有帮助，如果你已经查看概念性主题的此 SDK 中，并且可以大致了解中的通道[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，包括中的类型**T:Microsoft.ServiceModel.Channels**和**T:Microsoft.ServiceModel.Channels.Common**命名空间。</span><span class="sxs-lookup"><span data-stu-id="26f46-120">Before starting the tutorials, it will be helpful if you have reviewed the conceptual topics of this SDK, and have a general understanding of channels in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], including the types within the **T:Microsoft.ServiceModel.Channels** and **T:Microsoft.ServiceModel.Channels.Common** namespaces.</span></span>  <span data-ttu-id="26f46-121">有关通道的详细信息，请参阅[通道模型概述](https://msdn.microsoft.com/library/ms729840.aspx)。</span><span class="sxs-lookup"><span data-stu-id="26f46-121">For more information about channels, see the [Channel Model Overview](https://msdn.microsoft.com/library/ms729840.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f46-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26f46-122">See Also</span></span>  
 [<span data-ttu-id="26f46-123">若要了解 WCF LOB 适配器 SDK 的教程</span><span class="sxs-lookup"><span data-stu-id="26f46-123">Tutorials to learn the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)