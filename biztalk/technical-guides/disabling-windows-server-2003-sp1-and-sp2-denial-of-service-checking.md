---
title: 禁用 Windows Server 2003 SP1 和 SP2 拒绝服务检查 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8822c1e4-d146-4361-b25a-7b81cd5cdd3b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8a4d25a694c74c9d5667995b4d70866fc021e3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305751"
---
# <a name="disabling-windows-server-2003-sp1-and-sp2-denial-of-service-checking"></a><span data-ttu-id="bf2fc-102">禁用 Windows Server 2003 SP1 和 SP2 拒绝服务检查</span><span class="sxs-lookup"><span data-stu-id="bf2fc-102">Disabling Windows Server 2003 SP1 and SP2 Denial of Service Checking</span></span>
> [!NOTE]  
>  <span data-ttu-id="bf2fc-103">本主题是仅适用于 Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="bf2fc-104">应禁用服务检查，Windows Server 2003 Service Pack 1 和 Service Pack 2 的拒绝。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-104">You should disable the Windows Server 2003 Service Pack 1 and Service Pack 2 denial of service checking.</span></span> <span data-ttu-id="bf2fc-105">这是因为在某些高负载情况下，Windows Server 2003 SP1 和 SP2 拒绝服务检查可能会错误地标识有效的 TCP/IP 连接为拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-105">This is because under certain high-load scenarios, Windows Server 2003 SP1 and SP2 denial of service checking may incorrectly identify valid TCP/IP connections as a denial of service attack.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf2fc-106">当你确信您将不会受到实际拒绝服务攻击时，应禁用此功能仅在 intranet 方案中。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-106">You should disable this feature only in an intranet scenario when you are sure you will not suffer from actual denial of service attacks.</span></span>  
  
## <a name="how-denial-of-service-can-affect-tcpip-connections"></a><span data-ttu-id="bf2fc-107">如何拒绝服务可能会影响的 TCP/IP 连接</span><span class="sxs-lookup"><span data-stu-id="bf2fc-107">How Denial of Service Can Affect TCP/IP Connections</span></span>  
 <span data-ttu-id="bf2fc-108">Windows Server 2003 SP1 和 SP2 实施一项安全功能，从而减少到服务器的并发 TCP/IP 连接队列的大小。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-108">Windows Server 2003 SP1 and SP2 implement a security feature that reduces the size of the queue for concurrent TCP/IP connections to the server.</span></span> <span data-ttu-id="bf2fc-109">此功能有助于防止拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-109">This feature helps prevent denial of service attacks.</span></span> <span data-ttu-id="bf2fc-110">在高负载情况下在 Windows Server 2003 SP1 或更高版本的 TCP/IP 协议可能错误地标识为拒绝服务攻击的有效的 TCP/IP 连接。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-110">Under heavy load conditions, the TCP/IP protocol in Windows Server 2003 SP1 or later may incorrectly identify valid TCP/IP connections as a denial of service attack.</span></span> <span data-ttu-id="bf2fc-111">这可能会发生时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]负载过大。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-111">This may occur when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is under heavy load.</span></span>  
  
## <a name="modifying-the-registry-entry"></a><span data-ttu-id="bf2fc-112">修改注册表项</span><span class="sxs-lookup"><span data-stu-id="bf2fc-112">Modifying the Registry Entry</span></span>  
 <span data-ttu-id="bf2fc-113">有关详细信息，请参阅 Microsoft 知识库文章 899599， ["BizTalk Server 主机实例失败，并且当基于 BizTalk Server 的服务器处理大量文档时，常规网络错误写入到应用程序日志"](http://go.microsoft.com/fwlink/?LinkId=158860) (<http://go.microsoft.com/fwlink/?LinkId=158860>).</span><span class="sxs-lookup"><span data-stu-id="bf2fc-113">For more information, see Microsoft Knowledge Base article 899599, ["A BizTalk Server Host instance fails, and a 'General Network' error is written to the Application log when the BizTalk Server-based server processes a high volume of documents"](http://go.microsoft.com/fwlink/?LinkId=158860) (<http://go.microsoft.com/fwlink/?LinkId=158860>).</span></span> <span data-ttu-id="bf2fc-114">按照这篇文章中的说明来创建**SynAttackProtect**运行该主机的 SQL Server 的计算机上的注册表项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和运行的任何计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行 Windows Server2003 SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-114">Follow the instructions in this article to create the **SynAttackProtect** registry entry on computers running SQL Server that host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and on any computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that are running Windows Server 2003 SP1 or later.</span></span>  
  
## <a name="tuning-registry-settings-that-govern-the-level-of-denial-of-service-attack-protection"></a><span data-ttu-id="bf2fc-115">优化管理的拒绝服务攻击保护级别的注册表设置</span><span class="sxs-lookup"><span data-stu-id="bf2fc-115">Tuning Registry Settings that Govern the Level of Denial of Service Attack Protection</span></span>  
 <span data-ttu-id="bf2fc-116">在某些情况下您可能想要维护拒绝服务保护但减少的迫切程度应用拒绝服务的功能。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-116">In certain scenarios you may want to maintain denial of service protection but reduce how aggressively the denial of service functionality is applied.</span></span> <span data-ttu-id="bf2fc-117">就可以通过执行以下步骤优化拒绝服务保护功能的默认行为：</span><span class="sxs-lookup"><span data-stu-id="bf2fc-117">It is possible to tune the default behavior of the denial of service protection feature by following these steps:</span></span>  
  
1.  <span data-ttu-id="bf2fc-118">絋粄**SynAttackProtect**注册表项设置为的 REG_DWORD 值**1**中所述[ http://go.microsoft.com/fwlink/?LinkId=111477 ](http://go.microsoft.com/fwlink/?LinkId=111477)。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-118">Ensure that the **SynAttackProtect** registry entry is set to a REG_DWORD value of **1** as described at [http://go.microsoft.com/fwlink/?LinkId=111477](http://go.microsoft.com/fwlink/?LinkId=111477).</span></span>  
  
2.  <span data-ttu-id="bf2fc-119">配置**TcpMaxHalfOpen**注册表项中所述[ http://go.microsoft.com/fwlink/?LinkId=111478 ](http://go.microsoft.com/fwlink/?LinkId=111478)。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-119">Configure the **TcpMaxHalfOpen** registry entry as described at [http://go.microsoft.com/fwlink/?LinkId=111478](http://go.microsoft.com/fwlink/?LinkId=111478).</span></span>  
  
3.  <span data-ttu-id="bf2fc-120">配置**TcpMaxHalfOpenRetried**注册表项中所述[ http://go.microsoft.com/fwlink/?LinkId=111479 ](http://go.microsoft.com/fwlink/?LinkId=111479)。</span><span class="sxs-lookup"><span data-stu-id="bf2fc-120">Configure the **TcpMaxHalfOpenRetried** registry entry as described at [http://go.microsoft.com/fwlink/?LinkId=111479](http://go.microsoft.com/fwlink/?LinkId=111479).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf2fc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf2fc-121">See Also</span></span>  
 [<span data-ttu-id="bf2fc-122">操作准备就绪清单</span><span class="sxs-lookup"><span data-stu-id="bf2fc-122">Operational Readiness Checklists</span></span>](../technical-guides/operational-readiness-checklists.md)