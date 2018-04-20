---
title: 可以修改为提高网络性能的设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6aacc3-e697-4cc9-b937-73a2f54e733b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8557c8bbe8c0b1c785d6da8d87e8950d3779b8d0
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a><span data-ttu-id="ce5a4-102">可以修改为提高网络性能的设置</span><span class="sxs-lookup"><span data-stu-id="ce5a4-102">Settings that can be Modified to Improve Network Performance</span></span>
<span data-ttu-id="ce5a4-103">本主题提供建议的值的说明该影响网络性能。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-103">This topic provides a description of recommended values   that impact network performance.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ce5a4-104">在完成本指南中的性能测试期间它可以观察到，Windows Server 2008 显示默认情况下优化。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-104">During performance testing completed for this guide it was observed that Windows Server 2008 appears to be tuned by default.</span></span> <span data-ttu-id="ce5a4-105">应仅在系统上的效果的仔细的分析后完成修改注册表设置。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-105">Modification of  registry settings should only be done after a careful analysis of the effects on the system.</span></span>  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a><span data-ttu-id="ce5a4-106">调整 MaxUserPort 和 TcpTimedWaitDelay 设置</span><span class="sxs-lookup"><span data-stu-id="ce5a4-106">Adjust the MaxUserPort and TcpTimedWaitDelay settings</span></span>  
 <span data-ttu-id="ce5a4-107">**MaxUserPort**值控制在应用程序请求从系统的任何可用的用户端口时使用的最大端口号。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-107">The **MaxUserPort** value controls the maximum port number used when an application requests any available user port from the system.</span></span> <span data-ttu-id="ce5a4-108">通常情况下，生存期较短的端口是从分配的范围内 1025 到 65535 之间。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-108">Normally, short-lived ports are allocated in the range from 1025 through 65535.</span></span> <span data-ttu-id="ce5a4-109">端口范围现在真正是一组与起始点，并与终结点。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-109">The port range is now truly a range with a starting point and with an endpoint.</span></span> <span data-ttu-id="ce5a4-110">新的默认起始端口为 49152，而默认结束端口为 65535。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-110">The new default start port is 49152, and the default end port is 65535.</span></span> <span data-ttu-id="ce5a4-111">此范围是除了通过服务和应用程序使用的已知端口。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-111">This range is in addition to well-known ports that are used by services and by applications.</span></span> <span data-ttu-id="ce5a4-112">可以在每个服务器上修改的服务器使用的端口范围。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-112">The port range that is used by the servers can be modified on each server.</span></span> <span data-ttu-id="ce5a4-113">你可以按以下方式使用 netsh 命令中，调整此范围：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-113">You adjust this range by using the netsh command, as follows:</span></span>  
  
 <span data-ttu-id="ce5a4-114">**netsh int \<ipv4&#124;ipv6\>设置动态\<tcp&#124;udp\>启动 = 数字 num = 范围**</span><span class="sxs-lookup"><span data-stu-id="ce5a4-114">**netsh int \<ipv4&#124;ipv6\> set dynamicport \<tcp&#124;udp\> start=number num=range**</span></span>  
  
 <span data-ttu-id="ce5a4-115">此命令设置为 TCP 动态端口范围。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-115">This command sets the dynamic port range for TCP.</span></span> <span data-ttu-id="ce5a4-116">起始端口是**数**，和端口的总数是**范围**。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-116">The start port is **number**, and the total number of ports is **range**.</span></span> <span data-ttu-id="ce5a4-117">以下是示例命令： 你可以使用以下 netsh 命令来查看动态端口范围：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-117">The following are sample commands: You can view the dynamic port range by using the following netsh commands:</span></span>  
  
-   <span data-ttu-id="ce5a4-118">netsh int ipv4 显示动态 tcp。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-118">netsh int ipv4 show dynamicport tcp.</span></span> <span data-ttu-id="ce5a4-119">若要增加为 tcp v4 的最大允许值范围，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-119">To increase the range to the maximum allowed value for tcp v4, use the following command:</span></span>  
  
     <span data-ttu-id="ce5a4-120">**netsh int ipv4 设置动态 tcp 启动 = 1025 num = 64511**</span><span class="sxs-lookup"><span data-stu-id="ce5a4-120">**netsh int ipv4 set dynamicport tcp start=1025 num=64511**</span></span>  
  
