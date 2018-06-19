---
title: 解决 Web 服务中的权限问题的准则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e29543e9-9b87-437b-ac91-8f1cce01fab4
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68fc866a2a1f2c51a0649cf8a01ef03164b9a913
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246773"
---
# <a name="guidelines-for-resolving-web-services-permissions-problems"></a><span data-ttu-id="eb9ee-102">解决 Web 服务的权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="eb9ee-102">Guidelines for Resolving Web Services Permissions Problems</span></span>
<span data-ttu-id="eb9ee-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发布作为 Web 服务的业务流程时使广泛使用的用途，与 SOAP 适配器以及 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of Web services for use with the SOAP adapter and when publishing orchestrations as Web services.</span></span> <span data-ttu-id="eb9ee-104">本主题提供了一些一般性的指导，最小化 Web 服务中的权限问题和步骤，你可以遵循进行故障排除 Web 服务会影响的权限问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-104">This topic provides some general guidelines for minimizing Web services permissions problems and steps that you can follow to troubleshoot Web services permissions problems that affect [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="eb9ee-105">通用指导原则</span><span class="sxs-lookup"><span data-stu-id="eb9ee-105">General Guidelines</span></span>  
  
-   <span data-ttu-id="eb9ee-106">**设置用户帐户**： 确保与承载 Web 服务的虚拟目录关联的 IIS 应用程序主机进程标识已设置为特定用户帐户，并确保此用户帐户添加到以下组：</span><span class="sxs-lookup"><span data-stu-id="eb9ee-106">**Setting user accounts**: Ensure that the IIS application host process identity associated with the virtual directory that hosts the Web service is set to a specific user account and ensure that this user account is added to the following groups:</span></span>  
  
    -   <span data-ttu-id="eb9ee-107">BizTalk Isolated Host Users（域组或本地组）</span><span class="sxs-lookup"><span data-stu-id="eb9ee-107">BizTalk Isolated Host Users (domain or local group)</span></span>  
  
    -   <span data-ttu-id="eb9ee-108">IIS_WPG（本地组）</span><span class="sxs-lookup"><span data-stu-id="eb9ee-108">IIS_WPG (local group)</span></span>  
  
     <span data-ttu-id="eb9ee-109">要向由 BizTalk Web Services 发布向导创建的 Web Services 授予将 SOAP 请求消息发布到 BizTalk MessageBox 数据库中（随后将激活订阅业务流程）的正确权限，必须首先成为这两个组的成员。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-109">Membership in these 2 groups is required to grant the Web service created by the BizTalk Web Service Publishing Wizard the appropriate rights to publish a SOAP request message into the BizTalk MessageBox database which will in turn activate the subscribing orchestration.</span></span> <span data-ttu-id="eb9ee-110">有关确定或设置 IIS 应用程序主机进程标识的详细信息，请参阅**设置 IIS 应用程序主机进程标识**部分[解决 IIS 权限问题准则](../core/guidelines-for-resolving-iis-permissions-problems.md).</span><span class="sxs-lookup"><span data-stu-id="eb9ee-110">For more information about determining or setting the IIS application host process identity, see the **Setting IIS Application Host Process Identity** section of [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md).</span></span>  
  
-   <span data-ttu-id="eb9ee-111">**在由 TEMP 环境变量指定的文件夹上设置权限**： 确保承载 Web 服务的虚拟目录的 IIS 应用程序主机进程标识具有读取和写入到指定的文件夹的权限TEMP 环境变量。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-111">**Setting permissions on the folder specified by the TEMP environment variable**: Ensure that the IIS application host process identity for the virtual directory that hosts the Web service has read and write permissions to the folder specified by the TEMP environment variable.</span></span> <span data-ttu-id="eb9ee-112">若要确定由 TEMP 环境变量指定的文件夹，请在 BizTalk Server 上打开命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="eb9ee-112">To determine the folder that is specified by the TEMP environment variable open a command prompt on the BizTalk Server, type the following command, and then press ENTER:</span></span>  
  
    ```  
    echo %TEMP%  
    ```  
  
     <span data-ttu-id="eb9ee-113">Web Services 在由 TEMP 环境变量指定的文件夹中实时 (JIT) 编译为动态链接库 (dll) 文件，因而必须由此用户帐户通过读写权限来访问该文件夹。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-113">The folder specified by the TEMP environment variable is where the Web service is Just In Time (JIT) compiled into a dynamic link library (dll) file and therefore must be accessible with read and write permissions by this user account.</span></span>  
  
-   <span data-ttu-id="eb9ee-114">**SOAP 方法调用中发送凭据**： 确保 Web 服务客户端在 SOAP 方法调用中发送凭据。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-114">**Sending credentials in the SOAP method call**: Ensure that the Web service client is sending credentials in the SOAP method call.</span></span> <span data-ttu-id="eb9ee-115">默认情况下中的 IIS 7.0[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]需要 windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-115">By default IIS 7.0 in [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] requires windows authentication.</span></span> <span data-ttu-id="eb9ee-116">当使用 Internet Explorer 测试 Web Services 时，会自动发送当前登录的用户的凭据，这就是 Web Services 可以在 Internet Explorer 中工作但却无法在其他客户端中工作的原因。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-116">When testing a Web service with Internet Explorer, the credentials of the user who is currently logged on are automatically sent which is why the Web service may work from Internet Explorer but fail from another client.</span></span> <span data-ttu-id="eb9ee-117">如果 Web Services 客户端未将凭据添加到 SOAP 方法调用中，则会由于身份验证失败而产生 SOAP 异常。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-117">If the Web service client does not add credentials to the SOAP method call a SOAP exception will be generated due to an authentication failure.</span></span> <span data-ttu-id="eb9ee-118">有关将凭据发送 SOAP 方法中调用，请参阅中可用的示例代码[如何使用新的 System.Net 类创建 HTTP 客户端](http://support.microsoft.com/kb/303436)。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-118">For more information about sending credentials in a SOAP method call see the sample code available in [How to use the new System.Net classes to create an HTTP client](http://support.microsoft.com/kb/303436).</span></span>  
  
-   <span data-ttu-id="eb9ee-119">**调用 Web 服务的错误故障排除**： 如果在调用 Web 服务时，将出现错误，检查应用程序日志中，或消息通过 BizTalk Server 管理事件和服务实例跟踪**组中心数据库**页。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-119">**Troubleshooting errors calling a Web service**: If errors occur when calling a Web service, check the Application log, or message event and service instance tracking through the BizTalk Server Administration **Group Hub** page.</span></span> <span data-ttu-id="eb9ee-120">有关错误的可能的原因的详细信息，请参阅[监视 BizTalk Server](../core/monitoring-biztalk-server.md)和[使用组中心页](../core/using-the-group-hub-page.md)。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-120">For more information about the possible causes of the error, see [Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) and [Using the Group Hub Page](../core/using-the-group-hub-page.md).</span></span>  
  
-   <span data-ttu-id="eb9ee-121">**收集调试信息**： 若要获取详细的调试信息，请按照主题中所述的步骤[调试已发布的 Web 服务](../core/debugging-published-web-services.md)如果按照上述步骤无法解决问题。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-121">**Collecting debugging information**: To obtain detailed debugging information, follow the steps outlined in the topic [Debugging Published Web Services](../core/debugging-published-web-services.md) if following the steps above does not resolve the issue.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="eb9ee-122">已知问题</span><span class="sxs-lookup"><span data-stu-id="eb9ee-122">Known Issues</span></span>  
 <span data-ttu-id="eb9ee-123">有关其他信息的已知问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Web services 权限，请参阅"不能调用作为运行 BizTalk Server 的服务器上的 Web 服务公开的业务流程"在[http://go.microsoft.com/fwlink /？LinkId = 196379](http://go.microsoft.com/fwlink/?LinkId=196379)。</span><span class="sxs-lookup"><span data-stu-id="eb9ee-123">For additional information on known issues with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] related to Web services permissions, see "You cannot call an orchestration that is exposed as a Web service on a server that is running BizTalk Server" at [http://go.microsoft.com/fwlink/?LinkId=196379](http://go.microsoft.com/fwlink/?LinkId=196379).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb9ee-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb9ee-124">See Also</span></span>  
 <span data-ttu-id="eb9ee-125">[BizTalk Server 权限的疑难解答](../core/troubleshooting-biztalk-server-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="eb9ee-125">[Troubleshooting BizTalk Server Permissions](../core/troubleshooting-biztalk-server-permissions.md) </span></span>  
 [<span data-ttu-id="eb9ee-126">以解决 IIS 权限问题的指导原则</span><span class="sxs-lookup"><span data-stu-id="eb9ee-126">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)