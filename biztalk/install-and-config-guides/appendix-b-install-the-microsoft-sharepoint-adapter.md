---
title: 附录 B：安装 SharePoint 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f44c6e0a-dcce-4444-8cac-bd403c81a233
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e638eaaf4b677c5fc08e08d608a92ecf75345676
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401495"
---
# <a name="appendix-b-install-the-microsoft-sharepoint-adapter"></a><span data-ttu-id="83e4f-102">附录 B：安装 Microsoft SharePoint 适配器</span><span class="sxs-lookup"><span data-stu-id="83e4f-102">Appendix B: Install the Microsoft SharePoint Adapter</span></span>
<span data-ttu-id="83e4f-103">BizTalk Server 包含可以接收消息或将消息发送到 SharePoint 的 SharePoint 适配器。</span><span class="sxs-lookup"><span data-stu-id="83e4f-103">BizTalk Server includes a SharePoint adapter that can receive messages or send messages to SharePoint.</span></span> 

<span data-ttu-id="83e4f-104">软件要求[BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)并[BizTalk Server 2013 R2 / 2013年](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)列出的受支持的 SharePoint 版本。</span><span class="sxs-lookup"><span data-stu-id="83e4f-104">The software requirements for [BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) and [BizTalk Server 2013 R2 / 2013](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) list the supported SharePoint versions.</span></span>

## <a name="sharepoint-adapter-in-biztalk-server-2016"></a><span data-ttu-id="83e4f-105">BizTalk Server 2016 中的 SharePoint 适配器</span><span class="sxs-lookup"><span data-stu-id="83e4f-105">SharePoint adapter in BizTalk Server 2016</span></span>

<span data-ttu-id="83e4f-106">BizTalk Server 安装程序会自动安装 CSOM 可再发行组件包，就像文件适配器、 FTP 适配器和其他的箱适配器。</span><span class="sxs-lookup"><span data-stu-id="83e4f-106">The BizTalk Server setup automatically installs the CSOM redistributable package, just like the File adapter, FTP adapter, and other out-of-the-box adapters.</span></span> 

<span data-ttu-id="83e4f-107">SSOM 选项已删除，并且不可用。</span><span class="sxs-lookup"><span data-stu-id="83e4f-107">The SSOM option is removed, and is not available.</span></span>


## <a name="sharepoint-adapter-in-biztalk-server-2013-and-r2"></a><span data-ttu-id="83e4f-108">BizTalk Server 2013 和 R2 中的 SharePoint 适配器</span><span class="sxs-lookup"><span data-stu-id="83e4f-108">SharePoint adapter in BizTalk Server 2013 and R2</span></span>
<span data-ttu-id="83e4f-109">在 BizTalk Server 2013 R2 和 BizTalk Server 2013 中，有了 SharePoint 适配器的两个选项。</span><span class="sxs-lookup"><span data-stu-id="83e4f-109">In BizTalk Server 2013 R2 and BizTalk Server 2013, there are two options for the SharePoint adapter.</span></span>