-   <span data-ttu-id="ce5a4-121">netsh int ipv4 显示动态 udp</span><span class="sxs-lookup"><span data-stu-id="ce5a4-121">netsh int ipv4 show dynamicport udp</span></span>  
  
-   <span data-ttu-id="ce5a4-122">netsh int ipv6 show 动态 tcp</span><span class="sxs-lookup"><span data-stu-id="ce5a4-122">netsh int ipv6 show dynamicport tcp</span></span>  
  
-   <span data-ttu-id="ce5a4-123">netsh int ipv6 show 动态 udp</span><span class="sxs-lookup"><span data-stu-id="ce5a4-123">netsh int ipv6 show dynamicport udp</span></span>  
  
 <span data-ttu-id="ce5a4-124">**TcpTimedWaitDelay**值确定的连接在正在关闭时处于 TIME_WAIT 状态的时间长度。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-124">The **TcpTimedWaitDelay** value determines the length of time that a connection stays in the TIME_WAIT state when being closed.</span></span> <span data-ttu-id="ce5a4-125">TIME_WAIT 状态连接时，不能重用的套接字对。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-125">While a connection is in the TIME_WAIT state, the socket pair cannot be reused.</span></span> <span data-ttu-id="ce5a4-126">这是也称为 2MSL 状态，因为此值应该是两次在网络上的最大的段生存期。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-126">This is also known as the 2MSL state because the value should be twice the maximum segment lifetime on the network.</span></span> <span data-ttu-id="ce5a4-127">有关详细信息，请参阅[Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (超链接"http://go.microsoft.com/fwlink/?LinkId=113719" http://go.microsoft.com/fwlink/?LinkId=113719)。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-127">For more information, see [Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) ( HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=113719" http://go.microsoft.com/fwlink/?LinkId=113719).</span></span> <span data-ttu-id="ce5a4-128">若要调整 TcpTimedWaitDelay 设置，你必须修改注册表设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-128">To adjust the TcpTimedWaitDelay settings, you have to modify the registry settings as listed below:</span></span>  
  
###  
  
|||  
|-|-|  
|<span data-ttu-id="ce5a4-129">密钥：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-129">Key:</span></span>|<span data-ttu-id="ce5a4-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span><span class="sxs-lookup"><span data-stu-id="ce5a4-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span></span>|  
|<span data-ttu-id="ce5a4-131">值：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-131">Value:</span></span>|<span data-ttu-id="ce5a4-132">TcpTimedWaitDelay</span><span class="sxs-lookup"><span data-stu-id="ce5a4-132">TcpTimedWaitDelay</span></span>|  
|<span data-ttu-id="ce5a4-133">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-133">Data Type:</span></span>|<span data-ttu-id="ce5a4-134">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ce5a4-134">REG_DWORD</span></span>|  
|<span data-ttu-id="ce5a4-135">范围：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-135">Range:</span></span>|<span data-ttu-id="ce5a4-136">30-300 （十进制）</span><span class="sxs-lookup"><span data-stu-id="ce5a4-136">30-300 (decimal)</span></span>|  
|<span data-ttu-id="ce5a4-137">默认值：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-137">Default value:</span></span>|<span data-ttu-id="ce5a4-138">0x78 (120 十进制)</span><span class="sxs-lookup"><span data-stu-id="ce5a4-138">0x78 (120 decimal)</span></span>|  
|<span data-ttu-id="ce5a4-139">建议的值：</span><span class="sxs-lookup"><span data-stu-id="ce5a4-139">Recommended value:</span></span>|<span data-ttu-id="ce5a4-140">30</span><span class="sxs-lookup"><span data-stu-id="ce5a4-140">30</span></span>|  
|<span data-ttu-id="ce5a4-141">默认情况下存在值？</span><span class="sxs-lookup"><span data-stu-id="ce5a4-141">Value exists by default?</span></span>|<span data-ttu-id="ce5a4-142">**不**，需要添加。</span><span class="sxs-lookup"><span data-stu-id="ce5a4-142">**No**, needs to be added.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce5a4-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce5a4-143">See Also</span></span>  
 [<span data-ttu-id="ce5a4-144">优化网络性能的通用指南</span><span class="sxs-lookup"><span data-stu-id="ce5a4-144">General Guidelines for Improving Network Performance</span></span>](../technical-guides/general-guidelines-for-improving-network-performance.md)