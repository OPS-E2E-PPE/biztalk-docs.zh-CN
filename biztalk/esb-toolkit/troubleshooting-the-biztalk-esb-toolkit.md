---
title: "故障排除 BizTalk ESB 工具包 |Microsoft 文档"
description: "解决安装问题，以及与 BizTalk Server 中 ESB 工具包的常见错误"
caps.latest.revision: "2"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1ea2d56-2ace-40f2-80df-8a7489bbfc2e
ms.author: mandia
ms.openlocfilehash: 8fc1305e481de2444a54ea994f8a53da83b2eaed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-biztalk-esb-toolkit"></a><span data-ttu-id="33b38-103">解决 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="33b38-103">Troubleshoot the BizTalk ESB Toolkit</span></span>

  
## <a name="installation"></a><span data-ttu-id="33b38-104">安装</span><span class="sxs-lookup"><span data-stu-id="33b38-104">Installation</span></span>  
  
|<span data-ttu-id="33b38-105">问题</span><span class="sxs-lookup"><span data-stu-id="33b38-105">Issue</span></span>|<span data-ttu-id="33b38-106">解决方法</span><span class="sxs-lookup"><span data-stu-id="33b38-106">Resolution</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="33b38-107">收到安装期间出现"分配权限的错误"的异常。</span><span class="sxs-lookup"><span data-stu-id="33b38-107">You receive an "Error assigning permissions" exception during installation.</span></span>|<span data-ttu-id="33b38-108">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用标准的 BizTalk 帐户组，必须存在在安装过程中或安装将失败。</span><span class="sxs-lookup"><span data-stu-id="33b38-108">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses the standard BizTalk account groups, which must exist during the installation process or the installation will fail.</span></span> <span data-ttu-id="33b38-109">此外，该工具包假设其中的计算机是工作组的成员的独立安装或安装企业版的计算机所在域的成员。</span><span class="sxs-lookup"><span data-stu-id="33b38-109">In addition, the toolkit assumes either a standalone installation where the computer is a member of a workgroup or an enterprise installation where the computer is a member of a domain.</span></span>|  
|<span data-ttu-id="33b38-110">应用程序导入失败并显示错误消息，警告的信任级别不匹配。</span><span class="sxs-lookup"><span data-stu-id="33b38-110">Application import fails with an error message that warns of trust level mismatch.</span></span>|<span data-ttu-id="33b38-111">Microsoft.BizTalk.ESB 绑定文件被配置为使用默认值，BizTalkServerApplication 和 BizTalkServerIsolatedHost，反过来配置为在不受信任模式下执行。</span><span class="sxs-lookup"><span data-stu-id="33b38-111">The Microsoft.BizTalk.ESB binding files are configured to work with the default BizTalkServerApplication and BizTalkServerIsolatedHost, which are in turn configured to execute in untrusted mode.</span></span> <span data-ttu-id="33b38-112">如果你已更改你的主机在受信任模式下运行，将不导入绑定文件。</span><span class="sxs-lookup"><span data-stu-id="33b38-112">If you have changed your host to run in trusted mode, the binding file will not import.</span></span> <span data-ttu-id="33b38-113">若要纠正此问题，你必须将信任级别更改为不受信任或编辑以满足你的环境中的 BizTalk 工具包 \Bindings 目录的绑定文件。</span><span class="sxs-lookup"><span data-stu-id="33b38-113">To correct this, you must either change the trust level to untrusted or edit the binding file to suit your environment in the BizTalk Toolkit \Bindings directory.</span></span>|  
|<span data-ttu-id="33b38-114">Kerberos 身份验证未配置 Internet 信息服务 (IIS) 中。</span><span class="sxs-lookup"><span data-stu-id="33b38-114">Kerberos authentication is not configured in Internet Information Services (IIS).</span></span>|<span data-ttu-id="33b38-115">若要启用 Kerberos 身份验证的 IIS，请参阅 Microsoft 知识库中的以下文章：</span><span class="sxs-lookup"><span data-stu-id="33b38-115">To enable Kerberos authentication for IIS, see the following articles in the Microsoft Knowledge Base:</span></span><br /><br /> <span data-ttu-id="33b38-116">-   [如何配置 IIS 以支持 Kerberos 协议和 NTLM 协议的网络身份验证](http://go.microsoft.com/fwlink/?LinkId=188566)</span><span class="sxs-lookup"><span data-stu-id="33b38-116">-   [How to configure IIS to support both the Kerberos protocol and the NTLM protocol for network authentication](http://go.microsoft.com/fwlink/?LinkId=188566)</span></span><br /><span data-ttu-id="33b38-117">-   [如何启用 IIS 以在不是域控制器的计算机上使用 Kerberos 身份验证](http://go.microsoft.com/fwlink/?LinkId=188567)</span><span class="sxs-lookup"><span data-stu-id="33b38-117">-   [How to enable IIS to use Kerberos authentication on a computer that is not a domain controller](http://go.microsoft.com/fwlink/?LinkId=188567)</span></span><br /><span data-ttu-id="33b38-118">-   [你不能为 Internet 信息服务 (IIS) 7.0 为 Windows 集成身份验证在 IIS 管理器中配置 Negotiate 或 NTLM 协议](http://go.microsoft.com/fwlink/?LinkId=188568)</span><span class="sxs-lookup"><span data-stu-id="33b38-118">-   [You cannot configure the Negotiate or NTLM protocols for Windows Integrated Authentication in the IIS Manager for Internet Information Services (IIS) 7.0](http://go.microsoft.com/fwlink/?LinkId=188568)</span></span>|  
  
## <a name="general-issues"></a><span data-ttu-id="33b38-119">一般问题</span><span class="sxs-lookup"><span data-stu-id="33b38-119">General Issues</span></span>  
  
|<span data-ttu-id="33b38-120">问题</span><span class="sxs-lookup"><span data-stu-id="33b38-120">Issue</span></span>|<span data-ttu-id="33b38-121">解决方法</span><span class="sxs-lookup"><span data-stu-id="33b38-121">Resolution</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="33b38-122">向通用 ESB 路线上负载增加 Web 服务发送一条消息时，你会收到"内部 SOAP 处理"异常。</span><span class="sxs-lookup"><span data-stu-id="33b38-122">You receive an "Internal SOAP Processing" exception when sending a message to the generic ESB Itinerary On-Ramp Web service.</span></span>|<span data-ttu-id="33b38-123">使用 BizTalk Server 管理控制台来确保 Microsoft.Practices.ESB 应用程序正在运行;如果未运行，，启动它。</span><span class="sxs-lookup"><span data-stu-id="33b38-123">Use the BizTalk Server Administration Console to ensure that the Microsoft.Practices.ESB application is running; if it is not running, start it.</span></span>|  
|<span data-ttu-id="33b38-124">在管理门户中 ESB 站点中不显示异常消息。</span><span class="sxs-lookup"><span data-stu-id="33b38-124">Exception messages are not appearing in the ESB Management Portal site.</span></span>|<span data-ttu-id="33b38-125">检查 BizTalk 管理员组概述页和 Windows 应用程序事件日志，以指示失败发送消息的条目。</span><span class="sxs-lookup"><span data-stu-id="33b38-125">Check the BizTalk Administrator Group Overview page and the Windows Application Event Log for entries that indicate failures to send messages.</span></span> <span data-ttu-id="33b38-126">你可能需要重新配置异常发送适配器 （Microsoft.Practices.ESB 应用程序的一部分） 以匹配你的环境。</span><span class="sxs-lookup"><span data-stu-id="33b38-126">You may need to reconfigure the exception Send Adapter (part of the Microsoft.Practices.ESB application) to match your environment.</span></span> <span data-ttu-id="33b38-127">此外，请注意 BizTalk 失败消息路由功能和 BizTalk ESB 工具包异常管理框架生成的异常消息。</span><span class="sxs-lookup"><span data-stu-id="33b38-127">In addition, be aware that both the BizTalk Failed Message Routing feature and the BizTalk ESB Toolkit Exception Management Framework generate exceptions messages.</span></span> <span data-ttu-id="33b38-128">因此，请确保你启用**失败消息的路由**选项用于发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="33b38-128">Therefore, ensure that you enable the **Route on Failed Messages** option for send and receive ports.</span></span>|  
|<span data-ttu-id="33b38-129">在使用静态的解析程序使用 WCF 服务，你将收到无效的 SOAP 操作异常。</span><span class="sxs-lookup"><span data-stu-id="33b38-129">When consuming a WCF service with a static resolver, you receive an invalid SOAP action exception.</span></span>|<span data-ttu-id="33b38-130">如果 WCF 服务 SOAP 操作不包括的目标命名空间，采用以下格式设置的冲突解决程序中设置的 SOAP 操作值: {action} 以指示 ESB 工具包核心引擎在运行时将不连接的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="33b38-130">If the WCF service SOAP action does not include the target namespace, set the value of the SOAP action in the following format in the resolver setting: {action} to indicate that the target namespace will not be concatenated by the ESB Toolkit core engine at runtime.</span></span>|