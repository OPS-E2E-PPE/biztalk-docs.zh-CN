---
title: 解决 Web Services 权限问题的准则 |Microsoft Docs
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
ms.openlocfilehash: c56d784362861ad90788e8a3e8dde666dd863efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344808"
---
# <a name="guidelines-for-resolving-web-services-permissions-problems"></a><span data-ttu-id="849d8-102">解决 Web Services 权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="849d8-102">Guidelines for Resolving Web Services Permissions Problems</span></span>
<span data-ttu-id="849d8-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可广泛使用的 Web 服务使用 SOAP 适配器和业务流程发布为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="849d8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of Web services for use with the SOAP adapter and when publishing orchestrations as Web services.</span></span> <span data-ttu-id="849d8-104">本主题提供一些通用准则，最大程度减少 Web services 权限问题和步骤，你可以遵循解决 Web services 权限问题的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="849d8-104">This topic provides some general guidelines for minimizing Web services permissions problems and steps that you can follow to troubleshoot Web services permissions problems that affect [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="849d8-105">通用指导原则</span><span class="sxs-lookup"><span data-stu-id="849d8-105">General Guidelines</span></span>  
  
- <span data-ttu-id="849d8-106">**设置用户帐户**:请确保所 IIS 应用程序主机进程标识与之关联的虚拟目录用于承载 Web 服务设置为特定用户帐户，并确保此用户帐户添加到以下组：</span><span class="sxs-lookup"><span data-stu-id="849d8-106">**Setting user accounts**: Ensure that the IIS application host process identity associated with the virtual directory that hosts the Web service is set to a specific user account and ensure that this user account is added to the following groups:</span></span>  
  
  - <span data-ttu-id="849d8-107">BizTalk Isolated Host Users （域或本地组）</span><span class="sxs-lookup"><span data-stu-id="849d8-107">BizTalk Isolated Host Users (domain or local group)</span></span>  
  
  - <span data-ttu-id="849d8-108">IIS_WPG （本地组）</span><span class="sxs-lookup"><span data-stu-id="849d8-108">IIS_WPG (local group)</span></span>  
  
    <span data-ttu-id="849d8-109">这两个组的成员身份所需授予适当的权限来将 SOAP 请求消息发布到 BizTalk MessageBox 数据库，这将激活订阅由 BizTalk Web 服务发布向导创建的 Web 服务业务流程。</span><span class="sxs-lookup"><span data-stu-id="849d8-109">Membership in these 2 groups is required to grant the Web service created by the BizTalk Web Service Publishing Wizard the appropriate rights to publish a SOAP request message into the BizTalk MessageBox database which will in turn activate the subscribing orchestration.</span></span> <span data-ttu-id="849d8-110">有关确定或设置 IIS 应用程序主机进程标识的详细信息，请参阅**设置 IIS 应用程序主机进程标识**一部分[解决IIS权限问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md).</span><span class="sxs-lookup"><span data-stu-id="849d8-110">For more information about determining or setting the IIS application host process identity, see the **Setting IIS Application Host Process Identity** section of [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md).</span></span>  
  
- <span data-ttu-id="849d8-111">**在由 TEMP 环境变量指定的文件夹上设置权限**:确保承载 Web 服务的虚拟目录的 IIS 应用程序主机进程标识具有读取和写入到由 TEMP 环境变量指定的文件夹的权限。</span><span class="sxs-lookup"><span data-stu-id="849d8-111">**Setting permissions on the folder specified by the TEMP environment variable**: Ensure that the IIS application host process identity for the virtual directory that hosts the Web service has read and write permissions to the folder specified by the TEMP environment variable.</span></span> <span data-ttu-id="849d8-112">若要确定由 TEMP 环境变量打开指定的文件夹，BizTalk Server 上的命令提示符下键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="849d8-112">To determine the folder that is specified by the TEMP environment variable open a command prompt on the BizTalk Server, type the following command, and then press ENTER:</span></span>  
  
  ```  
  echo %TEMP%  
  ```  
  
   <span data-ttu-id="849d8-113">由 TEMP 环境变量指定的文件夹是 Web 服务的实时 (JIT) 编译为动态链接库 (dll) 文件，因此必须可具有读取和写入权限通过此用户帐户。</span><span class="sxs-lookup"><span data-stu-id="849d8-113">The folder specified by the TEMP environment variable is where the Web service is Just In Time (JIT) compiled into a dynamic link library (dll) file and therefore must be accessible with read and write permissions by this user account.</span></span>  
  
- <span data-ttu-id="849d8-114">**在 SOAP 方法调用中发送凭据**:请确保 Web 服务客户端在 SOAP 方法调用中发送凭据。</span><span class="sxs-lookup"><span data-stu-id="849d8-114">**Sending credentials in the SOAP method call**: Ensure that the Web service client is sending credentials in the SOAP method call.</span></span> <span data-ttu-id="849d8-115">默认情况下，IIS 7.0 中[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]需要 windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="849d8-115">By default IIS 7.0 in [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] requires windows authentication.</span></span> <span data-ttu-id="849d8-116">当测试 Web 服务与 Internet Explorer 中，当前登录的用户的凭据会自动发送正因如此，Web 服务可能会从 Internet 资源管理器中工作但却无法在另一个客户端。</span><span class="sxs-lookup"><span data-stu-id="849d8-116">When testing a Web service with Internet Explorer, the credentials of the user who is currently logged on are automatically sent which is why the Web service may work from Internet Explorer but fail from another client.</span></span> <span data-ttu-id="849d8-117">如果 Web 服务客户端不会将凭据添加到 SOAP 方法调用将因身份验证失败而生成 SOAP 异常。</span><span class="sxs-lookup"><span data-stu-id="849d8-117">If the Web service client does not add credentials to the SOAP method call a SOAP exception will be generated due to an authentication failure.</span></span> <span data-ttu-id="849d8-118">有关将凭据发送在 SOAP 方法调用，请参阅中提供的示例代码[如何使用新的 System.Net 类创建 HTTP 客户端](http://support.microsoft.com/kb/303436)。</span><span class="sxs-lookup"><span data-stu-id="849d8-118">For more information about sending credentials in a SOAP method call see the sample code available in [How to use the new System.Net classes to create an HTTP client](http://support.microsoft.com/kb/303436).</span></span>  
  
- <span data-ttu-id="849d8-119">**调用 Web 服务的错误故障排除**:如果调用 Web 服务时出现错误，检查应用程序日志，或消息通过 BizTalk Server 管理事件和服务实例跟踪**组中心**页。</span><span class="sxs-lookup"><span data-stu-id="849d8-119">**Troubleshooting errors calling a Web service**: If errors occur when calling a Web service, check the Application log, or message event and service instance tracking through the BizTalk Server Administration **Group Hub** page.</span></span> <span data-ttu-id="849d8-120">有关错误的可能的原因的详细信息，请参阅[监视 BizTalk Server](../core/monitoring-biztalk-server.md)并[使用的组中心页](../core/using-the-group-hub-page.md)。</span><span class="sxs-lookup"><span data-stu-id="849d8-120">For more information about the possible causes of the error, see [Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) and [Using the Group Hub Page](../core/using-the-group-hub-page.md).</span></span>  
  
- <span data-ttu-id="849d8-121">**收集调试信息**:若要获取详细的调试信息，请按照主题中所述的步骤[调试已发布 Web Services](../core/debugging-published-web-services.md)如果按照上述步骤无法解决此问题。</span><span class="sxs-lookup"><span data-stu-id="849d8-121">**Collecting debugging information**: To obtain detailed debugging information, follow the steps outlined in the topic [Debugging Published Web Services](../core/debugging-published-web-services.md) if following the steps above does not resolve the issue.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="849d8-122">已知问题</span><span class="sxs-lookup"><span data-stu-id="849d8-122">Known Issues</span></span>  
 <span data-ttu-id="849d8-123">有关其他信息的已知问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与 Web services 权限相关，请参阅"不能调用作为运行 BizTalk Server 的服务器上的 Web 服务公开的业务流程"网址[ http://go.microsoft.com/fwlink/?LinkId=196379 ](http://go.microsoft.com/fwlink/?LinkId=196379).</span><span class="sxs-lookup"><span data-stu-id="849d8-123">For additional information on known issues with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] related to Web services permissions, see "You cannot call an orchestration that is exposed as a Web service on a server that is running BizTalk Server" at [http://go.microsoft.com/fwlink/?LinkId=196379](http://go.microsoft.com/fwlink/?LinkId=196379).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="849d8-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="849d8-124">See Also</span></span>  
 <span data-ttu-id="849d8-125">[故障排除的 BizTalk Server 权限](../core/troubleshooting-biztalk-server-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="849d8-125">[Troubleshooting BizTalk Server Permissions](../core/troubleshooting-biztalk-server-permissions.md) </span></span>  
 [<span data-ttu-id="849d8-126">解决 IIS 权限疑难问题的准则</span><span class="sxs-lookup"><span data-stu-id="849d8-126">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)