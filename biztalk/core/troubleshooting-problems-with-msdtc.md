---
title: "与 MSDTC 问题疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f39cde52-da8f-4cc1-bdc5-e4b828891a79
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c244ec27cd3e584f7fb22a34effeaf0033c3e78a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-problems-with-msdtc"></a><span data-ttu-id="73dcc-102">MSDTC 疑难解答</span><span class="sxs-lookup"><span data-stu-id="73dcc-102">Troubleshooting Problems with MSDTC</span></span>
<span data-ttu-id="73dcc-103">大多数 BizTalk Server 运行时操作都需要 Microsoft 分布式事务处理协调器 (MSDTC) 支持，以确保操作事务性一致。</span><span class="sxs-lookup"><span data-stu-id="73dcc-103">Most BizTalk Server runtime operations require Microsoft Distributed Transaction Coordinator (MSDTC) support to ensure that the operations are transactionally consistent.</span></span> <span data-ttu-id="73dcc-104">如果没有 MSDTC 事务支持，则相关联的 BizTalk Server 运行时操作将无法进行。</span><span class="sxs-lookup"><span data-stu-id="73dcc-104">If MSDTC transaction support is not available, then the associated BizTalk Server runtime operations cannot proceed.</span></span> <span data-ttu-id="73dcc-105">未正确配置 MSDTC 事务支持时通常会影响的 BizTalk 组件包括（但不限于）单一登录服务、BizTalk 主机实例以及 BizTalk Server 所连接的任何 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="73dcc-105">The components of BizTalk that are commonly affected when MSDTC transaction support is not configured correctly include (but are not limited to) the Single Sign-On Service, BizTalk host instances, and any SQL Server instances that are connected to by BizTalk Server.</span></span> <span data-ttu-id="73dcc-106">本部分包含的信息描述了与 MSDTC 相关的错误和步骤，遵循这些步骤可帮助你诊断并解决 MSDTC 存在的问题。</span><span class="sxs-lookup"><span data-stu-id="73dcc-106">This section contains information that describes MSDTC related errors and steps that can be followed to diagnose and resolve problems with MSDTC.</span></span>  
  
## <a name="errors-that-can-occur-if-msdtc-transaction-support-is-not-configured-correctly"></a><span data-ttu-id="73dcc-107">未正确配置 MSDTC 事务支持时会出现的错误</span><span class="sxs-lookup"><span data-stu-id="73dcc-107">Errors that can occur if MSDTC transaction support is not configured correctly</span></span>  
 <span data-ttu-id="73dcc-108">如果未在 BizTalk 环境中的计算机上正确配置 MSDTC 事务支持，则 BizTalk Server 上可能出现如下错误：</span><span class="sxs-lookup"><span data-stu-id="73dcc-108">Errors similar to the following may occur on BizTalk Server when MSDTC transaction support is not configured correctly on the computers in a BizTalk environment:</span></span>  
  
-   <span data-ttu-id="73dcc-109">“由于 Microsoft 分布式事务处理协调器出现问题，因此无法连接到配置数据库。</span><span class="sxs-lookup"><span data-stu-id="73dcc-109">"A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database.</span></span> <span data-ttu-id="73dcc-110">该事务管理器已经禁止了它对远程/网络事务的支持"。</span><span class="sxs-lookup"><span data-stu-id="73dcc-110">The transaction manager has disabled its support for remote/network transactions".</span></span>  
  
-   <span data-ttu-id="73dcc-111">“由于 Microsoft 分布式事务处理协调器出现问题，因此无法连接到配置数据库。</span><span class="sxs-lookup"><span data-stu-id="73dcc-111">"A Microsoft Distributed Transaction Coordinator problem prevented connection to the Configuration database.</span></span> <span data-ttu-id="73dcc-112">此事务已明地或暗地被确认或终止”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-112">The transaction has already been implicitly or explicitly committed or aborted".</span></span>  
  
-   <span data-ttu-id="73dcc-113">“错误代码：0x8004d00a，无法在指定的事务处理协调器中登记新事务”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-113">"Error Code: 0x8004d00a, New transaction cannot enlist in the specified transaction coordinator".</span></span>  
  
-   <span data-ttu-id="73dcc-114">“无法从配置存储中检索接收位置‘MySample ReceiveLocation’的传输类型数据。</span><span class="sxs-lookup"><span data-stu-id="73dcc-114">"Could not retrieve transport type data for Receive Location 'MySample ReceiveLocation' from config store.</span></span> <span data-ttu-id="73dcc-115">主 SSO Server‘MyServer’发生故障。</span><span class="sxs-lookup"><span data-stu-id="73dcc-115">Primary SSO Server 'MyServer' failed.</span></span> <span data-ttu-id="73dcc-116">RPC 服务器不可用”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-116">The RPC server is unavailable".</span></span>  
  
-   <span data-ttu-id="73dcc-117">“错误代码：0x8004d025,，合作伙伴事务管理器已禁用对远程/网络事务的支持”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-117">"Error Code: 0x8004d025, The partner transaction manager has disabled its support for remote/network transactions".</span></span>  
  
-   <span data-ttu-id="73dcc-118">“错误代码：0xc0002a24，无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="73dcc-118">"Error Code: 0xc0002a24, Could not import a DTC transaction.</span></span> <span data-ttu-id="73dcc-119">请检查 MSDTC 是否正确配置以用于远程操作”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-119">Please check that MSDTC is configured correctly for remote operation".</span></span>  
  
-   <span data-ttu-id="73dcc-120">“0x8004d01c</span><span class="sxs-lookup"><span data-stu-id="73dcc-120">"0x8004d01c</span></span>  
  
     <span data-ttu-id="73dcc-121">[0x1705] 创建内部工作项时发生失败。</span><span class="sxs-lookup"><span data-stu-id="73dcc-121">[0x1705] There was a failure creating the internal work item.</span></span>  
  
     <span data-ttu-id="73dcc-122">确保 SQL Server 正在运行。”</span><span class="sxs-lookup"><span data-stu-id="73dcc-122">Make sure that SQL Server is running."</span></span>  
  
 <span data-ttu-id="73dcc-123">要解决 MSDTC 配置错误，请遵循以下步骤。</span><span class="sxs-lookup"><span data-stu-id="73dcc-123">To resolve MSDTC configuration errors, follow the steps below.</span></span>  
  
