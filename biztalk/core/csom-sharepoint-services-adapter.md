---
title: 'CSOM: SharePoint Services 适配器 |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 334c7f32-4620-4fee-8237-491d3c3ded4e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 146d4ecb253aca18c0699f526e01b28fd62ff984
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238621"
---
# <a name="csom-sharepoint-services-adapter"></a><span data-ttu-id="c47a2-102">CSOM: SharePoint Services Adapter</span><span class="sxs-lookup"><span data-stu-id="c47a2-102">CSOM: SharePoint Services Adapter</span></span>
<span data-ttu-id="c47a2-103">使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器，你可以从 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 接收消息以及将消息发送到 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c47a2-103">Using the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter, you can receive messages from [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and send messages to [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c47a2-104">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]适配器使用[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]客户端对象模型 (CSOM)，即***自动***时安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="c47a2-104">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM), which is ***automatically*** installed when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span> <span data-ttu-id="c47a2-105">在 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 计算机中没有其他安装步骤。</span><span class="sxs-lookup"><span data-stu-id="c47a2-105">There are no additional installation steps on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer.</span></span>  
  
 <span data-ttu-id="c47a2-106">我们建议使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器的客户端对象模型 (CSOM)。</span><span class="sxs-lookup"><span data-stu-id="c47a2-106">We recommend using the Client Side Object Model (CSOM) of the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter.</span></span>  
  
 <span data-ttu-id="c47a2-107">[附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)提供有关详细信息[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="c47a2-107">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides more information on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] installation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c47a2-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="c47a2-108">In This Section</span></span>  
  
-   [<span data-ttu-id="c47a2-109">配置 SharePoint 服务接收位置</span><span class="sxs-lookup"><span data-stu-id="c47a2-109">Configure SharePoint Services Receive Location</span></span>](../core/configure-sharepoint-services-receive-location.md)  
  
-   [<span data-ttu-id="c47a2-110">配置 SharePoint Services 发送端口</span><span class="sxs-lookup"><span data-stu-id="c47a2-110">Configure SharePoint Services Send Port</span></span>](../core/configure-sharepoint-services-send-port.md)  
  
-   [<span data-ttu-id="c47a2-111">故障排除 SharePoint Services Adapter</span><span class="sxs-lookup"><span data-stu-id="c47a2-111">Troubleshooting SharePoint Services Adapter</span></span>](../core/troubleshooting-sharepoint-services-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="c47a2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c47a2-112">See Also</span></span>  
 <span data-ttu-id="c47a2-113">[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c47a2-113">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 [<span data-ttu-id="c47a2-114">BizTalk Server 2013 和 2013 R2 安装概述</span><span class="sxs-lookup"><span data-stu-id="c47a2-114">Installation Overview for BizTalk Server 2013 and 2013 R2</span></span>](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)