|<span data-ttu-id="83e4f-110">SharePoint 对象模型</span><span class="sxs-lookup"><span data-stu-id="83e4f-110">SharePoint object model</span></span>|<span data-ttu-id="83e4f-111">Description</span><span class="sxs-lookup"><span data-stu-id="83e4f-111">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="83e4f-112">CSOM 的 SharePoint 适配器</span><span class="sxs-lookup"><span data-stu-id="83e4f-112">CSOM - SharePoint Adapter</span></span>|<span data-ttu-id="83e4f-113">**建议**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-113">**Recommended**.</span></span> <span data-ttu-id="83e4f-114">BizTalk Server 安装程序会自动安装 CSOM 可再发行组件包，就像文件适配器、 FTP 适配器和其他的箱适配器。</span><span class="sxs-lookup"><span data-stu-id="83e4f-114">The BizTalk Server setup automatically installs the CSOM redistributable package, just like the File adapter, FTP adapter, and other out-of-the-box adapters.</span></span> <br/><br/><span data-ttu-id="83e4f-115">SharePoint 计算机上的没有安装要求。</span><span class="sxs-lookup"><span data-stu-id="83e4f-115">There are no installation requirements on the SharePoint computer.</span></span>|  
|<span data-ttu-id="83e4f-116">SSOM-SharePoint Web 服务</span><span class="sxs-lookup"><span data-stu-id="83e4f-116">SSOM - SharePoint Web Service</span></span>|<span data-ttu-id="83e4f-117">**已弃用**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-117">**Deprecated**.</span></span> <span data-ttu-id="83e4f-118">在 SharePoint 计算机上运行 BizTalk Server 安装程序，并**仅**选择 SharePoint 适配器。</span><span class="sxs-lookup"><span data-stu-id="83e4f-118">On the SharePoint computer, run the BizTalk Server setup, and **only** select the SharePoint Adapter.</span></span> <span data-ttu-id="83e4f-119">此安装程序安装用于处理与 BizTalk 服务器上的 SharePoint 适配器通信的 IIS web 服务。</span><span class="sxs-lookup"><span data-stu-id="83e4f-119">This setup installs an IIS web service that handles the communication to the SharePoint adapter on BizTalk Server.</span></span> <br/><br/><span data-ttu-id="83e4f-120">在大多数环境中，BizTalk Server 和 SharePoint 在不同计算机上。</span><span class="sxs-lookup"><span data-stu-id="83e4f-120">In most environments, BizTalk Server and SharePoint are on separate computers.</span></span>|  

##  <a name="BKMK_Before"></a> <span data-ttu-id="83e4f-121">在安装之前</span><span class="sxs-lookup"><span data-stu-id="83e4f-121">Before You Install</span></span>  

*  <span data-ttu-id="83e4f-122">SharePoint SSOM 和 CSOM 组件可以同时安装如果同一台计算机上安装 BizTalk Server 2013 R2 或 2013年和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="83e4f-122">The SharePoint SSOM and CSOM components can both be installed if BizTalk Server 2013 R2 or 2013 and SharePoint are installed on the same computer.</span></span>  
  
* <span data-ttu-id="83e4f-123">BAM 门户仅在 32 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="83e4f-123">The BAM Portal only runs in 32-bit mode.</span></span> <span data-ttu-id="83e4f-124">如果在 64 位计算机上安装了 BAM 门户，请确保已启用 ASP.NET 2.0 32 位和 IIS 应用程序池处于 32 位模式。</span><span class="sxs-lookup"><span data-stu-id="83e4f-124">If the BAM Portal is installed on a 64-bit machine, ensure that ASP.NET 2.0 32-bit is enabled and the IIS application pool is in 32-bit mode.</span></span> <span data-ttu-id="83e4f-125">若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="83e4f-125">To do this:</span></span>  
  
    -   <span data-ttu-id="83e4f-126">**ASP.NET**:打开 IIS 管理器中，单击**BAM 门户**网站，，然后双击**处理程序映射**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-126">**ASP.NET**: Open IIS Manager, click the **BAM Portal** web site, and then double-click **Handler Mappings**.</span></span> <span data-ttu-id="83e4f-127">在中**已启用**列表中，确认**Pagehandlerfactory-isapi-2.0**列出。</span><span class="sxs-lookup"><span data-stu-id="83e4f-127">In the **Enabled** list, confirm **PageHandlerFactory-ISAPI-2.0** is listed.</span></span>  
  
    -   <span data-ttu-id="83e4f-128">**应用程序池**:打开 IIS 管理器中，单击**应用程序池**，单击**BAMAppPool**，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-128">**Application Pool**: Open IIS Manager, click **Application Pools**, click the **BAMAppPool**, and then click **Advanced Settings**.</span></span> <span data-ttu-id="83e4f-129">在中**启用 32 位应用程序**，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-129">In **Enable 32-bit applications**, select **True**.</span></span>  
  
