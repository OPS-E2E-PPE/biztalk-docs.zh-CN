---
title: Windows SharePoint Services 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters
ms.assetid: cbfc9bf3-912d-4849-ba8c-07a116888bbd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6f1365b11ce93717223ec35e395165e8d0e551
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289877"
---
# <a name="windows-sharepoint-services-adapter"></a><span data-ttu-id="253a3-102">Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="253a3-102">Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="253a3-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Microsoft Windows SharePoint Services 的适配器提供的 BizTalk Server 的 Windows SharePoint Services 和 Microsoft Office 更紧密的集成。</span><span class="sxs-lookup"><span data-stu-id="253a3-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Microsoft Windows SharePoint Services provides a tighter integration of BizTalk Server with Windows SharePoint Services and Microsoft Office.</span></span> <span data-ttu-id="253a3-104">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 解决方案中使用 Windows SharePoint Services 适配器可为你提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="253a3-104">Using the Windows SharePoint Services adapter in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution provides you with the following capabilities:</span></span>  
  
-   <span data-ttu-id="253a3-105">通过 Windows SharePoint Services 可方便地查看输入和输出消息。</span><span class="sxs-lookup"><span data-stu-id="253a3-105">Easy access to input and output messages through Windows SharePoint Services.</span></span>  
  
-   <span data-ttu-id="253a3-106">通过使用诸如 Microsoft Office InfoPath 之类的 Office 应用程序可编辑 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="253a3-106">The ability to edit XML messages by using Office applications such as Microsoft Office InfoPath.</span></span>  
  
-   <span data-ttu-id="253a3-107">XML 消息与 InfoPath 之间的双向转换。</span><span class="sxs-lookup"><span data-stu-id="253a3-107">Two-way transformations of XML messages to and from InfoPath.</span></span>  
  
 <span data-ttu-id="253a3-108">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="253a3-108">The [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter consists of the following components:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="253a3-109">CSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器</span><span class="sxs-lookup"><span data-stu-id="253a3-109">CSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter</span></span>|<span data-ttu-id="253a3-110">使用[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]客户端对象模型 (CSOM)。</span><span class="sxs-lookup"><span data-stu-id="253a3-110">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM).</span></span> <span data-ttu-id="253a3-111">此适配器将随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装。</span><span class="sxs-lookup"><span data-stu-id="253a3-111">The adapter is installed when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span> <span data-ttu-id="253a3-112">没有其他安装步骤。</span><span class="sxs-lookup"><span data-stu-id="253a3-112">There are no additional installation steps.</span></span><br /><br /> <span data-ttu-id="253a3-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装***自动***安装 SharePoint 客户端对象模型可再发行组件，这也是在[http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482)。</span><span class="sxs-lookup"><span data-stu-id="253a3-113">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation ***automatically*** installs the SharePoint Client Object Model Redistributable, which is also available at [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span></span>|  
|<span data-ttu-id="253a3-114">SSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web 服务</span><span class="sxs-lookup"><span data-stu-id="253a3-114">SSOM [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Web Service</span></span>|<span data-ttu-id="253a3-115">**已弃用**。</span><span class="sxs-lookup"><span data-stu-id="253a3-115">**Deprecated**.</span></span> <span data-ttu-id="253a3-116">使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 服务端对象模型 (SSOM)。</span><span class="sxs-lookup"><span data-stu-id="253a3-116">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span><br /><br /> <span data-ttu-id="253a3-117">在安装了 web 服务[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]可以是同一计算机的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="253a3-117">The web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span><br /><br /> <span data-ttu-id="253a3-118">若要安装 web 服务，运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的安装[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机并检查**Windows SharePoint Services Adapter**。</span><span class="sxs-lookup"><span data-stu-id="253a3-118">To install the web service, run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer and check **Windows SharePoint Services Adapter**.</span></span>|  
  
 <span data-ttu-id="253a3-119">[附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)提供有关详细信息[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="253a3-119">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides more information on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] installation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="253a3-120">当前不支持联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="253a3-120">Currently, federated authentication is not supported.</span></span> <span data-ttu-id="253a3-121">仅支持用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="253a3-121">Only Username and Password are supported.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="253a3-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="253a3-122">In This Section</span></span>  
  
-   [<span data-ttu-id="253a3-123">CSOM: SharePoint Services Adapter</span><span class="sxs-lookup"><span data-stu-id="253a3-123">CSOM: SharePoint Services Adapter</span></span>](../core/csom-sharepoint-services-adapter.md)  
  
-   [<span data-ttu-id="253a3-124">SSOM: SharePoint Services 适配器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="253a3-124">SSOM: SharePoint Services Adapter Web Service</span></span>](../core/ssom-sharepoint-services-adapter-web-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="253a3-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="253a3-125">See Also</span></span>  
 <span data-ttu-id="253a3-126">[使用适配器](../core/using-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="253a3-126">[Using Adapters](../core/using-adapters.md) </span></span>  
 [<span data-ttu-id="253a3-127">开发 BizTalk Server 应用程序</span><span class="sxs-lookup"><span data-stu-id="253a3-127">Developing BizTalk Server Applications</span></span>](../core/developing-biztalk-server-applications.md)