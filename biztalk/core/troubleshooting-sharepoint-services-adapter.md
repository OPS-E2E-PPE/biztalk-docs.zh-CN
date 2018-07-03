---
title: 故障排除 SharePoint Services 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f88174-118d-4ed6-8449-c89ca195ce5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3bc6cb2d7569e7d1ee0c8816bafa91151294df7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979310"
---
# <a name="troubleshooting-sharepoint-services-adapter"></a><span data-ttu-id="b50f6-102">SharePoint Services 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="b50f6-102">Troubleshooting SharePoint Services Adapter</span></span>
<span data-ttu-id="b50f6-103">本主题主要介绍 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) 适配器的疑难解答。</span><span class="sxs-lookup"><span data-stu-id="b50f6-103">This topic focuses on troubleshooting the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) adapter.</span></span>  

## <a name="installation"></a><span data-ttu-id="b50f6-104">安装</span><span class="sxs-lookup"><span data-stu-id="b50f6-104">Installation</span></span>  
 <span data-ttu-id="b50f6-105">当使用 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) 适配器时，有以下两个选项：</span><span class="sxs-lookup"><span data-stu-id="b50f6-105">When using the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] (WSS) adapter, there are two options:</span></span>  


|                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b50f6-106">**使用客户端 OM**设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="b50f6-106">**Use Client OM** set to **Yes**.</span></span> |                                                                                                                                     <span data-ttu-id="b50f6-107">**推荐**。</span><span class="sxs-lookup"><span data-stu-id="b50f6-107">**Recommended**.</span></span> <span data-ttu-id="b50f6-108">如果设置为“是”，则使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 客户端对象模型 (CSOM)。</span><span class="sxs-lookup"><span data-stu-id="b50f6-108">When set to Yes, the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM) is used.</span></span> <span data-ttu-id="b50f6-109">此适配器将随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装。</span><span class="sxs-lookup"><span data-stu-id="b50f6-109">The adapter is installed when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span> <span data-ttu-id="b50f6-110">没有其他安装步骤。</span><span class="sxs-lookup"><span data-stu-id="b50f6-110">There are no additional installation steps.</span></span> <span data-ttu-id="b50f6-111">**注意：** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装还会自动安装 SharePoint 客户端对象模型可再发行的网址[ http://go.microsoft.com/fwlink/p/?LinkId=263482 ](http://go.microsoft.com/fwlink/p/?LinkId=263482)。</span><span class="sxs-lookup"><span data-stu-id="b50f6-111">**Note:**  The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation also automatically installs the SharePoint Client Object Model Redistributable available at [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).</span></span>                                                                                                                                     |
| <span data-ttu-id="b50f6-112">**使用客户端 OM**设置为**否**。</span><span class="sxs-lookup"><span data-stu-id="b50f6-112">**Use Client OM** set to **No**.</span></span>  | <span data-ttu-id="b50f6-113">**已弃用**。</span><span class="sxs-lookup"><span data-stu-id="b50f6-113">**Deprecated**.</span></span> <span data-ttu-id="b50f6-114">使用 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 服务端对象模型 (SSOM)。</span><span class="sxs-lookup"><span data-stu-id="b50f6-114">Uses the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Service Side Object Model (SSOM).</span></span><br /><br /> <span data-ttu-id="b50f6-115">该 Web 服务安装在 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 计算机上，既可以和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在同一计算机上，也可以在单独的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b50f6-115">A web service is installed on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer, which can be on the same computer as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a separate computer.</span></span><br /><br /> <span data-ttu-id="b50f6-116">若要安装 web 服务，运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上的安装[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]计算机，然后检查**Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="b50f6-116">To install the web service, run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] computer and check **Windows SharePoint Services Adapter**.</span></span> <span data-ttu-id="b50f6-117">请参阅[附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)了解特定安装步骤。</span><span class="sxs-lookup"><span data-stu-id="b50f6-117">See [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) for specific installation steps.</span></span> |

 <span data-ttu-id="b50f6-118">**使用客户端 OM**设置为**是**建议。</span><span class="sxs-lookup"><span data-stu-id="b50f6-118">**Use Client OM** set to **Yes** is recommended.</span></span> <span data-ttu-id="b50f6-119">如果设置为**是**，SharePoint 计算机上未安装 web 服务。</span><span class="sxs-lookup"><span data-stu-id="b50f6-119">When set to **Yes**, the web service is NOT installed on the SharePoint computer.</span></span> <span data-ttu-id="b50f6-120">如果想要使用的 web 服务选项，则必须设置**使用客户端 OM**到**否**上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b50f6-120">If you prefer to use the web service option, you must set **Use Client OM** to **No** on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="iis"></a><span data-ttu-id="b50f6-121">IIS</span><span class="sxs-lookup"><span data-stu-id="b50f6-121">IIS</span></span>  
 <span data-ttu-id="b50f6-122">**BTSharePointAdapterWS.asmx web 服务**</span><span class="sxs-lookup"><span data-stu-id="b50f6-122">**BTSharePointAdapterWS.asmx web service**</span></span>  

 <span data-ttu-id="b50f6-123">在 SharePoint 计算机上安装 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] 适配器后，将在该 SharePoint 计算机上的 IIS 中创建 BTSharePointAdapterWS.asmx Web 服务。</span><span class="sxs-lookup"><span data-stu-id="b50f6-123">When the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter is installed on the SharePoint computer, the BTSharePointAdapterWS.asmx web service is created in IIS on the SharePoint computer.</span></span> <span data-ttu-id="b50f6-124">通常，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 SharePoint 安装在不同计算机上。</span><span class="sxs-lookup"><span data-stu-id="b50f6-124">Typically, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SharePoint are installed on different computers.</span></span> <span data-ttu-id="b50f6-125">当安装 SharePoint 时，内容 SQL 数据库可以位于 SharePoint 计算机本地，也可以位于远程 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 上。</span><span class="sxs-lookup"><span data-stu-id="b50f6-125">When SharePoint is installed, the content SQL database can be local to the SharePoint computer or on a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  

 <span data-ttu-id="b50f6-126">**应用程序池使用域帐户**</span><span class="sxs-lookup"><span data-stu-id="b50f6-126">**Application Pool uses Domain account**</span></span>  

 <span data-ttu-id="b50f6-127">当 BizTalk 和 SharePoint 位于不同计算机上时，运行 BTSharePointAdapterWS.asmx Web 服务的 IIS 应用程序池必须使用域帐户。</span><span class="sxs-lookup"><span data-stu-id="b50f6-127">When BizTalk and SharePoint are on different computers, the IIS application pool running the BTSharePointAdapterWS.asmx web service must use a domain account.</span></span> <span data-ttu-id="b50f6-128">如果全部在同一计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk 数据库、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint 数据库，则可以使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="b50f6-128">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the BizTalk databases, [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] SharePoint databases are all installed on the same computer, then a local account can be used.</span></span>  

 <span data-ttu-id="b50f6-129">**双跃点方案**</span><span class="sxs-lookup"><span data-stu-id="b50f6-129">**Double-Hop Scenario**</span></span>  

 <span data-ttu-id="b50f6-130">当涉及三台计算机（[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]）时，可以使用一个需要 Kerberos 身份验证的双跃点方案。</span><span class="sxs-lookup"><span data-stu-id="b50f6-130">When there are three computers involved ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]), there is a double-hop scenario that requires Kerberos authentication.</span></span> <span data-ttu-id="b50f6-131">BizTalk 计算机上的 SharePoint 适配器向 SharePoint 计算机上的 BTSharePointAdapterWS.asmx Web 服务提出一个 POST 请求。</span><span class="sxs-lookup"><span data-stu-id="b50f6-131">The SharePoint adapter on the BizTalk computer does a POST request to the BTSharePointAdapterWS.asmx web service on the SharePoint computer.</span></span> <span data-ttu-id="b50f6-132">然后，SharePoint 计算机查询其在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的数据库。</span><span class="sxs-lookup"><span data-stu-id="b50f6-132">The SharePoint computer then queries its databases on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  

 <span data-ttu-id="b50f6-133">这个来自 BizTalk 适配器的 POST 请求必须成功完成。</span><span class="sxs-lookup"><span data-stu-id="b50f6-133">This POST request from the BizTalk adapter must complete successfully.</span></span> <span data-ttu-id="b50f6-134">如果你怀疑某个身份验证失败，请查阅 IIS 日志。</span><span class="sxs-lookup"><span data-stu-id="b50f6-134">If you suspect an authentication failure, review the IIS logs.</span></span> <span data-ttu-id="b50f6-135">默认情况下，IIS 日志位于 c:\inetpub\logs\LogFiles\W3SVC*x*。</span><span class="sxs-lookup"><span data-stu-id="b50f6-135">By default, the IIS logs are in c:\inetpub\logs\LogFiles\W3SVC*x*.</span></span> <span data-ttu-id="b50f6-136">该 POST 请求应显示 200（成功）状态码。</span><span class="sxs-lookup"><span data-stu-id="b50f6-136">The POST request should display a 200 (success) status code.</span></span> <span data-ttu-id="b50f6-137">如果返回失败的状态代码，如 401.2，跟以下由另一个 4 401.1*xx*错误，则身份验证可能会失败。</span><span class="sxs-lookup"><span data-stu-id="b50f6-137">If a failed status code is returned, like a 401.2, followed by a 401.1, following by another 4*xx* error, then authentication may be failing.</span></span>  

 <span data-ttu-id="b50f6-138">当使用 Kerberos 身份验证时，将需要服务主体名称 (SPN)，并且必须启用委派。</span><span class="sxs-lookup"><span data-stu-id="b50f6-138">When Kerberos authentication is used, service principal names (SPN) are required and delegation must be enabled.</span></span>  

