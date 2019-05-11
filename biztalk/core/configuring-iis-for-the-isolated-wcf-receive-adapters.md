---
title: 配置 IIS 以实现独立 WCF 接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- WCF services, receive adapters
- IIS, configuring [WCF receive adapters]
ms.assetid: 1c6f1561-a7ba-4eb0-8878-bf213ebcd6a6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 477afeef37fdf62ecbbd5dc78d11bcf20b5fbd48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390915"
---
# <a name="configuring-iis-for-the-isolated-wcf-receive-adapters"></a><span data-ttu-id="2f3e2-102">配置 IIS 以实现独立 WCF 接收适配器</span><span class="sxs-lookup"><span data-stu-id="2f3e2-102">Configuring IIS for the Isolated WCF Receive Adapters</span></span>
<span data-ttu-id="2f3e2-103">若要通过使用 BizTalk WCF 服务发布向导发布 WCF 服务，必须配置 Internet 信息服务 (IIS)、 biztalk 独立主机和 Windows 用户组帐户。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-103">To publish WCF services by using the BizTalk WCF Service Publishing Wizard, you must configure Internet Information Services (IIS), BizTalk isolated hosts, and Windows user group accounts.</span></span> <span data-ttu-id="2f3e2-104">本部分讨论与 IIS 配置为发布的 WCF 服务通过独立 WCF 接收适配器，如 Wcf-basichttp 接收适配器相关的问题、 Wcf-wshttp 接收适配器和 Wcf-customisolated 适配器。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-104">This section discusses issues related to configuring IIS for publishing WCF services with isolated WCF receive adapters such as the WCF-BasicHttp receive adapter, WCF-WSHttp receive adapter, and WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="2f3e2-105">有关承载在 IIS 中的 WCF 服务的常规信息，请参阅"在 IIS 中承载"网址[ http://go.microsoft.com/fwlink/?LinkId=75700 ](http://go.microsoft.com/fwlink/?LinkId=75700)。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-105">For general information about hosting WCF services in IIS, see "Hosting in IIS" at [http://go.microsoft.com/fwlink/?LinkId=75700](http://go.microsoft.com/fwlink/?LinkId=75700).</span></span>  
  
## <a name="considerations-when-configuring-iis"></a><span data-ttu-id="2f3e2-106">配置 IIS 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="2f3e2-106">Considerations When Configuring IIS</span></span>  
 <span data-ttu-id="2f3e2-107">**Internet Information Services 7.0 和 7.5**</span><span class="sxs-lookup"><span data-stu-id="2f3e2-107">**Internet Information Services 7.0 and 7.5**</span></span>  
  
 <span data-ttu-id="2f3e2-108">可以使用 IIS 7.0 和 7.5 配置有 ASP.NET 4.0 发布 WCF 服务通过独立 WCF 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-108">You can use IIS 7.0 and 7.5 configured with ASP.NET 4.0 to publish WCF services with isolated WCF receive adapters.</span></span>  
  
 <span data-ttu-id="2f3e2-109">IIS 7.0 （适用于 Windows Server 2008 SP2) 和 IIS 7.5 （适用于 Windows Server 2008 R2) 使用 IIS 应用程序池处理 Web 服务请求。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-109">IIS 7.0 (for Windows Server 2008 SP2) and IIS 7.5 (for Windows Server 2008 R2) use the IIS application pools for processing Web service requests.</span></span> <span data-ttu-id="2f3e2-110">IIS 7.0 支持多个应用程序池。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-110">IIS 7.0 supports multiple application pools.</span></span> <span data-ttu-id="2f3e2-111">每个应用程序池进程可以运行在不同用户上下文。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-111">Each application pool process can run under a different user context.</span></span>  
  
 <span data-ttu-id="2f3e2-112">**Biztalk 独立主机**</span><span class="sxs-lookup"><span data-stu-id="2f3e2-112">**BizTalk isolated hosts**</span></span>  
  
 <span data-ttu-id="2f3e2-113">若要承载 WCF 服务通过独立 WCF 接收适配器，则必须在 BizTalk Server 中创建至少一个独立的主机。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-113">To host the WCF services with isolated WCF receive adapters, you must create at least one isolated host in BizTalk Server.</span></span> <span data-ttu-id="2f3e2-114">有关如何配置 biztalk 独立主机的详细信息，请参阅"BizTalk Isolated Hosts"中[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-114">For more information about how to configure BizTalk isolated hosts, see "BizTalk Isolated Hosts" in [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
 <span data-ttu-id="2f3e2-115">**多个服务器安装的数据库访问**</span><span class="sxs-lookup"><span data-stu-id="2f3e2-115">**Database access for multiple server installations**</span></span>  
  
 <span data-ttu-id="2f3e2-116">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 BizTalk 管理数据库驻留在不同服务器上，应将 IIS 应用程序池的用户上下文更改为域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-116">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the BizTalk Management database reside on different servers, you should change the user context of the IIS Application Pool to a domain user account.</span></span>  
  
 <span data-ttu-id="2f3e2-117">当实现多服务器部署时，独立的主机 Windows 组必须存在 BizTalk 数据库服务器所属的域上。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-117">When implementing a multi-server deployment, the Isolated Host Windows groups must exist on the domain to which the BizTalk database servers belong.</span></span>  
  
 <span data-ttu-id="2f3e2-118">**帐户权限和用户权限降至最低**</span><span class="sxs-lookup"><span data-stu-id="2f3e2-118">**Minimizing account privileges and user rights**</span></span>  
  
 <span data-ttu-id="2f3e2-119">使用独立的主机以便运行在外部进程访问到所需的资源与 BizTalk Server 进行交互的最小数量的适配器。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-119">You use isolated hosts to give adapters that run in external processes access to the minimal amount of required resources to interact with BizTalk Server.</span></span> <span data-ttu-id="2f3e2-120">为确保部署的您应该为提供的用户上下文的外部进程最小特权。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-120">For a secure deployment, you should give the user context for the external processes minimal privileges.</span></span>  
  
 <span data-ttu-id="2f3e2-121">**BizTalk Web Services 发布向导的安全建议**</span><span class="sxs-lookup"><span data-stu-id="2f3e2-121">**Security recommendations for the BizTalk Web Services Publishing Wizard**</span></span>  
  
 <span data-ttu-id="2f3e2-122">通过 BizTalk WCF 服务发布向导创建的虚拟目录从父虚拟目录或网站继承访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="2f3e2-122">The virtual directory created by the BizTalk WCF Service Publishing Wizard inherits the access control lists (ACL) from the parent virtual directory or Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3e2-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f3e2-123">See Also</span></span>  
 [<span data-ttu-id="2f3e2-124">发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="2f3e2-124">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)