---
title: 确定潜在的威胁 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43489c8cc0d70f4c4264778cf65672391e242eaa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382791"
---
# <a name="identifying-potential-threats"></a><span data-ttu-id="59b53-102">标识潜在威胁</span><span class="sxs-lookup"><span data-stu-id="59b53-102">Identifying Potential Threats</span></span>
<span data-ttu-id="59b53-103">可以使用 STRIDE 模型来识别潜在威胁的 BizTalk Server 部署。</span><span class="sxs-lookup"><span data-stu-id="59b53-103">You can use the STRIDE model to identify potential threats to your BizTalk Server deployment.</span></span> <span data-ttu-id="59b53-104">STRIDE 是派生自以下类别的首字母缩写：*S*poofing identity *T*篡改数据， *R*epudiation，*我*表示信息泄露*D*表示拒绝服务，和特权提升。</span><span class="sxs-lookup"><span data-stu-id="59b53-104">STRIDE is an acronym derived from the following categories: *S*poofing identity, *T*ampering with data, *R*epudiation, *I*nformation disclosure, *D*enial of service, and Elevation of privileges.</span></span> <span data-ttu-id="59b53-105">本部分包含潜在威胁的 BizTalk Server 环境，和机制来降低这些的示例。</span><span class="sxs-lookup"><span data-stu-id="59b53-105">This section contains examples of potential threats to a BizTalk Server environment, and mechanisms to mitigate them.</span></span>  
  
 <span data-ttu-id="59b53-106">**身份欺骗**</span><span class="sxs-lookup"><span data-stu-id="59b53-106">**Spoofing identity**</span></span>  
  
- <span data-ttu-id="59b53-107">如果将密码保存在绑定文件，并保存这些绑定文件时，未经授权的用户无法读取密码和使用它们来连接到 BizTalk 服务器，并可能造成损害。</span><span class="sxs-lookup"><span data-stu-id="59b53-107">If you save passwords in the binding files, and save these binding files, unauthorized users could read the passwords and use them to connect to the BizTalk Servers, and possibly cause harm.</span></span> <span data-ttu-id="59b53-108">不应将密码保存在绑定文件中，并应使用自由访问控制列表 (Dacl) 来限制对可能包含敏感数据的文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="59b53-108">You should not save passwords in binding files, and you should use discretionary access control lists (DACLs) to restrict access to files that may contain sensitive data.</span></span>  
  
  <span data-ttu-id="59b53-109">**篡改数据**</span><span class="sxs-lookup"><span data-stu-id="59b53-109">**Tampering with data**</span></span>  
  
- <span data-ttu-id="59b53-110">恶意用户可以截获到 BizTalk Server 中，来自合作伙伴的消息和修改消息的内容。</span><span class="sxs-lookup"><span data-stu-id="59b53-110">Malicious users can intercept messages from partners to BizTalk Server, and modify the content of the message.</span></span> <span data-ttu-id="59b53-111">可以使用数字签名以防止恶意用户篡改消息，尽管它们是在传输过程中。</span><span class="sxs-lookup"><span data-stu-id="59b53-111">You can use digital signatures to prevent malicious users from tampering with messages while they are in transit.</span></span>  
  
  <span data-ttu-id="59b53-112">**否认性**</span><span class="sxs-lookup"><span data-stu-id="59b53-112">**Repudiation**</span></span>  
  
- <span data-ttu-id="59b53-113">您需要跟踪的 BizTalk 发送和接收的消息。</span><span class="sxs-lookup"><span data-stu-id="59b53-113">You need to keep track of messages that BizTalk sends and receives.</span></span> <span data-ttu-id="59b53-114">可以使用数字签名，证明您发送的消息并，你的合作伙伴向你发送了一条消息。</span><span class="sxs-lookup"><span data-stu-id="59b53-114">You can use digital signatures to prove that you sent a message and that your partners sent you a message.</span></span>  
  
  <span data-ttu-id="59b53-115">**信息泄露**</span><span class="sxs-lookup"><span data-stu-id="59b53-115">**Information disclosure**</span></span>  
  
- <span data-ttu-id="59b53-116">恶意用户可以读取 BizTalk Server 和 Microsoft SQL Server™ 之间的明文通信。</span><span class="sxs-lookup"><span data-stu-id="59b53-116">Malicious users can read clear-text communication between BizTalk Server and Microsoft SQL Server™.</span></span> <span data-ttu-id="59b53-117">可以使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 来帮助保护服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="59b53-117">You can use Internet Protocol security (IPSec), or Secure Sockets Layer (SSL) to help secure the communication between servers.</span></span> <span data-ttu-id="59b53-118">可以使用防火墙来限制对每个服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="59b53-118">You can use firewalls to limit access to each server.</span></span> <span data-ttu-id="59b53-119">可以使用加密来帮助确保消息的隐私，而它是在传输过程中。</span><span class="sxs-lookup"><span data-stu-id="59b53-119">You can use encryption to help ensure the privacy of the message while it is in transit.</span></span>  
  
