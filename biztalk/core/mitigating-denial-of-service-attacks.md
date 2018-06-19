---
title: 减少拒绝服务攻击 |Microsoft 文档
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
ms.openlocfilehash: a02e3eddcd43acf67e8e928e1a8f172c0019c616
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971739"
---
# <a name="mitigating-denial-of-service-attacks"></a><span data-ttu-id="936d4-102">减少拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="936d4-102">Mitigating Denial of Service Attacks</span></span>
<span data-ttu-id="936d4-103">建议使用以下缓解措施来保护您的 BizTalk Server 和服务免受拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="936d4-103">It is recommended to use the following mitigation techniques to help protect your BizTalk servers and services against Denial of Service attacks.</span></span> <span data-ttu-id="936d4-104">您必须确定其中哪些缓解措施适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="936d4-104">You must decide which of these mitigation techniques are appropriate for your environment.</span></span>  
  
-   <span data-ttu-id="936d4-105">**接收端口中使用的身份验证所需属性。**</span><span class="sxs-lookup"><span data-stu-id="936d4-105">**Use the Authentication Required property in the receive port.**</span></span> <span data-ttu-id="936d4-106">默认情况下，BizTalk 将其接收的所有消息都发送到 MessageBox 数据库，即使这些消息来自未知或无法解析的参与方（来宾）。若要缓解攻击者将大量的消息发送到 BizTalk Server 以及扩散 （填充） 可能 MessageBox 数据库中，你可以使用**所需的身份验证**中仅接收到的接收端口属性来自 BizTalk 服务器知道的参与方的消息。</span><span class="sxs-lookup"><span data-stu-id="936d4-106">By default, BizTalk sends all the messages it receives to the MessageBox database, even if they come from an unknown or unresolved party (Guest.) To mitigate the potential of an attacker sending a large number of messages to BizTalk Server and flooding (filling) the MessageBox database, you can use the **Authentication Required** property in the receive port to only receive messages that come from parties BizTalk Server knows.</span></span> <span data-ttu-id="936d4-107">您可选择删除或挂起来自未知参与方的消息。</span><span class="sxs-lookup"><span data-stu-id="936d4-107">You can choose either to drop the messages coming from an unknown party or to suspend them.</span></span> <span data-ttu-id="936d4-108">有关详细信息**所需的身份验证**属性，请参阅[进行身份验证消息的发件人](../core/authenticating-the-sender-of-a-message.md)。</span><span class="sxs-lookup"><span data-stu-id="936d4-108">For more information about the **Authentication Required** property, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span> <span data-ttu-id="936d4-109">除了**所需的身份验证**属性，则应考虑使用的外部机制，如防火墙端口筛选或 IP 地址阻止来防止拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="936d4-109">In addition to the **Authentication Required** property, you should consider the use of an external mechanism such as firewall port filtering or IP-address blocking to protect against Denial of Service attacks.</span></span>  
  
-   <span data-ttu-id="936d4-110">**限制 BizTalk 可以接收的消息的大小。**</span><span class="sxs-lookup"><span data-stu-id="936d4-110">**Limit the size of the messages that BizTalk can receive.**</span></span> <span data-ttu-id="936d4-111">例如，当你使用 SOAP 接收适配器，你可以避免通过 maxRequestLength 属性设置接收非常大的消息大小\<httpRuntime\>到可接受的大小的元素。</span><span class="sxs-lookup"><span data-stu-id="936d4-111">For example, when you use the SOAP receive adapter, you can avoid receiving very large messages size by setting the maxRequestLength attribute in the \<httpRuntime\> element to an acceptable size.</span></span> <span data-ttu-id="936d4-112">\<HttpRuntime\>元素定义在 Machine.config 文件中，它位于\<*驱动器*\>:\\<*Windows目录*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG 目录。</span><span class="sxs-lookup"><span data-stu-id="936d4-112">The \<httpRuntime\> element is defined in the Machine.config file, which is located in the \<*drive*\>:\\<*Windows directory*\>\Microsoft.NET\Framework\vX.X.XXXXX\CONFIG directory.</span></span> <span data-ttu-id="936d4-113">有关详细信息\<httpRuntime\>元素，请参阅 Microsoft MSDN 网站， [http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948)。</span><span class="sxs-lookup"><span data-stu-id="936d4-113">For more information about \<httpRuntime\> element, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=60948](http://go.microsoft.com/fwlink/?LinkId=60948).</span></span>  
  
-   <span data-ttu-id="936d4-114">**有关使用强 Dacl 接收位置。**</span><span class="sxs-lookup"><span data-stu-id="936d4-114">**Use strong DACLs for receive locations.**</span></span> <span data-ttu-id="936d4-115">建议在接收位置的存放位置中使用加强的随机访问控制列表 (DACL)。</span><span class="sxs-lookup"><span data-stu-id="936d4-115">It is recommended that you use strong discretionary access control lists (DACLs) in the drop locations for the receive locations.</span></span> <span data-ttu-id="936d4-116">例如，在文件接收位置从其中提取消息的目录中，必须使用加强的 DACL，以便只有经过授权的用户才能在此位置中存放消息。</span><span class="sxs-lookup"><span data-stu-id="936d4-116">For example, you must use strong DACLs in the directory from which the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
-   <span data-ttu-id="936d4-117">**使用 IPSec。**</span><span class="sxs-lookup"><span data-stu-id="936d4-117">**Use IPSec.**</span></span> <span data-ttu-id="936d4-118">如果不使用硬件或软件防火墙，则应使用 Internet 协议安全性 (IPSec) 在 BizTalk Server 将消息和数据从一个服务器传输到另一个服务器时对其进行保护。</span><span class="sxs-lookup"><span data-stu-id="936d4-118">If you do not use hardware or software firewalls, use Internet Protocol security (IPSec) to help protect the messages and data as BizTalk Server transfers it from one server to another.</span></span> <span data-ttu-id="936d4-119">有关 IPSec 的详细信息，请参阅 Microsoft 下载中心[http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949)。</span><span class="sxs-lookup"><span data-stu-id="936d4-119">For more information about IPSec, see the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=60949](http://go.microsoft.com/fwlink/?LinkId=60949).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936d4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="936d4-120">See Also</span></span>  
 <span data-ttu-id="936d4-121">[识别潜在的威胁](../core/identifying-potential-threats.md) </span><span class="sxs-lookup"><span data-stu-id="936d4-121">[Identifying Potential Threats](../core/identifying-potential-threats.md) </span></span>  
 [<span data-ttu-id="936d4-122">Planning for Security</span><span class="sxs-lookup"><span data-stu-id="936d4-122">Planning for Security</span></span>](../core/planning-for-security.md)