## <a name="ensure-netbios-name-resolution-between-the-biztalk-server-and-remote-servers-is-successful"></a><span data-ttu-id="73dcc-124">确保 BizTalk Server 与远程服务器之间的 NetBIOS 名称解析成功</span><span class="sxs-lookup"><span data-stu-id="73dcc-124">Ensure NetBIOS name resolution between the BizTalk Server and remote servers is successful</span></span>  
 <span data-ttu-id="73dcc-125">要在计算机之间成功完成 MSDTC 事务，客户端计算机和服务器计算机都必须能够将对方的 NetBIOS 名称解析为正确的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="73dcc-125">Successful MSDTC transactions between computers require that the client computer is able to resolve the NetBIOS name of the server computer to the correct IP address and the server computer is able to resolve the NetBIOS name of the client computer to the correct IP address.</span></span> <span data-ttu-id="73dcc-126">要检查 NetBIOS 名称解析是否在两个方向上（客户端到服务器和服务器到客户端）都工作正常，请按以下步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="73dcc-126">To verify that NetBIOS name resolution works in both directions (client to server and server to client) follow these steps:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73dcc-127">NetBIOS 名称还常称为 **网络** 名称。</span><span class="sxs-lookup"><span data-stu-id="73dcc-127">The NetBIOS name is also commonly referred to as the **Network** name.</span></span>  
  
1.  <span data-ttu-id="73dcc-128">确定每台计算机的 NetBIOS 名称：</span><span class="sxs-lookup"><span data-stu-id="73dcc-128">Determine the NetBIOS name of each computer:</span></span>  
  
    1.  <span data-ttu-id="73dcc-129">右键单击“我的电脑”  以显示“系统属性”  对话框，然后单击“计算机名”  选项卡，查看分配给该计算机的“计算机全名”  。</span><span class="sxs-lookup"><span data-stu-id="73dcc-129">Right-click **My Computer** to display the **System Properties** dialog and click the **Computer Name** tab to view the **Full computer name** assigned to the computer.</span></span>  
  
    2.  <span data-ttu-id="73dcc-130">NetBIOS 名称是指定为 **完整计算机名称** 的名称的第一部分，例如，如果 **完整计算机名称** 为 myserver.company.domain.com，则计算机的 NetBIOS 名称为 **myserver**。</span><span class="sxs-lookup"><span data-stu-id="73dcc-130">The NetBIOS name is the first portion of the name designated as the **Full computer name** so for example if the **Full computer name** is listed as myserver.company.domain.com, then the NetBIOS name of the computer is **myserver**.</span></span>  
  
2.  <span data-ttu-id="73dcc-131">确定与每台计算机相关联的 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="73dcc-131">Determine the IP Address or addresses that are associated with each computer:</span></span>  
  
    1.  <span data-ttu-id="73dcc-132">在客户端计算机上启动命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="73dcc-132">Launch a command prompt on the client computer, type the following command, and then press ENTER:</span></span>  
  
        ```  
        ipconfig /all  
        ```  
  
    2.  <span data-ttu-id="73dcc-133">命令提示符窗口中即会列出与客户端计算机相关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="73dcc-133">The IP address or addresses associated with the client computer are listed in the command prompt window.</span></span>  
  
    3.  <span data-ttu-id="73dcc-134">在服务器计算机上启动命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="73dcc-134">Launch a command prompt on the server computer, type the following command, and then press ENTER:</span></span>  
  
        ```  
        ipconfig /all  
        ```  
  
    4.  <span data-ttu-id="73dcc-135">命令提示符窗口中即会列出与服务器计算机相关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="73dcc-135">The IP address or addresses associated with the server computer are listed in the command prompt window.</span></span>  
  
3.  <span data-ttu-id="73dcc-136">检查每台计算机的 NetBIOS 名称是否解析为与该计算机相关联的 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="73dcc-136">Verify that the NetBIOS name of each computer is resolved to one of the IP addresses associated with the computer:</span></span>  
  
    1.  <span data-ttu-id="73dcc-137">在客户端计算机上启动命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="73dcc-137">Launch a command prompt on the client computer, type the following command, and then press ENTER:</span></span>  
  
        ```  
        ping <NetBIOS name of server computer>  
        ```  
  
         <span data-ttu-id="73dcc-138">ping 命令的结果应该返回与服务器计算机相关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="73dcc-138">The results of the ping command should return an IP address associated with the server computer.</span></span>  
  
    2.  <span data-ttu-id="73dcc-139">在服务器计算机上启动命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="73dcc-139">Launch a command prompt on the server computer, type the following command, and then press ENTER:</span></span>  
  
        ```  
        ping <NetBIOS name of client computer>  
        ```  
  
         <span data-ttu-id="73dcc-140">ping 命令的结果应该返回与客户端计算机相关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="73dcc-140">The results of the ping command should return an IP address associated with the client computer.</span></span>  
  
4.  <span data-ttu-id="73dcc-141">验证每台计算机上与 NetBIOS 名称相关联的 IP 地址反向名称查找解析为正确的计算机名。</span><span class="sxs-lookup"><span data-stu-id="73dcc-141">Verify that reverse name lookup of the IP address associated with the NetBIOS name on each computer resolves to the correct computer name.</span></span>  
  
    1.  <span data-ttu-id="73dcc-142">在客户端计算机上启动命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="73dcc-142">Launch a command prompt on the client computer, type the following command, and then press ENTER:</span></span>  
  
        ```  
        ping -a <IP Address associated with client computer NetBIOS name>  
        ```  
  
         <span data-ttu-id="73dcc-143">ping 命令的结果应该返回一个 NetBIOS 名称或与步骤 3a 中使用的 NetBIOS 名称相对应的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="73dcc-143">The results of the ping command should return a NetBIOS name or fully qualified domain name that corresponds to the NetBIOS name that was used in step 3a.</span></span> <span data-ttu-id="73dcc-144">如果返回的名称不与步骤 3a 中使用的 NetBIOS 名称相匹配或对应，则 IP 地址反向查找将失败，这会导致 MSDTC 事务失败。</span><span class="sxs-lookup"><span data-stu-id="73dcc-144">If the name returned does not match or correspond to the NetBIOS name used in step 3a then IP address reverse lookup will fail which can cause MSDTC transactions to fail.</span></span>  
  
    2.  <span data-ttu-id="73dcc-145">在服务器计算机上启动命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="73dcc-145">Launch a command prompt on the server computer, type the following command, and then press ENTER:</span></span>  
  
        ```  
        ping -a <IP Address associated with server computer NetBIOS name>  
        ```  
  
         <span data-ttu-id="73dcc-146">ping 命令的结果应该返回一个 NetBIOS 名称或与步骤 3b 中使用的 NetBIOS 名称相对应的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="73dcc-146">The results of the ping command should return a NetBIOS name or fully qualified domain name that corresponds to the NetBIOS name that was used in step 3b.</span></span> <span data-ttu-id="73dcc-147">如果返回的名称不与步骤 3b 中使用的 NetBIOS 名称相匹配或对应，则 IP 地址反向查找将失败，这会导致 MSDTC 事务失败。</span><span class="sxs-lookup"><span data-stu-id="73dcc-147">If the name returned does not match or correspond to the NetBIOS name used in step 3b then IP address reverse lookup will fail which can cause MSDTC transactions to fail.</span></span>  
  
 <span data-ttu-id="73dcc-148">如果 NetBIOS 名称解析在任何一个方向上不成功，或者反向名称查找失败，请在 DNS 服务器、NetBIOS 名称服务器、HOSTS 文件或 LMHOSTS 文件中添加适当的条目以纠正问题。</span><span class="sxs-lookup"><span data-stu-id="73dcc-148">If NetBIOS name resolution is not successful in either direction or if reverse name lookup fails then make the appropriate entries in the DNS server, NetBIOS name server, HOSTS file, or LMHOSTS file to correct the problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73dcc-149">计算机使用的名称解析方法随计算机的 NetBIOS 节点类型不同而异。</span><span class="sxs-lookup"><span data-stu-id="73dcc-149">The method of name resolution used by the computer varies depending on the NetBIOS node type of the computer.</span></span> <span data-ttu-id="73dcc-150">有关 NetBIOS 节点类型的详细信息，请参阅 [NetBIOS 名称解析](http://go.microsoft.com/fwlink/?LinkId=201638)。</span><span class="sxs-lookup"><span data-stu-id="73dcc-150">For more information about NetBIOS node types, see [NetBIOS Name Resolution](http://go.microsoft.com/fwlink/?LinkId=201638).</span></span>  
  
