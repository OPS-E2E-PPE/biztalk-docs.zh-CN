---
title: 安装 BizTalk Accelerator for RosettaNet (BTARN) 在 BizTalk Server 上 |Microsoft Docs
description: 请参阅硬件和软件要求、 安装步骤中，以及 BizTalk Server 中的 BTARN 配置步骤
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd5c218e6862791b8eb2f6a80848c4f8b2755b8
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752669"
---
# <a name="install-biztalk-accelerator-for-rosettanet"></a><span data-ttu-id="faca4-103">安装 BizTalk Accelerator for RosettaNet</span><span class="sxs-lookup"><span data-stu-id="faca4-103">Install BizTalk Accelerator for RosettaNet</span></span>

## <a name="overview"></a><span data-ttu-id="faca4-104">概述</span><span class="sxs-lookup"><span data-stu-id="faca4-104">Overview</span></span>
<span data-ttu-id="faca4-105">安装 Microsoft BizTalk Accelerator for RosettaNet (BTARN)。</span><span class="sxs-lookup"><span data-stu-id="faca4-105">Install the Microsoft BizTalk Accelerator for RosettaNet (BTARN).</span></span>

> [!NOTE]
>  <span data-ttu-id="faca4-106">在 Enterprise Edition 的 BizTalk Server 上，可以安装仅 Enterprise Edition 的 BizTalk Accelerator for RosettaNet (BTARN)。</span><span class="sxs-lookup"><span data-stu-id="faca4-106">On the Enterprise Edition of BizTalk Server, you can install only the Enterprise Edition of BizTalk Accelerator for RosettaNet (BTARN).</span></span> <span data-ttu-id="faca4-107">在标准版的 BizTalk Server 上，可以安装仅标准版本的 BizTalk Accelerator for RosettaNet (BTARN)。</span><span class="sxs-lookup"><span data-stu-id="faca4-107">On the Standard Edition of BizTalk Server, you can install only the Standard Edition of BizTalk Accelerator for RosettaNet (BTARN).</span></span>  

 <span data-ttu-id="faca4-108">BTARN 安装包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="faca4-108">The BTARN installation includes the following:</span></span>  

-   <span data-ttu-id="faca4-109">BTARN 管理</span><span class="sxs-lookup"><span data-stu-id="faca4-109">BTARN Administration</span></span>  

-   <span data-ttu-id="faca4-110">BizTalk 业务流程设计器 XLANG 调度（合作伙伴接口流程模式）</span><span class="sxs-lookup"><span data-stu-id="faca4-110">BizTalk Orchestration Designer XLANG schedules (Partner Interface Process patterns)</span></span>  

-   <span data-ttu-id="faca4-111">RosettaNet 实现框架 (RNIF)</span><span class="sxs-lookup"><span data-stu-id="faca4-111">RosettaNet Implementation Framework (RNIF)</span></span>  

-   <span data-ttu-id="faca4-112">BTARN 数据库</span><span class="sxs-lookup"><span data-stu-id="faca4-112">BTARN database</span></span>  

-   <span data-ttu-id="faca4-113">HTTP 前端 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="faca4-113">HTTP front end Web applications</span></span>  

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="faca4-114">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="faca4-114">Hardware and software requirements</span></span>

<span data-ttu-id="faca4-115">与 BizTalk 服务器相同的最低硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="faca4-115">The minimum hardware and software requirements are the same as BizTalk Server.</span></span>


