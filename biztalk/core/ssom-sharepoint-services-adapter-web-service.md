---
title: "SSOM: SharePoint Services 适配器 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 064d97b0-eb4b-4943-af01-5ca11e5f7029
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362af6cb7d2deca1afe02e7b871d07849ac3671
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ssom-sharepoint-services-adapter-web-service"></a><span data-ttu-id="331a1-102">SSOM: SharePoint Services 适配器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="331a1-102">SSOM: SharePoint Services Adapter Web Service</span></span>
<span data-ttu-id="331a1-103">使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器，你可以从 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 接收消息以及将消息发送到 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="331a1-103">Using the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter, you can receive messages from [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and send messages to [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="331a1-104">已弃用的 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web 服务适配器使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 服务端对象模型 (SSOM)。</span><span class="sxs-lookup"><span data-stu-id="331a1-104">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web Service Adapter, which is deprecated, uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span> <span data-ttu-id="331a1-105">在安装了 web 服务[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]可以是同一计算机的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="331a1-105">The web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span> <span data-ttu-id="331a1-106">建议在单独的计算机上安装 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="331a1-106">It is recommended to install [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on separate computers.</span></span>  
  
 <span data-ttu-id="331a1-107">我们建议使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器的客户端对象模型 (CSOM)。</span><span class="sxs-lookup"><span data-stu-id="331a1-107">We recommend using the Client Side Object Model (CSOM) of the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter.</span></span> <span data-ttu-id="331a1-108">请参阅[CSOM: SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md)和[附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)有关安装和配置选项。</span><span class="sxs-lookup"><span data-stu-id="331a1-108">See [CSOM: SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md) and [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) for installation and configuration options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="331a1-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="331a1-109">In This Section</span></span>  
 [<span data-ttu-id="331a1-110">什么是 Windows SharePoint Services Adapter？</span><span class="sxs-lookup"><span data-stu-id="331a1-110">What Is the Windows SharePoint Services Adapter?</span></span>](../core/what-is-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="331a1-111">设置和部署 Windows SharePoint Services Adapter</span><span class="sxs-lookup"><span data-stu-id="331a1-111">Setting Up and Deploying the Windows SharePoint Services Adapter</span></span>](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="331a1-112">配置 Windows SharePoint Services Adapter</span><span class="sxs-lookup"><span data-stu-id="331a1-112">Configuring the Windows SharePoint Services Adapter</span></span>](../core/configuring-the-windows-sharepoint-services-adapter.md)  
  
 [<span data-ttu-id="331a1-113">Windows SharePoint Services 适配器演练</span><span class="sxs-lookup"><span data-stu-id="331a1-113">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)