## <a name="ensure-that-a-firewall-between-the-biztalk-server-and-remote-servers-is-not-blocking-ports-required-for-rpc-dynamic-port-allocation"></a><span data-ttu-id="73dcc-151">确保 BizTalk Server 与远程服务器之间的防火墙没有阻塞 RPC 动态端口分配所需要的端口</span><span class="sxs-lookup"><span data-stu-id="73dcc-151">Ensure that a firewall between the BizTalk Server and remote servers is not blocking ports required for RPC dynamic port allocation</span></span>  
 <span data-ttu-id="73dcc-152">通过网络实现的 MSDTC 功能取决于通过网络实现的 RPC 功能。</span><span class="sxs-lookup"><span data-stu-id="73dcc-152">MSDTC functionality over the network depends upon RPC functionality over the network.</span></span> <span data-ttu-id="73dcc-153">通过防火墙使用 RPC 功能需要打开特定的端口，以满足 RPC 动态端口的分配要求。</span><span class="sxs-lookup"><span data-stu-id="73dcc-153">RPC functionality through a firewall requires that specific ports are open to accommodate RPC dynamic port allocation.</span></span> <span data-ttu-id="73dcc-154">如果在 BizTalk Server 与远程服务器之间有防火墙，则请按照 [如何配置与防火墙一起使用的 RPC 动态端口分配](http://go.microsoft.com/fwlink/?LinkId=66831) 中的步骤进行操作，以满足 RPC 动态端口分配的要求。</span><span class="sxs-lookup"><span data-stu-id="73dcc-154">If a firewall is in place between the BizTalk Server and remote servers, follow the steps in [How to configure RPC dynamic port allocation to work with firewalls](http://go.microsoft.com/fwlink/?LinkId=66831) to accommodate RPC dynamic port allocation.</span></span>  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options"></a><span data-ttu-id="73dcc-155">设置相应的 MSDTC 安全配置选项</span><span class="sxs-lookup"><span data-stu-id="73dcc-155">Set the appropriate MSDTC Security Configuration options</span></span>  
 <span data-ttu-id="73dcc-156">Windows 提供了用于管理如何通过网络访问 MSDTC 的安全增强功能。</span><span class="sxs-lookup"><span data-stu-id="73dcc-156">Windows provides security enhancements that govern how MSDTC is accessed over a network.</span></span> <span data-ttu-id="73dcc-157">通过修改 MSDTC 安全设置，你可以控制 MSDTC 在网络中如何与远程计算机通信。</span><span class="sxs-lookup"><span data-stu-id="73dcc-157">By modifying the MSDTC security settings, you control how MSDTC communicates with remote computers over the network.</span></span> <span data-ttu-id="73dcc-158">此表列出了配置 MSDTC 安全配置时可用选项的建议值：</span><span class="sxs-lookup"><span data-stu-id="73dcc-158">This table lists the recommended values for the options that are available when configuring MSDTC security settings:</span></span>  
  
|<span data-ttu-id="73dcc-159">配置选项</span><span class="sxs-lookup"><span data-stu-id="73dcc-159">Configuration Option</span></span>|<span data-ttu-id="73dcc-160">默认值</span><span class="sxs-lookup"><span data-stu-id="73dcc-160">Default Value</span></span>|<span data-ttu-id="73dcc-161">推荐值</span><span class="sxs-lookup"><span data-stu-id="73dcc-161">Recommended Value</span></span>|  
|--------------------------|-------------------|-----------------------|  
|<span data-ttu-id="73dcc-162">网络 DTC 访问</span><span class="sxs-lookup"><span data-stu-id="73dcc-162">Network DTC Access</span></span>|<span data-ttu-id="73dcc-163">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-163">Disabled</span></span>|<span data-ttu-id="73dcc-164">已启用</span><span class="sxs-lookup"><span data-stu-id="73dcc-164">Enabled</span></span>|  
|<span data-ttu-id="73dcc-165">**客户端和管理**</span><span class="sxs-lookup"><span data-stu-id="73dcc-165">**Client and Administration**</span></span>|||  
|<span data-ttu-id="73dcc-166">允许远程客户端</span><span class="sxs-lookup"><span data-stu-id="73dcc-166">Allow Remote Clients</span></span>|<span data-ttu-id="73dcc-167">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-167">Disabled</span></span>|<span data-ttu-id="73dcc-168">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-168">Disabled</span></span>|  
|<span data-ttu-id="73dcc-169">允许远程管理</span><span class="sxs-lookup"><span data-stu-id="73dcc-169">Allow Remote Administration</span></span>|<span data-ttu-id="73dcc-170">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-170">Disabled</span></span>|<span data-ttu-id="73dcc-171">禁用</span><span class="sxs-lookup"><span data-stu-id="73dcc-171">Disabled</span></span>|  
|<span data-ttu-id="73dcc-172">**事务管理器通信**</span><span class="sxs-lookup"><span data-stu-id="73dcc-172">**Transaction Manager Communication**</span></span>|||  
|<span data-ttu-id="73dcc-173">允许入站</span><span class="sxs-lookup"><span data-stu-id="73dcc-173">Allow Inbound</span></span>|<span data-ttu-id="73dcc-174">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-174">Disabled</span></span>|<span data-ttu-id="73dcc-175">已启用</span><span class="sxs-lookup"><span data-stu-id="73dcc-175">Enabled</span></span>|  
|<span data-ttu-id="73dcc-176">允许出站</span><span class="sxs-lookup"><span data-stu-id="73dcc-176">Allow Outbound</span></span>|<span data-ttu-id="73dcc-177">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-177">Disabled</span></span>|<span data-ttu-id="73dcc-178">已启用</span><span class="sxs-lookup"><span data-stu-id="73dcc-178">Enabled</span></span>|  
|<span data-ttu-id="73dcc-179">要求进行相互身份验证</span><span class="sxs-lookup"><span data-stu-id="73dcc-179">Mutual Authentication Required</span></span>|<span data-ttu-id="73dcc-180">已启用</span><span class="sxs-lookup"><span data-stu-id="73dcc-180">Enabled</span></span>|<span data-ttu-id="73dcc-181">如果所有远程计算机都运行的是 Windows Server 2003 SP1 或 Windows XP SP2 或更高版本，并且都配置有“要求相互身份验证”，则为“已启用”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-181">Enabled if all remote machines are running Windows Server 2003 SP1 or Windows XP SP2 or higher, and are configured with “Mutual Authentication Required”.</span></span>|  
|<span data-ttu-id="73dcc-182">要求对呼叫方进行身份验证</span><span class="sxs-lookup"><span data-stu-id="73dcc-182">Incoming Caller Authentication Required</span></span>|<span data-ttu-id="73dcc-183">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-183">Disabled</span></span>|<span data-ttu-id="73dcc-184">如果在群集上运行 MSDTC，则为“已启用”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-184">Enabled if running MSDTC on cluster.</span></span>|  
|<span data-ttu-id="73dcc-185">不要求进行身份验证</span><span class="sxs-lookup"><span data-stu-id="73dcc-185">No Authentication Required</span></span>|<span data-ttu-id="73dcc-186">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-186">Disabled</span></span>|<span data-ttu-id="73dcc-187">在远程计算机为 Windows Server 2003 SP1 之前的版本或 Windows XP SP2 之前的版本时启用。</span><span class="sxs-lookup"><span data-stu-id="73dcc-187">Enabled if remote machines are pre-Windows Server 2003 SP1 or pre- Windows XP SP2.</span></span>|  
|<span data-ttu-id="73dcc-188">启用 TIP</span><span class="sxs-lookup"><span data-stu-id="73dcc-188">Enable TIP</span></span>|<span data-ttu-id="73dcc-189">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-189">Disabled</span></span>|<span data-ttu-id="73dcc-190">如果运行 BAM 门户，则为“已启用”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-190">Enabled if running the BAM Portal.</span></span>|  
|<span data-ttu-id="73dcc-191">启用 XA 事务</span><span class="sxs-lookup"><span data-stu-id="73dcc-191">Enable XA Transactions</span></span>|<span data-ttu-id="73dcc-192">Disabled</span><span class="sxs-lookup"><span data-stu-id="73dcc-192">Disabled</span></span>|<span data-ttu-id="73dcc-193">如果与基于 XA 的事务系统进行通信（例如，使用 MQSeries 适配器与 IBM WebSphere MQ 通信），则为“已启用”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-193">Enabled if communicating with an XA based transactional system such as when communicating with IBM WebSphere MQ using the MQSeries adapter.</span></span>|  
  
 <span data-ttu-id="73dcc-194">应用这些更改后，MSDTC 服务将重新启动。</span><span class="sxs-lookup"><span data-stu-id="73dcc-194">After applying these changes, the MSDTC service will be restarted.</span></span>  
  
 <span data-ttu-id="73dcc-195">要访问 MSDTC 安全配置选项，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="73dcc-195">To access the MSDTC security configuration options follow these steps:</span></span>  
  
1.  <span data-ttu-id="73dcc-196">依次单击 **“开始”**和 **“运行”**，再键入 **dcomcnfg** 以启动 **“组件服务”**管理控制台。</span><span class="sxs-lookup"><span data-stu-id="73dcc-196">Click **Start**, click **Run**, and type **dcomcnfg** to launch the **Component Services**Management console.</span></span>  
  
2.  <span data-ttu-id="73dcc-197">单击以展开“组件服务”  ，然后单击以展开“计算机” 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-197">Click to expand **Component Services** and click to expand **Computers**.</span></span>  
  
3.  <span data-ttu-id="73dcc-198">依次单击以展开“我的电脑” 、“分布式事务协调器” ，右键单击“本地 DTC” ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-198">Click to expand **My Computer**, click to expand **Distributed Transaction Coordinator**, right-click **Local DTC**, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="73dcc-199">单击“本地 DTC 属性”  对话框的“安全”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="73dcc-199">Click the **Security** tab of the **Local DTC Properties** dialog.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73dcc-200">根据所做的更改，可能需要重新启动计算机以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="73dcc-200">Depending on the changes that were made, you may need to reboot the computer to enact the changes.</span></span> <span data-ttu-id="73dcc-201">如果在应用更改并重新启动 MSDTC 服务后仍然遇到问题，请重新启动在其中进行了更改的计算机，以确保更改生效。</span><span class="sxs-lookup"><span data-stu-id="73dcc-201">If you are still encountering problems after applying changes and restarting the MSDTC service, reboot the computer on which the changes were made to ensure that the changes take effect.</span></span>  
  
 <span data-ttu-id="73dcc-202">如果启用了“要求相互身份验证”  或“要求对呼叫方进行验证”  配置选项，则必须为客户端计算机帐户授予“从网络访问此计算机”  用户权限。</span><span class="sxs-lookup"><span data-stu-id="73dcc-202">If either the **Mutual Authentication Required** or the **Incoming Caller Authentication Required** configuration options are enabled then the client(s) computer account must be granted the **Access this computer from the network** user right.</span></span> <span data-ttu-id="73dcc-203">如果没有为客户端计算机的计算机帐户授予“从网络访问此计算机”  用户权限，或者该帐户包括在“拒绝从网络访问这台计算机”  用户权限中，则该客户端与服务器计算机之间的 DTC 通信将失败。</span><span class="sxs-lookup"><span data-stu-id="73dcc-203">If the computer account for a client computer is not granted the **Access this computer from the network** user right, or is included in the **Deny access to this computer from the network** user right, then DTC communication between the client and server computer will fail.</span></span>  
  
 <span data-ttu-id="73dcc-204">默认设置为向 Everyone 组授予“从网络访问此计算机”  用户权限。</span><span class="sxs-lookup"><span data-stu-id="73dcc-204">The default setting is to grant the Everyone group the **Access this computer from the network** user right.</span></span> <span data-ttu-id="73dcc-205">因此，除非修改了默认设置，否则无需更改此用户权限。</span><span class="sxs-lookup"><span data-stu-id="73dcc-205">Therefore this user right will not need to be changed unless the default setting has been modified.</span></span> <span data-ttu-id="73dcc-206">如果启用了“不要求进行验证”  配置选项，则“从网络访问此计算机”  用户权限不会应用于客户端计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="73dcc-206">If the **No Authentication Required** configuration option is enabled then the **Access this computer from the network** user right does not apply to the client(s) computer account.</span></span>  
  
 <span data-ttu-id="73dcc-207">要更改授予了“从网络访问此计算机”用户权限的用户或组，请按以下步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="73dcc-207">To change the users or groups that are granted the "Access this computer from the network" user right, follow these steps:</span></span>  
  
1.  <span data-ttu-id="73dcc-208">依次单击 **“开始”**和 **“运行”**，键入 **Gpedit.msc**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="73dcc-208">Click **Start**, click **Run**, type **Gpedit.msc**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="73dcc-209">展开“本地计算机策略”列表中的以下项：</span><span class="sxs-lookup"><span data-stu-id="73dcc-209">Expand the following items in the Local Computer Policy list:</span></span>  
  
    -   <span data-ttu-id="73dcc-210">计算机配置</span><span class="sxs-lookup"><span data-stu-id="73dcc-210">Computer Configuration</span></span>  
  
    -   <span data-ttu-id="73dcc-211">Windows Settings</span><span class="sxs-lookup"><span data-stu-id="73dcc-211">Windows Settings</span></span>  
  
    -   <span data-ttu-id="73dcc-212">安全设置</span><span class="sxs-lookup"><span data-stu-id="73dcc-212">Security Settings</span></span>  
  
    -   <span data-ttu-id="73dcc-213">本地策略</span><span class="sxs-lookup"><span data-stu-id="73dcc-213">Local Policies</span></span>  
  
3.  <span data-ttu-id="73dcc-214">单击“用户权限分配” 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-214">Click **User Rights Assignment**.</span></span>  
  
4.  <span data-ttu-id="73dcc-215">双击“从网络访问此计算机” ，然后单击“添加用户或组” 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-215">Double-click **Access this computer from the network**, and then click **Add User or Group**.</span></span>  
  
5.  <span data-ttu-id="73dcc-216">单击“对象类型” ，选择“计算机”  并单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-216">Click **Object Types**, select **Computers** and click **OK**.</span></span>  
  
6.  <span data-ttu-id="73dcc-217">在“输入对象名称来选择”区域中  添加计算机名称或组名称。</span><span class="sxs-lookup"><span data-stu-id="73dcc-217">Add the computer name or the group name in the **Enter the object names to select** area.</span></span>  
  
7.  <span data-ttu-id="73dcc-218">单击“检查名称”  以验证输入的内容。</span><span class="sxs-lookup"><span data-stu-id="73dcc-218">Click **Check Names** to verify the entry.</span></span>  
  
8.  <span data-ttu-id="73dcc-219">单击“确定”两次  。</span><span class="sxs-lookup"><span data-stu-id="73dcc-219">Click **OK** twice.</span></span>  
  
 <span data-ttu-id="73dcc-220">要更改“拒绝从网络访问这台计算机”用户权限中包括的用户或组  ，请按以下步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="73dcc-220">To change the users or groups that are included in the **Deny access to this computer from the network** user right, follow these steps:</span></span>  
  
1.  <span data-ttu-id="73dcc-221">展开“本地计算机策略”列表中的以下项：</span><span class="sxs-lookup"><span data-stu-id="73dcc-221">Expand the following items in the Local Computer Policy list:</span></span>  
  
    -   <span data-ttu-id="73dcc-222">计算机配置</span><span class="sxs-lookup"><span data-stu-id="73dcc-222">Computer Configuration</span></span>  
  
    -   <span data-ttu-id="73dcc-223">Windows Settings</span><span class="sxs-lookup"><span data-stu-id="73dcc-223">Windows Settings</span></span>  
  
    -   <span data-ttu-id="73dcc-224">安全设置</span><span class="sxs-lookup"><span data-stu-id="73dcc-224">Security Settings</span></span>  
  
    -   <span data-ttu-id="73dcc-225">本地策略</span><span class="sxs-lookup"><span data-stu-id="73dcc-225">Local Policies</span></span>  
  
2.  <span data-ttu-id="73dcc-226">单击“用户权限分配” 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-226">Click **User Rights Assignment**.</span></span>  
  
3.  <span data-ttu-id="73dcc-227">双击“拒绝从网络访问这台计算机” ，然后进行单击以选择要从此用户权限中删除的计算机名称或组。</span><span class="sxs-lookup"><span data-stu-id="73dcc-227">Double-click **Deny access this computer from the network**, and then click to select the computer name or group that you want to remove from this user right.</span></span>  
  
4.  <span data-ttu-id="73dcc-228">单击“删除”  ，然后单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-228">Click **Remove** and then click **OK**.</span></span>  
  
## <a name="set-the-appropriate-values-for-the-enableauthepresolution-and-restrictremoteclients-options"></a><span data-ttu-id="73dcc-229">为 EnableAuthEpResolution 和 RestrictRemoteClients 选项设置相应的值</span><span class="sxs-lookup"><span data-stu-id="73dcc-229">Set the appropriate values for the EnableAuthEpResolution and RestrictRemoteClients options</span></span>  
 <span data-ttu-id="73dcc-230">Windows 通过要求验证对 RPC 接口的调用来提高安全性。</span><span class="sxs-lookup"><span data-stu-id="73dcc-230">Windows enhances security by requiring authenticated calls to the RPC interface.</span></span> <span data-ttu-id="73dcc-231">该功能可以通过 **EnableAuthEpResolution** 和 **RestrictRemoteClients** 注册表项来配置。</span><span class="sxs-lookup"><span data-stu-id="73dcc-231">This functionality is configurable through the **EnableAuthEpResolution** and **RestrictRemoteClients** registry keys.</span></span> <span data-ttu-id="73dcc-232">若要确保远程计算机能够访问 RPC 接口，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="73dcc-232">To ensure that remote computers are able to access the RPC interface, follow these steps:</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="73dcc-233">对注册表编辑器的不当使用可能会引起问题，而必须重新安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="73dcc-233">Incorrect use of Registry Editor may cause problems requiring you to reinstall your operating system.</span></span> <span data-ttu-id="73dcc-234">请慎用注册表编辑器，风险自负。</span><span class="sxs-lookup"><span data-stu-id="73dcc-234">Use Registry Editor at your own risk.</span></span> <span data-ttu-id="73dcc-235">有关如何备份、还原和修改注册表的详细信息，请参阅 Microsoft 知识库文章“Microsoft Windows 注册表说明”，网址为 [Microsoft Windows 注册表说明](http://go.microsoft.com/fwlink/?LinkId=62729)。</span><span class="sxs-lookup"><span data-stu-id="73dcc-235">For more information about how to back up, restore, and modify the registry, see the Microsoft Knowledge Base article "Description of the Microsoft Windows registry" at [Description of the Microsoft Windows registry](http://go.microsoft.com/fwlink/?LinkId=62729).</span></span>  
  
1.  <span data-ttu-id="73dcc-236">依次单击 **启动”**和 **运行”**，键入 **regedit.exe**，然后单击 **确定”** 以启动注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="73dcc-236">Click **Start**, click **Run**, type **regedit.exe**, and then click **OK** to start Registry Editor.</span></span>  
  
     <span data-ttu-id="73dcc-237">导航到 **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT**</span><span class="sxs-lookup"><span data-stu-id="73dcc-237">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT**</span></span>  
  
2.  <span data-ttu-id="73dcc-238">在 **RPC** 密钥下，创建具有所示值的以下 DWORD 项。</span><span class="sxs-lookup"><span data-stu-id="73dcc-238">Under the **RPC** key, create the following DWORD entries with the indicated values.</span></span> <span data-ttu-id="73dcc-239">如果 **RPC** 密钥不存在，则必须予以创建。</span><span class="sxs-lookup"><span data-stu-id="73dcc-239">If the **RPC** key does not exist then it must be created.</span></span>  
  
    |<span data-ttu-id="73dcc-240">DWORD 项</span><span class="sxs-lookup"><span data-stu-id="73dcc-240">DWORD entry</span></span>|<span data-ttu-id="73dcc-241">默认值</span><span class="sxs-lookup"><span data-stu-id="73dcc-241">Default value</span></span>|<span data-ttu-id="73dcc-242">推荐值</span><span class="sxs-lookup"><span data-stu-id="73dcc-242">Recommended value</span></span>|  
    |-----------------|-------------------|-----------------------|  
    |<span data-ttu-id="73dcc-243">EnableAuthEpResolution</span><span class="sxs-lookup"><span data-stu-id="73dcc-243">EnableAuthEpResolution</span></span>|<span data-ttu-id="73dcc-244">0（禁用）</span><span class="sxs-lookup"><span data-stu-id="73dcc-244">0 (disabled)</span></span>|<span data-ttu-id="73dcc-245">1</span><span class="sxs-lookup"><span data-stu-id="73dcc-245">1</span></span>|  
    |<span data-ttu-id="73dcc-246">RestrictRemoteClients</span><span class="sxs-lookup"><span data-stu-id="73dcc-246">RestrictRemoteClients</span></span>|<span data-ttu-id="73dcc-247">1（启用）</span><span class="sxs-lookup"><span data-stu-id="73dcc-247">1 (enabled)</span></span>|<span data-ttu-id="73dcc-248">0</span><span class="sxs-lookup"><span data-stu-id="73dcc-248">0</span></span>|  
  
3.  <span data-ttu-id="73dcc-249">关闭“注册表编辑器”。</span><span class="sxs-lookup"><span data-stu-id="73dcc-249">Close Registry Editor.</span></span>  
  
4.  <span data-ttu-id="73dcc-250">重新启动 MSDTC 服务。</span><span class="sxs-lookup"><span data-stu-id="73dcc-250">Restart the MSDTC Service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73dcc-251">根据所做的更改，可能需要重新启动计算机以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="73dcc-251">Depending on the changes that were made, you may need to reboot the computer to enact the changes.</span></span> <span data-ttu-id="73dcc-252">如果在应用更改并重新启动 MSDTC 服务后仍然遇到问题，请重新启动在其中进行了更改的计算机，以确保更改生效。</span><span class="sxs-lookup"><span data-stu-id="73dcc-252">If you are still encountering problems after applying changes and restarting the MSDTC service, reboot the computer on which the changes were made to ensure that the changes take effect.</span></span>  
  
## <a name="if-windows-firewall-is-running-add-an-exception-for-the-msdtc-service"></a><span data-ttu-id="73dcc-253">如果 Windows 防火墙正在运行，则为 MSDTC 服务添加一个例外</span><span class="sxs-lookup"><span data-stu-id="73dcc-253">If Windows Firewall is running, add an exception for the MSDTC service</span></span>  
 <span data-ttu-id="73dcc-254">Windows 防火墙服务可能会阻止计算机之间的 MSDTC 通信。</span><span class="sxs-lookup"><span data-stu-id="73dcc-254">The Windows Firewall service may block MSDTC communications between computers.</span></span> <span data-ttu-id="73dcc-255">要确保未阻止计算机之间的 MSDTC 通信，请在 Windows 防火墙服务正在运行时，将 msdtc.exe 添加到 Windows 防火墙例外列表中。</span><span class="sxs-lookup"><span data-stu-id="73dcc-255">To ensure that MSDTC communications are not blocked between computers, add msdtc.exe to the Windows Firewall exception list if the Windows Firewall service is running.</span></span>  
  
1.  <span data-ttu-id="73dcc-256">依次单击 **开始”**和 **“运行”**，键入 **firewall.cpl**，然后单击 **确定”** 以显示 **“Windows 防火墙”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="73dcc-256">Click **Start**, click **Run**, type **firewall.cpl**, and then click **OK** to display the **Windows Firewall** dialog box.</span></span>  
  
2.  <span data-ttu-id="73dcc-257">单击“允许程序通过 Windows 防火墙”  以显示“Windows 防火墙设置”  对话框。</span><span class="sxs-lookup"><span data-stu-id="73dcc-257">Click **Allow a program through the Windows Firewall** to display the **Windows Firewall Settings** dialog box.</span></span>  
  
3.  <span data-ttu-id="73dcc-258">单击 **“Windows 防火墙设置”** 对话框的 **“例外”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="73dcc-258">Click the **Exceptions** tab of the **Windows Firewall Settings** dialog box.</span></span>  
  
4.  <span data-ttu-id="73dcc-259">单击“添加程序”  以显示“添加程序”对话框  。</span><span class="sxs-lookup"><span data-stu-id="73dcc-259">Click **Add Program** to display the **Add a Program** dialog box.</span></span>  
  
5.  <span data-ttu-id="73dcc-260">单击 **浏览”** 并导航到 *%system32%*\msdtc.ex。</span><span class="sxs-lookup"><span data-stu-id="73dcc-260">Click **Browse** and navigate to *%system32%*\msdtc.exe.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73dcc-261">启动命令提示符，键入 **echo %system32%** 并按 **Enter** ，以确定此计算机上的 \System32 目录的位置。</span><span class="sxs-lookup"><span data-stu-id="73dcc-261">Launch a command prompt, type **echo %system32%** and press **Enter** to determine the location of the \System32 directory on this computer.</span></span>  
  
6.  <span data-ttu-id="73dcc-262">单击以选择 **“msdtc.exe”** ，然后单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="73dcc-262">Click to select **msdtc.exe** and click **Open**.</span></span>  
  
7.  <span data-ttu-id="73dcc-263">单击 **“更改作用域”** ，指定将允许其进行 MSDTC 通信的一组计算机，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="73dcc-263">Click **Change scope** to specify the set of computers for which MSDTC communications should be allowed and click **OK**.</span></span>  
  
8.  <span data-ttu-id="73dcc-264">在 **“添加程序”** 对话框中单击 **“确定”** ，并在 **“Windows 防火墙设置”** 对话框中单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="73dcc-264">Click **OK** in the **Add a Program** dialog box and click **OK** in the **Windows Firewall Settings** dialog box.</span></span>  
  
9. <span data-ttu-id="73dcc-265">关闭 **“Windows 防火墙”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="73dcc-265">Close the **Windows Firewall** dialog box.</span></span>  
  
10. <span data-ttu-id="73dcc-266">停止并重新启动分布式事务处理协调器服务。</span><span class="sxs-lookup"><span data-stu-id="73dcc-266">Stop and restart the Distributed Transaction Coordinator service.</span></span>  
  
    -   <span data-ttu-id="73dcc-267">启动命令提示符，键入 **net stop msdtc** ，然后按 **Enter**键。</span><span class="sxs-lookup"><span data-stu-id="73dcc-267">Launch a command prompt, type **net stop msdtc** and press **Enter**.</span></span>  
  
    -   <span data-ttu-id="73dcc-268">在分布式事务处理协调器服务停止后，键入 **net start msdtc** ，然后按 **Enter**键。</span><span class="sxs-lookup"><span data-stu-id="73dcc-268">After the Distributed Transaction Coordinator service has stopped, type **net start msdtc** and press **Enter**.</span></span>  
  
## <a name="use-dtctester-or-dtcping-to-verify-msdtc-functionality-over-the-network"></a><span data-ttu-id="73dcc-269">使用 DTCTester 或 DTCPing 通过网络检查 MSDTC 功能</span><span class="sxs-lookup"><span data-stu-id="73dcc-269">Use DTCTester or DTCPing to verify MSDTC functionality over the network</span></span>  
 <span data-ttu-id="73dcc-270">如果在两台计算机中的一台上安装了 SQL Server，则可以使用 DTCTester 实用程序检查这两台计算机之间是否支持事务处理。</span><span class="sxs-lookup"><span data-stu-id="73dcc-270">Use the DTCTester utility to verify transaction support between two computers if SQL Server is installed on one of the computers.</span></span> <span data-ttu-id="73dcc-271">DTCTester 实用程序使用 ODBC 检查 SQL Server 数据库是否支持事务处理。</span><span class="sxs-lookup"><span data-stu-id="73dcc-271">The DTCTester utility uses ODBC to verify transaction support against a SQL Server database.</span></span> <span data-ttu-id="73dcc-272">有关 DTCTester 的详细信息，请参阅 [如何使用 DTCTester 工具](http://go.microsoft.com/fwlink/?LinkId=66232)。</span><span class="sxs-lookup"><span data-stu-id="73dcc-272">For more information about DTCTester see [How to Use DTCTester Tool](http://go.microsoft.com/fwlink/?LinkId=66232).</span></span>  
  
 <span data-ttu-id="73dcc-273">如果两台计算机中都没有安装 SQL Server，则可以使用 DTCPing 检查这两台计算机之间是否支持事务处理。</span><span class="sxs-lookup"><span data-stu-id="73dcc-273">Use DTCPing to verify transaction support between two computers if SQL Server is not installed on either computer.</span></span> <span data-ttu-id="73dcc-274">DTCPing 是在两台计算机中都没有安装 SQL Server 的情况下替代 DTCTester 实用程序的良好工具，使用时必须既在客户端计算机上运行，也在服务器计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="73dcc-274">The DTCPing tool must be run on both the client and server computer and is a good alternative to the DTCTester utility when SQL Server is not installed on either computer.</span></span> <span data-ttu-id="73dcc-275">有关 DTCPing 的详细信息，请参阅[如何 MS DTC 防火墙问题进行疑难解答](http://go.microsoft.com/fwlink/?LinkId=61915)。</span><span class="sxs-lookup"><span data-stu-id="73dcc-275">For more information about DTCPing, see [How to troubleshoot MS DTC firewall issues](http://go.microsoft.com/fwlink/?LinkId=61915).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73dcc-276">如果 DCTPing 返回警告：“警告：两台测试机器的 CID 值相同”，请按照 **确保为 MSDTC 分配唯一的 CID 值** 一节中的步骤在测试机器之间调整适当的 MSDTC 功能。</span><span class="sxs-lookup"><span data-stu-id="73dcc-276">If DTCPing returns the warning that “WARNING:the CID values for both test machines are the same” then follow the steps in the section **Ensure that MSDTC is assigned a unique CID value** to accommodate proper MSDTC functionality between the test machines.</span></span>  
  
## <a name="ensure-that-msdtc-is-assigned-a-unique-cid-value"></a><span data-ttu-id="73dcc-277">确保为 MSDTC 分配唯一的 CID 值</span><span class="sxs-lookup"><span data-stu-id="73dcc-277">Ensure that MSDTC is assigned a unique CID value</span></span>  
 <span data-ttu-id="73dcc-278">Windows 操作系统的 MSDTC 功能要求唯一的 CID 值以确保计算机间的 MSDTC 功能正常工作。</span><span class="sxs-lookup"><span data-stu-id="73dcc-278">The MSDTC feature of the Windows operating system requires unique CID values to ensure that MSDTC functionality between computers works correctly.</span></span> <span data-ttu-id="73dcc-279">Windows 安装的磁盘重复映像必须具有唯一的 CID 值，否则，MSDTC 功能将受到影响。</span><span class="sxs-lookup"><span data-stu-id="73dcc-279">Disk duplicate images of Windows installations must have unique CID values or MSDTC functionality may be impaired.</span></span> <span data-ttu-id="73dcc-280">在使用虚拟硬盘将一个操作系统部署到虚拟机上时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="73dcc-280">This can occur when using virtual hard disks to deploy an operating system to a virtual machine.</span></span>  
  
 <span data-ttu-id="73dcc-281">要确定运行 Windows 操作系统的计算机的 MSDTC CID 值是否唯一，请检查两台计算机上 HKEY_CLASSES_ROOT\CID 注册表项下的各条目值。</span><span class="sxs-lookup"><span data-stu-id="73dcc-281">To determine if MSDTC CID values for computers that are running the Windows operating system are unique, check the values for the entries under the HKEY_CLASSES_ROOT\CID registry key on both computers.</span></span> <span data-ttu-id="73dcc-282">如果这些值对于每台计算机并不是唯一的，请按照 **如果其他疑难解答步骤不成功，请考虑重新安装分布式事务协调器服务** 一节中的步骤在其中一台计算机上重新安装 MSDTC，为该计算机生成唯一的 MSDTC CID 值并调整相应的 MSDTC 操作。</span><span class="sxs-lookup"><span data-stu-id="73dcc-282">If these values are not unique for each computer then follow the steps in the section **Consider reinstalling the Distributed Transaction Coordinator service if other troubleshooting steps are not successful** to reinstall MSDTC on one of the computers, which will then generate unique MSDTC CID values for that computer and accommodate proper MSDTC operations.</span></span>  
  
## <a name="error-new-transaction-cannot-enlist-in-the-specified-transaction-coordinator-0x8004d00a-occurs-if-the-msdtc-connection-between-a-client-computer-and-a-server-computer-is-closed"></a><span data-ttu-id="73dcc-283">如果关闭了客户端计算机与服务器计算机之间的 MSDTC 连接，则出现错误“无法在指定事务协调器中登记新事务(0x8004d00a)”</span><span class="sxs-lookup"><span data-stu-id="73dcc-283">Error “New transaction cannot enlist in the specified transaction coordinator (0x8004d00a)” occurs if the MSDTC connection between a client computer and a server computer is closed</span></span>  
 <span data-ttu-id="73dcc-284">在某些情况下，可能出现客户端和服务器之间的现有 MSDTC 连接关闭，并且后续尝试使用此连接将导致以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="73dcc-284">In certain scenarios, it is possible that an existing MSDTC connection between a client and server is closed and subsequent attempts to use this connection will result in the following error message:</span></span>  
<span data-ttu-id="73dcc-285">无法在指定的事务处理协调器中登记新事务 (0x8004d00a)</span><span class="sxs-lookup"><span data-stu-id="73dcc-285">New transaction cannot enlist in the specified transaction coordinator (0x8004d00a)</span></span>  
<span data-ttu-id="73dcc-286">有关详细信息，请参阅[当你尝试在 MS DTC 中启动事务时的错误消息:"中指定的事务处理协调器无法登记新的事务"](http://support.microsoft.com/kb/922430)。</span><span class="sxs-lookup"><span data-stu-id="73dcc-286">For more information, see [Error message when you try to start a transaction in MS DTC: "New transaction cannot enlist in the specified transaction coordinator"](http://support.microsoft.com/kb/922430).</span></span>  
  
## <a name="consider-reinstalling-the-distributed-transaction-coordinator-service-if-other-troubleshooting-steps-are-not-successful"></a><span data-ttu-id="73dcc-287">如果其他疑难解答步骤不成功，请考虑重新安装分布式事务协调器服务</span><span class="sxs-lookup"><span data-stu-id="73dcc-287">Consider reinstalling the Distributed Transaction Coordinator service if other troubleshooting steps are not successful</span></span>  
 <span data-ttu-id="73dcc-288">如果尝试解决 MSDTC 问题的其他操作不成功，请考虑卸载并重新安装 MSDTC。</span><span class="sxs-lookup"><span data-stu-id="73dcc-288">If other attempts at troubleshooting problems with MSDTC are not successful consider uninstalling and reinstalling MSDTC.</span></span> <span data-ttu-id="73dcc-289">请按照下列步骤卸载并重新安装 MSDTC：</span><span class="sxs-lookup"><span data-stu-id="73dcc-289">Follow these steps to uninstall and reinstall MSDTC:</span></span>  
  
1.  <span data-ttu-id="73dcc-290">以管理员身份打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="73dcc-290">Open a command prompt as Administrator.</span></span>  
  
2.  <span data-ttu-id="73dcc-291">在命令提示符处，键入以下内容来卸载分布式事务处理协调器服务：</span><span class="sxs-lookup"><span data-stu-id="73dcc-291">At the command prompt, type the following to uninstall the Distributed Transaction Coordinator service:</span></span>  
    `msdtc -uninstall`  
  
3.  <span data-ttu-id="73dcc-292">在命令提示符下，键入以下内容来安装分布式事务处理协调器服务：</span><span class="sxs-lookup"><span data-stu-id="73dcc-292">At the command prompt, type the following to install the Distributed Transaction Coordinator service:</span></span>  
    `msdtc –install`  
  
> [!IMPORTANT]
>  <span data-ttu-id="73dcc-293">重新安装 MSDTC 可能会更改分布式事务处理协调器服务的默认行为。</span><span class="sxs-lookup"><span data-stu-id="73dcc-293">Reinstalling MSDTC may change the default behavior of the Distributed Transaction Coordinator service.</span></span> <span data-ttu-id="73dcc-294">重新安装 MSDTC 后，请按照下列步骤以确保分布式事务处理协调器服务能够正常工作：</span><span class="sxs-lookup"><span data-stu-id="73dcc-294">Follow these steps after reinstalling MSDTC to ensure that the Distributed Transaction Coordinator service works correctly:</span></span>  
>   
>  -   <span data-ttu-id="73dcc-295">重新安装 MSDTC 可能会将 MSDTC 安全配置选项重置回默认值。</span><span class="sxs-lookup"><span data-stu-id="73dcc-295">Reinstalling MSDTC may reset MSDTC Security Configuration options back to default values.</span></span> <span data-ttu-id="73dcc-296">验证重新安装 MSDTC 后 MSDTC 安全配置选项是否设置为相应的值。</span><span class="sxs-lookup"><span data-stu-id="73dcc-296">Verify that the MSDTC Security Configuration options are set to the appropriate values after reinstalling MSDTC.</span></span>  
> -   <span data-ttu-id="73dcc-297">重新安装 MSDTC 可能会更改分布式事务处理协调器服务的 **“启动类型”** 值。</span><span class="sxs-lookup"><span data-stu-id="73dcc-297">Reinstalling MSDTC may change the **Startup Type** value for the Distributed Transaction Coordinator service.</span></span> <span data-ttu-id="73dcc-298">验证重新安装 MSDTC 后分布式事务协调器服务的“启动类型”  值已设置为“自动”  。</span><span class="sxs-lookup"><span data-stu-id="73dcc-298">Verify that the **Startup Type** value for the Distributed Transaction Coordinator service is set to **Automatic** after reinstalling MSDTC.</span></span>  
> -   <span data-ttu-id="73dcc-299">重新安装 MSDTC 可能需要重启计算机。</span><span class="sxs-lookup"><span data-stu-id="73dcc-299">Reinstalling MSDTC may require a reboot of the computer.</span></span> <span data-ttu-id="73dcc-300">若要确保分布式事务处理协调器服务工作正常，可在重新安装 MSDTC 后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="73dcc-300">To ensure that the Distributed Transaction Coordinator service works correctly, reboot the computer after reinstalling MSDTC.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73dcc-301">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73dcc-301">See Also</span></span>  
 <span data-ttu-id="73dcc-302">[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="73dcc-302">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="73dcc-303">Windows Server 群集进行疑难解答</span><span class="sxs-lookup"><span data-stu-id="73dcc-303">Troubleshooting a Windows Server Cluster</span></span>](../core/troubleshooting-a-windows-server-cluster.md)