- <span data-ttu-id="59b53-120">未经授权的用户可以访问网络共享或目录的信息。</span><span class="sxs-lookup"><span data-stu-id="59b53-120">Unauthorized users may access information on network shares or directories.</span></span> <span data-ttu-id="59b53-121">可以使用加强的任意访问控制列表 (Dacl) 来限制帐户的访问权限的使用的资源。</span><span class="sxs-lookup"><span data-stu-id="59b53-121">You can use strong discretionary access control lists (DACLs) to limit access to the accounts that use the resources.</span></span>  
  
- <span data-ttu-id="59b53-122">运行 BizTalk 主机实例的计算机上的 Windows 管理员可以错误行为和不同级别的攻击 （例如，信息泄露或拒绝服务）。</span><span class="sxs-lookup"><span data-stu-id="59b53-122">The Windows administrator on a computer running a BizTalk Host instance can misbehave and carry out different levels of attacks (for example, information disclosure, or denial of service).</span></span> <span data-ttu-id="59b53-123">但是，在大多数情况下，您可以限制到特定主机的计算机攻击者攻击这些攻击。</span><span class="sxs-lookup"><span data-stu-id="59b53-123">However, in most cases you can limit these attacks to the particular host whose computer the attacker compromised.</span></span>  
  
  <span data-ttu-id="59b53-124">**拒绝服务**</span><span class="sxs-lookup"><span data-stu-id="59b53-124">**Denial of service**</span></span>  
  
- <span data-ttu-id="59b53-125">恶意用户可以将大量的消息发送到 BizTalk Server 中，这可能会阻止 BizTalk 接收有效的消息。</span><span class="sxs-lookup"><span data-stu-id="59b53-125">A malicious user can send a large number of messages to BizTalk Server, which could prevent BizTalk from receiving valid messages.</span></span> <span data-ttu-id="59b53-126">有关此类威胁的缓解措施的详细信息，请参阅[缓解拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。</span><span class="sxs-lookup"><span data-stu-id="59b53-126">For more information about mitigation techniques to this threat, see [Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md).</span></span>  
  
  <span data-ttu-id="59b53-127">**特权提升**</span><span class="sxs-lookup"><span data-stu-id="59b53-127">**Elevation of privileges**</span></span>  
  
- <span data-ttu-id="59b53-128">在受信任环境中，你不信任的代码运行时或当恶意用户利用软件或配置缺陷时，通常会发生特权提升威胁。</span><span class="sxs-lookup"><span data-stu-id="59b53-128">Elevation of privileges threats typically occur when code you do not trust runs in a trusted environment, or when a malicious user exploits a software or configuration flaw.</span></span> <span data-ttu-id="59b53-129">您必须确保您信任程序集和在环境中部署其他组件。</span><span class="sxs-lookup"><span data-stu-id="59b53-129">You must ensure that you trust the assemblies and other components you deploy in your environment.</span></span> <span data-ttu-id="59b53-130">若要提升权限攻击的可能性降到最低，应使用非重叠、 最低权限的帐户，并应避免使用管理帐户的运行的时服务和操作。</span><span class="sxs-lookup"><span data-stu-id="59b53-130">To minimize the possibility of an elevation of privileges attack, you should use non-overlapping, least permission accounts, and you should avoid the use of administrative accounts for run time services and operations.</span></span> <span data-ttu-id="59b53-131">您应尽量少组件、 应用程序，并在环境中运行的服务的数。</span><span class="sxs-lookup"><span data-stu-id="59b53-131">You should also minimize the number of components, applications, and services running in the environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b53-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="59b53-132">See Also</span></span>  
 <span data-ttu-id="59b53-133">[缓解拒绝服务攻击](../core/mitigating-denial-of-service-attacks.md) </span><span class="sxs-lookup"><span data-stu-id="59b53-133">[Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md) </span></span>  
 <span data-ttu-id="59b53-134">[BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="59b53-134">[Security Recommendations for a BizTalk Server Deployment](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span></span>  
 [<span data-ttu-id="59b53-135">规划安全性</span><span class="sxs-lookup"><span data-stu-id="59b53-135">Planning for Security</span></span>](../core/planning-for-security.md)