* <span data-ttu-id="83e4f-130">安装 SharePoint 时，单击**服务器场**选项，即使你要创建单服务器 BizTalk Server 和 SharePoint 安装。</span><span class="sxs-lookup"><span data-stu-id="83e4f-130">When installing SharePoint, click the **Server Farm** option, even when you are creating a single-server BizTalk Server and SharePoint installation.</span></span> <span data-ttu-id="83e4f-131">一个**服务器场**安装允许您配置 SharePoint 数据库。</span><span class="sxs-lookup"><span data-stu-id="83e4f-131">A **Server Farm** installation allows you to configure the SharePoint databases.</span></span>  
* <span data-ttu-id="83e4f-132">[CSOM:SharePoint Services 适配器](../core/csom-sharepoint-services-adapter.md)信息提供有关配置 SharePoint 接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="83e4f-132">[CSOM: SharePoint Services Adapter](../core/csom-sharepoint-services-adapter.md) provides information on configuring a SharePoint receive location and send port.</span></span>  
* <span data-ttu-id="83e4f-133">BizTalk Server 2010 及以前版本使用服务器端对象模型 (SSOM) 连接到 SharePoint 2010。</span><span class="sxs-lookup"><span data-stu-id="83e4f-133">BizTalk Server 2010 and previous versions use the Server Side Object Model (SSOM) to connect to SharePoint 2010.</span></span> 

## <a name="csom-and-ssom-supported-versions"></a><span data-ttu-id="83e4f-134">支持 CSOM 和 SSOM 的版本</span><span class="sxs-lookup"><span data-stu-id="83e4f-134">CSOM and SSOM supported versions</span></span>  
<span data-ttu-id="83e4f-135">下表中列出了 SharePoint 的支持：</span><span class="sxs-lookup"><span data-stu-id="83e4f-135">SharePoint support is listed in the following table:</span></span>  
  
||<span data-ttu-id="83e4f-136">支持 CSOM</span><span class="sxs-lookup"><span data-stu-id="83e4f-136">Supports CSOM</span></span>|<span data-ttu-id="83e4f-137">支持 SSOM</span><span class="sxs-lookup"><span data-stu-id="83e4f-137">Supports SSOM</span></span>|  
|---|---|---|  
|<span data-ttu-id="83e4f-138">SharePoint 2016</span><span class="sxs-lookup"><span data-stu-id="83e4f-138">SharePoint 2016</span></span>|<span data-ttu-id="83e4f-139">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-139">Yes</span></span>|<span data-ttu-id="83e4f-140">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-140">No</span></span>|  
|<span data-ttu-id="83e4f-141">SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="83e4f-141">SharePoint 2013</span></span>|<span data-ttu-id="83e4f-142">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-142">Yes</span></span>|<span data-ttu-id="83e4f-143">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-143">No</span></span>|  
|<span data-ttu-id="83e4f-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="83e4f-144">SharePoint Online</span></span>|<span data-ttu-id="83e4f-145">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-145">Yes</span></span>|<span data-ttu-id="83e4f-146">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-146">No</span></span>|  
|<span data-ttu-id="83e4f-147">SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="83e4f-147">SharePoint 2010</span></span>|<span data-ttu-id="83e4f-148">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-148">Yes</span></span>|<span data-ttu-id="83e4f-149">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-149">Yes</span></span>|  
|<span data-ttu-id="83e4f-150">SharePoint 2007</span><span class="sxs-lookup"><span data-stu-id="83e4f-150">SharePoint 2007</span></span> |<span data-ttu-id="83e4f-151">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-151">No</span></span>|<span data-ttu-id="83e4f-152">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-152">Yes</span></span>|  
  
##  <a name="BKMK_CSOM"></a> <span data-ttu-id="83e4f-153">安装 CSOM SharePoint 适配器</span><span class="sxs-lookup"><span data-stu-id="83e4f-153">Install the CSOM SharePoint adapter</span></span>  
  
