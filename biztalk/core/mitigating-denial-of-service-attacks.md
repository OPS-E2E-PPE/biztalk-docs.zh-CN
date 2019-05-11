---
title: 缓解拒绝服务攻击 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IPSec, message protection
- messages, size
- security, configuring
- Authentication Required property
- security, Internet Information Services (IIS) Lockdown Tool
- security, Denial of Service attacks
- discretionary access control lists (DACLs)
- IPSec, data protection
- Internet Information Services (IIS) Lockdown Tool
- Denial of Service attacks
ms.assetid: f39c0d0a-b890-4c48-874d-5cafbc71473c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9595bf828a1960f50090371232f25282fed21b6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394423"
---
# <a name="mitigating-denial-of-service-attacks"></a><span data-ttu-id="8bf48-102">缓解拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="8bf48-102">Mitigating Denial of Service Attacks</span></span>
<span data-ttu-id="8bf48-103">建议使用以下缓解措施来帮助保护你的 BizTalk 服务器和服务免受拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="8bf48-103">It is recommended to use the following mitigation techniques to help protect your BizTalk servers and services against Denial of Service attacks.</span></span> <span data-ttu-id="8bf48-104">您必须决定哪些缓解措施是适用于你的环境。</span><span class="sxs-lookup"><span data-stu-id="8bf48-104">You must decide which of these mitigation techniques are appropriate for your environment.</span></span>  
  
-   <span data-ttu-id="8bf48-105">**在接收端口中使用的身份验证所需属性。**</span><span class="sxs-lookup"><span data-stu-id="8bf48-105">**Use the Authentication Required property in the receive port.**</span></span> <span data-ttu-id="8bf48-106">默认情况下，BizTalk 发送到 MessageBox 数据库接收的所有消息，即使它们来自未知或无法解析参与方 （来宾）。若要缓解攻击者向 BizTalk Server 发送大量消息以及扩散 （填满） 的可能性 MessageBox 数据库中，您可以使用**身份验证所需**中仅接收到的接收端口属性来自 BizTalk Server 已知的参与方的消息。</span><span class="sxs-lookup"><span data-stu-id="8bf48-106">By default, BizTalk sends all the messages it receives to the MessageBox database, even if they come from an unknown or unresolved party (Guest.) To mitigate the potential of an attacker sending a large number of messages to BizTalk Server and flooding (filling) the MessageBox database, you can use the **Authentication Required** property in the receive port to only receive messages that come from parties BizTalk Server knows.</span></span> <span data-ttu-id="8bf48-107">可以选择删除来自未知参与方的消息，或若要暂停使用它们。</span><span class="sxs-lookup"><span data-stu-id="8bf48-107">You can choose either to drop the messages coming from an unknown party or to suspend them.</span></span> <span data-ttu-id="8bf48-108">有关详细信息**所需的身份验证**属性，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="8bf48-108">For more information about the **Authentication Required** property, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span> <span data-ttu-id="8bf48-109">除了**身份验证所需**属性，应考虑使用外部机制，如防火墙端口筛选或 IP 地址阻止来防止拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="8bf48-109">In addition to the **Authentication Required** property, you should consider the use of an external mechanism such as firewall port filtering or IP-address blocking to protect against Denial of Service attacks.</span></span>  
  
-   <span data-ttu-id="8bf48-110">**限制 BizTalk 可接收的消息的大小。**</span><span class="sxs-lookup"><span data-stu-id="8bf48-110">**Limit the size of the messages that BizTalk can receive.**</span></span> <span data-ttu-id="8bf48-111">例如，当您使用 SOAP 接收适配器，可以避免接收超大的消息大小的 maxRequestLength 属性设置通过\<httpRuntime\>元素为可接受的大小。</span><span class="sxs-lookup"><span data-stu-id="8bf48-111">For example, when you use the SOAP receive adapter, you can avoid receiving very large messages size by setting the maxRequestLength attribute in the \<httpRuntime\> element to an acceptable size.</span></span> <span data-ttu-id="8bf48-112">\<HttpRuntime\>元素定义在 Machine.config 文件中，位于\<*驱动器*\>:\\<*Windows目录*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG 目录。</span><span class="sxs-lookup"><span data-stu-id="8bf48-112">The \<httpRuntime\> element is defined in the Machine.config file, which is located in the \<*drive*\>:\\<*Windows directory*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG directory.</span></span> <span data-ttu-id="8bf48-113">有关详细信息\<httpRuntime\>元素，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkId=60948 ](http://go.microsoft.com/fwlink/?LinkId=60948)。</span><span class="sxs-lookup"><span data-stu-id="8bf48-113">For more information about \<httpRuntime\> element, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948).</span></span>  
  
-   <span data-ttu-id="8bf48-114">**使用加强的 Dacl 的接收位置。**</span><span class="sxs-lookup"><span data-stu-id="8bf48-114">**Use strong DACLs for receive locations.**</span></span> <span data-ttu-id="8bf48-115">建议使用加强的任意访问控制列表 (Dacl) 中的放置位置的接收位置。</span><span class="sxs-lookup"><span data-stu-id="8bf48-115">It is recommended that you use strong discretionary access control lists (DACLs) in the drop locations for the receive locations.</span></span> <span data-ttu-id="8bf48-116">例如，必须在目录中的文件接收位置从其中提取消息，使用加强的 Dacl，以便只有经过授权的用户可以在此位置中存放消息。</span><span class="sxs-lookup"><span data-stu-id="8bf48-116">For example, you must use strong DACLs in the directory from which the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
-   <span data-ttu-id="8bf48-117">**使用 IPSec。**</span><span class="sxs-lookup"><span data-stu-id="8bf48-117">**Use IPSec.**</span></span> <span data-ttu-id="8bf48-118">如果看不到使用硬件或软件防火墙，请使用 Internet 协议安全 (IPSec) 到另一个以帮助保护 BizTalk Server 将将其传输从一台服务器的消息和数据。</span><span class="sxs-lookup"><span data-stu-id="8bf48-118">If you do not use hardware or software firewalls, use Internet Protocol security (IPSec) to help protect the messages and data as BizTalk Server transfers it from one server to another.</span></span> <span data-ttu-id="8bf48-119">有关 IPSec 的详细信息，请参阅 Microsoft 下载中心[ http://go.microsoft.com/fwlink/?LinkId=60949 ](http://go.microsoft.com/fwlink/?LinkId=60949)。</span><span class="sxs-lookup"><span data-stu-id="8bf48-119">For more information about IPSec, see the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf48-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bf48-120">See Also</span></span>  
 <span data-ttu-id="8bf48-121">[标识潜在威胁](../core/identifying-potential-threats.md) </span><span class="sxs-lookup"><span data-stu-id="8bf48-121">[Identifying Potential Threats](../core/identifying-potential-threats.md) </span></span>  
 [<span data-ttu-id="8bf48-122">规划安全性</span><span class="sxs-lookup"><span data-stu-id="8bf48-122">Planning for Security</span></span>](../core/planning-for-security.md)