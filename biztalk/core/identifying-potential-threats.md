---
title: "识别潜在的威胁 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d20f17ee3d1c4d1291de27ae73d18fed3e604fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="identifying-potential-threats"></a><span data-ttu-id="e92bf-102">识别潜在的威胁</span><span class="sxs-lookup"><span data-stu-id="e92bf-102">Identifying Potential Threats</span></span>
<span data-ttu-id="e92bf-103">您可以使用 STRIDE 模型来对 BizTalk Server 部署的潜在威胁进行分类。</span><span class="sxs-lookup"><span data-stu-id="e92bf-103">You can use the STRIDE model to identify potential threats to your BizTalk Server deployment.</span></span> <span data-ttu-id="e92bf-104">STRIDE 是派生自以下类别的首字母缩写： *S*哄骗标识*T*篡改数据， *R*epudiation，*我*璝泄露*D*用以服务和特权提升。</span><span class="sxs-lookup"><span data-stu-id="e92bf-104">STRIDE is an acronym derived from the following categories: *S*poofing identity, *T*ampering with data, *R*epudiation, *I*nformation disclosure, *D*enial of service, and Elevation of privileges.</span></span> <span data-ttu-id="e92bf-105">本部分列举了对 BizTalk Server 环境的潜在威胁及相应的威胁缓解机制。</span><span class="sxs-lookup"><span data-stu-id="e92bf-105">This section contains examples of potential threats to a BizTalk Server environment, and mechanisms to mitigate them.</span></span>  
  
 <span data-ttu-id="e92bf-106">**欺骗标识**</span><span class="sxs-lookup"><span data-stu-id="e92bf-106">**Spoofing identity**</span></span>  
  
-   <span data-ttu-id="e92bf-107">如果您将密码保存在绑定文件中并保存这些绑定文件，则未经授权的用户可能会读取密码并使用这些密码连接到 BizTalk Servers，从而可能造成损害。</span><span class="sxs-lookup"><span data-stu-id="e92bf-107">If you save passwords in the binding files, and save these binding files, unauthorized users could read the passwords and use them to connect to the BizTalk Servers, and possibly cause harm.</span></span> <span data-ttu-id="e92bf-108">您不应该将密码保存在绑定文件中，而应使用任意访问控制列表 (DACL) 来限制访问可能包含敏感数据的文件。</span><span class="sxs-lookup"><span data-stu-id="e92bf-108">You should not save passwords in binding files, and you should use discretionary access control lists (DACLs) to restrict access to files that may contain sensitive data.</span></span>  
  
 <span data-ttu-id="e92bf-109">**篡改数据**</span><span class="sxs-lookup"><span data-stu-id="e92bf-109">**Tampering with data**</span></span>  
  
-   <span data-ttu-id="e92bf-110">恶意用户可能会截获合作伙伴发送到 BizTalk Server 的消息，并修改消息内容。</span><span class="sxs-lookup"><span data-stu-id="e92bf-110">Malicious users can intercept messages from partners to BizTalk Server, and modify the content of the message.</span></span> <span data-ttu-id="e92bf-111">您可以使用数字签名，以防消息在传输过程中遭恶意用户篡改。</span><span class="sxs-lookup"><span data-stu-id="e92bf-111">You can use digital signatures to prevent malicious users from tampering with messages while they are in transit.</span></span>  
  
 <span data-ttu-id="e92bf-112">**否认性**</span><span class="sxs-lookup"><span data-stu-id="e92bf-112">**Repudiation**</span></span>  
  
-   <span data-ttu-id="e92bf-113">您需要跟踪 BizTalk 发送和接收的消息。</span><span class="sxs-lookup"><span data-stu-id="e92bf-113">You need to keep track of messages that BizTalk sends and receives.</span></span> <span data-ttu-id="e92bf-114">可以使用数字签名以证明您发送的消息以及合作伙伴发送给您的消息。</span><span class="sxs-lookup"><span data-stu-id="e92bf-114">You can use digital signatures to prove that you sent a message and that your partners sent you a message.</span></span>  
  
 <span data-ttu-id="e92bf-115">**信息泄露**</span><span class="sxs-lookup"><span data-stu-id="e92bf-115">**Information disclosure**</span></span>  
  
-   <span data-ttu-id="e92bf-116">恶意用户可能会读取 BizTalk Server 和 Microsoft SQL Server™ 之间的明文通信。</span><span class="sxs-lookup"><span data-stu-id="e92bf-116">Malicious users can read clear-text communication between BizTalk Server and Microsoft SQL Server™.</span></span> <span data-ttu-id="e92bf-117">您可使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 来保证服务器间的通信安全。</span><span class="sxs-lookup"><span data-stu-id="e92bf-117">You can use Internet Protocol security (IPSec), or Secure Sockets Layer (SSL) to help secure the communication between servers.</span></span> <span data-ttu-id="e92bf-118">可以使用防火墙来限制对每台服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="e92bf-118">You can use firewalls to limit access to each server.</span></span> <span data-ttu-id="e92bf-119">此外，还可以使用加密在消息传输过程中保护隐私。</span><span class="sxs-lookup"><span data-stu-id="e92bf-119">You can use encryption to help ensure the privacy of the message while it is in transit.</span></span>  
  