1.  <span data-ttu-id="83e4f-154">使用 SharePoint 计算机根据以下要求：</span><span class="sxs-lookup"><span data-stu-id="83e4f-154">Use a SharePoint computer based on the following requirements:</span></span>  
  
    ||<span data-ttu-id="83e4f-155">CSOM 支持</span><span class="sxs-lookup"><span data-stu-id="83e4f-155">CSOM Support</span></span>|  
    |---|---|  
    |<span data-ttu-id="83e4f-156">SharePoint 2016</span><span class="sxs-lookup"><span data-stu-id="83e4f-156">SharePoint 2016</span></span><br /><br /> <span data-ttu-id="83e4f-157">[安装 SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)</span><span class="sxs-lookup"><span data-stu-id="83e4f-157">[Install SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)</span></span>|<span data-ttu-id="83e4f-158">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-158">Yes</span></span>|  
    |<span data-ttu-id="83e4f-159">SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="83e4f-159">SharePoint 2013</span></span><br /><br /> [<span data-ttu-id="83e4f-160">安装 SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="83e4f-160">Install SharePoint 2013</span></span>](https://technet.microsoft.com/library/cc262957.aspx)|<span data-ttu-id="83e4f-161">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-161">Yes</span></span>|  
    |<span data-ttu-id="83e4f-162">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="83e4f-162">SharePoint Online</span></span><br /><br /> [<span data-ttu-id="83e4f-163">SharePoint Online 管理</span><span class="sxs-lookup"><span data-stu-id="83e4f-163">SharePoint Online administration</span></span>](https://technet.microsoft.com/library/gg132908.aspx)|<span data-ttu-id="83e4f-164">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-164">Yes</span></span>|  
    |<span data-ttu-id="83e4f-165">SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="83e4f-165">SharePoint 2010</span></span><br /><br /> <span data-ttu-id="83e4f-166">[安装和部署 SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)</span><span class="sxs-lookup"><span data-stu-id="83e4f-166">[Installation and Deployment for SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)</span></span>|<span data-ttu-id="83e4f-167">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-167">Yes</span></span>|  
    |<span data-ttu-id="83e4f-168">SharePoint 2007</span><span class="sxs-lookup"><span data-stu-id="83e4f-168">SharePoint 2007</span></span> |<span data-ttu-id="83e4f-169">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-169">No</span></span>|  
  
2.  <span data-ttu-id="83e4f-170">BizTalk Server 上安装 Windows Identity Foundation:</span><span class="sxs-lookup"><span data-stu-id="83e4f-170">On the BizTalk Server, install Windows Identity Foundation:</span></span>  
  
    | <span data-ttu-id="83e4f-171">操作系统</span><span class="sxs-lookup"><span data-stu-id="83e4f-171">Operating System</span></span> | <span data-ttu-id="83e4f-172">T:System.Diagnostics.Switch</span><span class="sxs-lookup"><span data-stu-id="83e4f-172">Info</span></span> |  
    |---|---|  
    |<span data-ttu-id="83e4f-173">Windows 10、 Windows 8.1、 Windows Server 2016、 Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="83e4f-173">Windows 10, Windows 8.1, Windows Server 2016, Windows Server 2012, and Windows Server 2012 R2</span></span>|<span data-ttu-id="83e4f-174">Windows Identity Foundation 作为一项功能是操作系统附带**打开或关闭打开的 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-174">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>|  
    |<span data-ttu-id="83e4f-175">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="83e4f-175">Windows Vista SP1</span></span>|<span data-ttu-id="83e4f-176">下载位置[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331)。</span><span class="sxs-lookup"><span data-stu-id="83e4f-176">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331).</span></span>|  
  
3.  <span data-ttu-id="83e4f-177">安装 BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="83e4f-177">Install BizTalk Server:</span></span>

    | |  |  
    |---|---|  
     | <span data-ttu-id="83e4f-178">BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="83e4f-178">BizTalk Server 2016</span></span> | <span data-ttu-id="83e4f-179">运行 BizTalk 安装程序。</span><span class="sxs-lookup"><span data-stu-id="83e4f-179">Run BizTalk setup.</span></span> |
    | <span data-ttu-id="83e4f-180">BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="83e4f-180">BizTalk Server 2013 R2</span></span> | <span data-ttu-id="83e4f-181">运行 BizTalk 安装程序，并执行**不**检查**Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-181">Run BizTalk setup, and do **not** check **Windows SharePoint Services Adapter**.</span></span> |  
    | <span data-ttu-id="83e4f-182">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="83e4f-182">BizTalk Server 2013</span></span> | <span data-ttu-id="83e4f-183">运行 BizTalk 安装程序，并执行**不**检查**Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-183">Run BizTalk setup, and do **not** check **Windows SharePoint Services Adapter**.</span></span> |
  
##  <a name="BKMK_SSOM"></a> <span data-ttu-id="83e4f-184">安装 SSOM SharePoint 适配器 （已弃用）</span><span class="sxs-lookup"><span data-stu-id="83e4f-184">Install the SSOM SharePoint adapter (deprecated)</span></span>  
  
1.  <span data-ttu-id="83e4f-185">使用基于以下 SSOM 要求 SharePoint 计算机：</span><span class="sxs-lookup"><span data-stu-id="83e4f-185">Use a SharePoint computer based on the following SSOM requirements:</span></span>  
  
    ||<span data-ttu-id="83e4f-186">SSOM 支持</span><span class="sxs-lookup"><span data-stu-id="83e4f-186">SSOM Support</span></span>|  
    |---|---|  
    |<span data-ttu-id="83e4f-187">SharePoint 2016</span><span class="sxs-lookup"><span data-stu-id="83e4f-187">SharePoint 2016</span></span><br /><br /> <span data-ttu-id="83e4f-188">[安装 SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)</span><span class="sxs-lookup"><span data-stu-id="83e4f-188">[Install SharePoint 2016](https://technet.microsoft.com/library/cc262957(v=office.16).aspx)</span></span>|<span data-ttu-id="83e4f-189">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-189">No</span></span>| 
    |<span data-ttu-id="83e4f-190">SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="83e4f-190">SharePoint 2013</span></span><br /><br /> [<span data-ttu-id="83e4f-191">安装 SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="83e4f-191">Install SharePoint 2013</span></span>](http://technet.microsoft.com/library/cc303424.aspx)|<span data-ttu-id="83e4f-192">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-192">No</span></span>|  
    |<span data-ttu-id="83e4f-193">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="83e4f-193">SharePoint Online</span></span><br /><br /> [<span data-ttu-id="83e4f-194">SharePoint Online 管理</span><span class="sxs-lookup"><span data-stu-id="83e4f-194">SharePoint Online administration</span></span>](https://technet.microsoft.com/library/gg132908.aspx)|<span data-ttu-id="83e4f-195">否</span><span class="sxs-lookup"><span data-stu-id="83e4f-195">No</span></span>|  
    |<span data-ttu-id="83e4f-196">SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="83e4f-196">SharePoint 2010</span></span><br /><br /> <span data-ttu-id="83e4f-197">[安装和部署 SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)</span><span class="sxs-lookup"><span data-stu-id="83e4f-197">[Installation and Deployment for SharePoint Server 2010](https://technet.microsoft.com/library/cc262957(v=office.14).aspx)</span></span>|<span data-ttu-id="83e4f-198">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-198">Yes</span></span>|  
    |<span data-ttu-id="83e4f-199">SharePoint 2007</span><span class="sxs-lookup"><span data-stu-id="83e4f-199">SharePoint 2007</span></span><br /><br /> <span data-ttu-id="83e4f-200">[安装 SharePoint Server 2007](https://technet.microsoft.com/library/cc262957(v=office.12).aspx)</span><span class="sxs-lookup"><span data-stu-id="83e4f-200">[Installation for SharePoint Server 2007](https://technet.microsoft.com/library/cc262957(v=office.12).aspx)</span></span> |<span data-ttu-id="83e4f-201">是</span><span class="sxs-lookup"><span data-stu-id="83e4f-201">Yes</span></span>|  
  
2.  <span data-ttu-id="83e4f-202">在 SharePoint 计算机上，配置 SharePoint，并扩展默认网站。</span><span class="sxs-lookup"><span data-stu-id="83e4f-202">On the SharePoint computer, configure SharePoint, and extend the Default Web Site.</span></span> <span data-ttu-id="83e4f-203">在扩展 web 站点时，单独的 IIS 网站上创建它包含相同的内容，但还提供了一个唯一的 URL 和身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="83e4f-203">When you extend the web site, a separate IIS web site is created that contains the same content but also provides a unique URL and authentication type.</span></span>  
  
     <span data-ttu-id="83e4f-204">请参阅[SharePoint 2010:扩展 Web 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=259124)。</span><span class="sxs-lookup"><span data-stu-id="83e4f-204">See [SharePoint 2010: Extend a Web Application](http://go.microsoft.com/fwlink/p/?LinkId=259124).</span></span>  
  
3.  <span data-ttu-id="83e4f-205">在 SharePoint 计算机上运行 BizTalk Server 安装和**仅**检查**Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-205">On the SharePoint computer, run the BizTalk Server installation and **only** check **Windows SharePoint Services Adapter**.</span></span> <span data-ttu-id="83e4f-206">这将安装 web 服务。</span><span class="sxs-lookup"><span data-stu-id="83e4f-206">This installs the web service.</span></span> <span data-ttu-id="83e4f-207">**不要运行 BizTalk 配置**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-207">**Do not run the BizTalk configuration**.</span></span>  
  
4.  <span data-ttu-id="83e4f-208">BizTalk Server 上安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="83e4f-208">On the BizTalk Server, install BizTalk Server.</span></span> <span data-ttu-id="83e4f-209">不要**不**检查**Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-209">Do **not** check **Windows SharePoint Services Adapter**.</span></span>  
  
5.  <span data-ttu-id="83e4f-210">SharePoint Web 服务 (SSOM) 仅在 64 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="83e4f-210">The SharePoint Web Service (SSOM) only runs in 64-bit mode.</span></span> <span data-ttu-id="83e4f-211">ASP.NET 和 IIS 应用程序池必须是在 SharePoint 计算机上的 64 位模式下安装 SharePoint 之前。</span><span class="sxs-lookup"><span data-stu-id="83e4f-211">ASP.NET and the IIS application pool must be in 64-bit mode on the SharePoint computer before installing SharePoint.</span></span> <span data-ttu-id="83e4f-212">若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="83e4f-212">To do this:</span></span>  
  
    -   <span data-ttu-id="83e4f-213">**ASP.NET**:打开 IIS 管理器中，单击网站，并双击**处理程序映射**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-213">**ASP.NET**: Open IIS Manager, click the web site, and then double-click **Handler Mappings**.</span></span> <span data-ttu-id="83e4f-214">在中**已启用**列表中，确认**PageHandlerFactory ISAPI-2.0 64**列出。</span><span class="sxs-lookup"><span data-stu-id="83e4f-214">In the **Enabled** list, confirm **PageHandlerFactory-ISAPI-2.0-64** is listed.</span></span>  
  
    -   <span data-ttu-id="83e4f-215">**应用程序池**:打开 IIS 管理器中，单击**应用程序池**，选择应用程序池，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-215">**Application Pool**: Open IIS Manager, click **Application Pools**, select the application pool, and then click **Advanced Settings**.</span></span> <span data-ttu-id="83e4f-216">在中**启用 32 位应用程序**，选择**False**。</span><span class="sxs-lookup"><span data-stu-id="83e4f-216">In **Enable 32-bit applications**, select **False**.</span></span>  