|                                                                                         |                                                                                <span data-ttu-id="faca4-116">BizTalk 要求</span><span class="sxs-lookup"><span data-stu-id="faca4-116">BizTalk requirements</span></span>                                                                                 |                                                                                                                                                                                                                                                            <span data-ttu-id="faca4-117">SQL 和操作系统要求</span><span class="sxs-lookup"><span data-stu-id="faca4-117">SQL and OS requirements</span></span>                                                                                                                                                                                                                                                            |
|-----------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                  [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]                   |             [<span data-ttu-id="faca4-118">BizTalk Server 2016 的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="faca4-118">Hardware and Software Requirements for BizTalk Server 2016</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)             |                                      <span data-ttu-id="faca4-119">**SQL Server 的硬件和软件要求**:</span><span class="sxs-lookup"><span data-stu-id="faca4-119">**SQL Server hardware and software requirements**:</span></span> <br/><span data-ttu-id="faca4-120">[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)</span><span class="sxs-lookup"><span data-stu-id="faca4-120">[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)</span></span><br/><span data-ttu-id="faca4-121">[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="faca4-121">[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)</span></span><br/><br/><span data-ttu-id="faca4-122">**Windows Server 的硬件要求**:</span><span class="sxs-lookup"><span data-stu-id="faca4-122">**Windows Server hardware requirements**:</span></span> <br/>[<span data-ttu-id="faca4-123">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="faca4-123">Windows Server 2016</span></span>](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[<span data-ttu-id="faca4-124">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="faca4-124">Windows Server 2012</span></span>](https://technet.microsoft.com/library/jj134246.aspx)                                      |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> <span data-ttu-id="faca4-125">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="faca4-125">BizTalk Server 2013</span></span> | [<span data-ttu-id="faca4-126">BizTalk Server 2013 和 2013 R2 的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="faca4-126">Hardware and Software Requirements for BizTalk Server 2013 and 2013 R2</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) | <span data-ttu-id="faca4-127">**SQL Server 的硬件和软件要求**:</span><span class="sxs-lookup"><span data-stu-id="faca4-127">**SQL Server hardware and software requirements**:</span></span> <br/><span data-ttu-id="faca4-128">[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="faca4-128">[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)</span></span><br/><span data-ttu-id="faca4-129">[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)</span><span class="sxs-lookup"><span data-stu-id="faca4-129">[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)</span></span><br/><span data-ttu-id="faca4-130">[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)</span><span class="sxs-lookup"><span data-stu-id="faca4-130">[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)</span></span><br/><br/><span data-ttu-id="faca4-131">**Windows Server 的硬件要求**:</span><span class="sxs-lookup"><span data-stu-id="faca4-131">**Windows Server hardware requirements**:</span></span> <br/>[<span data-ttu-id="faca4-132">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="faca4-132">Windows Server 2012</span></span>](https://technet.microsoft.com/library/jj134246.aspx)<br/><span data-ttu-id="faca4-133">[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="faca4-133">[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)</span></span> |

> [!TIP] 
> <span data-ttu-id="faca4-134">列出的是最低硬件要求。</span><span class="sxs-lookup"><span data-stu-id="faca4-134">The hardware requirements listed are the minimum.</span></span> <span data-ttu-id="faca4-135">每个环境都不同，可能你的环境具有更高要求。</span><span class="sxs-lookup"><span data-stu-id="faca4-135">Every environment is different and there's a very good chance that your environment may need more.</span></span> <span data-ttu-id="faca4-136">请参阅 [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)（BizTalk Server 解决方案的安装、大小调整、部署和维护建议）。</span><span class="sxs-lookup"><span data-stu-id="faca4-136">See [Recommendations for Installing, Sizing, Deploying, and Maintaining a BizTalk Server Solution](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx).</span></span> 

## <a name="install-and-configure"></a><span data-ttu-id="faca4-137">安装和配置</span><span class="sxs-lookup"><span data-stu-id="faca4-137">Install and configure</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="faca4-138">开始之前</span><span class="sxs-lookup"><span data-stu-id="faca4-138">Before you begin</span></span>

* <span data-ttu-id="faca4-139">对于 BTARN 数据库中，BTARN 仅可配置 SQL Server 计算机名称和数据库名称属性。</span><span class="sxs-lookup"><span data-stu-id="faca4-139">For the BTARN database, BTARN only configures the SQL Server computer name and database name properties.</span></span> <span data-ttu-id="faca4-140">有关这些属性的信息存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="faca4-140">Information about these properties is stored in the registry.</span></span>
* <span data-ttu-id="faca4-141">使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="faca4-141">Sign in using an account that is a member of the BizTalk Server Administrators group.</span></span> 
* <span data-ttu-id="faca4-142">在 BizTalk Server 下载中，BTARN 安装过程中`\BizTalk Accelerators`文件夹。</span><span class="sxs-lookup"><span data-stu-id="faca4-142">In your BizTalk Server download, the BTARN setup is in the `\BizTalk Accelerators` folder.</span></span>
* <span data-ttu-id="faca4-143">必须安装 BizTalk Server，并且必须运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="faca4-143">BizTalk Server must be installed, and SQL Server must be running.</span></span>
* <span data-ttu-id="faca4-144">BTARN 和 BizTalk Server 需要 Microsoft.NET Framework 软件必备组件。</span><span class="sxs-lookup"><span data-stu-id="faca4-144">Both BTARN and BizTalk Server require Microsoft .NET Framework as software prerequisite.</span></span> <span data-ttu-id="faca4-145">如果必须在计算机上安装的.NET Framework 的多个版本，请确保 BtarnAPP Web 应用程序引用的.NET Framework 4.0 经典。</span><span class="sxs-lookup"><span data-stu-id="faca4-145">If you have multiple versions of .NET Framework installed on your computer, make sure that the BtarnAPP Web application is referencing .NET Framework 4.0 classic.</span></span> <span data-ttu-id="faca4-146">你可以使用 Internet 信息服务 (IIS) 管理器对此进行配置。</span><span class="sxs-lookup"><span data-stu-id="faca4-146">You can configure this by using the Internet Information Services (IIS) Manager.</span></span>  
* <span data-ttu-id="faca4-147">BizTalk 主机实例帐户和 BizTalk 独立主机实例帐户应该相同。</span><span class="sxs-lookup"><span data-stu-id="faca4-147">The BizTalk Host Instance Account and the BizTalk Isolated Host Instance Account should be the same.</span></span> <span data-ttu-id="faca4-148">否则，BTARN 将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="faca4-148">Otherwise, BTARN does not function correctly.</span></span>  
* <span data-ttu-id="faca4-149">BTARN，可将只有单个服务帐户，而不要使用组，添加到 BizTalk Server Administrators 组或 BizTalk Application Users 组。</span><span class="sxs-lookup"><span data-stu-id="faca4-149">BTARN allows you to add only individual service accounts, and not groups, to the BizTalk Server Administrators group or the BizTalk Application Users group.</span></span>  
* <span data-ttu-id="faca4-150">你需要为 BTSHTTPReceive.dll 创建 WebService 扩展，并配置 IIS 隔离模式。</span><span class="sxs-lookup"><span data-stu-id="faca4-150">You need to create a WebService extension for BTSHTTPReceive.dll, configuring the IIS isolation mode.</span></span> <span data-ttu-id="faca4-151">有关详细信息，请参阅上的"故障排除:: 问题和解决办法"主题中的"404 找不到错误时发送 HTTP 请求"条目[ http://go.microsoft.com/fwlink/?LinkId=188560 ](http://go.microsoft.com/fwlink/?LinkId=188560)。</span><span class="sxs-lookup"><span data-stu-id="faca4-151">For more information, see the "404 Not found error when sending a HTTP request" entry in the "Troubleshooting: Issues and Resolutions" topic at [http://go.microsoft.com/fwlink/?LinkId=188560](http://go.microsoft.com/fwlink/?LinkId=188560).</span></span> <span data-ttu-id="faca4-152">此外，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../../core/how-to-configure-iis-for-an-http-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="faca4-152">Also, see [How to Configure IIS for an HTTP Receive Location](../../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
* <span data-ttu-id="faca4-153">添加你的服务器 (http:// <*服务器名称*>) 到本地 Internet 区域中的 Internet Explorer 安全选项。</span><span class="sxs-lookup"><span data-stu-id="faca4-153">Add your server (http://<*server name*>) to the Local Internet zone in the Internet Explorer security options.</span></span>  
*  <span data-ttu-id="faca4-154">如果配置 BTARN 时使用的是采用非默认端口的远程 SQL 实例，则必须本地安装 SQL Server 客户端工具。</span><span class="sxs-lookup"><span data-stu-id="faca4-154">If a remote SQL instance using non default port is used for configuring BTARN, then the SQL Server Client Tools must be installed locally.</span></span> <span data-ttu-id="faca4-155">有关详细信息，请参阅[针对多计算机环境的 BizTalk Server 安装指南](../../install-and-config-guides/install-biztalk-server-in-a-multi-computer-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="faca4-155">For details, see [BizTalk Server Installation Guide for multicomputer environment](../../install-and-config-guides/install-biztalk-server-in-a-multi-computer-environment.md).</span></span>
*  <span data-ttu-id="faca4-156">在 BizTalk Server 配置的过程，必须为角色 BizTalk Administrator、 BizTalk Host Users 和 BizTalk Isolated Host Users 使用单独的组。</span><span class="sxs-lookup"><span data-stu-id="faca4-156">A separate group must be used for role - BizTalk Administrator, BizTalk Host Users, and BizTalk Isolated Host Users during the configuration of BizTalk Server.</span></span>  
*  <span data-ttu-id="faca4-157">BTARN 不支持使用针对 SQL 实例，若要配置 BTARN 数据库中创建的别名。</span><span class="sxs-lookup"><span data-stu-id="faca4-157">BTARN does not support the use of alias created for SQL instance to configure the BTARN database.</span></span>  

### <a name="install-btarn"></a><span data-ttu-id="faca4-158">安装 BTARN</span><span class="sxs-lookup"><span data-stu-id="faca4-158">Install BTARN</span></span>

1.  <span data-ttu-id="faca4-159">运行 BTARN **setup.exe**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="faca4-159">Run the BTARN **setup.exe** as Administrator.</span></span>

2.  <span data-ttu-id="faca4-160">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="faca4-160">Select **Install**.</span></span>  

3.  <span data-ttu-id="faca4-161">上**客户信息**页上，键入你的用户名、 组织和产品密钥，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="faca4-161">On the **Customer Information** page, type your user name, organization, and the product key, and then click **Next**.</span></span>  

4.  <span data-ttu-id="faca4-162">上**许可协议**页上，阅读最终用户许可协议，，然后单击**接受**。</span><span class="sxs-lookup"><span data-stu-id="faca4-162">On the **License Agreement** page, read the End User License Agreement, and then click **Accept**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="faca4-163">如果不接受许可协议，则无法继续安装。</span><span class="sxs-lookup"><span data-stu-id="faca4-163">If you do not accept the license agreement, you cannot continue with the installation.</span></span>  

5.  <span data-ttu-id="faca4-164">上**安装选项**页上，选择**完成**的完整安装或**自定义**部分安装。</span><span class="sxs-lookup"><span data-stu-id="faca4-164">On the **Installation Options** page, select **Complete** for a full installation or **Custom** for a partial installation.</span></span> <span data-ttu-id="faca4-165">请确保安装路径正确，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="faca4-165">Ensure the installation path is correct, and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="faca4-166">如果选择**自定义**，选择要从安装的组件**自定义安装**页。</span><span class="sxs-lookup"><span data-stu-id="faca4-166">If you select **Custom**, select the components to install from the **Custom Installation** page.</span></span> <span data-ttu-id="faca4-167">如果您选择安装 SDK 或文档组件，您必须运行安装程序之前安装.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="faca4-167">If you select to install SDK or Documentation components only, you must have .NET Framework installed before running the setup program.</span></span>  

6.  <span data-ttu-id="faca4-168">上**摘要**页上，查看的组件安装，然后依次**安装**。</span><span class="sxs-lookup"><span data-stu-id="faca4-168">On the **Summary** page, review the components you are installing, and then click **Install**.</span></span> <span data-ttu-id="faca4-169">**安装进度**屏幕将显示安装过程的进度。</span><span class="sxs-lookup"><span data-stu-id="faca4-169">The **Installation Progress** screen displays the progress of the installation procedure.</span></span>  

7.  <span data-ttu-id="faca4-170">上**安装已完成**页上，确保**运行配置向导**中已选中，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="faca4-170">On the **Installation Completed** page, ensure the **Run Configuration Wizard** box is selected, and then click **Finish**.</span></span>  

     <span data-ttu-id="faca4-171">BTARN 配置向导将打开。</span><span class="sxs-lookup"><span data-stu-id="faca4-171">The BTARN Configuration Wizard opens.</span></span> <span data-ttu-id="faca4-172">下一步将配置 BTARN。</span><span class="sxs-lookup"><span data-stu-id="faca4-172">Next, you configure BTARN.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="faca4-173">如果执行自定义安装来仅安装 BTARN HTTP 前端功能，BTARN 配置可能会失败，安装程序完成后，显示"未能为功能创建对象： WebApp"错误。</span><span class="sxs-lookup"><span data-stu-id="faca4-173">If you perform a custom installation to install only the BTARN HTTP Front End feature, BTARN configuration may fail after setup is complete, displaying the "Failed to create object for feature: WebApp" error.</span></span> <span data-ttu-id="faca4-174">如果发生这种情况，将两个文件复制 (**Microsoft.VC80.ATL.manifest**并**atl80.dll**) 与 BizTalk Server 的计算机上安装它，到安装了 BTARN HTTP 前端功能的计算机。</span><span class="sxs-lookup"><span data-stu-id="faca4-174">If this occurs, copy two files (**Microsoft.VC80.ATL.manifest** and **atl80.dll**) from a computer with BizTalk Server installed on it, to the computer where you installed the BTARN HTTP Front End feature.</span></span>  
    >   
    >  <span data-ttu-id="faca4-175">如果在 BizTalk Server 所在的计算机上安装 Visual Studio，两个文件的源文件夹是 *< 驱动器\>*: \Program Files\Microsoft Visual Studio 11.0\VC\redist\x86\Microsoft.VC100.ATL。</span><span class="sxs-lookup"><span data-stu-id="faca4-175">If Visual Studio is installed on the same computer as BizTalk Server, the source folder for the two files is *<drive\>*:\Program Files\Microsoft Visual Studio 11.0\VC\redist\x86\Microsoft.VC100.ATL.</span></span> <span data-ttu-id="faca4-176">如果在 BizTalk server 上未安装 Visual Studio，在 BizTalk server 上的两个文件的源文件夹是下的文件夹 *< 驱动器\>*: \WINDOWS\WinSxS。</span><span class="sxs-lookup"><span data-stu-id="faca4-176">If Visual Studio is not installed on the BizTalk server, the source folder for the two files on the BizTalk server is a folder under *<drive\>*:\WINDOWS\WinSxS.</span></span> <span data-ttu-id="faca4-177">这两个文件的版本应该是 8.0.50727.42。</span><span class="sxs-lookup"><span data-stu-id="faca4-177">The version of the files should be 8.0.50727.42.</span></span> <span data-ttu-id="faca4-178">在已安装 HTTP 前端功能的计算机上的目标文件夹为 BTARN 安装目录 (默认情况下 *< 驱动器\>*: \Program Files\Microsoft BTARN)。</span><span class="sxs-lookup"><span data-stu-id="faca4-178">The destination folder on the computer where you have installed the HTTP Front End feature is the BTARN installation directory (by default, *<drive\>*:\Program Files\Microsoft BTARN).</span></span>  
    >   
    >  <span data-ttu-id="faca4-179">这些文件复制到计算机安装了 HTTP 前端功能后，重新运行**Configuration.exe**。</span><span class="sxs-lookup"><span data-stu-id="faca4-179">After you have copied these files to the computer with the HTTP Front End feature installed, rerun **Configuration.exe**.</span></span>  

### <a name="configure-btarn"></a><span data-ttu-id="faca4-180">配置 BTARN</span><span class="sxs-lookup"><span data-stu-id="faca4-180">Configure BTARN</span></span>  

> [!TIP]
 >  <span data-ttu-id="faca4-181">配置 BTARN 之前，请确保映射在 IIS 中的处理程序映射的.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="faca4-181">Before configuring BTARN, make sure you map .NET Framework under Handler Mappings in IIS.</span></span> <span data-ttu-id="faca4-182">此外，在配置 BTARN 时，您可能需要手动创建 IIS_WPG 组。</span><span class="sxs-lookup"><span data-stu-id="faca4-182">Also, when configuring BTARN, you may need to create the IIS_WPG group manually.</span></span>  

1.  <span data-ttu-id="faca4-183">上**Microsoft BTARN 配置向导**页上，选择**基本配置**若要配置服务器的默认设置，或**自定义配置**到使用高级的配置选项将服务器配置。</span><span class="sxs-lookup"><span data-stu-id="faca4-183">On the **Microsoft BTARN Configuration Wizard** page, select **Basic configuration** to configure the server with default settings, or **Custom configuration** to configure the server using advanced configuration options.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="faca4-184">如果你想要配置 btarn，让使用本地管理员帐户，输入与帐户 *< 计算机名称\>\\< 管理员名称\>* 中**用户 ID**字段**服务凭据**区域。</span><span class="sxs-lookup"><span data-stu-id="faca4-184">If you want to configure BTARN using a local administrator account, enter the account as *<machine name\>\\<administrator name\>* in the **User ID** field of the **Service Credential** area.</span></span>  

2.  <span data-ttu-id="faca4-185">在中**数据库服务器名称**文字框中，验证显示的服务器名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="faca4-185">In the **Database server name** text box, verify that the server name displayed is correct.</span></span> <span data-ttu-id="faca4-186">在中**服务凭据**区域中，输入将在运行此服务帐户 （含有域名） 的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="faca4-186">In the **Service credential** area, enter the user name (with domain) and password for the account that the services will run under.</span></span> <span data-ttu-id="faca4-187">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="faca4-187">Click **Configure**.</span></span>  

3.  <span data-ttu-id="faca4-188">如果你的帐户具有管理权限，请单击**是**以继续进行配置。</span><span class="sxs-lookup"><span data-stu-id="faca4-188">If your account has administrative privileges, click **Yes** to proceed with the configuration.</span></span>  

4.  <span data-ttu-id="faca4-189">如果所选**基本配置**在步骤 1 中，验证要在中配置的组件列表**摘要**对话框中，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="faca4-189">If you selected **Basic configuration** in step 1, verify the list of components to be configured in the **Summary** dialog box, and then click **Next**.</span></span> <span data-ttu-id="faca4-190">转到步骤 10。</span><span class="sxs-lookup"><span data-stu-id="faca4-190">Go to step 10.</span></span>  

5.  <span data-ttu-id="faca4-191">如果所选**自定义配置**在步骤 1 中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="faca4-191">If you selected **Custom configuration** in step 1, perform the following steps:</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="faca4-192">如果你在任何 BTARN 数据库的名称中使用特殊字符，则 BTARN 配置将失败。</span><span class="sxs-lookup"><span data-stu-id="faca4-192">BTARN configuration will fail if you use a special character in the name of any of the BTARN databases.</span></span>  

6.  <span data-ttu-id="faca4-193">若要在中配置运行时， **Microsoft BTRAN 配置**对话框中，单击**运行时**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="faca4-193">To configure the runtime, in the **Microsoft BTRAN Configuration** dialog box, click **Runtime** in the left pane.</span></span> <span data-ttu-id="faca4-194">在右侧**运行时**窗格中，单击**启用此计算机上的运行时功能**。</span><span class="sxs-lookup"><span data-stu-id="faca4-194">In the right **Runtime** pane, click **Enable the Runtime feature on this computer**.</span></span> <span data-ttu-id="faca4-195">若要加入现有数据库组，请清除**你想要创建一个新数据库组**。</span><span class="sxs-lookup"><span data-stu-id="faca4-195">To join an existing database group, clear **Do you want to create a new database group**.</span></span> <span data-ttu-id="faca4-196">选择适当的 Web 服务器名称、端口号、数据存储区、应用程序池服务帐户和 BizTalk HTTP 接收虚拟文件夹。</span><span class="sxs-lookup"><span data-stu-id="faca4-196">Select the appropriate Web server name, port number, data stores, Application Pool service account, and BizTalk HTTP Receive virtual folder.</span></span>  

7.  <span data-ttu-id="faca4-197">若要配置 WebApps 功能，在**Microsoft BTRAN 配置**对话框中，单击**WebApps**在左窗格中，然后单击**启用此计算机上的运行时功能**.</span><span class="sxs-lookup"><span data-stu-id="faca4-197">To configure the WebApps feature, in the **Microsoft BTRAN Configuration** dialog box, click **WebApps** in the left pane, and then click **Enable the Runtime feature on this computer**.</span></span> <span data-ttu-id="faca4-198">输入相应的 BizTalk Server 名称和端口号，或选择默认值。</span><span class="sxs-lookup"><span data-stu-id="faca4-198">Enter the appropriate BizTalk Server name and port number, or select the defaults.</span></span> <span data-ttu-id="faca4-199">选择适当的 Web 应用程序虚拟文件夹。</span><span class="sxs-lookup"><span data-stu-id="faca4-199">Select the appropriate Web application virtual folder.</span></span>  

8.  <span data-ttu-id="faca4-200">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="faca4-200">Click **Apply Configuration**.</span></span>  

9. <span data-ttu-id="faca4-201">上**摘要**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="faca4-201">On the **Summary** page, click **Next**.</span></span>  

10. <span data-ttu-id="faca4-202">上**配置已完成**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="faca4-202">On the **Configuration Completed** page, click **Finish**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="faca4-203">安装了 BTARN 后，系统管理员必须将用户添加到 BAS Business User、Business Manager 和 Business Administrator 组。</span><span class="sxs-lookup"><span data-stu-id="faca4-203">After you install BTARN, your system administrator must add users to the BAS Business User, Business Manager, and Business Administrator groups.</span></span> <span data-ttu-id="faca4-204">如果你是系统管理员，则必须填充这些组并注销，然后登录将自己添加到这些组中。</span><span class="sxs-lookup"><span data-stu-id="faca4-204">If you are a system administrator, you will have to populate these groups and log off, and then log in adding yourself to the groups.</span></span>

    > [!WARNING]
    >  <span data-ttu-id="faca4-205">为 BizTalk Administrator、 BizTalk Host Users 和 BizTalk Isolated Host Users 配置 BizTalk Server 时，必须使用三个不同的组。</span><span class="sxs-lookup"><span data-stu-id="faca4-205">Three different groups must be used while configuring BizTalk Server for BizTalk Administrator, BizTalk Host Users, and BizTalk Isolated Host Users.</span></span>  

## <a name="start-the-artifacts"></a><span data-ttu-id="faca4-206">启动项目</span><span class="sxs-lookup"><span data-stu-id="faca4-206">Start the artifacts</span></span>
<span data-ttu-id="faca4-207">BTARN 业务流程、 发送端口和接收位置配置 BTARN 后不自动启动。</span><span class="sxs-lookup"><span data-stu-id="faca4-207">The BTARN orchestrations, send ports, and receive locations are not automatically started after you configure BTARN.</span></span>

> [!NOTE]
>  <span data-ttu-id="faca4-208">必须先启动 PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB 发送端口，然后才能启动 PrivateInitiatorProcess 和 PrivateResponderProcess 业务流程。</span><span class="sxs-lookup"><span data-stu-id="faca4-208">Start the PrivateInitiator_To_LOB and PrivateResponder_To_LOB send ports before you can start the PrivateInitiatorProcess and PrivateResponderProcess orchestrations.</span></span>  

-   <span data-ttu-id="faca4-209">对于某些计算机，如果已通过安全套接字层 (SSL) 配置了 Internet Information Services (IIS) 虚拟服务器，则必须先配置虚拟服务器以接受客户端证书。</span><span class="sxs-lookup"><span data-stu-id="faca4-209">On computers where you have configured an Internet Information Services (IIS) virtual server with Secure Sockets Layer (SSL), you must configure the virtual server to accept the client certificate.</span></span> <span data-ttu-id="faca4-210">请参阅[步骤 4： 启用安全套接字在 IIS 中的层](step-4-enabling-secure-sockets-layer-in-iis.md)中[双操作教程](double-action-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="faca4-210">See [Step 4: Enabling Secure Sockets Layer in IIS](step-4-enabling-secure-sockets-layer-in-iis.md) in the [Double Action Tutorial](double-action-tutorial.md).</span></span>


1.  <span data-ttu-id="faca4-211">打开**BizTalk Server 管理**以管理员身份。</span><span class="sxs-lookup"><span data-stu-id="faca4-211">Open **BizTalk Server Administration** as an administrator.</span></span>  

2.  <span data-ttu-id="faca4-212">展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk Application 1**。</span><span class="sxs-lookup"><span data-stu-id="faca4-212">Expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  

3.  <span data-ttu-id="faca4-213">单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="faca4-213">Click **Send Ports**.</span></span> <span data-ttu-id="faca4-214">在右窗格中，对于每个未启动的发送端口，右键单击，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="faca4-214">In the right pane, for each send port that is not started, right-click and then click **Start**.</span></span>  

4.  <span data-ttu-id="faca4-215">单击**接收端口**并**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="faca4-215">Click **Receive Ports** and **Receive Locations**.</span></span> <span data-ttu-id="faca4-216">在右窗格中，每个接收位置未启动的右键单击，然后再单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="faca4-216">In the right pane, for each receive location that is not started, right-click and then click **Start**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="faca4-217">必须启动 PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB 发送端口，然后才能启动 PrivateInitiatorProcess 和 PrivateResponderProcess 业务流程。</span><span class="sxs-lookup"><span data-stu-id="faca4-217">You must start the PrivateInitiator_To_LOB and PrivateResponder_To_LOB send ports before you can start the PrivateInitiatorProcess and PrivateResponderProcess orchestrations.</span></span>  

5.  <span data-ttu-id="faca4-218">单击**业务流程**并**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="faca4-218">Click **Orchestrations** and **Receive Locations**.</span></span> <span data-ttu-id="faca4-219">在右窗格中，未启动的每个业务流程，右键单击，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="faca4-219">In the right pane, for each orchestration that is not started, right-click and then click **Start**.</span></span>  

## <a name="restart-your-computer"></a><span data-ttu-id="faca4-220">重新启动计算机</span><span class="sxs-lookup"><span data-stu-id="faca4-220">Restart your computer</span></span>  

<span data-ttu-id="faca4-221">请重新启动计算机，以应用对配置和权限所做的任何修改。</span><span class="sxs-lookup"><span data-stu-id="faca4-221">Restart your computer to apply any modifications made in configuration and permissions.</span></span>  

> [!NOTE]
>  <span data-ttu-id="faca4-222">开发人员可能出于开发、阶段调试或测试目的，选择在单个服务器上安装并配置 BTARN。</span><span class="sxs-lookup"><span data-stu-id="faca4-222">Developers may choose to install and configure BTARN on a single server for development, staging, or testing purposes.</span></span> <span data-ttu-id="faca4-223">开发人员可使用此服务器编写自定义代码，并在用于生产之前对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="faca4-223">Developers use this server to write their own custom code and test it before moving it to production.</span></span>  

 <span data-ttu-id="faca4-224">有关在单个服务器上安装 BTARN 的详细信息，请参阅[Loopback 教程](loopback-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="faca4-224">For more information about installing BTARN on a single server, see the [Loopback Tutorial](loopback-tutorial.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="faca4-225">后续步骤</span><span class="sxs-lookup"><span data-stu-id="faca4-225">Next steps</span></span>  

* [<span data-ttu-id="faca4-226">升级 RosettaNet 加速器</span><span class="sxs-lookup"><span data-stu-id="faca4-226">Upgrade the RosettaNet accelerator</span></span>](upgrade-biztalk-accelerator-for-rosettanet.md)
* [<span data-ttu-id="faca4-227">卸载 RosettaNet 加速器</span><span class="sxs-lookup"><span data-stu-id="faca4-227">Uninstall the RosettaNet accelerator</span></span>](uninstall-biztalk-accelerator-for-rosettanet.md)
* [<span data-ttu-id="faca4-228">安装疑难解答和了解已知安装问题</span><span class="sxs-lookup"><span data-stu-id="faca4-228">Troubleshoot the installation and see the known install issues</span></span>](troubleshoot-known-issues-installation.md)