-   <span data-ttu-id="e92bf-120">未经授权的用户可能会访问网络共享位置或目录下的信息。</span><span class="sxs-lookup"><span data-stu-id="e92bf-120">Unauthorized users may access information on network shares or directories.</span></span> <span data-ttu-id="e92bf-121">您可以使用加强的任意访问控制列表 (DACL) 进行限制，仅将访问权限授予需要使用这些资源的帐户。</span><span class="sxs-lookup"><span data-stu-id="e92bf-121">You can use strong discretionary access control lists (DACLs) to limit access to the accounts that use the resources.</span></span>  
  
-   <span data-ttu-id="e92bf-122">运行 BizTalk 主机实例的计算机的 Windows 管理员有可能误操作，从而招致不同级别的攻击（例如信息泄露或拒绝服务）。</span><span class="sxs-lookup"><span data-stu-id="e92bf-122">The Windows administrator on a computer running a BizTalk Host instance can misbehave and carry out different levels of attacks (for example, information disclosure, or denial of service).</span></span> <span data-ttu-id="e92bf-123">不过，在大多数情况下，您都可以将这些攻击限制在攻击者已对其计算机造成危害的特定主机上。</span><span class="sxs-lookup"><span data-stu-id="e92bf-123">However, in most cases you can limit these attacks to the particular host whose computer the attacker compromised.</span></span>  
  
 <span data-ttu-id="e92bf-124">**拒绝服务**</span><span class="sxs-lookup"><span data-stu-id="e92bf-124">**Denial of service**</span></span>  
  
-   <span data-ttu-id="e92bf-125">恶意用户可能会向 BizTalk Server 发送大量的消息，从而阻止 BizTalk 接收有效的消息。</span><span class="sxs-lookup"><span data-stu-id="e92bf-125">A malicious user can send a large number of messages to BizTalk Server, which could prevent BizTalk from receiving valid messages.</span></span> <span data-ttu-id="e92bf-126">有关对此威胁的缓解技术的详细信息，请参阅[减少拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。</span><span class="sxs-lookup"><span data-stu-id="e92bf-126">For more information about mitigation techniques to this threat, see [Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md).</span></span>  
  
 <span data-ttu-id="e92bf-127">**特权提升**</span><span class="sxs-lookup"><span data-stu-id="e92bf-127">**Elevation of privileges**</span></span>  
  
-   <span data-ttu-id="e92bf-128">当在受信任环境中运行不受信任代码时，或是当恶意用户利用软件或配置缺陷时，通常会出现特权提升威胁。</span><span class="sxs-lookup"><span data-stu-id="e92bf-128">Elevation of privileges threats typically occur when code you do not trust runs in a trusted environment, or when a malicious user exploits a software or configuration flaw.</span></span> <span data-ttu-id="e92bf-129">您必须确保在环境中部署的程序集和其他组件是受信任的。</span><span class="sxs-lookup"><span data-stu-id="e92bf-129">You must ensure that you trust the assemblies and other components you deploy in your environment.</span></span> <span data-ttu-id="e92bf-130">若要最大程度地降低特权提升攻击的可能性，则不同帐户的权限不得重复，并要满足最低权限原则。此外，对于运行时服务和操作，应避免使用管理帐户。</span><span class="sxs-lookup"><span data-stu-id="e92bf-130">To minimize the possibility of an elevation of privileges attack, you should use non-overlapping, least permission accounts, and you should avoid the use of administrative accounts for run time services and operations.</span></span> <span data-ttu-id="e92bf-131">您还应最大程度地减少环境中运行的组件、应用程序和服务数。</span><span class="sxs-lookup"><span data-stu-id="e92bf-131">You should also minimize the number of components, applications, and services running in the environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92bf-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e92bf-132">See Also</span></span>  
 <span data-ttu-id="e92bf-133">[减少拒绝服务攻击](../core/mitigating-denial-of-service-attacks.md) </span><span class="sxs-lookup"><span data-stu-id="e92bf-133">[Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md) </span></span>  
 <span data-ttu-id="e92bf-134">[BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="e92bf-134">[Security Recommendations for a BizTalk Server Deployment](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span></span>  
 [<span data-ttu-id="e92bf-135">Planning for Security</span><span class="sxs-lookup"><span data-stu-id="e92bf-135">Planning for Security</span></span>](../core/planning-for-security.md)