## <a name="enable-kerberos-authentication"></a><span data-ttu-id="b50f6-139">启用 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="b50f6-139">Enable Kerberos Authentication</span></span>  
 <span data-ttu-id="b50f6-140">在双跃点方案中，需要 Kerberos 身份验证并启用委派。</span><span class="sxs-lookup"><span data-stu-id="b50f6-140">In a double-hop scenario, Kerberos authentication and enabling delegation are required.</span></span> <span data-ttu-id="b50f6-141">相关步骤包括：</span><span class="sxs-lookup"><span data-stu-id="b50f6-141">Steps include:</span></span>  

1. <span data-ttu-id="b50f6-142">启用**Negotiate** IIS/SharePoint 服务器上。</span><span class="sxs-lookup"><span data-stu-id="b50f6-142">Enable **Negotiate** on the IIS/SharePoint server.</span></span> <span data-ttu-id="b50f6-143">[215383： 如何配置 IIS 以用于网络身份验证支持 Kerberos 协议和 NTLM 协议](http://support.microsoft.com/kb/215383)列出的步骤。</span><span class="sxs-lookup"><span data-stu-id="b50f6-143">[215383: How to configure IIS to support both the Kerberos protocol and the NTLM protocol for network authentication](http://support.microsoft.com/kb/215383) lists the steps.</span></span>  

2. <span data-ttu-id="b50f6-144">执行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 服务的域帐户和 IIS/SharePoint 计算机上的应用程序池需要服务主体名称 (SPN)。</span><span class="sxs-lookup"><span data-stu-id="b50f6-144">Service Principal Names (SPNs) are required for the domain accounts executing the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Service and the Application Pool on the IIS/SharePoint computer.</span></span> <span data-ttu-id="b50f6-145">若要创建 SPN，请使用 SetSPN.exe 命令行工具：</span><span class="sxs-lookup"><span data-stu-id="b50f6-145">To create an SPN, use the SetSPN.exe command-line tool:</span></span>  

    [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]<span data-ttu-id="b50f6-146">:[有可用的 Windows Server 2003 中的 Setspn.exe 更新](http://support.microsoft.com/kb/970536)</span><span class="sxs-lookup"><span data-stu-id="b50f6-146">: [An update for Setspn.exe in Windows Server 2003 is available](http://support.microsoft.com/kb/970536)</span></span>  

    [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]<span data-ttu-id="b50f6-147"> 8 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]并[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)</span><span class="sxs-lookup"><span data-stu-id="b50f6-147"> 8, [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]: [SetSPN](http://technet.microsoft.com/library/cc731241.aspx)</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="b50f6-148">SetSPN 需要域管理员权限，并且可以从域中的任何计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="b50f6-148">SetSPN requires Domain Administrator rights and can be executed from any computer in the domain.</span></span>  

    <span data-ttu-id="b50f6-149">若要返回注册到某个域帐户的所有 SPN 的列表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b50f6-149">To return a list of all SPNs registered to a domain account:</span></span>  

   ```  
   setspn.exe -l Domain\UserAccount  
   ```  

    <span data-ttu-id="b50f6-150">创建 SPN：</span><span class="sxs-lookup"><span data-stu-id="b50f6-150">Create the SPNs:</span></span>  

   1.  <span data-ttu-id="b50f6-151">为 IIS/SharePoint 计算机的 FQDN 创建 SPN：</span><span class="sxs-lookup"><span data-stu-id="b50f6-151">Create an SPN for the FQDN of the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s http/IISSharePointComputerName.domain.com domain\IISApplicationPoolDomainAccount  
       ```  

   2.  <span data-ttu-id="b50f6-152">为 IIS/SharePoint 计算机的 NETBIOS 名称创建 SPN：</span><span class="sxs-lookup"><span data-stu-id="b50f6-152">Create an SPN for the NETBIOS name of the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s http/IISSharePointComputerNamedomain\IISApplicationPoolDomainAccount  
       ```  

   3.  <span data-ttu-id="b50f6-153">为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 FQDN 创建 SPN：</span><span class="sxs-lookup"><span data-stu-id="b50f6-153">Create an SPN for the FQDN of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com domain\SQLServerServiceDomainAccount  
       ```  

   4.  <span data-ttu-id="b50f6-154">为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 FQDN 和 TCP 端口创建 SPN：</span><span class="sxs-lookup"><span data-stu-id="b50f6-154">Create an SPN for the FQDN and TCP Port of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName.domain.com:1433 domain\SQLServerServiceDomainAccount  
       ```  

   5.  <span data-ttu-id="b50f6-155">为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 NETBIOS 名称创建 SPN：</span><span class="sxs-lookup"><span data-stu-id="b50f6-155">Create an SPN for the NETBIOS name of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerNamedomain\SQLServerServiceDomainAccount  
       ```  

   6.  <span data-ttu-id="b50f6-156">为 IIS/SharePoint 计算机使用的 SQL Server 计算机的 NETBIOS 名称:TCP 端口创建 SPN：</span><span class="sxs-lookup"><span data-stu-id="b50f6-156">Create an SPN for the NETBIOS name:TCP Port of the SQL Server computer used by the IIS/SharePoint computer:</span></span>  

       ```  
       setspn.exe -s mssqlsvc/SQLComputerName:1433 domain\SQLServerServiceDomainAccount  
       ```  

3. <span data-ttu-id="b50f6-157">在域控制器上转到**Active Directory 用户和计算机**并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b50f6-157">On the Domain controller, go to **Active Directory Users & Computers** and do the following:</span></span>  

   1.  <span data-ttu-id="b50f6-158">检查**信任此计算机来委派任何服务**以下计算机：</span><span class="sxs-lookup"><span data-stu-id="b50f6-158">Check **Trust this computer for delegation to any service** for the following computers:</span></span>  

       -   <span data-ttu-id="b50f6-159">SharePoint/IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="b50f6-159">SharePoint/IIS server</span></span>  

       -   <span data-ttu-id="b50f6-160">由 SharePoint 使用的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="b50f6-160">SQL Server used by SharePoint</span></span>  

   2.  <span data-ttu-id="b50f6-161">检查**帐户受信任为委派**并取消选中**敏感帐户，不能被委派**对于以下域帐户：</span><span class="sxs-lookup"><span data-stu-id="b50f6-161">Check **Account is Trusted for Delegation** and uncheck **Account is sensitive and cannot be delegated** for the following domain accounts:</span></span>  

       -   <span data-ttu-id="b50f6-162">SQL Server 服务域帐户</span><span class="sxs-lookup"><span data-stu-id="b50f6-162">SQL Server service domain account</span></span>  

       -   <span data-ttu-id="b50f6-163">IIS 应用程序池域帐户</span><span class="sxs-lookup"><span data-stu-id="b50f6-163">IIS Application Pool domain account</span></span>  

   <span data-ttu-id="b50f6-164">有关其他故障排除，请转到[Windows SharePoint Services 适配器故障排除](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="b50f6-164">For additional troubleshooting, go to [Troubleshooting the Windows SharePoint Services Adapter](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)</span></span>  

## <a name="see-also"></a><span data-ttu-id="b50f6-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="b50f6-165">See Also</span></span>  
 <span data-ttu-id="b50f6-166">[配置 SharePoint Services 接收位置](../core/configure-sharepoint-services-receive-location.md) </span><span class="sxs-lookup"><span data-stu-id="b50f6-166">[Configure SharePoint Services Receive Location](../core/configure-sharepoint-services-receive-location.md) </span></span>  
 <span data-ttu-id="b50f6-167">[配置 SharePoint Services 发送端口](../core/configure-sharepoint-services-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="b50f6-167">[Configure SharePoint Services Send Port](../core/configure-sharepoint-services-send-port.md) </span></span>  
 [<span data-ttu-id="b50f6-168">CSOM：SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="b50f6-168">CSOM: SharePoint Services Adapter</span></span>](../core/csom-sharepoint-services-adapter.md)