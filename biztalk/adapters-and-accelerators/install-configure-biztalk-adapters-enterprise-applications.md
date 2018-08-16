---
title: 安装企业应用程序的 BizTalk 适配器 |Microsoft Docs
description: 要求和 JD Edwards OneWorld，JD Edwards EnterpriseOne PeopleSoft Enterprise、 TIBCO Rendezvous 和 TIBCO Enterprise Message Service 的 BizTalk Server 上的安装步骤
ms.custom: ''
ms.date: 10/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7777b7027e51460e79a6dff6a591d8faa4fe57e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987518"
---
# <a name="install-and-configure-the-microsoft-biztalk-adapters-for-enterprise-applications"></a><span data-ttu-id="0ec96-103">安装和配置 Microsoft BizTalk 适配器的企业应用程序</span><span class="sxs-lookup"><span data-stu-id="0ec96-103">Install and configure the Microsoft BizTalk Adapters for Enterprise Applications</span></span> 
  
 <span data-ttu-id="0ec96-104">用于企业应用程序的 Microsoft BizTalk 适配器包括以下适配器：</span><span class="sxs-lookup"><span data-stu-id="0ec96-104">Microsoft BizTalk Adapters for Enterprise Applications includes the following adapters:</span></span>  
  
-   <span data-ttu-id="0ec96-105">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-105">Microsoft BizTalk Adapter for JD Edwards OneWorld</span></span>  
  
-   <span data-ttu-id="0ec96-106">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-106">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne</span></span>  
  
-   <span data-ttu-id="0ec96-107">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-107">Microsoft BizTalk Adapter for PeopleSoft Enterprise</span></span>  
  
-   <span data-ttu-id="0ec96-108">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-108">Microsoft BizTalk Adapter for TIBCO Rendezvous</span></span>  
  
-   <span data-ttu-id="0ec96-109">用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-109">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service</span></span>  


> [!IMPORTANT]
> - <span data-ttu-id="0ec96-110">进行任何配置更改之前备份所有数据</span><span class="sxs-lookup"><span data-stu-id="0ec96-110">Back up all data before you make any configuration changes</span></span>
> - <span data-ttu-id="0ec96-111">您必须非常熟悉特定企业应用程序进行任何配置更改之前</span><span class="sxs-lookup"><span data-stu-id="0ec96-111">You must be experienced with the specific enterprise application before you make any configuration changes</span></span>
  
## <a name="supported-versions--requirements"></a><span data-ttu-id="0ec96-112">支持的版本和要求</span><span class="sxs-lookup"><span data-stu-id="0ec96-112">Supported versions & requirements</span></span>

||<span data-ttu-id="0ec96-113">要求</span><span class="sxs-lookup"><span data-stu-id="0ec96-113">Requirements</span></span>|  
|---|---|
|<span data-ttu-id="0ec96-114">操作系统</span><span class="sxs-lookup"><span data-stu-id="0ec96-114">Operating System</span></span>|<span data-ttu-id="0ec96-115">适配器支持 BizTalk Server 相同的操作系统：</span><span class="sxs-lookup"><span data-stu-id="0ec96-115">The adapter supports the same OS as BizTalk Server:</span></span><ul><li>[<span data-ttu-id="0ec96-116">BizTalk Server 2016 要求</span><span class="sxs-lookup"><span data-stu-id="0ec96-116">BizTalk Server 2016 requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)</li><li>[<span data-ttu-id="0ec96-117">BizTalk Server 2013 R2 / 2013年要求</span><span class="sxs-lookup"><span data-stu-id="0ec96-117">BizTalk Server 2013 R2 / 2013 requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)</li></ul>|
|<span data-ttu-id="0ec96-118">支持的企业系统</span><span class="sxs-lookup"><span data-stu-id="0ec96-118">Supported enterprise system</span></span>|<span data-ttu-id="0ec96-119">[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)列出了受支持的版本</span><span class="sxs-lookup"><span data-stu-id="0ec96-119">[Supported Line-of-Business (LOB) and Enterprise systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported versions</span></span> |
|<span data-ttu-id="0ec96-120">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="0ec96-120">JD Edwards OneWorld XE</span></span> | <ul><li><span data-ttu-id="0ec96-121">在 Windows 上的 JD Edwards 企业服务器</span><span class="sxs-lookup"><span data-stu-id="0ec96-121">JD Edwards Enterprise server on Windows</span></span></li><li><span data-ttu-id="0ec96-122">在 Windows 上的 JD Edwards 部署服务器</span><span class="sxs-lookup"><span data-stu-id="0ec96-122">JD Edwards Deployment server on Windows</span></span></li></ul>|
|<span data-ttu-id="0ec96-123">JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="0ec96-123">JD Edwards EnterpriseOne</span></span> | <span data-ttu-id="0ec96-124">适配器调用 JD Edwards EnterpriseOne API 使用 JDBC 驱动程序需要数据库。</span><span class="sxs-lookup"><span data-stu-id="0ec96-124">The adapter calls the JD Edwards EnterpriseOne API that uses JDBC, which needs a driver for the database.</span></span> <span data-ttu-id="0ec96-125">如果安装 JD Edwards EnterpriseOne 的同时安装了 SQL 数据库，则需要 MS-SQL 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-125">If you install JD Edwards EnterpriseOne with a SQL database, you need MS-SQL drivers.</span></span> <span data-ttu-id="0ec96-126">同样如果您安装 JD Edwards EnterpriseOne 的 Oracle 数据库，则需要 Oracle 驱动程序;或者，如果安装了 DB2 数据库，则需要 DB2 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-126">Similarly if you installed JD Edwards EnterpriseOne with an Oracle database, you need Oracle drivers; or if you installed with a DB2 database, you need DB2 drivers.</span></span> |
|<span data-ttu-id="0ec96-127">PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="0ec96-127">PeopleSoft Enterprise</span></span> | <ul><li><span data-ttu-id="0ec96-128">Sun Systems Java 开发工具包 (JDK)</span><span class="sxs-lookup"><span data-stu-id="0ec96-128">Sun Systems Java Development Kit (JDK)</span></span></li><li><span data-ttu-id="0ec96-129">PeopleSoft 工具发行版本</span><span class="sxs-lookup"><span data-stu-id="0ec96-129">PeopleSoft Tools release</span></span></li><li><span data-ttu-id="0ec96-130">PeopleSoft 应用程序发行版本</span><span class="sxs-lookup"><span data-stu-id="0ec96-130">PeopleSoft Applications release</span></span></li><li><span data-ttu-id="0ec96-131">此适配器要求对 PeopleSoft 应用程序的修改。</span><span class="sxs-lookup"><span data-stu-id="0ec96-131">This adapter requires a modification to the PeopleSoft application.</span></span> <span data-ttu-id="0ec96-132">若要使用组件接口，自定义组件接口 GET_CI_INFO 上载到 PeopleSoft 中。</span><span class="sxs-lookup"><span data-stu-id="0ec96-132">To use component interfaces, upload a custom component interface, GET_CI_INFO, into PeopleSoft.</span></span> <span data-ttu-id="0ec96-133">GET_CI_INFO.pc 位于 Program Files\Common Files\Microsoft BizTalk Adapters 为 Enterprise Applications\PeopleSoft Enterprise(r) \Config\。</span><span class="sxs-lookup"><span data-stu-id="0ec96-133">GET_CI_INFO.pc is in Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Config\.</span></span></li></ul>|
|<span data-ttu-id="0ec96-134">TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0ec96-134">TIBCO Rendezvous</span></span> | <ul><li><span data-ttu-id="0ec96-135">必须在运行用于 TIBCO Rendezvous 的 BizTalk 适配器的计算机上安装 TIBCO Rendezvous 运行时组件</span><span class="sxs-lookup"><span data-stu-id="0ec96-135">The TIBCO Rendezvous run-time component must be installed on the computer where BizTalk Adapter for TIBCO Rendezvous is running</span></span></li><li><span data-ttu-id="0ec96-136">必须运行用于 TIBCO Rendezvous 的 BizTalk 适配器的计算机上配置的 TIBCO Rendezvous 许可证。</span><span class="sxs-lookup"><span data-stu-id="0ec96-136">The TIBCO Rendezvous license must be configured on the computer where BizTalk Adapter for TIBCO Rendezvous is running.</span></span></li><li><span data-ttu-id="0ec96-137">TIBCO Rendezvous 二进制文件目录必须对该适配器可见：在环境变量 PATH 值中，或在 BizTalk 服务器中的每个 Rendezvous 端口上指定。</span><span class="sxs-lookup"><span data-stu-id="0ec96-137">The TIBCO Rendezvous binaries directory must be visible to the adapter: either in the Environment variables PATH value, or specified on each Rendezvous port in BizTalk Server.</span></span> <span data-ttu-id="0ec96-138">这对于 Rendezvous 程序集查找它的库和可执行文件是必需的。</span><span class="sxs-lookup"><span data-stu-id="0ec96-138">This is necessary for the Rendezvous assembly to find its libraries and executable.</span></span></li></ul>|
|<span data-ttu-id="0ec96-139">TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="0ec96-139">TIBCO Enterprise Message Service</span></span> | <span data-ttu-id="0ec96-140">Enterprise Message Service (EMS) 版本 5.x 和更高版本包括一个客户端 SDK （使用 TIBCO EMS C# API）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-140">Enterprise Message Service (EMS) version 5.x and above includes a client SDK (using the TIBCO EMS C# API).</span></span> <span data-ttu-id="0ec96-141">用于 TIBCO EMS 的 BizTalk 适配器使用此与服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="0ec96-141">BizTalk Adapter for TIBCO EMS uses this to communicate with the server.</span></span> |


## <a name="jd-edwards-oneworld-xe"></a><span data-ttu-id="0ec96-142">JD Edwards OneWorld XE</span><span class="sxs-lookup"><span data-stu-id="0ec96-142">JD Edwards OneWorld XE</span></span>

<span data-ttu-id="0ec96-143">本部分包含有关使用用于 JD Edwards OneWorld XE 与 BizTalk Server 的 Microsoft BizTalk 适配器的密钥信息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-143">This sections includes key information on using the Microsoft BizTalk Adapter for JD Edwards OneWorld XE with BizTalk Server.</span></span>
  
### <a name="create-the-jar-files"></a><span data-ttu-id="0ec96-144">创建 JAR 文件</span><span class="sxs-lookup"><span data-stu-id="0ec96-144">Create the JAR Files</span></span>
 <span data-ttu-id="0ec96-145">本节介绍 JD Edwards OneWorld 与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器一起工作的要求。</span><span class="sxs-lookup"><span data-stu-id="0ec96-145">This section describes the requirements for JD Edwards OneWorld to work with Microsoft BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
#### <a name="jar-files-and-the-classpath"></a><span data-ttu-id="0ec96-146">JAR 文件和 CLASSPATH</span><span class="sxs-lookup"><span data-stu-id="0ec96-146">JAR Files and the CLASSPATH</span></span>  
 <span data-ttu-id="0ec96-147">JD Edwards OneWorld JAR 文件必须是可用于适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-147">JD Edwards OneWorld JAR files must be available to the adapter.</span></span> <span data-ttu-id="0ec96-148">例如，若要连接到 B7.3.3.3 版本，以下 jar 文件所需。</span><span class="sxs-lookup"><span data-stu-id="0ec96-148">For instance, to connect to B7.3.3.3 Version, the following jar files are required.</span></span> <span data-ttu-id="0ec96-149">具体取决于所连接的服务器，可能会更改 jar 文件列表：</span><span class="sxs-lookup"><span data-stu-id="0ec96-149">Depending on the server you connect, the jar file list may change:</span></span>
  
- <span data-ttu-id="0ec96-150">Connector.jar</span><span class="sxs-lookup"><span data-stu-id="0ec96-150">Connector.jar</span></span>    
- <span data-ttu-id="0ec96-151">Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="0ec96-151">Kernel.jar</span></span>  
  
  <span data-ttu-id="0ec96-152">这些文件位于运行 JD Edwards OneWorld 的计算机上的以下位置：</span><span class="sxs-lookup"><span data-stu-id="0ec96-152">These files are located on a computer running JD Edwards OneWorld, at the following locations:</span></span>  
  
- <span data-ttu-id="0ec96-153">JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar</span><span class="sxs-lookup"><span data-stu-id="0ec96-153">JD Edwards OneWorld XE_install_Directory\System\classes\Connector.jar</span></span>    
- <span data-ttu-id="0ec96-154">JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar</span><span class="sxs-lookup"><span data-stu-id="0ec96-154">JD Edwards OneWorld XE_install_Directory\System\classes\Kernel.jar</span></span>  
  
  <span data-ttu-id="0ec96-155">你可将这些文件复制到任何位置；但是，必须指定 CLASSPATH 中的 JAR 文件位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-155">You can copy these files to any location; however, you must specify the location of the JAR files in the CLASSPATH.</span></span> <span data-ttu-id="0ec96-156">CLASSPATH 必须包括文件的完整路径和 JAR 文件的名称（用分号隔开）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-156">The CLASSPATH must include both the full path of the file and the name of the JAR file (separated by a semicolon).</span></span>  
  
  <span data-ttu-id="0ec96-157">用于 JD Edwards OneWorld 的 BizTalk 适配器提供 JDEJAccess JAR 文件以用于 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="0ec96-157">BizTalk Adapter for JD Edwards OneWorld provides the JDEJAccess JAR file for use with JD Edwards OneWorld.</span></span> <span data-ttu-id="0ec96-158">默认情况下，JDEJAccess.jar 文件引用从*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise applications\j.d.Edwards OneWorld(r)\classes\JDEJAccess.jar*.</span><span class="sxs-lookup"><span data-stu-id="0ec96-158">By default, the JDEJAccess.jar file is referenced from *Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld(r)\classes\JDEJAccess.jar*.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="0ec96-159">你必须在可以使用用于 JD Edwards OneWorld 的 BizTalk 适配器之前验证 jdeinterop.ini 文件的注册。</span><span class="sxs-lookup"><span data-stu-id="0ec96-159">You must verify the registration of the jdeinterop.ini file before you can use BizTalk Adapter for JD Edwards OneWorld.</span></span> <span data-ttu-id="0ec96-160">请确保您包括在此文件的路径**JDE 传输属性**页面时 BizTalk Server 中创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-160">Make sure that you include a path to this file in the **JDE Transport Property** page when you create the send port in BizTalk Server.</span></span> <span data-ttu-id="0ec96-161">有关完整说明，请参阅"自定义 jdeinterop.ini 文件。"</span><span class="sxs-lookup"><span data-stu-id="0ec96-161">For a complete explanation, see "Customize the jdeinterop.ini File."</span></span>  
  
#### <a name="create-the-btslibinteropjar-file"></a><span data-ttu-id="0ec96-162">创建 BTSLIBinterop.jar 文件</span><span class="sxs-lookup"><span data-stu-id="0ec96-162">Create the BTSLIBinterop.jar File</span></span>  
<span data-ttu-id="0ec96-163">创建文件，并确认适配器都可以访问它。</span><span class="sxs-lookup"><span data-stu-id="0ec96-163">Create the file, and confirm it can be accessed by the adapter.</span></span> <span data-ttu-id="0ec96-164">使用下面的示例作为指南：</span><span class="sxs-lookup"><span data-stu-id="0ec96-164">Use the following sample as a guide:</span></span>  
  
1.  <span data-ttu-id="0ec96-165">创建包括以下代码的 BTSLIB.cmd 文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-165">Create the BTSLIB.cmd file that contains the following code:</span></span>  
  
    ```  
    define library BTSLIB  
    login  
    library BTSLIB  
    interface JDEAdapter  
    import B5500900  
    build  
    logout  
    ```  
  
2.  <span data-ttu-id="0ec96-166">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0ec96-166">Run the following command:</span></span>  
  
    ```  
    GenJava  /cmd  .\BTSLIB.cmd  
    ```  
  
### <a name="verify-your-setup"></a><span data-ttu-id="0ec96-167">验证您的安装程序</span><span class="sxs-lookup"><span data-stu-id="0ec96-167">Verify your setup</span></span>  
  
1.  <span data-ttu-id="0ec96-168">使用受支持的版本，包括服务包编号 ([受支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))。</span><span class="sxs-lookup"><span data-stu-id="0ec96-168">Use a supported version, including service pack number ([Supported Line-of-Business (LOB) and Enterprise systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)).</span></span> <span data-ttu-id="0ec96-169">服务包（ESU 和 ASU）更新系统二进制文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-169">Service packs (ESUs and ASUs) update the system binaries.</span></span> <span data-ttu-id="0ec96-170">必备的服务包提供用于导入的 ASU/ESU 菜单选项。</span><span class="sxs-lookup"><span data-stu-id="0ec96-170">The prerequisite service pack provides the ASU/ESU menu choice for import.</span></span>  
  
2.  <span data-ttu-id="0ec96-171">配置 jdeinterop.ini 文件以使用正确的驱动器进行日志记录，如果它不同于驱动器 c。例如，如果 TEMP 目录空间不足在 JD Edwards OneWorld 更新可能会失败。</span><span class="sxs-lookup"><span data-stu-id="0ec96-171">Configure the jdeinterop.ini file to use the correct drive for logging, if it differs from drive C. For example, your JD Edwards OneWorld update can fail if the TEMP directory is out of space.</span></span>  
  
3.  <span data-ttu-id="0ec96-172">确定是否必须添加用于左/右填充 JD Edwards OneWorld 字段的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-172">Determine whether you must add a configuration file for the left/right padding of the JD Edwards OneWorld fields.</span></span>  
  
4.  <span data-ttu-id="0ec96-173">请验证你的 JAVA_HOME 的环境变量指向 Java 开发工具包 (JDK) 安装以便从计算机上的任何程序启用 javac 和 java 命令。</span><span class="sxs-lookup"><span data-stu-id="0ec96-173">Verify that your JAVA_HOME environment variable is pointing to your Java Development Kit (JDK) installation to enable the javac and java commands from any program on the computer.</span></span>  
  
5.  <span data-ttu-id="0ec96-174">验证设置 CLASSPATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="0ec96-174">Verify that the CLASSPATH environment variable is set.</span></span> <span data-ttu-id="0ec96-175">这样，若要找到 Kernel.jar 和 Connect.jar 文件的 JD Edwards OneWorld 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-175">This enables BizTalk Adapter for JD Edwards OneWorld to locate the Kernel.jar and Connect.jar files.</span></span>  
  
    <span data-ttu-id="0ec96-176">JAR 文件的路径是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="0ec96-176">The path of the JAR files is case sensitive.</span></span>  
  
6.  <span data-ttu-id="0ec96-177">通过键入区分大小写的以下命令来测试环境。</span><span class="sxs-lookup"><span data-stu-id="0ec96-177">Test the environment by typing the following command, which is case sensitive.</span></span>  
  
    ```  
    javap -s -p com.microsoft.jde.JDEJAccess  
    ```  
  
7.  <span data-ttu-id="0ec96-178">你给出的命令 (javap) 是 Java 类文件拆装器：</span><span class="sxs-lookup"><span data-stu-id="0ec96-178">The command you give, javap, is the Java Class File Disassembler:</span></span>  
  
    ```  
    http://java.sun.com/j2se/1.3/docs/tooldocs/solaris/javap.html  
    ```  
  
8.  <span data-ttu-id="0ec96-179">`javap`命令拆分类文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-179">The `javap` command disassembles a class file.</span></span> <span data-ttu-id="0ec96-180">其输出取决于所使用的选项。</span><span class="sxs-lookup"><span data-stu-id="0ec96-180">Its output depends on the options used.</span></span> <span data-ttu-id="0ec96-181">如果未不使用任何选项，javap 输出包、 受保护，和公共字段和类传递给它的方法。</span><span class="sxs-lookup"><span data-stu-id="0ec96-181">If no options are used, javap prints out the package, protected, and public fields and methods of the classes passed to it.</span></span> <span data-ttu-id="0ec96-182">javap 打印其输出到 stdout。</span><span class="sxs-lookup"><span data-stu-id="0ec96-182">javap prints its output to stdout.</span></span>  
  
     <span data-ttu-id="0ec96-183">如果没有错误，所有 Java 文件及其依赖项都在 CLASSPATH 中。</span><span class="sxs-lookup"><span data-stu-id="0ec96-183">If there are no errors, all the Java files and their dependencies are in the CLASSPATH.</span></span>  
  
9. <span data-ttu-id="0ec96-184">通过配置本地主机文件中设置 DNS 解析 (*C:\WINNT\system32\drivers\etc\hosts*)，JD Edwards OneWorld 系统的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="0ec96-184">Set up the DNS resolution by configuring the local host file (*C:\WINNT\system32\drivers\etc\hosts*), with the server name of the JD Edwards OneWorld system.</span></span>  
  
### <a name="create-and-install-the-custom-package"></a><span data-ttu-id="0ec96-185">创建并安装自定义包</span><span class="sxs-lookup"><span data-stu-id="0ec96-185">Create and install the custom package</span></span>  
<span data-ttu-id="0ec96-186">安装 BTSREL 自定义包以使用用于 JD Edwards OneWorld 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-186">Install the BTSREL custom package to use BizTalk Adapter for JD Edwards OneWorld.</span></span> <span data-ttu-id="0ec96-187">本节介绍：</span><span class="sxs-lookup"><span data-stu-id="0ec96-187">This section describes:</span></span>  
  
-   <span data-ttu-id="0ec96-188">JD Edwards OneWorld 自定义包创建过程</span><span class="sxs-lookup"><span data-stu-id="0ec96-188">The JD Edwards OneWorld custom package-creation process</span></span>  
-   <span data-ttu-id="0ec96-189">如何创建并安装 BTSREL</span><span class="sxs-lookup"><span data-stu-id="0ec96-189">How to create and install BTSREL</span></span>  
-   <span data-ttu-id="0ec96-190">在 JD Edwards OneWorld 中创建的 BTSREL 对象</span><span class="sxs-lookup"><span data-stu-id="0ec96-190">The BTSREL objects created in JD Edwards OneWorld</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0ec96-191">BTSREL.exe 是一个自定义包（在 JD Edwards OneWorld 术语中为自动化的软件更新或 ASU）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-191">BTSREL.exe is a custom package (an automated software update, or ASU, in JD Edwards OneWorld terminology).</span></span> <span data-ttu-id="0ec96-192">它包含业务功能以提取元数据。</span><span class="sxs-lookup"><span data-stu-id="0ec96-192">It contains business functions to extract metadata.</span></span> <span data-ttu-id="0ec96-193">应为特定的 JD Edwards OneWorld 配置和版本创建自定义包。</span><span class="sxs-lookup"><span data-stu-id="0ec96-193">A custom package should be created for a specific configuration and version of JD Edwards OneWorld.</span></span>  
  
#### <a name="define-a-custom-package"></a><span data-ttu-id="0ec96-194">定义自定义包</span><span class="sxs-lookup"><span data-stu-id="0ec96-194">Define a custom package</span></span>  
 <span data-ttu-id="0ec96-195">自定义包是一个后发布的可交付结果，为特定目的（例如法规更改或增强功能）提供软件更改。</span><span class="sxs-lookup"><span data-stu-id="0ec96-195">A custom package is a post-release deliverable that provides software changes for specific purposes, such as regulatory changes or enhancements.</span></span> <span data-ttu-id="0ec96-196">这些自定义包是为特定功能创建的。</span><span class="sxs-lookup"><span data-stu-id="0ec96-196">These custom packages are created for specific functionality.</span></span> <span data-ttu-id="0ec96-197">例如，创建 BTSREL 来提取元数据。</span><span class="sxs-lookup"><span data-stu-id="0ec96-197">For example, BTSREL is created to extract metadata.</span></span> <span data-ttu-id="0ec96-198">当安装 BTSREL 自定义包时，它会更新在 JD Edwards OneWorld 环境中的选定的模块。</span><span class="sxs-lookup"><span data-stu-id="0ec96-198">When the BTSREL custom package is installed, it updates selected modules in the JD Edwards OneWorld environment.</span></span> <span data-ttu-id="0ec96-199">若要更新，必须将 BTSREL 对象合并到适当的 JD Edwards OneWorld 环境中。</span><span class="sxs-lookup"><span data-stu-id="0ec96-199">To update, BTSREL objects must be merged into the appropriate JD Edwards OneWorld environment.</span></span> <span data-ttu-id="0ec96-200">有关通过 BTSREL 进行更新的模块的详细列表，请参阅模块列表。</span><span class="sxs-lookup"><span data-stu-id="0ec96-200">For a detailed list of modules updated by BTSREL, see the list of modules.</span></span>  
  
#### <a name="install-the-btsrel-custom-package"></a><span data-ttu-id="0ec96-201">安装 BTSREL 自定义包</span><span class="sxs-lookup"><span data-stu-id="0ec96-201">Install the BTSREL custom package</span></span>   
<span data-ttu-id="0ec96-202">下载[BTSREL](https://www.microsoft.com/download/details.aspx?id=56113)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-202">Download [BTSREL](https://www.microsoft.com/download/details.aspx?id=56113).</span></span> <span data-ttu-id="0ec96-203">在部署服务器上安装它，然后将其部署到企业服务器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-203">Install it on the deployment server, and then deploy it to the enterprise server.</span></span>  
  
 <span data-ttu-id="0ec96-204">现有的 BTSREL.exe 程序包可直接用于 B7333 版本。</span><span class="sxs-lookup"><span data-stu-id="0ec96-204">The existing BTSREL.exe package directly works with the B7333 version.</span></span> <span data-ttu-id="0ec96-205">若要与 B7334 版本，然后运行包：</span><span class="sxs-lookup"><span data-stu-id="0ec96-205">For the package to work with the B7334 version, then:</span></span>  
  
1. <span data-ttu-id="0ec96-206">下载并将 BTSREL.exe 的内容提取到你的工作文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ec96-206">Download and extract the contents of BTSREL.exe to your working folder.</span></span>  
  
2. <span data-ttu-id="0ec96-207">同时修改**ReleaseLevelRequired**并**发行**B7334 Deployment.Inf 文件中的值。</span><span class="sxs-lookup"><span data-stu-id="0ec96-207">Modify both the **ReleaseLevelRequired** and the **Release** values to B7334 in the Deployment.Inf file.</span></span>  
  
3. <span data-ttu-id="0ec96-208">运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-208">Run the Setup.</span></span>  
  
   <span data-ttu-id="0ec96-209">若要安装 BTSREL，需要以下项：</span><span class="sxs-lookup"><span data-stu-id="0ec96-209">To install BTSREL, the following are required:</span></span>  
  
-   <span data-ttu-id="0ec96-210">部署服务器安装</span><span class="sxs-lookup"><span data-stu-id="0ec96-210">Deployment server installation</span></span>    
-   <span data-ttu-id="0ec96-211">安装工作台</span><span class="sxs-lookup"><span data-stu-id="0ec96-211">Installation Workbench</span></span>  
  
#### <a name="install-btsrel-on-the-deployment-server"></a><span data-ttu-id="0ec96-212">在部署服务器上安装 BTSREL</span><span class="sxs-lookup"><span data-stu-id="0ec96-212">Install BTSREL on the deployment server</span></span>  
 <span data-ttu-id="0ec96-213">自定义包仅适用于 Windows 操作系统，并与部署服务器一起使用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-213">The custom package only works on a Windows operating system, and is used with the deployment server.</span></span> <span data-ttu-id="0ec96-214">必须在部署服务器上，构建并随后部署到企业服务器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-214">It must be built on the deployment server, and then deployed to the enterprise server.</span></span> <span data-ttu-id="0ec96-215">企业服务器通常是生产服务器，并且可在 Windows 或 UNIX 的操作系统上使用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-215">The enterprise server is usually a production server, and can be on either a Windows or UNIX operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-216">将 ASU 应用于 JD Edwards OneWorld 部署服务器上，确认你已加入**更新**模式。</span><span class="sxs-lookup"><span data-stu-id="0ec96-216">When applying the ASU to the JD Edwards OneWorld deployment server, verify that you are in **Update** mode.</span></span> <span data-ttu-id="0ec96-217">**证明**模式中验证 ASU 中没有任何 bug 而**更新**模式应用 ASU 时已指定。</span><span class="sxs-lookup"><span data-stu-id="0ec96-217">The **Proof** mode verifies that there are no bugs in the ASU, whereas **Update** mode is designated for when you apply the ASU.</span></span>  
  
1.  <span data-ttu-id="0ec96-218">登录到部署服务器以用户身份**JDE**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-218">Sign in to the deployment server as user **JDE**.</span></span>  
  
2.  <span data-ttu-id="0ec96-219">在部署服务器 (root)/B7 文件夹上创建一个名为 BTSREL 的新文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ec96-219">Create a new folder, named BTSREL, on the Deployment Server (root) /B7 folder.</span></span>  
  
3.  <span data-ttu-id="0ec96-220">将 BTSREL.exe 复制到新创建的 BTSREL 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ec96-220">Copy BTSREL.exe to the newly created BTSREL folder.</span></span>  
  
4.  <span data-ttu-id="0ec96-221">从.../B7/BTSREL 文件夹运行 BTSREL.exe。</span><span class="sxs-lookup"><span data-stu-id="0ec96-221">Run BTSREL.exe from the.../B7/BTSREL folder.</span></span> <span data-ttu-id="0ec96-222">安装管理器会自动启动。</span><span class="sxs-lookup"><span data-stu-id="0ec96-222">The installation manager automatically starts.</span></span>  
  
5.  <span data-ttu-id="0ec96-223">在安装程序窗口中，选择**下一步**，然后选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-223">In the setup window, select **Next**, and then select **Finish**.</span></span> <span data-ttu-id="0ec96-224">如果安装成功，将显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-224">A message displays if the installation is successful.</span></span>  
  
6.  <span data-ttu-id="0ec96-225">登录到 JDEPLAN 环境**JDE** JD Edwards OneWorld 部署服务器上的用户。</span><span class="sxs-lookup"><span data-stu-id="0ec96-225">Sign to the JDEPLAN environment as the**JDE** user on the JD Edwards OneWorld deployment server.</span></span>  
  
    1.  <span data-ttu-id="0ec96-226">如果系统上未安装包括 SAR #4533357 的电子软件更新 (ESU)，选择**软件更新**从**系统安装工具**菜单 (GH9612)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-226">If the electronic software update (ESU) that includes SAR #4533357 is not installed on the system, select **Software Updates** from the **System Installation Tools** menu (GH9612).</span></span>  
  
    2.  <span data-ttu-id="0ec96-227">中的选项 1 输入 02**处理选项**面板。</span><span class="sxs-lookup"><span data-stu-id="0ec96-227">Enter 02 for option 1 in the **Processing Options** panel.</span></span>  
  
    3.  <span data-ttu-id="0ec96-228">如果安装包括 SAR #4533357 ESU 后系统上，选择**应用程序软件更新**从**系统安装工具**菜单 (GH9612)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-228">If the ESU that includes SAR #4533357 has been installed on the system, select **Application Software Update** from the **System Installation Tools** menu (GH9612).</span></span>  
  
#### <a name="install-btsrel-on-the-jd-edwards-oneworld-workbench"></a><span data-ttu-id="0ec96-229">在 JD Edwards OneWorld 工作台上安装 BTSREL</span><span class="sxs-lookup"><span data-stu-id="0ec96-229">Install BTSREL on the JD Edwards OneWorld WorkBench</span></span>  
   
1.  <span data-ttu-id="0ec96-230">上**使用应用程序更新**屏幕上，双击 BTSREL 更新，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-230">On the **Work with Application Update** screen, double-click the BTSREL update, and then select **Next**.</span></span>  
  
2.  <span data-ttu-id="0ec96-231">双击要安装，更新的环境，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-231">Double-click the environments where you want the update installed, and then select **Next**.</span></span>  
  
    1.  <span data-ttu-id="0ec96-232">检查**无人参与的工作台**如果你想要在无人参与模式下运行的软件更新。</span><span class="sxs-lookup"><span data-stu-id="0ec96-232">Check **Unattended Workbench** if you want the software update to run in unattended mode.</span></span>  
  
    2.  <span data-ttu-id="0ec96-233">选择**备份**如果你希望规范的备份 （以便可以还原原始的规范）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-233">Select **Backup** if you want the backup of the specifications (so that the original specifications can be restored).</span></span>  
  
3.  <span data-ttu-id="0ec96-234">上**使用安装计划**屏幕上，选择要安装的更新的计划，然后**选择**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-234">On the **Work with Installation Plan** screen, select the plan for the update you are installing, and then **Select**.</span></span>  
  
4.  <span data-ttu-id="0ec96-235">安装完成后，请查看自动生成的 PDF 是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="0ec96-235">See the automatically generated PDFs for errors after the installation is finished.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ec96-236">如果出现错误，在 JD Edwards OneWorld 软件更新指南中查找故障排除技巧，或直接与 JD Edwards OneWorld 联系。</span><span class="sxs-lookup"><span data-stu-id="0ec96-236">If errors occur, look in the JD Edwards OneWorld Software Update Guide for troubleshooting tips, or contact JD Edwards OneWorld directly.</span></span>  
  
5.  <span data-ttu-id="0ec96-237">手动注册业务函数库使用"手动注册业务函数库"在本部分中所描述的步骤。</span><span class="sxs-lookup"><span data-stu-id="0ec96-237">Manually register the business function library using the steps included in "Manually register the business function library" in this section.</span></span>  
  
#### <a name="uninstall-the-custom-package"></a><span data-ttu-id="0ec96-238">卸载自定义包</span><span class="sxs-lookup"><span data-stu-id="0ec96-238">Uninstall the custom package</span></span>  
 <span data-ttu-id="0ec96-239">无需卸载自定义包。</span><span class="sxs-lookup"><span data-stu-id="0ec96-239">There is no requirement to uninstall the custom package.</span></span> <span data-ttu-id="0ec96-240">但是，如果想要清理系统，可以不同方式卸载。</span><span class="sxs-lookup"><span data-stu-id="0ec96-240">However, if you want to clean the system, you can uninstall in different ways.</span></span> <span data-ttu-id="0ec96-241">卸载后，重新生成包使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="0ec96-241">After you uninstall, rebuild the package using one of the following methods:</span></span>  
  
- <span data-ttu-id="0ec96-242">使用 JD Edwards OneWorld 部署服务器 Gh8612 — P96470，在**行**菜单中，选择**更新**，然后选择**卸载**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-242">Use the JD Edwards OneWorld Deployment Server, Gh8612—P96470, on the **ROW** menu, select **Update**, and then select **Uninstall**.</span></span>    
- <span data-ttu-id="0ec96-243">将所有自定义对象 (BTSREL) 签出到客户端计算机并将其删除。</span><span class="sxs-lookup"><span data-stu-id="0ec96-243">Check out all the custom objects (BTSREL) to a client computer and delete them.</span></span>    
- <span data-ttu-id="0ec96-244">应用之前的数据库快照。</span><span class="sxs-lookup"><span data-stu-id="0ec96-244">Apply a previous snapshot of database.</span></span>  
  
  <span data-ttu-id="0ec96-245">在清理过程中，验证对 JD Edwards OneWorld 的其他对象做出的任何其他修改。</span><span class="sxs-lookup"><span data-stu-id="0ec96-245">During the clean-up, verify any other modifications to the other objects of JD Edwards OneWorld.</span></span>  
  
#### <a name="manually-register-the-business-function-library"></a><span data-ttu-id="0ec96-246">手动注册业务函数库</span><span class="sxs-lookup"><span data-stu-id="0ec96-246">Manually register the business function library</span></span>  
 <span data-ttu-id="0ec96-247">由于 JD Edwards OneWorld 产品打包过程的限制，用于 JD Edwards OneWorld 的 BizTalk 适配器的自定义业务函数库 DLL 必须使用 JD Edwards OneWorld 进行手动注册。</span><span class="sxs-lookup"><span data-stu-id="0ec96-247">Because of a limitation of the JD Edwards OneWorld product packaging process, the custom Business Function Library DLL for BizTalk Adapter for JD Edwards OneWorld must be manually registered with JD Edwards OneWorld.</span></span> <span data-ttu-id="0ec96-248">此过程包括以下步骤。</span><span class="sxs-lookup"><span data-stu-id="0ec96-248">This process consists of the following steps.</span></span>
  
##### <a name="step-1-create-the-custom-business-function-library"></a><span data-ttu-id="0ec96-249">步骤 1： 创建自定义业务函数库</span><span class="sxs-lookup"><span data-stu-id="0ec96-249">Step 1: Create the custom business function library</span></span>  
 <span data-ttu-id="0ec96-250">使用 JD Edwards OneWorld 对象管理工作台 (OMW) 创建自定义业务函数库。</span><span class="sxs-lookup"><span data-stu-id="0ec96-250">Using JD Edwards OneWorld Object Management Workbench (OMW), create the Custom Business Function Library.</span></span> <span data-ttu-id="0ec96-251">下面的过程必须在初始安装中，执行，并适用于所有平台。</span><span class="sxs-lookup"><span data-stu-id="0ec96-251">The following procedure must be performed on initial setup, and applies to all platforms.</span></span>  
  
1.  <span data-ttu-id="0ec96-252">启动对象管理工作台 (快速路径:"OMW"或菜单选项： GH902 对象： P98220)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-252">Start the Object Management Workbench (fast path: "OMW" or menu selection: GH902 Object: P98220).</span></span>  
  
2.  <span data-ttu-id="0ec96-253">选择**外**，然后选择的选项**业务函数库**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-253">Select **Add**, and select the option for **Business Function Library**.</span></span>  
  
3.  <span data-ttu-id="0ec96-254">对新业务函数库对象输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="0ec96-254">Enter the following information for the New Business Function Library Object:</span></span>  
  
    -   <span data-ttu-id="0ec96-255">**名称：** ACBLIB</span><span class="sxs-lookup"><span data-stu-id="0ec96-255">**Name:** ACBLIB</span></span>    
    -   <span data-ttu-id="0ec96-256">**说明：** Microsoft DLL</span><span class="sxs-lookup"><span data-stu-id="0ec96-256">**Description:** Microsoft DLL</span></span>    
    -   <span data-ttu-id="0ec96-257">**产品代码：** 55</span><span class="sxs-lookup"><span data-stu-id="0ec96-257">**Product Code:** 55</span></span>    
    -   <span data-ttu-id="0ec96-258">**产品系统代码：** 55</span><span class="sxs-lookup"><span data-stu-id="0ec96-258">**Product System Code:** 55</span></span>  
  
4.  <span data-ttu-id="0ec96-259">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="0ec96-259">Select **OK**.</span></span>  
  
##### <a name="step-2-rebuild-libraries-from-the-deployment-server"></a><span data-ttu-id="0ec96-260">步骤 2： 重新生成库从部署服务器</span><span class="sxs-lookup"><span data-stu-id="0ec96-260">Step 2: Rebuild libraries from the deployment server</span></span>  
<span data-ttu-id="0ec96-261">完成初始安装程序为每个平台上的以下步骤。</span><span class="sxs-lookup"><span data-stu-id="0ec96-261">Complete the following steps on initial setup for each platform.</span></span>  
  
1.  <span data-ttu-id="0ec96-262">若要在独立模式下启动 BusBuild 程序，请选择**启动**，选择**运行**，然后选择**busbuild.exe**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-262">To start the BusBuild program in a standalone mode, select **Start**, select  **Run**, and then select **busbuild.exe**.</span></span>
  
2.  <span data-ttu-id="0ec96-263">在 pathcode （PY7333，PD7333 或 DV7333） 中登录到 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="0ec96-263">Sign in to JD Edwards OneWorld in the pathcode (PY7333, PD7333, or DV7333).</span></span>  
  
3.  <span data-ttu-id="0ec96-264">在中**重新生成库**列表中，选择**生成**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-264">In the **Rebuild Libraries** list, select the **Build**.</span></span>  
  
##### <a name="step-3-copy-the-custom-dll"></a><span data-ttu-id="0ec96-265">步骤 3： 复制自定义 DLL</span><span class="sxs-lookup"><span data-stu-id="0ec96-265">Step 3: Copy the Custom DLL</span></span>  
 <span data-ttu-id="0ec96-266">将自定义 DLL 从 pathcode 目录复制到 JD Edwards OneWorld 部署服务器和 JD Edwards OneWorld 企业服务器上的父包目录。</span><span class="sxs-lookup"><span data-stu-id="0ec96-266">Copy the custom DLL from the pathcode directory to the parent package directories on the JD Edwards OneWorld deployment server and on the JD Edwards OneWorld Enterprise Server.</span></span>
  
<span data-ttu-id="0ec96-267">**JD Edwards OneWorld XE 部署服务器上**</span><span class="sxs-lookup"><span data-stu-id="0ec96-267">**On the JD Edwards OneWorld XE Deployment Server**</span></span>  
  
1.  <span data-ttu-id="0ec96-268">将 ACBLIB.dll 从 DV7333\bin32 复制到 DV7333\Packages\DV7333FA\bin32。</span><span class="sxs-lookup"><span data-stu-id="0ec96-268">Copy ACBLIB.dll from DV7333\bin32 to DV7333\Packages\DV7333FA\bin32.</span></span>  
  
2.  <span data-ttu-id="0ec96-269">将 ACBLIB.def、ACBLIB.dmp 和 ACBLIB.mak 从 DV7333\obj 文件夹复制到 DV7333\Packages\DV7333FA\obj 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ec96-269">Copy ACBLIB.def, ACBLIB.dmp, and ACBLIB.mak from DV7333\obj folder to DV7333\Packages\DV7333FA\obj folder.</span></span>  
  
3.  <span data-ttu-id="0ec96-270">ACBLIB.exp、 ACBLIB.lib 和 sACBLIB.lib DV7333\lib32 文件夹复制到 DV7333\Packages\DV7333FA\lib32 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ec96-270">Copy ACBLIB.exp, ACBLIB.lib, and sACBLIB.lib from DV7333\lib32 folder to DV7333\Packages\DV7333FA\lib32 folder.</span></span>  
  
<span data-ttu-id="0ec96-271">**JD Edwards OneWorld 企业服务器上**</span><span class="sxs-lookup"><span data-stu-id="0ec96-271">**On the JD Edwards OneWorld Enterprise Server**</span></span>  
  
<span data-ttu-id="0ec96-272">在创建每个目录和文件后，验证授权。</span><span class="sxs-lookup"><span data-stu-id="0ec96-272">After each directory and file is created, verify the authorization.</span></span>  
  
1.  <span data-ttu-id="0ec96-273">创建一个目录 ACBLIB 下 DV7333FA\obj\\。</span><span class="sxs-lookup"><span data-stu-id="0ec96-273">Create a directory ACBLIB under DV7333FA\obj\\.</span></span>  
  
2.  <span data-ttu-id="0ec96-274">创建一个目录 ACBLIB DV7333FA\source 下。</span><span class="sxs-lookup"><span data-stu-id="0ec96-274">Create a directory ACBLIB under DV7333FA\source.</span></span>  
  
3.  <span data-ttu-id="0ec96-275">从部署服务器 DV7333\source 目录到 DV7333FA\source\ACBLIB 目录的 FTP b5500900.c。</span><span class="sxs-lookup"><span data-stu-id="0ec96-275">FTP b5500900.c from Deployment Server DV7333\source directory to DV7333FA\source\ACBLIB directory.</span></span>  
  
4.  <span data-ttu-id="0ec96-276">FTP b5500900.h 从部署服务器 DV7333\include 目录复制到 DV7333FA\include 目录。</span><span class="sxs-lookup"><span data-stu-id="0ec96-276">FTP b5500900.h from Deployment Server DV7333\include directory to DV7333FA\include directory.</span></span>  
  
##### <a name="step-4-build-a-full-package"></a><span data-ttu-id="0ec96-277">步骤 4： 生成完整的包</span><span class="sxs-lookup"><span data-stu-id="0ec96-277">Step 4: Build a Full Package</span></span>  
 <span data-ttu-id="0ec96-278">由于 JD Edwards 包生成过程的限制，生成的环境中向其应用了 BTSREL 更新，或更新包内部版本无法正常工作的完整包。</span><span class="sxs-lookup"><span data-stu-id="0ec96-278">Because of a limitation of the JD Edwards package-build process, build a full package for the environments to which you applied the BTSREL update, or the update package build does not work correctly.</span></span> <span data-ttu-id="0ec96-279">请参阅有关如何生成完整包内部版本的 JD Edwards 文档。</span><span class="sxs-lookup"><span data-stu-id="0ec96-279">See the JD Edwards documentation on how to build a full package build.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-280">当应用 JD Edwards OneWorld ASU/ESU 时，ASU/ESU 通常不创建新的库和业务函数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-280">When you apply JD Edwards OneWorld ASU/ESUs, the ASU/ESU does not typically create new library and business functions.</span></span> <span data-ttu-id="0ec96-281">因此，该过程很简单： 但是，用于 JD Edwards OneWorld 自定义软件包的 BizTalk 适配器创建新的库。</span><span class="sxs-lookup"><span data-stu-id="0ec96-281">Therefore, the process is simple: however, the BizTalk Adapter for JD Edwards OneWorld custom package creates a new library.</span></span> <span data-ttu-id="0ec96-282">因此，必须执行额外的步骤，例如，手动创建一个目录并运行完整包内部版本。</span><span class="sxs-lookup"><span data-stu-id="0ec96-282">Therefore, you must perform extra steps, such as manually create a directory and run a full package build.</span></span>  
  
#### <a name="modules-list"></a><span data-ttu-id="0ec96-283">模块列表</span><span class="sxs-lookup"><span data-stu-id="0ec96-283">Modules list</span></span>  
 <span data-ttu-id="0ec96-284">自定义包 BTSREL 在 JD Edwards OneWorld 中创建以下对象。</span><span class="sxs-lookup"><span data-stu-id="0ec96-284">The BTSREL custom package creates the following objects in JD Edwards OneWorld.</span></span> <span data-ttu-id="0ec96-285">BTSREL 包含用来提取元数据的业务功能和测试数据类型的自定义函数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-285">BTSREL contains business functions to extract metadata and custom functions to test the data types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-286">JD Edwards OneWorld 的更新中有一个 bug。</span><span class="sxs-lookup"><span data-stu-id="0ec96-286">There is a bug in the JD Edwards OneWorld update.</span></span> <span data-ttu-id="0ec96-287">如果没有所有业务和自定义函数，请验证已完成的是完整包内部版本，而不是更新包内部版本。</span><span class="sxs-lookup"><span data-stu-id="0ec96-287">If you don't have all the business and custom functions, verify that a full package build was completed, rather than an update package build.</span></span>  
>  
>  <span data-ttu-id="0ec96-288">如果列表缺失文件，例如，在 ACBTEST 之下有所有内容而其上没有任何内容，则你可能缺失数据字典 (DD) 项目。</span><span class="sxs-lookup"><span data-stu-id="0ec96-288">If you are missing files from the list, for example, if you have everything below ACBTEST but nothing above it, you might be missing the Data Dictionary (DD) items.</span></span> <span data-ttu-id="0ec96-289">你可以转到**使用数据项**，查找缺少的文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-289">You can go to **Work With Data Items** and look for missing files.</span></span>  
>   
>  <span data-ttu-id="0ec96-290">如果缺失其他项，例如 ACBCHAR01、 ACBDATE01、 ADBINT01、 ACBMATH01 和 ACBSTR01，这些是*主数据元素*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-290">If you are missing other items, such as ACBCHAR01, ACBDATE01, ADBINT01, ACBMATH01, and ACBSTR01, these are the *Primary Data Elements*.</span></span> <span data-ttu-id="0ec96-291">如果你从及计划者到开发人员合并对象，许多报表将在后台运行。</span><span class="sxs-lookup"><span data-stu-id="0ec96-291">When you merge objects from planner to DEV, many reports run in the background.</span></span> <span data-ttu-id="0ec96-292">你可以打开合并报告并检查错误。</span><span class="sxs-lookup"><span data-stu-id="0ec96-292">You can open the merge reports and look for errors.</span></span> <span data-ttu-id="0ec96-293">报告应列出的所有项目并指示它们已完成，且无错误或警告。</span><span class="sxs-lookup"><span data-stu-id="0ec96-293">The reports should list all the items and indicate that they were completed without errors or warnings.</span></span> <span data-ttu-id="0ec96-294">有了此验证，你可以继续，因为所有项都已检查过。</span><span class="sxs-lookup"><span data-stu-id="0ec96-294">With this verification, you can continue because all items are accounted for.</span></span>  
  
-   <span data-ttu-id="0ec96-295">ACBCHAR01 - 测试字符类型 01</span><span class="sxs-lookup"><span data-stu-id="0ec96-295">ACBCHAR01 - TEST CHAR TYPE 01</span></span>  
  
-   <span data-ttu-id="0ec96-296">ACBCUST - ACB 客户 ID</span><span class="sxs-lookup"><span data-stu-id="0ec96-296">ACBCUST - ACB CUSTOMER ID</span></span>  
  
-   <span data-ttu-id="0ec96-297">ACBDATE01 - 测试数据类型 01</span><span class="sxs-lookup"><span data-stu-id="0ec96-297">ACBDATE01 - TEST DATE TYPE 01</span></span>  
  
-   <span data-ttu-id="0ec96-298">ACBDEF - ACB 函数类型定义</span><span class="sxs-lookup"><span data-stu-id="0ec96-298">ACBDEF - ACB FUNCTION TYPE DEFINITION</span></span>  
  
-   <span data-ttu-id="0ec96-299">ACBFCNT - ACB 函数名称列表计数</span><span class="sxs-lookup"><span data-stu-id="0ec96-299">ACBFCNT - ACB FUNCTION NAME LIST COUNT</span></span>  
  
-   <span data-ttu-id="0ec96-300">ACBFUNC - ACB 函数名称列表</span><span class="sxs-lookup"><span data-stu-id="0ec96-300">ACBFUNC - ACB FUNCTION NAME LIST</span></span>  
  
-   <span data-ttu-id="0ec96-301">ACBFUNCN - ACB 函数名称</span><span class="sxs-lookup"><span data-stu-id="0ec96-301">ACBFUNCN - ACB FUNCTION NAME</span></span>  
  
-   <span data-ttu-id="0ec96-302">ACBINT01 - 测试整数类型 01</span><span class="sxs-lookup"><span data-stu-id="0ec96-302">ACBINT01 - TEST INTEGER TYPE 01</span></span>  
  
-   <span data-ttu-id="0ec96-303">ACBLIB - 控制 BROKER 库</span><span class="sxs-lookup"><span data-stu-id="0ec96-303">ACBLIB - CONTROL BROKER LIBRARY</span></span>  
  
-   <span data-ttu-id="0ec96-304">ACBMATH01 - 测试数学类型 01</span><span class="sxs-lookup"><span data-stu-id="0ec96-304">ACBMATH01 - TEST MATH TYPE 01</span></span>  
  
-   <span data-ttu-id="0ec96-305">ACBNEWS - ACB 新状态</span><span class="sxs-lookup"><span data-stu-id="0ec96-305">ACBNEWS - ACB NEW STATUS</span></span>  
  
-   <span data-ttu-id="0ec96-306">ACBORDER - ACB 订单号</span><span class="sxs-lookup"><span data-stu-id="0ec96-306">ACBORDER - ACB ORDER NUMBER</span></span>  
  
-   <span data-ttu-id="0ec96-307">ACBPRC - ACB 商品价格</span><span class="sxs-lookup"><span data-stu-id="0ec96-307">ACBPRC - ACB ITEM PRICE</span></span>  
  
-   <span data-ttu-id="0ec96-308">ACBPROD - ACB 产品 ID</span><span class="sxs-lookup"><span data-stu-id="0ec96-308">ACBPROD - ACB PRODUCT ID</span></span>  
  
-   <span data-ttu-id="0ec96-309">ACBQTY - ACB 商品数量</span><span class="sxs-lookup"><span data-stu-id="0ec96-309">ACBQTY - ACB ITEM QUANTITY</span></span>  
  
-   <span data-ttu-id="0ec96-310">ACBRES - ACB 结果指示器</span><span class="sxs-lookup"><span data-stu-id="0ec96-310">ACBRES - ACB RESULT INDICATOR</span></span>  
  
-   <span data-ttu-id="0ec96-311">ACBSTAT - ACB 状态</span><span class="sxs-lookup"><span data-stu-id="0ec96-311">ACBSTAT - ACB STATUS</span></span>  
  
-   <span data-ttu-id="0ec96-312">ACBSTR01 - 测试字符串类型 01</span><span class="sxs-lookup"><span data-stu-id="0ec96-312">ACBSTR01 - TEST STRING TYPE 01</span></span>  
  
-   <span data-ttu-id="0ec96-313">ACBTEST - ACB 测试屏幕</span><span class="sxs-lookup"><span data-stu-id="0ec96-313">ACBTEST - ACB TEST SCREEN</span></span>  
  
-   <span data-ttu-id="0ec96-314">ACBTEST2 - ACB 测试屏幕 2</span><span class="sxs-lookup"><span data-stu-id="0ec96-314">ACBTEST2 - ACB TEST SCREEN 2</span></span>  
  
-   <span data-ttu-id="0ec96-315">ACBTEST3 - ACB 测试屏幕 3</span><span class="sxs-lookup"><span data-stu-id="0ec96-315">ACBTEST3 - ACB TEST SCREEN 3</span></span>  
  
-   <span data-ttu-id="0ec96-316">B5500900 - 控制 BROKER 支持模块</span><span class="sxs-lookup"><span data-stu-id="0ec96-316">B5500900 - CONTROL BROKER SUPPORT MODULE</span></span>  
  
-   <span data-ttu-id="0ec96-317">D5500900 - 控制 BROKER 数据结构</span><span class="sxs-lookup"><span data-stu-id="0ec96-317">D5500900 - CONTROL BROKER DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="0ec96-318">D5500900A - 控制 BROKER 数据结构</span><span class="sxs-lookup"><span data-stu-id="0ec96-318">D5500900A - CONTROL BROKER DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="0ec96-319">D5500900B - FETCH 价格数据结构</span><span class="sxs-lookup"><span data-stu-id="0ec96-319">D5500900B - FETCH PRICE DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="0ec96-320">D5500900C - 获得客户状态数据结构</span><span class="sxs-lookup"><span data-stu-id="0ec96-320">D5500900C - GET CUSTOMER STATUS DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="0ec96-321">D5500900D - 设置客户状态数据结构</span><span class="sxs-lookup"><span data-stu-id="0ec96-321">D5500900D - SET CUSTOMER STATUS DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="0ec96-322">D5500900E - 更新销售订单状态数据结构</span><span class="sxs-lookup"><span data-stu-id="0ec96-322">D5500900E - UPDATE SALES ORDER STATUS DATA STRUCTURE</span></span>  
  
-   <span data-ttu-id="0ec96-323">D5500900F - 测试整数</span><span class="sxs-lookup"><span data-stu-id="0ec96-323">D5500900F - TEST INTEGER</span></span>  
  
-   <span data-ttu-id="0ec96-324">D5500900G - 测试字符串</span><span class="sxs-lookup"><span data-stu-id="0ec96-324">D5500900G - TEST STRING</span></span>  
  
-   <span data-ttu-id="0ec96-325">D5500900H - 测试日期</span><span class="sxs-lookup"><span data-stu-id="0ec96-325">D5500900H - TEST DATE</span></span>  
  
-   <span data-ttu-id="0ec96-326">D5500900I - 测试字符</span><span class="sxs-lookup"><span data-stu-id="0ec96-326">D5500900I - TEST CHAR</span></span>  
  
-   <span data-ttu-id="0ec96-327">D5500900J - 测试数学数值</span><span class="sxs-lookup"><span data-stu-id="0ec96-327">D5500900J - TEST MATH NUMERIC</span></span>  
  
-   <span data-ttu-id="0ec96-328">D5500900K - 测试日期 2</span><span class="sxs-lookup"><span data-stu-id="0ec96-328">D5500900K - TEST DATE 2</span></span>  
  
#### <a name="customize-the-jdeinteropini-file"></a><span data-ttu-id="0ec96-329">自定义 jdeinterop.ini 文件</span><span class="sxs-lookup"><span data-stu-id="0ec96-329">Customize the jdeinterop.ini file</span></span>  
 <span data-ttu-id="0ec96-330">Connector.jar 和 Kernel.jar 中的 JD Edwards OneWorld XE 连接器类需要使用 jdeinterop.ini 的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-330">The JD Edwards OneWorld XE connector classes in Connector.jar and Kernel.jar require that you use the jdeinterop.ini configuration file.</span></span> <span data-ttu-id="0ec96-331">此文件由 JD Edwards OneWorld 软件定义，并使用其术语。</span><span class="sxs-lookup"><span data-stu-id="0ec96-331">This file is defined by the JD Edwards OneWorld software and uses its terminology.</span></span> <span data-ttu-id="0ec96-332">JD Edwards 互操作性指南发行 OneWorld 可能提供有关用途和术语的此文件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-332">The JD Edwards Interoperability Guide Release OneWorld may provide more information about the purpose and terminology of this file.</span></span> <span data-ttu-id="0ec96-333">还有一个示例 jdeinterop.ini 文件中的 *< 自 > \config\jde*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-333">There is a sample jdeinterop.ini file in *<Adapter_Installation>\config\jde*.</span></span>  
  
<span data-ttu-id="0ec96-334">更新 jdeinterop.ini 以匹配你在中定义的参数值**传输属性**屏幕。</span><span class="sxs-lookup"><span data-stu-id="0ec96-334">Update jdeinterop.ini to match the parameter values that you defined in the **Transport Properties** screen.</span></span> <span data-ttu-id="0ec96-335">如果它们的参数兼容，则多个 JD Edwards OneWorld 逻辑系统可以共享同一个 jdeinterop.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-335">Multiple JD Edwards OneWorld logical systems can share the same jdeinterop.ini file if their parameters are compatible.</span></span> <span data-ttu-id="0ec96-336">通常情况下，如果两个逻辑系统指向两个不同的 JD Edwards OneWorld 计算机，他们需要两个不同的 jdeinterop.ini 副本。</span><span class="sxs-lookup"><span data-stu-id="0ec96-336">Generally, if two logical systems point to two different JD Edwards OneWorld computers, they need two different copies of jdeinterop.ini.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-337">Jdeinterop.ini 中的日志记录应关闭，并且可以安全地忽略各种日志文件的参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-337">The logging in jdeinterop.ini should be turned off, and the parameters for the various log files can safely be ignored.</span></span>  
  
 <span data-ttu-id="0ec96-338">下表列举 jdeinterop.ini 文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-338">The following table itemizes the settings found in the jdeinterop.ini file.</span></span> <span data-ttu-id="0ec96-339">信息是按节组织的。</span><span class="sxs-lookup"><span data-stu-id="0ec96-339">The information is organized by section.</span></span> <span data-ttu-id="0ec96-340">例如 [JDENET] 与本节按其在 JD Edwards OneWorld 软件中出现的顺序列出。</span><span class="sxs-lookup"><span data-stu-id="0ec96-340">For example [JDENET] and the sections are listed in the order that they appear in the JD Edwards OneWorld software.</span></span>  
  
#### <a name="jdeinteropini-file-settings"></a><span data-ttu-id="0ec96-341">jdeinterop.ini 文件设置</span><span class="sxs-lookup"><span data-stu-id="0ec96-341">jdeinterop.ini file settings</span></span>
  
|<span data-ttu-id="0ec96-342">部分</span><span class="sxs-lookup"><span data-stu-id="0ec96-342">Section</span></span>|<span data-ttu-id="0ec96-343">参数和说明</span><span class="sxs-lookup"><span data-stu-id="0ec96-343">Parameter and Description</span></span>|  
|-------------|-------------------------------|  
|<span data-ttu-id="0ec96-344">[JDENET]</span><span class="sxs-lookup"><span data-stu-id="0ec96-344">[JDENET]</span></span>|<span data-ttu-id="0ec96-345">**EnterpriseServerTimeout.**</span><span class="sxs-lookup"><span data-stu-id="0ec96-345">**EnterpriseServerTimeout.**</span></span> <span data-ttu-id="0ec96-346">对企业服务器的请求的超时值（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-346">The time-out value for a request to the enterprise server in milliseconds.</span></span> <span data-ttu-id="0ec96-347">默认大小为 120000。</span><span class="sxs-lookup"><span data-stu-id="0ec96-347">The default size is 120000.</span></span><br /><br /> <span data-ttu-id="0ec96-348">**maxPoolSize.**</span><span class="sxs-lookup"><span data-stu-id="0ec96-348">**maxPoolSize.**</span></span> <span data-ttu-id="0ec96-349">JDENET 套接字连接池大小。</span><span class="sxs-lookup"><span data-stu-id="0ec96-349">The JDENET socket connection pool size.</span></span> <span data-ttu-id="0ec96-350">默认大小为 30。</span><span class="sxs-lookup"><span data-stu-id="0ec96-350">The default size is 30.</span></span>|  
|<span data-ttu-id="0ec96-351">[SERVER]</span><span class="sxs-lookup"><span data-stu-id="0ec96-351">[SERVER]</span></span>|<span data-ttu-id="0ec96-352">**glossaryTextServer.**</span><span class="sxs-lookup"><span data-stu-id="0ec96-352">**glossaryTextServer.**</span></span> <span data-ttu-id="0ec96-353">提供词汇表文本信息的企业服务器和端口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-353">The enterprise server and port that provide glossary text information.</span></span> <span data-ttu-id="0ec96-354">这是返回错误的文本说明的服务器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-354">This is the server that returns text descriptions for errors.</span></span> <span data-ttu-id="0ec96-355">这通常是与 JD Edwards OneWorld 应用程序服务器相同的主机和端口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-355">This is frequently the same host and port as the JD Edwards OneWorld application server.</span></span> <span data-ttu-id="0ec96-356">不同的受支持的语言编码可能有不止一个词汇表服务器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-356">There may be more than one glossary server for different supported language encodings.</span></span> <span data-ttu-id="0ec96-357">例如，JDED:6010 或 actsrv1:6009。</span><span class="sxs-lookup"><span data-stu-id="0ec96-357">For example, JDED:6010 or actsrv1:6009.</span></span> <span data-ttu-id="0ec96-358">值必须与系统定义中设置的相匹配。</span><span class="sxs-lookup"><span data-stu-id="0ec96-358">The values must match those set in System Definition.</span></span><br /><br /> <span data-ttu-id="0ec96-359">**codePage.**</span><span class="sxs-lookup"><span data-stu-id="0ec96-359">**codePage.**</span></span> <span data-ttu-id="0ec96-360">编码方案。</span><span class="sxs-lookup"><span data-stu-id="0ec96-360">The encoding scheme.</span></span> <span data-ttu-id="0ec96-361">默认为 1252。</span><span class="sxs-lookup"><span data-stu-id="0ec96-361">The default is 1252.</span></span><br /><br /> <span data-ttu-id="0ec96-362">1252 英语和西欧语言</span><span class="sxs-lookup"><span data-stu-id="0ec96-362">- 1252 English and Western European</span></span><br /><br /> <span data-ttu-id="0ec96-363">-932 日语</span><span class="sxs-lookup"><span data-stu-id="0ec96-363">- 932 Japanese</span></span><br /><br /> <span data-ttu-id="0ec96-364">-950 繁体中文</span><span class="sxs-lookup"><span data-stu-id="0ec96-364">- 950 Traditional Chinese</span></span><br /><br /> <span data-ttu-id="0ec96-365">-936 中文 （简体的)</span><span class="sxs-lookup"><span data-stu-id="0ec96-365">- 936 Simplified Chinese</span></span><br /><br /> <span data-ttu-id="0ec96-366">-949 朝鲜语</span><span class="sxs-lookup"><span data-stu-id="0ec96-366">- 949 Korean</span></span>|  
|<span data-ttu-id="0ec96-367">[LOGS]</span><span class="sxs-lookup"><span data-stu-id="0ec96-367">[LOGS]</span></span>|<span data-ttu-id="0ec96-368">**日志 = c:\jas.log。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-368">**log= c:\jas.log.**</span></span> <span data-ttu-id="0ec96-369">日志文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-369">Location of the log file.</span></span> <span data-ttu-id="0ec96-370">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-370">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="0ec96-371">**debuglog = c:\jasdebug.log。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-371">**debuglog= c:\jasdebug.log.**</span></span> <span data-ttu-id="0ec96-372">调试日志文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-372">Location of debug log file.</span></span> <span data-ttu-id="0ec96-373">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-373">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="0ec96-374">**调试。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-374">**Debug.**</span></span> <span data-ttu-id="0ec96-375">确定是否已启用 JDENET 调试。</span><span class="sxs-lookup"><span data-stu-id="0ec96-375">Determines whether JDENET debugging is on.</span></span> <span data-ttu-id="0ec96-376">默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0ec96-376">The default is FALSE.</span></span>|  
|<span data-ttu-id="0ec96-377">[DEBUG]</span><span class="sxs-lookup"><span data-stu-id="0ec96-377">[DEBUG]</span></span>|<span data-ttu-id="0ec96-378">**JobFile = c:\Interop.log。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-378">**JobFile= c:\Interop.log.**</span></span> <span data-ttu-id="0ec96-379">错误文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-379">Location of error file.</span></span> <span data-ttu-id="0ec96-380">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-380">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="0ec96-381">**DebugFile = c:\InteropDebug.log。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-381">**DebugFile= c:\InteropDebug.log.**</span></span> <span data-ttu-id="0ec96-382">调试文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-382">Location of debug file.</span></span> <span data-ttu-id="0ec96-383">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-383">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="0ec96-384">**日志 = c:\net.log。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-384">**log= c:\net.log.**</span></span> <span data-ttu-id="0ec96-385">日志文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-385">Location of log file.</span></span> <span data-ttu-id="0ec96-386">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-386">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="0ec96-387">**debugLevel = 0-12。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-387">**debugLevel= 0 - 12.**</span></span> <span data-ttu-id="0ec96-388">调试级别。</span><span class="sxs-lookup"><span data-stu-id="0ec96-388">Debug levels.</span></span> <span data-ttu-id="0ec96-389">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-389">You can safely ignore this parameter.</span></span> <span data-ttu-id="0ec96-390">此项定义了由仅在 COM 服务器中的指定日志文件中的 COM 连接器和 Callobject 组件提供的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="0ec96-390">This defines the level of tracing provided by the COM Connector and the Callobject component in the specified log file, in the COM server only.</span></span><br /><br /> <span data-ttu-id="0ec96-391">-0 none。</span><span class="sxs-lookup"><span data-stu-id="0ec96-391">- 0 None.</span></span> <span data-ttu-id="0ec96-392">关闭日志记录并仅将错误写入 JobFile。</span><span class="sxs-lookup"><span data-stu-id="0ec96-392">Logging is turned off and only errors are written to the JobFile.</span></span><br /><br /> <span data-ttu-id="0ec96-393">-2 个错误 （错误消息）</span><span class="sxs-lookup"><span data-stu-id="0ec96-393">- 2 Errors (error messages)</span></span><br /><br /> <span data-ttu-id="0ec96-394">-4 系统错误 （异常消息）</span><span class="sxs-lookup"><span data-stu-id="0ec96-394">- 4 System Errors (exception messages)</span></span><br /><br /> <span data-ttu-id="0ec96-395">-6 警告信息</span><span class="sxs-lookup"><span data-stu-id="0ec96-395">- 6 Warning Information</span></span><br /><br /> <span data-ttu-id="0ec96-396">-8 分钟跟踪 （键操作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-396">- 8 Min Trace (Key operations.</span></span> <span data-ttu-id="0ec96-397">例如，登录、注销、业务函数调用。）</span><span class="sxs-lookup"><span data-stu-id="0ec96-397">For example, Logon, Logoff, Business Function calls.)</span></span><br /><br /> <span data-ttu-id="0ec96-398">-10 个故障排除信息 （帮助）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-398">- 10 Troubleshooting Information (Help).</span></span><br /><br /> <span data-ttu-id="0ec96-399">-12 完整的调试信息 （记录所有内容）</span><span class="sxs-lookup"><span data-stu-id="0ec96-399">- 12 Complete Debug Information (Logs everything)</span></span><br /><br /> <span data-ttu-id="0ec96-400">-默认情况下，不需要启用跟踪，但调试代码时，跟踪是非常有用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-400">- By default, you do not have to turn on tracing, but tracing is useful when you are debugging your code.</span></span><br /><br /> <span data-ttu-id="0ec96-401">-NetTraceLevel = 0。</span><span class="sxs-lookup"><span data-stu-id="0ec96-401">- NetTraceLevel=0.</span></span> <span data-ttu-id="0ec96-402">跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="0ec96-402">Trace levels.</span></span> <span data-ttu-id="0ec96-403">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-403">You can safely ignore this parameter.</span></span> <span data-ttu-id="0ec96-404">定义由 ThinNet 组件在指定的日志文件中，仅在 COM 服务器中提供的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="0ec96-404">Defines the level of tracing provided by the ThinNet component in the specified log file, in the COM server only.</span></span> <span data-ttu-id="0ec96-405">对于未来要添加的级别保留奇数值。</span><span class="sxs-lookup"><span data-stu-id="0ec96-405">The odd values are reserved for future levels to be added.</span></span><br /><br /> <span data-ttu-id="0ec96-406">-以下列表介绍了更多的调试级别：</span><span class="sxs-lookup"><span data-stu-id="0ec96-406">-  The following list describes debug levels even more:</span></span><br /><br /> <span data-ttu-id="0ec96-407">-0 没有跟踪</span><span class="sxs-lookup"><span data-stu-id="0ec96-407">-     0 No trace</span></span><br /><br /> <span data-ttu-id="0ec96-408">-1 表示记录进程 ID、 线程 ID 和可用套接字状态时添加新的连接和搜索套接字池。</span><span class="sxs-lookup"><span data-stu-id="0ec96-408">- 1 Refers to the Record process ID, thread ID, and the available socket status when a new connection is added and the socket pool is searched.</span></span><br /><br /> <span data-ttu-id="0ec96-409">-2 包括跟踪级别 1 中的信息，还跟踪在连接管理器类中所做的每个调用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-409">- 2 Includes the information in trace level 1 and also traces every call made in the connection manager class.</span></span><br /><br /> <span data-ttu-id="0ec96-410">-3 包括跟踪级别 2，还跟踪 getport （） 调用和 gethost （） 调用中的所有信息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-410">- 3 Includes all information in trace level 2, and also traces getPort() calls and getHost() calls.</span></span>|  
|<span data-ttu-id="0ec96-411">[INTEROP]</span><span class="sxs-lookup"><span data-stu-id="0ec96-411">[INTEROP]</span></span>|<span data-ttu-id="0ec96-412">**enterpriseServer.**</span><span class="sxs-lookup"><span data-stu-id="0ec96-412">**enterpriseServer.**</span></span> <span data-ttu-id="0ec96-413">此值是主机服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0ec96-413">This value is the name of the host server.</span></span> <span data-ttu-id="0ec96-414">请确保此值是相同的值中输入**主机名**字段中**JDE 凭据**主题中**系统定义**中**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="0ec96-414">Make sure that this value is the same value that you enter in the **Host Name** field in the **JDE Credentials** section in **System Definition** in the **Transport Properties** dialog box.</span></span> <span data-ttu-id="0ec96-415">默认值为 JDED。</span><span class="sxs-lookup"><span data-stu-id="0ec96-415">The default is JDED.</span></span><br /><br /> <span data-ttu-id="0ec96-416">**端口。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-416">**port.**</span></span> <span data-ttu-id="0ec96-417">此值是用于交换数据的端口号。</span><span class="sxs-lookup"><span data-stu-id="0ec96-417">This value is the port number that is used to exchange data.</span></span> <span data-ttu-id="0ec96-418">请确保此值是相同的值中输入**端口号**字段中 JD Edwards**凭据**主题中**传输属性系统定义**.</span><span class="sxs-lookup"><span data-stu-id="0ec96-418">Make sure that this value is the same value that you enter in the **Port Number** field in the JD Edwards **Credentials** section in the **Transport Properties, System Definition**.</span></span> <span data-ttu-id="0ec96-419">例如，6010 或 6009。</span><span class="sxs-lookup"><span data-stu-id="0ec96-419">For example, 6010 or 6009.</span></span> <span data-ttu-id="0ec96-420">值必须匹配中设置的相**系统定义**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-420">The values must match those set in **System Definition**.</span></span><br /><br /> <span data-ttu-id="0ec96-421">**inactive_timeout**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-421">**inactive_timeout**.</span></span> <span data-ttu-id="0ec96-422">自动提交模式下的事务的超时值（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-422">The time-out value in milliseconds for a transaction in auto-commit mode.</span></span> <span data-ttu-id="0ec96-423">如果用户在这段时间（以毫秒为单位）处于非活动状态，互操作的服务器将注销用户。</span><span class="sxs-lookup"><span data-stu-id="0ec96-423">If the user is inactive for this period of time (in milliseconds), the interop server logs off the user.</span></span> <span data-ttu-id="0ec96-424">可以将此值更改为较短的时间段。</span><span class="sxs-lookup"><span data-stu-id="0ec96-424">You can change this value to a shorter period of time.</span></span> <span data-ttu-id="0ec96-425">默认值为 1200000。</span><span class="sxs-lookup"><span data-stu-id="0ec96-425">The default is 1200000.</span></span><br /><br /> <span data-ttu-id="0ec96-426">**manual_timeout。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-426">**manual_timeout.**</span></span> <span data-ttu-id="0ec96-427">以毫秒为单位在手动提交模式下事务超时值。</span><span class="sxs-lookup"><span data-stu-id="0ec96-427">The time-out value in milliseconds for a transaction in manual commit mode.</span></span> <span data-ttu-id="0ec96-428">默认值为 120000。</span><span class="sxs-lookup"><span data-stu-id="0ec96-428">The default is 120000.</span></span><br /><br /> <span data-ttu-id="0ec96-429">**存储库。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-429">**Repository.**</span></span> <span data-ttu-id="0ec96-430">指向包含 Connector.jar 和 Kernel.jar 的目录的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-430">Points to the location of the directory that contains Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="0ec96-431">在 UNIX 上，这是完整路径。</span><span class="sxs-lookup"><span data-stu-id="0ec96-431">On UNIX, this is a full path.</span></span>|  
|<span data-ttu-id="0ec96-432">[CORBA]</span><span class="sxs-lookup"><span data-stu-id="0ec96-432">[CORBA]</span></span>|<span data-ttu-id="0ec96-433">可以安全地忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="0ec96-433">You can safely ignore this parameter.</span></span><br /><br /> <span data-ttu-id="0ec96-434">**多线程。**</span><span class="sxs-lookup"><span data-stu-id="0ec96-434">**Multithread.**</span></span> <span data-ttu-id="0ec96-435">可以忽略该设置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-435">The setting can be ignored.</span></span> <span data-ttu-id="0ec96-436">将 CORBA 的多线程支持设置为 1。</span><span class="sxs-lookup"><span data-stu-id="0ec96-436">Set to 1 for multithread support for CORBA.</span></span><br /><br /> <span data-ttu-id="0ec96-437">Objects= CORBA::Connector；CORBA::OneWorldVersion</span><span class="sxs-lookup"><span data-stu-id="0ec96-437">Objects= CORBA::Connector;CORBA::OneWorldVersion</span></span><br /><br /> <span data-ttu-id="0ec96-438">定义要在启动时创建的 CORBA 服务器的对象。</span><span class="sxs-lookup"><span data-stu-id="0ec96-438">Defines the objects for the CORBA server to create at startup.</span></span> <span data-ttu-id="0ec96-439">此外会替换-DIORFILENAME = 命令行选项，例如： CORBA::Connector=connector.ior。</span><span class="sxs-lookup"><span data-stu-id="0ec96-439">Also replaces the -DIORFILENAME = command-line option, for example: CORBA::Connector=connector.ior.</span></span>|  
  
## <a name="jd-edwards-enterpriseone"></a><span data-ttu-id="0ec96-440">JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="0ec96-440">JD Edwards EnterpriseOne</span></span>  
<span data-ttu-id="0ec96-441">本部分包含有关用于 JD Edwards EnterpriseOne 的 BizTalk Server 使用的 Microsoft BizTalk 适配器的密钥信息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-441">This sections includes key information on using the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne with BizTalk Server.</span></span>
  
### <a name="execute-a-jd-edwards-enterpriseone-master-business-function"></a><span data-ttu-id="0ec96-442">执行 JD Edwards EnterpriseOne 主业务函数</span><span class="sxs-lookup"><span data-stu-id="0ec96-442">Execute a JD Edwards EnterpriseOne master business function</span></span>  
 <span data-ttu-id="0ec96-443">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器可用于调用 JD Edwards EnterpriseOne 主业务函数，例如通讯簿、采购订单或销售订单。</span><span class="sxs-lookup"><span data-stu-id="0ec96-443">You can use the BizTalk Adapter for JD Edwards EnterpriseOne to invoke a JD Edwards EnterpriseOne master business function, such as Address Book, Purchase Order, or Sales Order.</span></span> <span data-ttu-id="0ec96-444">也可使用适配器作为集成工作的一部分来将 JD Edwards EnterpriseOne 和 BizTalk 服务器相连接。</span><span class="sxs-lookup"><span data-stu-id="0ec96-444">You can also use the adapter as part of an integration effort to connect JD Edwards EnterpriseOne with BizTalk Server.</span></span>  
  
##### <a name="access-data-stored-in-jd-edwards-enterpriseone"></a><span data-ttu-id="0ec96-445">访问 JD Edwards EnterpriseOne 中存储的数据</span><span class="sxs-lookup"><span data-stu-id="0ec96-445">Access data stored in JD Edwards EnterpriseOne</span></span>  
 <span data-ttu-id="0ec96-446">适配器接受 XML 消息，使 BizTalk 服务器应用程序能够使用以下端口之一与 JD Edwards EnterpriseOne 进行通信和事务交换：</span><span class="sxs-lookup"><span data-stu-id="0ec96-446">The adapter accepts XML messages to enable BizTalk Server applications to communicate and exchange transactions with JD Edwards EnterpriseOne using one of the following:</span></span>  
  
-   <span data-ttu-id="0ec96-447">**传输适配器**，其中使用静态要求响应发送端口将消息发送到 JD Edwards EnterpriseOne 并等待响应。</span><span class="sxs-lookup"><span data-stu-id="0ec96-447">**Transmit Adapter**, which uses a Static Solicit-Response Send port to send a message to JD Edwards EnterpriseOne and expects a response.</span></span>    
-   <span data-ttu-id="0ec96-448">**接收适配器**，它使用静态单向接收端口以接收来自 JD Edwards EnterpriseOne 的消息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-448">**Receive Adapter**, which uses a Static One-Way Receive port to receive messages from JD Edwards EnterpriseOne.</span></span>  
  
### <a name="interoperability-framework"></a><span data-ttu-id="0ec96-449">互操作性框架</span><span class="sxs-lookup"><span data-stu-id="0ec96-449">Interoperability framework</span></span>  
 <span data-ttu-id="0ec96-450">JD Edwards EnterpriseOne 为通过其互操作性框架与系统集成做准备。</span><span class="sxs-lookup"><span data-stu-id="0ec96-450">JD Edwards EnterpriseOne provides for integration with systems through its interoperability framework.</span></span> <span data-ttu-id="0ec96-451">适配器使用 JD Edwards EnterpriseOne 框架，并利用各种集成访问方法，以提供最大程度的灵活性和功能。</span><span class="sxs-lookup"><span data-stu-id="0ec96-451">The adapter uses the JD Edwards EnterpriseOne framework, and takes advantage of various integration access methods to provide the greatest amount of flexibility and functionality.</span></span>  
  
 <span data-ttu-id="0ec96-452">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器支持以下集成访问方法：</span><span class="sxs-lookup"><span data-stu-id="0ec96-452">BizTalk Adapter for JD Edwards EnterpriseOne supports the following integration access methods:</span></span>  
  
- <span data-ttu-id="0ec96-453">JD Edwards EnterpriseOne ThinNet API</span><span class="sxs-lookup"><span data-stu-id="0ec96-453">JD Edwards EnterpriseOne ThinNet API</span></span>    
- <span data-ttu-id="0ec96-454">JD Edwards EnterpriseOne XML</span><span class="sxs-lookup"><span data-stu-id="0ec96-454">JD Edwards EnterpriseOne XML</span></span>    
- <span data-ttu-id="0ec96-455">JD Edwards EnterpriseOne 未编辑的事务表（Z 表）</span><span class="sxs-lookup"><span data-stu-id="0ec96-455">JD Edwards EnterpriseOne unedited transaction tables (Z tables)</span></span>  
  
  <span data-ttu-id="0ec96-456">适配器使用 JD Edwards EnterpriseOne ThinNet API 与 JD Edwards EnterpriseOne 应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="0ec96-456">The adapter uses the JD Edwards EnterpriseOne ThinNet API to communicate with the JD Edwards EnterpriseOne application.</span></span> <span data-ttu-id="0ec96-457">通过使用 ThinNet API，该适配器可以调用单个工作单元 (UOW) 中的一个主业务函数 (MBF)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-457">By using the ThinNet API, the adapter can invoke one master business function (MBF) in a single unit of work (UOW).</span></span> <span data-ttu-id="0ec96-458">当 MBF 失败时，整个 UOW 无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-458">When an MBF fails, the whole UOW fails.</span></span> <span data-ttu-id="0ec96-459">这样可以防止部分更新。</span><span class="sxs-lookup"><span data-stu-id="0ec96-459">This prevents partial updates.</span></span> <span data-ttu-id="0ec96-460">数据验证、业务规则和与基础数据库的通信都由 JD Edwards EnterpriseOne 应用程序处理。</span><span class="sxs-lookup"><span data-stu-id="0ec96-460">The validation of data, business rules, and communications to the underlying database are handled by the JD Edwards EnterpriseOne application.</span></span>  
  
#### <a name="jd-edwards-outbound-processing-framework"></a><span data-ttu-id="0ec96-461">JD Edwards 出站处理框架</span><span class="sxs-lookup"><span data-stu-id="0ec96-461">JD Edwards Outbound Processing Framework</span></span>  
 <span data-ttu-id="0ec96-462">在出站过程中，当在 JD Edwards EnterpriseOne 环境中执行一个特定的 MBF 时，事件启动。</span><span class="sxs-lookup"><span data-stu-id="0ec96-462">In the outbound process, the event starts when a specific MBF is executed in the JD Edwards EnterpriseOne environment.</span></span> <span data-ttu-id="0ec96-463">MBF 将该事件所需的信息写入到适当的接口表并随后通知发生事件的子系统批处理函数 (BF)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-463">The MBF writes the required information for the event into the appropriate interface table and then notifies the subsystem batch function (BF) that an event occurred.</span></span> <span data-ttu-id="0ec96-464">随后子系统 BF 包括一个关于子系统数据队列上的事件的条目。</span><span class="sxs-lookup"><span data-stu-id="0ec96-464">The subsystem BF then includes an entry about the event on the subsystem data queue.</span></span>  
  
 <span data-ttu-id="0ec96-465">出站子系统检索数据队列条目，并在数据输出控制表中查找外部进程以进行通知。</span><span class="sxs-lookup"><span data-stu-id="0ec96-465">The outbound subsystem retrieves the data queue entry and looks in the Data Export Control table for the external processes to notify.</span></span> <span data-ttu-id="0ec96-466">随后出站子系统调用用于 JD Edwards EnterpriseOne 侦听器的 BizTalk 适配器并发出通知。</span><span class="sxs-lookup"><span data-stu-id="0ec96-466">The outbound subsystem then calls the BizTalk Adapter for JD Edwards EnterpriseOne listener with notification.</span></span> <span data-ttu-id="0ec96-467">侦听器将通知传递给生成器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-467">The listener passes the notification to the generator.</span></span> <span data-ttu-id="0ec96-468">随后生成器使用 JD Edwards EnterpriseOne ThinNet API 检索来自接口表的相应信息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-468">The generator then uses the JD Edwards EnterpriseOne ThinNet API to retrieve the appropriate information from the interface table.</span></span>  
  
### <a name="set-string-justification-in-jdearglist"></a><span data-ttu-id="0ec96-469">在 Jdearglist 中设置字符串对齐</span><span class="sxs-lookup"><span data-stu-id="0ec96-469">Set string justification in Jdearglist</span></span>  
 <span data-ttu-id="0ec96-470">若要将某些字符串参数配置为右对齐和左填充中 j.d.</span><span class="sxs-lookup"><span data-stu-id="0ec96-470">To configure certain string arguments as right-justified and left padded in the J.D.</span></span> <span data-ttu-id="0ec96-471">Edwards EnterpriseOne jdearglist.txt 文件中右对齐和左填充，你必须知道你希望访问哪些业务函数，特别是，你必须知道你希望调用业务函数中的哪些字段。</span><span class="sxs-lookup"><span data-stu-id="0ec96-471">Edwards EnterpriseOne jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="0ec96-472">您必须先更新该 jdearglist.txt，然后在业务流程中生成绑定（架构）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-472">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="0ec96-473">用于更新 jdearglist.txt 文件中的"处理字符串值"部分所述的说明。</span><span class="sxs-lookup"><span data-stu-id="0ec96-473">The instructions for updating the jdearglist.txt file outlined in the "Handling String Values" section.</span></span>  
  
 <span data-ttu-id="0ec96-474">如果在日志中收到 jdearglist.txt 警告消息，其目的是通知您缺少指定 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="0ec96-474">If you receive a jdearglist.txt warning message in the log, its purpose is to inform you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="0ec96-475">但是，如果运行 SalesOrder 或 PurchaseOrder 业务函数，必须在你的路径具有该文件或它不起作用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-475">However, if you are running the SalesOrder or PurchaseOrder business function, you must have that file in your PATH or it does not work.</span></span>  
  
### <a name="understand-jdeinteropini"></a><span data-ttu-id="0ec96-476">了解 jdeinterop.ini</span><span class="sxs-lookup"><span data-stu-id="0ec96-476">Understand jdeinterop.ini</span></span>  
 <span data-ttu-id="0ec96-477">Connector.jar 和 Kernel.jar 中的 JD Edwards EnterpriseOne 连接器类需要你使用名为 jdeinterop.ini 的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-477">The JD Edwards EnterpriseOne connector classes in Connector.jar and Kernel.jar require that you use a configuration file named jdeinterop.ini.</span></span> <span data-ttu-id="0ec96-478">此文件由 JD Edwards EnterpriseOne 软件定义，并使用其术语。</span><span class="sxs-lookup"><span data-stu-id="0ec96-478">This file is defined by the JD Edwards EnterpriseOne software and uses its terminology.</span></span> <span data-ttu-id="0ec96-479">有关用途和术语的此文件的详细信息，请参阅 JD Edwards 互操作性指南。</span><span class="sxs-lookup"><span data-stu-id="0ec96-479">For more information about the purpose and terminology of this file, see the JD Edwards Interoperability Guide.</span></span> <span data-ttu-id="0ec96-480">还有一个示例 jdeinterop.ini 文件中： Program Files\ Microsoft BizTalk Adapters for Enterprise Applications\ J.D.</span><span class="sxs-lookup"><span data-stu-id="0ec96-480">There is a sample jdeinterop.ini file in: Program Files\ Microsoft BizTalk Adapters for Enterprise Applications\ J.D.</span></span> <span data-ttu-id="0ec96-481">Edwards EnterpriseOne(r) \config。</span><span class="sxs-lookup"><span data-stu-id="0ec96-481">Edwards EnterpriseOne(r)\config.</span></span>  
  
 <span data-ttu-id="0ec96-482">建议不要因为它与交互手动编辑此文件**传输属性**发送端口-例如这些字段标记为对话框 **< 由 BizTalk 配置\>**.</span><span class="sxs-lookup"><span data-stu-id="0ec96-482">It is not recommended that you edit this file manually because it interacts with the **Transport Properties** dialog box for the send port -- for example those fields marked as **<configured by BizTalk\>**.</span></span>  
  
## <a name="peoplesoft-enterprise"></a><span data-ttu-id="0ec96-483">PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="0ec96-483">PeopleSoft Enterprise</span></span>  
<span data-ttu-id="0ec96-484">此部分包含有关适用于 PeopleSoft Enterprise 的 BizTalk Server 使用的 Microsoft BizTalk 适配器的关键信息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-484">This section includes key information on using the Microsoft BizTalk Adapter for PeopleSoft Enterprise with BizTalk Server.</span></span>
  
### <a name="receive-handler-peoplesoft-requirements"></a><span data-ttu-id="0ec96-485">接收处理程序 PeopleSoft 要求</span><span class="sxs-lookup"><span data-stu-id="0ec96-485">Receive handler PeopleSoft requirements</span></span>  
 <span data-ttu-id="0ec96-486">PeopleSoft Integration Broker 必须能够与 BizTalk 服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="0ec96-486">The PeopleSoft Integration Broker must be able to communicate with BizTalk Server.</span></span> <span data-ttu-id="0ec96-487">以下情况可能已经在现有 PeopleSoft 环境中发生，你可以重新使用现有节点；因此，除了从 PeopleSoft 系统管理员那里获取 HTTP 规范之外，你不需要进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-487">The following could have already occurred in an existing PeopleSoft environment and you could reuse an existing node; therefore, you would not have to do anything except obtain the HTTP specifications from a PeopleSoft System Administrator.</span></span> <span data-ttu-id="0ec96-488">有关详细信息，请参阅 PeopleSoft 文档。</span><span class="sxs-lookup"><span data-stu-id="0ec96-488">For detailed information, see the PeopleSoft documentation.</span></span>  

<span data-ttu-id="0ec96-489">以下步骤提供的概述，可在 PeopleSoft 中完成：</span><span class="sxs-lookup"><span data-stu-id="0ec96-489">The following steps provide an overview to complete in PeopleSoft:</span></span>  
  
1.  <span data-ttu-id="0ec96-490">设置该消息，并使它通过应用程序设计器处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="0ec96-490">Set up the message, and make it active through the Application Designer.</span></span>  
  
2.  <span data-ttu-id="0ec96-491">对 PeopleSoft integration.gateway.properties 文件进行一次性更改。</span><span class="sxs-lookup"><span data-stu-id="0ec96-491">Make a one-time change to the PeopleSoft integration.gateway.properties file.</span></span>  
  
3.  <span data-ttu-id="0ec96-492">创建和配置网关以及节点以激活 HTTP:</span><span class="sxs-lookup"><span data-stu-id="0ec96-492">Create and configure the gateway and nodes to activate HTTP:</span></span>
  
    -   <span data-ttu-id="0ec96-493">节点必须使用一些触发方法，例如 LOCATION_SYNC 机制。</span><span class="sxs-lookup"><span data-stu-id="0ec96-493">The node must be using some triggering method, for example, the LOCATION_SYNC mechanism.</span></span>   
    -   <span data-ttu-id="0ec96-494">节点必须使用 HTTP。</span><span class="sxs-lookup"><span data-stu-id="0ec96-494">The node must use HTTP.</span></span>    
    -   <span data-ttu-id="0ec96-495">节点必须指向发送该事件的主机和端口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-495">The node must point to the host and port to which you are sending the event.</span></span>  
  
### <a name="send-handler-peoplesoft-requirements"></a><span data-ttu-id="0ec96-496">发送处理程序 PeopleSoft 要求</span><span class="sxs-lookup"><span data-stu-id="0ec96-496">Send handler PeopleSoft requirements</span></span>  
 <span data-ttu-id="0ec96-497">用于 PeopleSoft Enterprise 的 BizTalk 适配器包含自定义组件接口 (CI) 用于通过 Java API 的访问。</span><span class="sxs-lookup"><span data-stu-id="0ec96-497">BizTalk Adapter for PeopleSoft Enterprise consists of a custom component interface (CI) that provides access through a Java API.</span></span> <span data-ttu-id="0ec96-498">自定义 CI 对象**GET_CI_INFO**，使用 PeopleSoft 工具提供用于 PeopleSoft Enterprise 的 BizTalk 适配器所需的元数据信息在 PeopleSoft 系统中部署。</span><span class="sxs-lookup"><span data-stu-id="0ec96-498">A custom CI object, **GET_CI_INFO**, is deployed in the PeopleSoft system using PeopleSoft Tools, to provide metadata information that is required by BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="0ec96-499">有关详细信息，请参阅 PeopleSoft 文档。</span><span class="sxs-lookup"><span data-stu-id="0ec96-499">For more information, refer to PeopleSoft documentation.</span></span>  
  
 <span data-ttu-id="0ec96-500">上载自定义组件接口是一次性的。</span><span class="sxs-lookup"><span data-stu-id="0ec96-500">Uploading of the custom component interface is a one-time occurrence.</span></span> <span data-ttu-id="0ec96-501">文件 GET_CI_INFO.pc 是随产品提供的，且在使用适配器来浏览 CI 之前必须安装在 PeopleSoft 系统中。</span><span class="sxs-lookup"><span data-stu-id="0ec96-501">This file, GET_CI_INFO.pc, is provided with the product and must be installed in the PeopleSoft system before you can use the adapter to browse CIs.</span></span> <span data-ttu-id="0ec96-502">必须有权访问 PeopleSoft 应用程序设计器;但是，应用程序设计器不必位于 BizTalk Server 计算机附近的任何位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-502">You must have access to the PeopleSoft Application Designer; however, the Application Designer does not have to be anywhere near the BizTalk Server computer.</span></span> <span data-ttu-id="0ec96-503">应用程序设计器用于将自定义 CI 上载到您浏览的 PeopleSoft 计算机。</span><span class="sxs-lookup"><span data-stu-id="0ec96-503">You use the Application Designer to upload the custom CI into the PeopleSoft computer that you browse.</span></span>  
  
 <span data-ttu-id="0ec96-504">必须有权访问的 PeopleSoft 计算机，因为您必须设置环境变量 CLASSPATH (或中设置该信息**传输属性**窗口) 以指向 PeopleSoft PSJOA/psjoa.jar 文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-504">You must have access to the PeopleSoft computer because you must set the environment variable CLASSPATH (or set the information in the **Transport Properties** window) to point to the PeopleSoft PSJOA/psjoa.jar file.</span></span>  
  
### <a name="set-environment-variable-and-use-component-interface"></a><span data-ttu-id="0ec96-505">设置环境变量和使用组件接口</span><span class="sxs-lookup"><span data-stu-id="0ec96-505">Set environment variable and use component interface</span></span>  
<span data-ttu-id="0ec96-506">有关 PeopleSoft 的详细信息，请参阅 PeopleSoft 文档。</span><span class="sxs-lookup"><span data-stu-id="0ec96-506">For more information about PeopleSoft, see the PeopleSoft documentation.</span></span>  
  
#### <a name="set-classpath-environment-variable"></a><span data-ttu-id="0ec96-507">设置 ClassPath 环境变量</span><span class="sxs-lookup"><span data-stu-id="0ec96-507">Set ClassPath environment variable</span></span>  

<span data-ttu-id="0ec96-508">**更新 JAVA_HOME**</span><span class="sxs-lookup"><span data-stu-id="0ec96-508">**Update JAVA_HOME**</span></span>    
  
 <span data-ttu-id="0ec96-509">设置 JAVA_HOME 变量，使其指向您的 JDK 安装，例如：</span><span class="sxs-lookup"><span data-stu-id="0ec96-509">Set the JAVA_HOME variable to point to your JDK installation, for example:</span></span>  
  
```  
set JAVA_HOME=C:\j2sdk1.4.2_06  
```  
  
 <span data-ttu-id="0ec96-510">**更新 CLASSPATH**</span><span class="sxs-lookup"><span data-stu-id="0ec96-510">**Update CLASSPATH**</span></span>  
  
<span data-ttu-id="0ec96-511">若要使用组件接口 (仅适用于 PeopleSoft 8)，则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-511">To use component interfaces (PeopleSoft 8 only) you must update your CLASSPATH to include the PeopleSoft component interface jar file:</span></span>
  
1. <span data-ttu-id="0ec96-512">在中**Control Panel**，打开**系统**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-512">In **Control Panel**, open **System**.</span></span>  
  
2. <span data-ttu-id="0ec96-513">上**高级**选项卡上，选择**环境变量**，然后选择**CLASSPATH**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-513">On the **Advanced** tab, select **Environment Variables**, and then select **CLASSPATH**.</span></span>  
  
3. <span data-ttu-id="0ec96-514">添加的路径。</span><span class="sxs-lookup"><span data-stu-id="0ec96-514">Add the path.</span></span> <span data-ttu-id="0ec96-515">例如，输入：</span><span class="sxs-lookup"><span data-stu-id="0ec96-515">For example, enter:</span></span>  
  
   ```  
   <PeopleSoft_Home>\web\PSJOA\psjoa.jar  
   ```  
  
   <span data-ttu-id="0ec96-516">用于 PeopleSoft Enterprise 的 BizTalk 适配器需要 psjoa.jar 文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-516">BizTalk Adapter for PeopleSoft Enterprise requires the psjoa.jar file.</span></span> <span data-ttu-id="0ec96-517">创建发送端口时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-517">This is performed when you create a send port.</span></span> <span data-ttu-id="0ec96-518">有关详细信息，请参阅适配器文档中的"在 PeopleSoft 系统中设置传输属性"。</span><span class="sxs-lookup"><span data-stu-id="0ec96-518">For more information, see "Setting Transport Properties in PeopleSoft System" in the adapter documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-519">只要你的 PATH 中有一个目录，就可确保用于 PeopleSoft Enterprise 的 BizTalk 适配器拾取正确的 DLL。</span><span class="sxs-lookup"><span data-stu-id="0ec96-519">Only have one of these directories in your PATH to make sure that BizTalk Adapter for PeopleSoft Enterprise picks up the correct DLLs.</span></span> <span data-ttu-id="0ec96-520">未能对你想要的 PeopleSoft 版本正确设置环境可能导致难以追踪的错误。</span><span class="sxs-lookup"><span data-stu-id="0ec96-520">Failure to set up your environment correctly for the desired version of PeopleSoft could lead to errors that are difficult to trace.</span></span>  
  
#### <a name="use-component-interfaces"></a><span data-ttu-id="0ec96-521">使用组件接口</span><span class="sxs-lookup"><span data-stu-id="0ec96-521">Use component interfaces</span></span>  
  
<a name="BKMK_CustomCI"></a>   
##### <a name="upload-a-custom-ci-into-peoplesoft"></a><span data-ttu-id="0ec96-522">将自定义 CI 上载到 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="0ec96-522">Upload a Custom CI into PeopleSoft</span></span>  
 <span data-ttu-id="0ec96-523">用于 PeopleSoft Enterprise 的 BizTalk 适配器要求对 PeopleSoft 应用程序进行修改。</span><span class="sxs-lookup"><span data-stu-id="0ec96-523">BizTalk Adapter for PeopleSoft Enterprise requires a modification to the PeopleSoft application.</span></span> <span data-ttu-id="0ec96-524">要使用组件接口，必须将自定义组件接口 GET_CI_INFO 上载到 PeopleSoft。</span><span class="sxs-lookup"><span data-stu-id="0ec96-524">To use component interfaces, you must upload a custom component interface, GET_CI_INFO, into PeopleSoft.</span></span> <span data-ttu-id="0ec96-525">只需在初始安装过程中导入 GET_CI_INFO 以使用适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-525">You only have to import GET_CI_INFO during initial setup to use the adapter.</span></span> <span data-ttu-id="0ec96-526">适配器使用 GET_CI_INFO 获取有关 PeopleSoft 中的其他现有组件接口的信息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-526">The adapter uses GET_CI_INFO to obtain information about other existing component interfaces in PeopleSoft.</span></span>  
  
 <span data-ttu-id="0ec96-527">本部分介绍如何手动导入一个可浏览 PeopleSoft 中的组件接口的自定义组件接口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-527">This section explains how to manually import a custom component interface that let you browse component interfaces in PeopleSoft.</span></span> <span data-ttu-id="0ec96-528">请注意自定义的方法不使用或修改它所安装的位置中的任何组件接口属性。</span><span class="sxs-lookup"><span data-stu-id="0ec96-528">Note that the custom methods do not use or modify any properties of the component interface that it is installed in.</span></span> <span data-ttu-id="0ec96-529">若要导入自定义组件接口，可以使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="0ec96-529">To import the custom component interface, you can use one of the following methods:</span></span>  
  
- <span data-ttu-id="0ec96-530">创建新的组件导入自定义方法。</span><span class="sxs-lookup"><span data-stu-id="0ec96-530">Create a new component to import the custom methods.</span></span>  
  
- <span data-ttu-id="0ec96-531">使用未包含键的现有的组件，例如，INSTALLATION_RS。</span><span class="sxs-lookup"><span data-stu-id="0ec96-531">Use an existing component that contains no keys, for example, INSTALLATION_RS.</span></span>  
  
  <span data-ttu-id="0ec96-532">简单的组件接口不得包含键。</span><span class="sxs-lookup"><span data-stu-id="0ec96-532">The simple component interface must not contain keys.</span></span> <span data-ttu-id="0ec96-533">如果你不确定特定组件接口是否包含键，则可以使用 SQL 查询工具运行此简单 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="0ec96-533">If you are not sure whether a particular component interface contains keys, you can run this simple SQL statement using your SQL Query tool.</span></span> <span data-ttu-id="0ec96-534">这样，可以在应用程序中所有不包含键的组件接口的列表。</span><span class="sxs-lookup"><span data-stu-id="0ec96-534">It gives you a list of all the component interfaces in your application that have no keys.</span></span>  
  
```  
select distinct BCNAME  
from PSBCITEM bc1  
where not exists  
(select 1  
from PSBCITEM bc2  
where bc1.BCNAME = bc2.BCNAME  
and bc2.BCTYPE in (1, 2))  
```  
  
 <span data-ttu-id="0ec96-535">你可以按照 PeopleSoft 文档创建用于存储 PeopleSoft Enterprise 自定义方法的 BizTalk 适配器的唯一简单组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-535">You can follow PeopleSoft documentation to create a unique simple component for storing BizTalk Adapter for PeopleSoft Enterprise custom methods.</span></span> <span data-ttu-id="0ec96-536">你还可以克隆一个预先存在的组件接口并使用它来存储自定义方法。</span><span class="sxs-lookup"><span data-stu-id="0ec96-536">You can also clone one of the pre-existing component interfaces and use it to store the custom methods.</span></span>  
  
 <span data-ttu-id="0ec96-537">要验证 GET_CI_INFO 不包含键，请运行 PeopleTools 应用程序设计器组件接口测试工具。</span><span class="sxs-lookup"><span data-stu-id="0ec96-537">To verify that your GET_CI_INFO has no keys, run the PeopleTools Application Designer Component Interface Test tool.</span></span>  
  
<a name="BKMK_NewCom"></a>   
##### <a name="create-a-new-component-interface"></a><span data-ttu-id="0ec96-538">创建新的组件接口</span><span class="sxs-lookup"><span data-stu-id="0ec96-538">Create a new component interface</span></span>  
 <span data-ttu-id="0ec96-539">请按照以下步骤创建新的组件接口使用 PeopleSoft 应用程序设计器操作：</span><span class="sxs-lookup"><span data-stu-id="0ec96-539">Follow these steps to create a new component interface using the PeopleSoft, Application Designer:</span></span>
  
1. <span data-ttu-id="0ec96-540">打开**PeopleSoft 应用程序设计器**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-540">Open the **PeopleSoft Application Designer**.</span></span>  
  
2. <span data-ttu-id="0ec96-541">输入一个三层连接类型，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-541">Enter a three-tier connection type, and then click **OK**.</span></span> <span data-ttu-id="0ec96-542">例如，从列表中选择应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-542">For example, select Application Server from the list.</span></span>  
  
3. <span data-ttu-id="0ec96-543">在应用程序设计器上**文件**菜单中，选择**新建**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-543">In the Application Designer, on the **File** menu, select **New**.</span></span>  
  
4. <span data-ttu-id="0ec96-544">在中**新建**对话框中，选择**组件接口**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-544">In the **New** dialog box, select **Component Interface**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="0ec96-545">然后单击“选择”。</span><span class="sxs-lookup"><span data-stu-id="0ec96-545">Click **Select**.</span></span>  
  
6. <span data-ttu-id="0ec96-546">从所有组件的列表，选择任何简单组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-546">From the list of all components, select any simple component.</span></span> <span data-ttu-id="0ec96-547">例如，选择 INSTALLATION_RS 或你创建一个新的 PeopleSoft 组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-547">For example, select INSTALLATION_RS, or a new PeopleSoft component that you created.</span></span>  
  
   <span data-ttu-id="0ec96-548">自定义方法不要使用或修改的组件接口安装在任何属性。</span><span class="sxs-lookup"><span data-stu-id="0ec96-548">The custom methods do not use or modify any properties of the component interface that it is installed in.</span></span>  
  
   <span data-ttu-id="0ec96-549">此简单的组件接口不得包含键。</span><span class="sxs-lookup"><span data-stu-id="0ec96-549">This simple component interface must not contain keys.</span></span> <span data-ttu-id="0ec96-550">如果你不确定特定组件接口是否包含键，则可以使用 SQL 查询工具运行此简单 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="0ec96-550">If you are not sure whether a particular component interface contains keys, you can run this simple SQL statement using your SQL Query tool.</span></span> <span data-ttu-id="0ec96-551">这样，可以在应用程序中所有不包含键的组件接口的列表：</span><span class="sxs-lookup"><span data-stu-id="0ec96-551">It gives you a list of all the component interfaces in your application that have no keys:</span></span>  
  
```  
select distinct BCNAME from PSBCITEM bc1 where not exists (select 1 from PSBCITEM bc2 where bc1.BCNAME = bc2.BCNAME and bc2.BCTYPE in (1, 2))  
```  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-552">您也可以按照 PeopleSoft 文档创建用于存储 PeopleSoft Enterprise 的 BizTalk 适配器自定义方法的唯一简单组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-552">You can also follow PeopleSoft documentation to create a unique simple component for storing custom methods for BizTalk Adapter for PeopleSoft Enterprise.</span></span>  
  
 <span data-ttu-id="0ec96-553">要验证 GET_CI_INFO 不包含键，请运行 PeopleTools 应用程序设计器组件接口测试工具。</span><span class="sxs-lookup"><span data-stu-id="0ec96-553">To verify that your GET_CI_INFO has no keys, run the PeopleTools Application Designer Component Interface Test tool.</span></span>  
  
##### <a name="check-component-interface"></a><span data-ttu-id="0ec96-554">检查组件接口</span><span class="sxs-lookup"><span data-stu-id="0ec96-554">Check component interface</span></span>  
 <span data-ttu-id="0ec96-555">你已完成将 PeopleSoft GET_CI_INFO 的 Microsoft BizTalk 适配器的上载到 PeopleSoft 系统的工作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-555">You have completed uploading the Microsoft BizTalk Adapter for PeopleSoft GET_CI_INFO into your PeopleSoft System.</span></span> <span data-ttu-id="0ec96-556">GET_CI_INFO 是一个用户定义的自定义组件接口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-556">The GET_CI_INFO is a user-defined custom component interface.</span></span> <span data-ttu-id="0ec96-557">它包含用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="0ec96-557">It contains user-defined methods.</span></span> <span data-ttu-id="0ec96-558">GET_CI_INFO 组件接口允许你在 PeopleSoft 系统中使用 Microsoft 适配器向导浏览组件接口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-558">The GET_CI_INFO component interface lets you browse component interfaces in your PeopleSoft system using the Microsoft Adapter Wizard.</span></span> <span data-ttu-id="0ec96-559">你可以找到并展开 GET_CI_INFO 以查看其用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="0ec96-559">You can locate and expand GET_CI_INFO to view its user-defined methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-560">有关用户定义的方法的详细信息，请参阅适配器文档中的"PeopleSoft:: 组件接口用户定义方法"。</span><span class="sxs-lookup"><span data-stu-id="0ec96-560">For more information about user-defined methods, see "PeopleSoft: Component Interface User-Defined Methods" in the adapter documentation.</span></span>  
  
##### <a name="set-the-component-interface-security"></a><span data-ttu-id="0ec96-561">设置组件接口安全性</span><span class="sxs-lookup"><span data-stu-id="0ec96-561">Set the component interface security</span></span>  
 <span data-ttu-id="0ec96-562">在 PeopleSoft 上安装自定义 GET_CI_INFO PeopleSoft 组件接口后，设置的安全设置**GetCINamespace**， **GetDetails**，和**GetCollections**用于 PeopleSoft Enterprise 的 BizTalk 适配器的方法。</span><span class="sxs-lookup"><span data-stu-id="0ec96-562">After you install the custom GET_CI_INFO PeopleSoft component interface on PeopleSoft, set the security settings for **GetCINamespace**, **GetDetails**, and **GetCollections** methods for BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="0ec96-563">这是创建自定义组件或用户定义方法的标准做法。</span><span class="sxs-lookup"><span data-stu-id="0ec96-563">This is standard practice when you create custom components or user-defined methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-564">以下过程介绍如何在所有支持的模式下为 PeopleSoft 的所有支持发行版配置安全性。</span><span class="sxs-lookup"><span data-stu-id="0ec96-564">The following procedure describes how to configure security for all supported releases of PeopleSoft in all supported modes.</span></span>  
>   
>  <span data-ttu-id="0ec96-565">要配置组件接口的安全性</span><span class="sxs-lookup"><span data-stu-id="0ec96-565">To configure security for the component interface</span></span>  
  
1.  <span data-ttu-id="0ec96-566">指向**PeopleTools**，依次指向**安全**，指向**权限与角色**，然后选择**权限列表**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-566">Point to **PeopleTools**, point to **Security**, point to **Permissions & Roles**, and then select **Permission Lists**.</span></span>  
  
2.  <span data-ttu-id="0ec96-567">在中**维护安全**窗口中，单击**搜索**，选择相关**权限列表**，然后单击相应的列表超链接。</span><span class="sxs-lookup"><span data-stu-id="0ec96-567">In the **Maintain Security** window, click **Search**, select the relevant **Permission List**, and then click the appropriate list hyperlink.</span></span>  
  
3.  <span data-ttu-id="0ec96-568">在中**权限列表**窗格在右侧，单击右箭头旁边**登录时间**选项卡以显示**组件接口**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ec96-568">In the **Permission List** pane on the right, click the right arrow next to the **Sign-on Times** tab to display the **Component Interfaces** tab.</span></span>  
  
4.  <span data-ttu-id="0ec96-569">单击**组件接口**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0ec96-569">Click the **Component Interfaces** tab.</span></span>  
  
5.  <span data-ttu-id="0ec96-570">单击加号 （+） 以将新行添加到**组件接口**列表。</span><span class="sxs-lookup"><span data-stu-id="0ec96-570">Click the plus sign (+) to add a new row to the **Component Interfaces** list.</span></span>  
  
6.  <span data-ttu-id="0ec96-571">选择**GET_CI_INFO**组件接口，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-571">Select the **GET_CI_INFO** component interface, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="0ec96-572">将方法设置为**的完全访问权限**，单击 **（全部） 的完全访问权限**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-572">To set the methods to **Full Access**, click **Full Access (All)**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="0ec96-573">滚动到底部**组件接口**窗口，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-573">Scroll to the bottom of the **Component Interfaces** window, and then click **Save**.</span></span>  
  
##### <a name="test-the-component-interface"></a><span data-ttu-id="0ec96-574">测试组件接口</span><span class="sxs-lookup"><span data-stu-id="0ec96-574">Test the component interface</span></span>  
 <span data-ttu-id="0ec96-575">你已经为以 PeopleSoft Enterprise 的 BizTalk 适配器传递的 GET_CI_INFO 组件接口完成了配置安全性的工作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-575">You have finished configuring security for the GET_CI_INFO component interface delivered with BizTalk Adapter for PeopleSoft Enterprise.</span></span> <span data-ttu-id="0ec96-576">你的 PeopleSoft 组件接口已准备就绪，可浏览 PeopleSoft 组件接口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-576">Your PeopleSoft component interface is ready, and you can browse PeopleSoft component interfaces.</span></span>  
  
 <span data-ttu-id="0ec96-577">请按照以下步骤在应用程序设计器中测试组件接口。</span><span class="sxs-lookup"><span data-stu-id="0ec96-577">Follow these steps to test the component interface in the Application Designer.</span></span>  
  
 <span data-ttu-id="0ec96-578">若要测试组件接口</span><span class="sxs-lookup"><span data-stu-id="0ec96-578">To test the component interface</span></span>  
  
1.  <span data-ttu-id="0ec96-579">启动**PeopleSoft 应用程序设计器**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-579">Start the **PeopleSoft Application Designer**.</span></span>  
  
2.  <span data-ttu-id="0ec96-580">上**文件**菜单，依次指向**打开**，然后选择**定义 = 组件接口**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-580">On the **File** menu, point to **Open**, and then select **Definition = Component Interface**.</span></span>  
  
3.  <span data-ttu-id="0ec96-581">从组件接口的列表中选择**GET_CI_INFO CI**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-581">From the list of component interfaces, select **GET_CI_INFO CI**.</span></span>  
  
4.  <span data-ttu-id="0ec96-582">打开 GET_CI_INFO 后，在组件接口定义中，右窗格中右键单击任意位置，然后选择**测试组件接口**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-582">After you open GET_CI_INFO, right-click anywhere in the right pane of your component interface definition, and then select **Test Component Interface**.</span></span>  
  
<span data-ttu-id="0ec96-583">**Component Interface Tester**窗口随即打开。</span><span class="sxs-lookup"><span data-stu-id="0ec96-583">The **Component Interface Tester** window opens.</span></span> <span data-ttu-id="0ec96-584">不应列出任何键。</span><span class="sxs-lookup"><span data-stu-id="0ec96-584">There should be no keys listed.</span></span> <span data-ttu-id="0ec96-585">如果 GET_CI_INFO 包含键，或如果没有为所选内容的另一种方法，返回到应用程序设计器中，并消除 GET_CI_INFO 中的所有键。</span><span class="sxs-lookup"><span data-stu-id="0ec96-585">If your GET_CI_INFO contains keys, or if there is another option for selection, return to the Application Designer, and eliminate all keys from GET_CI_INFO.</span></span>  
  
## <a name="install-steps"></a><span data-ttu-id="0ec96-586">安装步骤</span><span class="sxs-lookup"><span data-stu-id="0ec96-586">Install steps</span></span>
 <span data-ttu-id="0ec96-587">在安装之前，请确保 BizTalk Server 并安装所有必备软件的适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-587">Before you install, be sure BizTalk Server and all the software prerequisites for the adapters are installed.</span></span> <span data-ttu-id="0ec96-588">建议你运行安装程序之前关闭所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-588">It is recommended that you close all applications before running Setup.</span></span>  
  
1.  <span data-ttu-id="0ec96-589">运行 BizTalk Server **Setup.exe**，选择**安装 Microsoft BizTalk 适配器**，然后选择**用于企业应用程序中安装 Microsoft BizTalk 适配器**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-589">Run the BizTalk Server **Setup.exe**, select **Install Microsoft BizTalk Adapters**, and select **Install Microsoft BizTalk Adapters for Enterprise Applications**.</span></span>  
  
    > [!NOTE]
    >  - <span data-ttu-id="0ec96-590">您还可以运行使用以下命令无提示安装： msiexec /i < msi\> /qn /l\* < 日志文件\>-其中 < 日志文件\>是可选的但如果安装失败非常有用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-590">You can also run a silent installation using the following command: msiexec /i <msi\> /qn /l\* <logfile\> -- where <logfile\> is optional, but is useful in the event of a failed installation.</span></span>  
    >  - <span data-ttu-id="0ec96-591">安装更新了 PATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="0ec96-591">The installation updates the PATH environment variable.</span></span> <span data-ttu-id="0ec96-592">要确保正在使用正确的变量，请关闭安装命令窗口来更新你的变量。</span><span class="sxs-lookup"><span data-stu-id="0ec96-592">To make sure that you are using the correct variables, close the installation command window to update your variables.</span></span>  
  
2.  <span data-ttu-id="0ec96-593">接受**许可协议**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-593">Accept the **License Agreement**, and select **Next**.</span></span>
  
3.  <span data-ttu-id="0ec96-594">输入你**客户信息**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-594">Enter your **Customer Information**, and select **Next**.</span></span>  
  
4.  <span data-ttu-id="0ec96-595">选择**完成**或**自定义**安装：</span><span class="sxs-lookup"><span data-stu-id="0ec96-595">Select a **Complete** or **Custom** installation:</span></span> 
  
    -   <span data-ttu-id="0ec96-596">**完整**： 企业应用程序，所有程序功能，可安装所有 Microsoft BizTalk 适配器，用于开发和运行时。</span><span class="sxs-lookup"><span data-stu-id="0ec96-596">**Complete**: Installs all the Microsoft BizTalk Adapters for Enterprise Applications, all the program features, and is used for development and run time.</span></span>  
  
    -   <span data-ttu-id="0ec96-597">**自定义**： 您选择的适配器和功能，你想要安装，并安装位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-597">**Custom**: You choose the adapters and features that you want to install, and where they are installed.</span></span>  
  
    <span data-ttu-id="0ec96-598">若要设置目标，请选择**浏览**，并设置安装路径。</span><span class="sxs-lookup"><span data-stu-id="0ec96-598">To set the destination, select **Browse**, and set the installation path.</span></span>  
  
    <span data-ttu-id="0ec96-599">选择**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="0ec96-599">Select **Next** to continue.</span></span>  
  
5. <span data-ttu-id="0ec96-600">**安装**，然后选择**完成**时完成。</span><span class="sxs-lookup"><span data-stu-id="0ec96-600">**Install**, and select **Finish** when complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0ec96-601">在安装过程中，可能会遇到以下错误：</span><span class="sxs-lookup"><span data-stu-id="0ec96-601">You may encounter the following error during installation:</span></span>  
>   
>  `Error 1609. An error occurred while applying security settings. CREATOR OWNER is not a valid user or group`  
>   
>  <span data-ttu-id="0ec96-602">若要解决此错误，执行以下操作，并再次运行安装程序：</span><span class="sxs-lookup"><span data-stu-id="0ec96-602">To work around this error, do the following, and run the installation again:</span></span>  
>   
>  1. <span data-ttu-id="0ec96-603">打开命令提示符</span><span class="sxs-lookup"><span data-stu-id="0ec96-603">Open a command prompt</span></span>
>  2. <span data-ttu-id="0ec96-604">类型： `net user "CREATOR OWNER" /add`。</span><span class="sxs-lookup"><span data-stu-id="0ec96-604">Type: `net user "CREATOR OWNER" /add`.</span></span> <span data-ttu-id="0ec96-605">这将创建一个名为 CREATOR OWNER 的新用户。</span><span class="sxs-lookup"><span data-stu-id="0ec96-605">This creates a new user called CREATOR OWNER.</span></span>
>  3. <span data-ttu-id="0ec96-606">类型： `net localgroup Users /add`。</span><span class="sxs-lookup"><span data-stu-id="0ec96-606">Type: `net localgroup Users /add`.</span></span> <span data-ttu-id="0ec96-607">这将创建名为用户的新组。</span><span class="sxs-lookup"><span data-stu-id="0ec96-607">This creates a new group called Users.</span></span>
  
<span data-ttu-id="0ec96-608">若要将适配器添加到 BizTalk Server，请参阅"添加适配器向 BizTalk 管理员"本主题中。</span><span class="sxs-lookup"><span data-stu-id="0ec96-608">To add the adapters to BizTalk Server, see "Add adapters to BizTalk Admin" in this topic.</span></span>

## <a name="add-adapters-to-biztalk-admin"></a><span data-ttu-id="0ec96-609">将适配器添加到 BizTalk 管理员</span><span class="sxs-lookup"><span data-stu-id="0ec96-609">Add adapters to BizTalk Admin</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0ec96-610">如果在多计算机环境 （仅限运行时的一台计算机上的安装和管理仅工具安装在另一台计算机上的） 中安装 BizTalk，你应在两台计算机上用于企业应用程序安装 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-610">If you install BizTalk in a multicomputer environment (runtime-only installation on one computer, and an administration tools-only installation on another computer),  you should install the BizTalk Adapters for Enterprise Applications on both the computers.</span></span>  
  
1.  <span data-ttu-id="0ec96-611">打开 BizTalk Server 管理控制台中，依次展开**Microsoft BizTalk Server**，然后展开**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-611">Open the BizTalk Server Administration Console, expand **Microsoft BizTalk Server**, and then expand **Platform Settings**.</span></span>  
  
2.  <span data-ttu-id="0ec96-612">右键单击**适配器**，选择**新建**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-612">Right-click **Adapters**, select **New**, and then select **Adapter**.</span></span>  
  
3.  <span data-ttu-id="0ec96-613">输入一个名称，例如**PeopleSoft**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-613">Enter a name, such as **PeopleSoft**.</span></span>  
  
4.  <span data-ttu-id="0ec96-614">选择从输入的名称**适配器**列表，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-614">Select the name you entered from the **Adapter** list, and select **OK**.</span></span>  
   
## <a name="post-install---jd-edwards-oneworld"></a><span data-ttu-id="0ec96-615">安装后的 JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="0ec96-615">Post-install - JD Edwards OneWorld</span></span>  
 <span data-ttu-id="0ec96-616">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器包含接口支持的数据库和服务器系统与 Microsoft BizTalk Server 传输适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-616">Microsoft BizTalk Adapter for JD Edwards OneWorld consists of a transmit adapter that interfaces supported databases and server systems to Microsoft BizTalk Server.</span></span> <span data-ttu-id="0ec96-617">通过传输适配器，你可以从 BizTalk 服务器调用服务器系统。</span><span class="sxs-lookup"><span data-stu-id="0ec96-617">The transmit adapter enables you to invoke a server system's call from BizTalk Server.</span></span> <span data-ttu-id="0ec96-618">传输适配器（BizTalk 服务器管理发送处理程序）配置指定 SQL 数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-618">The transmit adapter (the BizTalk Server Administration Send Handler) configuration specifies the location of the SQL database.</span></span>  
  
 <span data-ttu-id="0ec96-619">有关如何使用用于 JD Edwards OneWorld 的 BizTalk 适配器以及在它的模型和 BizTalk 服务器模型之间进行映射的详细信息，请参阅适配器文档。</span><span class="sxs-lookup"><span data-stu-id="0ec96-619">See the adapter documentation for information about how to use BizTalk Adapter for JD Edwards OneWorld and about the mapping between its model and the BizTalk Server model.</span></span>  
  
### <a name="single-sign-on"></a><span data-ttu-id="0ec96-620">单一登录</span><span class="sxs-lookup"><span data-stu-id="0ec96-620">Single Sign-On</span></span>  
 <span data-ttu-id="0ec96-621">用于 JD Edwards OneWorld 的 BizTalk 适配器提供支持的企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-621">BizTalk Adapter for JD Edwards OneWorld provides support for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="0ec96-622">如果你选择要使用的 SSO**传输属性**页上，凭据用于 SSO 凭据数据库中的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-622">If you select to use SSO in the **Transport Properties** page, the credentials for the affiliate application in the SSO Credentials database are used.</span></span> <span data-ttu-id="0ec96-623">关联应用程序表示一个应用程序 - 一个需要凭据的后端。</span><span class="sxs-lookup"><span data-stu-id="0ec96-623">An affiliate application represents an application—a back-end that requires credentials.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="0ec96-624">已安装的组件</span><span class="sxs-lookup"><span data-stu-id="0ec96-624">Installed components</span></span>  

* <span data-ttu-id="0ec96-625">适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-625">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="0ec96-626">你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符：</span><span class="sxs-lookup"><span data-stu-id="0ec96-626">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span>

    -   <span data-ttu-id="0ec96-627">Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-627">Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="0ec96-628">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-628">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>    
    -   <span data-ttu-id="0ec96-629">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-629">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="0ec96-630">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-630">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="0ec96-631">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-631">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  

  
* <span data-ttu-id="0ec96-632">btsTask.exe 安装并部署`Microsoft.BizTalk.Adapters.JDEProperties.dll`到 gac 中的文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-632">btsTask.exe installs and deploys the `Microsoft.BizTalk.Adapters.JDEProperties.dll` file to the GAC.</span></span> <span data-ttu-id="0ec96-633">BizTalk Server 部署日志结果位于*\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\jdeDeploy.html*并**jdeDeploy.xml**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-633">The BizTalk Server deployment log results are in *\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\jdeDeploy.html* and **jdeDeploy.xml**.</span></span>
  
* <span data-ttu-id="0ec96-634">特定于适配器的文件安装在*Program Files*并*Program Files\Common Files*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-634">Adapter-specific files are installed in *Program Files* and *Program Files\Common Files*.</span></span>  
  
* <span data-ttu-id="0ec96-635">`sdk\`安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ J.D.Edwards OneWorld(r)*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-635">The `sdk\` is installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ J.D. Edwards OneWorld(r)*.</span></span>
  
* <span data-ttu-id="0ec96-636">* 程序 Files\Microsoft BizTalk Adapters for Enterprise Applications\JD Edwards OneWorld(r)\*包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-636">*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\JD Edwards OneWorld(r)\* contains the following files:</span></span>  
  
    -   <span data-ttu-id="0ec96-637">classes\JDEJAccess.jar</span><span class="sxs-lookup"><span data-stu-id="0ec96-637">classes\JDEJAccess.jar</span></span>    
    -   <span data-ttu-id="0ec96-638">Config\ J.D.</span><span class="sxs-lookup"><span data-stu-id="0ec96-638">Config\ J.D.</span></span> <span data-ttu-id="0ec96-639">Edwards OneWorld(r) \BTSREL.exe</span><span class="sxs-lookup"><span data-stu-id="0ec96-639">Edwards OneWorld(r) \BTSREL.exe</span></span>    
    -   <span data-ttu-id="0ec96-640">Config\ J.D.</span><span class="sxs-lookup"><span data-stu-id="0ec96-640">Config\ J.D.</span></span> <span data-ttu-id="0ec96-641">Edwards OneWorld(r) \jdearglist.txt</span><span class="sxs-lookup"><span data-stu-id="0ec96-641">Edwards OneWorld(r) \jdearglist.txt</span></span>    
    -   <span data-ttu-id="0ec96-642">Config\ J.D.</span><span class="sxs-lookup"><span data-stu-id="0ec96-642">Config\ J.D.</span></span> <span data-ttu-id="0ec96-643">Edwards OneWorld(r) \jdeinterop.ini</span><span class="sxs-lookup"><span data-stu-id="0ec96-643">Edwards OneWorld(r) \jdeinterop.ini</span></span>  
  
* <span data-ttu-id="0ec96-644">* 编程 Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin\*包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-644">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin\* contains the following files:</span></span>  
  
    -   <span data-ttu-id="0ec96-645">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-645">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>    
    -   <span data-ttu-id="0ec96-646">jdecba.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-646">jdecba.dll</span></span>  
  
## <a name="post-install---jd-edwards-enterpriseone"></a><span data-ttu-id="0ec96-647">安装后的 JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="0ec96-647">Post-install - JD Edwards EnterpriseOne</span></span>  
 <span data-ttu-id="0ec96-648">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器包含支持的数据库和服务器系统与 BizTalk Server 与连接的传输适配器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-648">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne contains a transmit adapter that interfaces with supported databases and server systems to BizTalk Server.</span></span> <span data-ttu-id="0ec96-649">传输适配器允许你从 BizTalk 服务器调用服务系统。</span><span class="sxs-lookup"><span data-stu-id="0ec96-649">The transmit adapter enables you to invoke a server system’s call from BizTalk Server.</span></span>  
  
 <span data-ttu-id="0ec96-650">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器提供支持的企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-650">BizTalk Adapter for JD Edwards EnterpriseOne provides support for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="0ec96-651">如果你选择要使用的 SSO**传输属性**页上，凭据用于 SSO 凭据数据库中的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-651">If you select to use SSO in the **Transport Properties** page, the credentials for the affiliate application in the SSO Credentials database are used.</span></span> <span data-ttu-id="0ec96-652">关联应用程序表示一个应用程序 - 一个需要凭据的后端。</span><span class="sxs-lookup"><span data-stu-id="0ec96-652">An affiliate application represents an application—a back-end that requires credentials.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="0ec96-653">已安装的组件</span><span class="sxs-lookup"><span data-stu-id="0ec96-653">Installed components</span></span>  
* <span data-ttu-id="0ec96-654">适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-654">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="0ec96-655">你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符：</span><span class="sxs-lookup"><span data-stu-id="0ec96-655">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span>
  
    -   <span data-ttu-id="0ec96-656">Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-656">Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="0ec96-657">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-657">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>    
    -   <span data-ttu-id="0ec96-658">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-658">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="0ec96-659">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-659">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="0ec96-660">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-660">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>    

* <span data-ttu-id="0ec96-661">特定于适配器的文件安装在*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin*文件夹。</span><span class="sxs-lookup"><span data-stu-id="0ec96-661">The adapter-specific files are installed in the *Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\Bin* folder.</span></span> <span data-ttu-id="0ec96-662">此文件夹包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-662">This folder contains the following files:</span></span>  
  
    -   <span data-ttu-id="0ec96-663">Jdecba.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-663">Jdecba.dll</span></span>    
    -   <span data-ttu-id="0ec96-664">Microsoft.BizTalk.Adapters.JDEProperties.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-664">Microsoft.BizTalk.Adapters.JDEProperties.dll</span></span>  
  
* <span data-ttu-id="0ec96-665">以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise applications\j.d.。Edwards EnterpriseOne(r)*:</span><span class="sxs-lookup"><span data-stu-id="0ec96-665">The following files are installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards EnterpriseOne(r)*:</span></span>  
  
    -   <span data-ttu-id="0ec96-666">Bin\BTAJDEEnterpriseOneTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="0ec96-666">Bin\BTAJDEEnterpriseOneTrace.cmd</span></span>    
    -   <span data-ttu-id="0ec96-667">Classes\JDEDynAccess.jar</span><span class="sxs-lookup"><span data-stu-id="0ec96-667">Classes\JDEDynAccess.jar</span></span>    
    -   <span data-ttu-id="0ec96-668">Config\btaJDEEnterpriseOneTrace.mof</span><span class="sxs-lookup"><span data-stu-id="0ec96-668">Config\btaJDEEnterpriseOneTrace.mof</span></span>    
    -   <span data-ttu-id="0ec96-669">Config\jdearglist.txt</span><span class="sxs-lookup"><span data-stu-id="0ec96-669">Config\jdearglist.txt</span></span>    
    -   <span data-ttu-id="0ec96-670">Config\jdeinterop.ini</span><span class="sxs-lookup"><span data-stu-id="0ec96-670">Config\jdeinterop.ini</span></span>    
    -   <span data-ttu-id="0ec96-671">Config\jdelog.properties</span><span class="sxs-lookup"><span data-stu-id="0ec96-671">Config\jdelog.properties</span></span>    
    -   <span data-ttu-id="0ec96-672">Sdk</span><span class="sxs-lookup"><span data-stu-id="0ec96-672">Sdk</span></span>  
  
 
## <a name="post-install---peoplesoft-enterprise"></a><span data-ttu-id="0ec96-673">安装后的 PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="0ec96-673">Post-install - PeopleSoft Enterprise</span></span>  
 <span data-ttu-id="0ec96-674">用于 PeopleSoft Enterprise 的 Microsof BizTalk 适配器包括一个传输适配器，该适配器将支持的数据库和服务器系统与 BizTalk 服务器相连接。</span><span class="sxs-lookup"><span data-stu-id="0ec96-674">Microsoft BizTalk Adapter for PeopleSoft Enterprise contains a transmit adapter that interfaces supported databases and server systems to BizTalk Server.</span></span> <span data-ttu-id="0ec96-675">传输适配器允许你从 BizTalk 服务器调用服务系统。</span><span class="sxs-lookup"><span data-stu-id="0ec96-675">The transmit adapter enables you to invoke a server system’s call from BizTalk Server.</span></span> <span data-ttu-id="0ec96-676">传输适配器（BizTalk 服务器管理发送处理程序）配置指定 SQL 数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-676">The transmit adapter (the BizTalk Server Administration Send Handler) configuration specifies the location of the SQL database.</span></span>  
  
 <span data-ttu-id="0ec96-677">用于 PeopleSoft Enterprise 的 BizTalk 适配器提供支持的企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="0ec96-677">BizTalk Adapter for PeopleSoft Enterprise provides support for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="0ec96-678">如果你选择要使用的 SSO**传输属性**页上，凭据用于 SSO 凭据数据库中的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-678">If you select to use SSO in the **Transport Properties** page, the credentials for the affiliate application in the SSO Credentials database are used.</span></span> <span data-ttu-id="0ec96-679">关联应用程序表示一个应用程序 - 一个需要凭据的后端。</span><span class="sxs-lookup"><span data-stu-id="0ec96-679">An affiliate application represents an application—a back-end that requires credentials.</span></span>  
  
 <span data-ttu-id="0ec96-680">适配器安装包括 \sdk 目录中的示例。</span><span class="sxs-lookup"><span data-stu-id="0ec96-680">The adapter installation includes samples in the \sdk directory.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="0ec96-681">已安装的组件</span><span class="sxs-lookup"><span data-stu-id="0ec96-681">Installed components</span></span>  
* <span data-ttu-id="0ec96-682">适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-682">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="0ec96-683">你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符：</span><span class="sxs-lookup"><span data-stu-id="0ec96-683">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span>
  
    -   <span data-ttu-id="0ec96-684">Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-684">Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="0ec96-685">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-685">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="0ec96-686">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-686">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="0ec96-687">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-687">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>    

* <span data-ttu-id="0ec96-688">特定于适配器的文件安装在*Program Files*并*Program Files\Common Files*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-688">Adapter-specific files are installed in *Program Files* and *Program Files\Common Files*.</span></span> <span data-ttu-id="0ec96-689">以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise (r)*:</span><span class="sxs-lookup"><span data-stu-id="0ec96-689">The following files are installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise (r)*:</span></span>
  
    -   <span data-ttu-id="0ec96-690">bin\BTAPeopleSoftTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="0ec96-690">bin\BTAPeopleSoftTrace.cmd</span></span>    
    -   <span data-ttu-id="0ec96-691">config\btaPeopleSoftTrace.mof</span><span class="sxs-lookup"><span data-stu-id="0ec96-691">config\btaPeopleSoftTrace.mof</span></span>    
    -   <span data-ttu-id="0ec96-692">config\GET_CI_INFO.pc</span><span class="sxs-lookup"><span data-stu-id="0ec96-692">config\GET_CI_INFO.pc</span></span>    
    -   <span data-ttu-id="0ec96-693">config\GET_CI_INFO.pc</span><span class="sxs-lookup"><span data-stu-id="0ec96-693">config\GET_CI_INFO.pc</span></span>    
    -   <span data-ttu-id="0ec96-694">sdk\\</span><span class="sxs-lookup"><span data-stu-id="0ec96-694">sdk\\</span></span>  
  
* <span data-ttu-id="0ec96-695">*用于企业应用程序进行编程 Files\Common Files\Microsoft BizTalk Adapters*包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-695">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications* contains the following files:</span></span>  
  
    -   <span data-ttu-id="0ec96-696">bin\psosa.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-696">bin\psosa.dll</span></span>    
    -   <span data-ttu-id="0ec96-697">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-697">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="0ec96-698">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-698">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="0ec96-699">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-699">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  
  
## <a name="post-install-overview---tibco-rendezvous"></a><span data-ttu-id="0ec96-700">安装后概述-TIBCO Rendezvous</span><span class="sxs-lookup"><span data-stu-id="0ec96-700">Post-install overview - TIBCO Rendezvous</span></span>  
 <span data-ttu-id="0ec96-701">用于 TIBCO Rendezvous 的 BizTalk 适配器包括接收和传输功能，该功能将支持的数据库和服务器系统与 BizTalk 服务器相连接。</span><span class="sxs-lookup"><span data-stu-id="0ec96-701">Microsoft BizTalk Adapter for TIBCO Rendezvous contains receive and transmit functionality that interface with supported databases and server systems to BizTalk Server.</span></span>  
  
- <span data-ttu-id="0ec96-702">接收端侦听来从服务器系统出站的调用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-702">The receive side listens for calls that are outbound from the server system.</span></span>  
  
- <span data-ttu-id="0ec96-703">传输端使你能够从 BizTalk 服务器调用服务器系统。</span><span class="sxs-lookup"><span data-stu-id="0ec96-703">The transmit side enables you to invoke a server system’s call from BizTalk Server.</span></span>  
  
  <span data-ttu-id="0ec96-704">请参阅适配器文档，以了解有关如何使用用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器以及有关其模型和 BizTalk 服务器模型之间的映射。</span><span class="sxs-lookup"><span data-stu-id="0ec96-704">See the adapter documentation for information about how to use Microsoft BizTalk Adapter for TIBCO Rendezvous and about the mapping between its model and the BizTalk Server model.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="0ec96-705">已安装的组件</span><span class="sxs-lookup"><span data-stu-id="0ec96-705">Installed components</span></span>  
* <span data-ttu-id="0ec96-706">适配器安装安装，并在全局程序集缓存 (GAC) 中注册以下组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-706">The adapter installation installs and registers the following components in the global assembly cache (GAC).</span></span> <span data-ttu-id="0ec96-707">你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符：</span><span class="sxs-lookup"><span data-stu-id="0ec96-707">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt:</span></span> 
  
    -   <span data-ttu-id="0ec96-708">Microsoft.BizTalk.Adapters.TibcoRV</span><span class="sxs-lookup"><span data-stu-id="0ec96-708">Microsoft.BizTalk.Adapters.TibcoRV</span></span>    
    -   <span data-ttu-id="0ec96-709">Microsoft.BizTalk.Adapters.TibcoRV.Common</span><span class="sxs-lookup"><span data-stu-id="0ec96-709">Microsoft.BizTalk.Adapters.TibcoRV.Common</span></span>    
    -   <span data-ttu-id="0ec96-710">Microsoft.BizTalk.Adapters.TibcoRV.Service</span><span class="sxs-lookup"><span data-stu-id="0ec96-710">Microsoft.BizTalk.Adapters.TibcoRV.Service</span></span>    
    -   <span data-ttu-id="0ec96-711">Microsoft.BizTalk.Adapters.TibRV.Properties</span><span class="sxs-lookup"><span data-stu-id="0ec96-711">Microsoft.BizTalk.Adapters.TibRV.Properties</span></span>    
    -   <span data-ttu-id="0ec96-712">Microsoft.BizTalk.Adapters.TibcoEMS</span><span class="sxs-lookup"><span data-stu-id="0ec96-712">Microsoft.BizTalk.Adapters.TibcoEMS</span></span>    
    -   <span data-ttu-id="0ec96-713">Microsoft.BizTalk.Adapters.TibcoEMS.Properties</span><span class="sxs-lookup"><span data-stu-id="0ec96-713">Microsoft.BizTalk.Adapters.TibcoEMS.Properties</span></span>    
    -   <span data-ttu-id="0ec96-714">Microsoft.BizTalk.Adapters.TibcoRVManagement</span><span class="sxs-lookup"><span data-stu-id="0ec96-714">Microsoft.BizTalk.Adapters.TibcoRVManagement</span></span>    
    -   <span data-ttu-id="0ec96-715">Microsoft.BizTalk.Adapters.TibcoRVReceiver</span><span class="sxs-lookup"><span data-stu-id="0ec96-715">Microsoft.BizTalk.Adapters.TibcoRVReceiver</span></span>  
    -   <span data-ttu-id="0ec96-716">Microsoft.BizTalk.Adapters.TibcoRVTransmitter</span><span class="sxs-lookup"><span data-stu-id="0ec96-716">Microsoft.BizTalk.Adapters.TibcoRVTransmitter</span></span>  
  
* <span data-ttu-id="0ec96-717">特定于适配器的文件安装在*Program Files 和 Program Files\Common Files*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-717">Adapter-specific files are installed in *Program Files and Program Files\Common Files*.</span></span> <span data-ttu-id="0ec96-718">以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ tibco （) Rendezvous(r)*:</span><span class="sxs-lookup"><span data-stu-id="0ec96-718">The following files are installed in *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\ TIBCO(r) Rendezvous(r)*:</span></span>  
  
    -   <span data-ttu-id="0ec96-719">bin\BTATibcoRVTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="0ec96-719">bin\BTATibcoRVTrace.cmd</span></span>    
    -   <span data-ttu-id="0ec96-720">bin\mbaRV.exe</span><span class="sxs-lookup"><span data-stu-id="0ec96-720">bin\mbaRV.exe</span></span>    
    -   <span data-ttu-id="0ec96-721">bin\Microsoft.BizTalk.Adapters.TibcoRV.Common.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-721">bin\Microsoft.BizTalk.Adapters.TibcoRV.Common.dll</span></span>    
    -   <span data-ttu-id="0ec96-722">bin\Microsoft.BizTalk.Adapters.TibcoRV.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-722">bin\Microsoft.BizTalk.Adapters.TibcoRV.dll</span></span>    
    -   <span data-ttu-id="0ec96-723">bin\Microsoft.BizTalk.Adapters.TibcoRV.Service.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-723">bin\Microsoft.BizTalk.Adapters.TibcoRV.Service.dll</span></span>    
    -   <span data-ttu-id="0ec96-724">bin\Microsoft.BizTalk.Adapters.BizUtil.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-724">bin\Microsoft.BizTalk.Adapters.BizUtil.dll</span></span>    
    -   <span data-ttu-id="0ec96-725">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-725">bin\Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="0ec96-726">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-726">bin\Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="0ec96-727">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-727">bin\Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>    
    -   <span data-ttu-id="0ec96-728">bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-728">bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll</span></span>    
    -   <span data-ttu-id="0ec96-729">Config\btaTibcoRVTrace.mof</span><span class="sxs-lookup"><span data-stu-id="0ec96-729">Config\btaTibcoRVTrace.mof</span></span>    
    -   <span data-ttu-id="0ec96-730">sdk\\</span><span class="sxs-lookup"><span data-stu-id="0ec96-730">sdk\\</span></span>  
  
* <span data-ttu-id="0ec96-731">*用于企业应用程序进行编程 Files\Common Files\Microsoft BizTalk Adapters*包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-731">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications* contains the following files:</span></span>  
  
    -   <span data-ttu-id="0ec96-732">bin\tibcorvcba.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-732">bin\tibcorvcba.dll</span></span>    
    -   <span data-ttu-id="0ec96-733">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-733">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
    -   <span data-ttu-id="0ec96-734">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-734">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
    -   <span data-ttu-id="0ec96-735">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-735">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  
  
### <a name="add-tibcorendezvousdll-to-the-gac"></a><span data-ttu-id="0ec96-736">添加 TIBCO。Rendezvous.dll 到 GAC</span><span class="sxs-lookup"><span data-stu-id="0ec96-736">Add TIBCO.Rendezvous.dll to the GAC</span></span>  
 <span data-ttu-id="0ec96-737">用于 TIBCO Rendezvous 的 BizTalk 适配器要求**TIBCO。Rendezvous.dll**文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-737">BizTalk Adapter for TIBCO Rendezvous requires the **TIBCO.Rendezvous.dll** file.</span></span> <span data-ttu-id="0ec96-738">所需的最低版本是 1.0.3036.23330 附带的产品版本 8.1 的文件版本。</span><span class="sxs-lookup"><span data-stu-id="0ec96-738">The minimum version that is required is 1.0.3036.23330 FileVersion, which is shipped with the product version 8.1.</span></span> <span data-ttu-id="0ec96-739">如果未安装此程序集，则适配器会触发异常并记录相应的消息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-739">The adapter triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
 <span data-ttu-id="0ec96-740">必须使用后期绑定加载程序集，以便当特定版本的 TIBCO TIBCO Rendezvous 程序集不会发生故障。Rendezvous.dll 和 TIBCO。Rendezvous.net 模块不是目标计算机上。</span><span class="sxs-lookup"><span data-stu-id="0ec96-740">You must use late binding to load assemblies so that the TIBCO Rendezvous assemblies don't fail when a particular version of the TIBCO.Rendezvous.dll and TIBCO.Rendezvous.net module aren't on the target computer.</span></span>
  
 <span data-ttu-id="0ec96-741">**运行时组件**</span><span class="sxs-lookup"><span data-stu-id="0ec96-741">**Runtime Component**</span></span>  
  
 <span data-ttu-id="0ec96-742">验证你的计算机上安装了 TIBCO Rendezvous 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-742">Verify you have the TIBCO Rendezvous Runtime Component installed on your computer.</span></span> <span data-ttu-id="0ec96-743">运行时组件是安装 TIBCO Rendezvous 时必须安装的唯一组件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-743">The Runtime Component is the only component that you must install when you install TIBCO Rendezvous.</span></span>  

1. <span data-ttu-id="0ec96-744">在 Visual Studio 命令提示符中，将目录更改为 TIBCO 的位置。Rendezvous.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-744">In a Visual Studio command prompt, change directories to the location of the TIBCO.Rendezvous.dll file.</span></span> <span data-ttu-id="0ec96-745">在 TIBCO rendezvous 默认安装此 DLL 的路径是**C:\TIBCO\TIBRV\BIN\TIBCO。Rendezvous.dll**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-745">The path of this DLL in the default installation of TIBCO Rendezvous is **C:\TIBCO\TIBRV\BIN\TIBCO.Rendezvous.dll**.</span></span>  
  
2. <span data-ttu-id="0ec96-746">在命令提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="0ec96-746">At the command prompt, type the following:</span></span>  
  
```
C:\TIBCO\TIBRV\BIN > gacutil /i TIBCO.Rendezvous.dll
```
  
 <span data-ttu-id="0ec96-747">TIBCO.Rendezvous.dl 现在显示 GAC 列表。</span><span class="sxs-lookup"><span data-stu-id="0ec96-747">The TIBCO.Rendezvous.dll now shows GAC list.</span></span> <span data-ttu-id="0ec96-748">若要查看列表中，在控制面板中，打开**管理工具**，打开**Microsoft.NET Framework 配置**，然后打开**程序集缓存**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-748">To view the list, in Control Panel, open **Administrator Tools**, open **Microsoft .NET Framework Configuration**, and then open **Assembly Cache**.</span></span>  
  
## <a name="post-install---tibco-enterprise-message-service"></a><span data-ttu-id="0ec96-749">安装后的 TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="0ec96-749">Post-install - TIBCO Enterprise Message Service</span></span>  
 <span data-ttu-id="0ec96-750">Microsoft BizTalk 适配器包含 TIBCO Enterprise Message Service (EMS) 接收和传输与支持的数据库和服务器系统与 BizTalk Server 进行交互的功能。</span><span class="sxs-lookup"><span data-stu-id="0ec96-750">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) contains receive and transmit functionality that interface with supported databases and server systems to BizTalk Server.</span></span>  
  
- <span data-ttu-id="0ec96-751">接收端侦听来从服务器系统出站的调用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-751">The receive side listens for calls that are outbound from the server system.</span></span>  

- <span data-ttu-id="0ec96-752">传输端使你能够从 BizTalk 服务器调用服务器系统。</span><span class="sxs-lookup"><span data-stu-id="0ec96-752">The transmit side enables you to invoke a server system’s call from BizTalk Server.</span></span>  
  
  <span data-ttu-id="0ec96-753">请参阅有关如何使用用于 TIBCO EMS 的 BizTalk 适配器以及其模型和 BizTalk 服务器模型之间的映射信息的适配器文档。</span><span class="sxs-lookup"><span data-stu-id="0ec96-753">See the adapter documentation for information about how to use BizTalk Adapter for TIBCO EMS and about the mapping between its model and the BizTalk Server model.</span></span>  
  
### <a name="installed-components"></a><span data-ttu-id="0ec96-754">已安装的组件</span><span class="sxs-lookup"><span data-stu-id="0ec96-754">Installed components</span></span>  
* <span data-ttu-id="0ec96-755">适配器安装安装并注册`Microsoft.BizTalk.Adapters.TibcoEMS.dll`全局程序集缓存 (GAC) 中的文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-755">The adapter installation installs and registers the `Microsoft.BizTalk.Adapters.TibcoEMS.dll` file in the global assembly cache (GAC).</span></span> <span data-ttu-id="0ec96-756">你可以通过在资源管理器中打开的程序集文件夹以验证注册 (< %WINDIR%> \assembly)，或使用`gacutil /l`从 Visual Studio 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="0ec96-756">You can verify the registration by opening the assembly folder in your explorer (<%WINDIR%>\assembly), or use the `gacutil /l` from the Visual Studio command prompt.</span></span>
  
* <span data-ttu-id="0ec96-757">特定于适配器的文件安装在*Program Files*并*Program Files\Common Files*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-757">Adapter-specific files are installed in *Program Files* and *Program Files\Common Files*.</span></span> <span data-ttu-id="0ec96-758">以下文件安装在*Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) 企业消息 Service(TM)*:</span><span class="sxs-lookup"><span data-stu-id="0ec96-758">The following files are installed under *Program Files\Microsoft BizTalk Adapters for Enterprise Applications\TIBCO(r) Enterprise Message Service(TM)*:</span></span>  
  
    -   <span data-ttu-id="0ec96-759">bin\BTATibcoEMSTrace.cmd</span><span class="sxs-lookup"><span data-stu-id="0ec96-759">bin\BTATibcoEMSTrace.cmd</span></span>    
    -   <span data-ttu-id="0ec96-760">Microsoft.BizTalk.Adapters.TibcoEMS.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-760">Microsoft.BizTalk.Adapters.TibcoEMS.dll</span></span>    
    -   <span data-ttu-id="0ec96-761">Config\btaTibcoEMSTrace.mof</span><span class="sxs-lookup"><span data-stu-id="0ec96-761">Config\btaTibcoEMSTrace.mof</span></span>    
    -   <span data-ttu-id="0ec96-762">sdk\\</span><span class="sxs-lookup"><span data-stu-id="0ec96-762">sdk\\</span></span>  
  
* <span data-ttu-id="0ec96-763">*程序 Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin*文件夹包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-763">*Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin* folder contains the following files:</span></span>  
  
  - <span data-ttu-id="0ec96-764">Microsoft.BizTalk.Adapters.CoreManagement.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-764">Microsoft.BizTalk.Adapters.CoreManagement.dll</span></span>    
  - <span data-ttu-id="0ec96-765">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-765">Microsoft.BizTalk.Adapters.CoreReceiver.dll</span></span>    
  - <span data-ttu-id="0ec96-766">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span><span class="sxs-lookup"><span data-stu-id="0ec96-766">Microsoft.BizTalk.Adapters.CoreTransmitter.dll</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ec96-767">必须使用后期绑定加载程序集，以便当特定版本的 TIBCO TIBCO EMS 程序集不会失败。EMS.dll 不存在于目标计算机上。</span><span class="sxs-lookup"><span data-stu-id="0ec96-767">You must use late binding to load assemblies so that the TIBCO EMS assemblies do not fail when a particular version of the TIBCO.EMS.dll is not present on the target computer.</span></span>  
  
### <a name="add-tibcoemsdll-api-to-the-gac"></a><span data-ttu-id="0ec96-768">添加 TIBCO。EMS.dll API 到 GAC</span><span class="sxs-lookup"><span data-stu-id="0ec96-768">Add TIBCO.EMS.dll API to the GAC</span></span>  
 <span data-ttu-id="0ec96-769">用于 TIBCO EMS 的 BizTalk 适配器要求将 TIBCO.EMS.dll 添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="0ec96-769">BizTalk Adapter for TIBCO EMS requires that you add the TIBCO.EMS.dll to the GAC.</span></span> <span data-ttu-id="0ec96-770">如果未安装该程序集，则用于 TIBCO EMS 的 BizTalk 适配器触发异常并记录相应的消息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-770">BizTalk Adapter for TIBCO EMS triggers an exception and logs an appropriate message if this assembly is not installed.</span></span>  
  
1. <span data-ttu-id="0ec96-771">将 TIBCO EMS C #API 复制到 BizTalk 计算机。</span><span class="sxs-lookup"><span data-stu-id="0ec96-771">Copy the TIBCO EMS C#API to your BizTalk computer.</span></span>  
  
2. <span data-ttu-id="0ec96-772">在 Visual Studio 命令提示符中，将目录更改为 C# API 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-772">In a Visual Studio command prompt, change directories to the location of the C# API file.</span></span>  
  
3. <span data-ttu-id="0ec96-773">在 Visual Studio 命令提示符中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="0ec96-773">In a Visual Studio command prompt, type the following:</span></span>  
  
   ```
   C:\\<TIBCO EMS Folder\>bin> gacutil /i TIBCO.EMS.dll
   ```
  
   <span data-ttu-id="0ec96-774">TIBCO.EMS.dll 现在显示在 C:\Windows\assembly 列表中。</span><span class="sxs-lookup"><span data-stu-id="0ec96-774">The TIBCO.EMS.dll now shows in the C:\Windows\assembly listing.</span></span> <span data-ttu-id="0ec96-775">或者，在控制面板中打开**管理工具**，打开**Microsoft.NET Framework**，并打开**程序集缓存**若要查看 GAC 列表。</span><span class="sxs-lookup"><span data-stu-id="0ec96-775">Or, in Control Panel, open **Administrator Tools**, open **Microsoft .NET Framework**, and open **Assembly Cache** to view the GAC list.</span></span>  
  
   <span data-ttu-id="0ec96-776">**限制**</span><span class="sxs-lookup"><span data-stu-id="0ec96-776">**Limitations**</span></span>  
  
   <span data-ttu-id="0ec96-777">用于 TIBCO EMS 的 BizTalk 适配器使用 TIBCO。若要与服务器通信的 EMS.dll。</span><span class="sxs-lookup"><span data-stu-id="0ec96-777">BizTalk Adapter for TIBCO EMS uses TIBCO.EMS.dll to communicate with the server.</span></span> <span data-ttu-id="0ec96-778">使用 TIBCO.EMS.dll 的限制如下：</span><span class="sxs-lookup"><span data-stu-id="0ec96-778">The following are limitations when you use the TIBCO.EMS.dll:</span></span>  
  
4. <span data-ttu-id="0ec96-779">消息压缩不可用，它允许 TIBCO EMS 客户端以压缩格式向 EMS 发送消息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-779">Message compression, which enables the TIBCO EMS client to send messages in a compressed form to EMS, is not available.</span></span>  
  
5. <span data-ttu-id="0ec96-780">适配器与服务器之间的消息加密不可用。</span><span class="sxs-lookup"><span data-stu-id="0ec96-780">Encryption of messages between the adapter and the server is not available.</span></span> <span data-ttu-id="0ec96-781">TIBCO.EMS.dll 不允许 SSL 加密使用 OpenSSL 库，但适配器使用 ProductVersion 5.0 及以上的 Tibco.EMS.dll 支持 SLL。</span><span class="sxs-lookup"><span data-stu-id="0ec96-781">The TIBCO.EMS.dll does not allow for SSL encryption using the OpenSSL libraries but the Adapters support the SLL with Tibco.EMS.dll with ProductVersion 5.0 and above.</span></span>  
  
6. <span data-ttu-id="0ec96-782">不支持用于 EMS 的管理 API。</span><span class="sxs-lookup"><span data-stu-id="0ec96-782">Administration API for EMS is not supported.</span></span>  
  
## <a name="adapter-tracing"></a><span data-ttu-id="0ec96-783">适配器跟踪</span><span class="sxs-lookup"><span data-stu-id="0ec96-783">Adapter tracing</span></span>

### <a name="enable-tracing"></a><span data-ttu-id="0ec96-784">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="0ec96-784">Enable tracing</span></span>
 <span data-ttu-id="0ec96-785">Windows 跟踪所用的文件名由管理员决定。</span><span class="sxs-lookup"><span data-stu-id="0ec96-785">The file name used with Windows tracing is up to the administrator.</span></span> <span data-ttu-id="0ec96-786">应用程序写入到操作系统，除非你想要关于特定后端系统的日志，否则此操作将忽略所有日志。</span><span class="sxs-lookup"><span data-stu-id="0ec96-786">The application writes to the operating system, which ignores all logs until you want the logs for a particular back-end system.</span></span> <span data-ttu-id="0ec96-787">通过运行一个单独的用于企业应用程序的 BizTalk 适配器的命令文件来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-787">You do this by running a separate BizTalk Adapters for Enterprise Applications command file.</span></span> <span data-ttu-id="0ec96-788">该命令的参数之一是文件的用于捕获的跟踪信息的名称。</span><span class="sxs-lookup"><span data-stu-id="0ec96-788">One of the arguments for that command is the name of the file that is used to capture the trace information.</span></span> <span data-ttu-id="0ec96-789">有关详细信息，请参阅"使用 Windows 跟踪事件"（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-789">For more information, see "Use Windows trace event" (in this topic).</span></span>
  
 <span data-ttu-id="0ec96-790">跟踪文件安装到 * \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\*。</span><span class="sxs-lookup"><span data-stu-id="0ec96-790">Trace files install to *\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\*.</span></span>  
  
-   <span data-ttu-id="0ec96-791">bin\BTATrace.cmd</span><span class="sxs-lookup"><span data-stu-id="0ec96-791">bin\BTATrace.cmd</span></span>    
-   <span data-ttu-id="0ec96-792">config\btaTrace.mof</span><span class="sxs-lookup"><span data-stu-id="0ec96-792">config\btaTrace.mof</span></span>  
  
### <a name="use-windows-trace-event"></a><span data-ttu-id="0ec96-793">使用 Windows 跟踪事件</span><span class="sxs-lookup"><span data-stu-id="0ec96-793">Use Windows trace event</span></span>  
 <span data-ttu-id="0ec96-794">适配器将错误、警告和信息性消息记录到 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="0ec96-794">The adapters log error, warning, and information messages to the Windows Event Viewer.</span></span> <span data-ttu-id="0ec96-795">可以使用 Windows 事件跟踪 (ETW) 工具来查看更多的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-795">You can view additional tracing messages by using the Event Tracing for Windows (ETW) tool.</span></span> <span data-ttu-id="0ec96-796">如果启用 ETW，将创建一个 \*.etl 文件以接收消息。</span><span class="sxs-lookup"><span data-stu-id="0ec96-796">When ETW is enabled, it creates an \*.etl file to receive the messages.</span></span> <span data-ttu-id="0ec96-797">该文件为二进制格式，必须将其转换为可读格式。</span><span class="sxs-lookup"><span data-stu-id="0ec96-797">This file is in binary format and must be converted to be read.</span></span> <span data-ttu-id="0ec96-798">若要执行此操作，必须提供要解释的使用者应用程序\*.etl 文件，例如，Windows tracerpt.exe 或 tracedmp.exe。</span><span class="sxs-lookup"><span data-stu-id="0ec96-798">To do this, you must have a consumer application available to interpret the \*.etl file, for example, Windows tracerpt.exe or tracedmp.exe.</span></span>  
  
### <a name="etw-components"></a><span data-ttu-id="0ec96-799">ETW 组件</span><span class="sxs-lookup"><span data-stu-id="0ec96-799">ETW components</span></span>
  
 <span data-ttu-id="0ec96-800">Windows 事件跟踪包括以下三个组件：</span><span class="sxs-lookup"><span data-stu-id="0ec96-800">Event Tracing for Windows has three components:</span></span>  
  
* <span data-ttu-id="0ec96-801">**控制器应用程序：** 激活和停用提供程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-801">**Controller application:** Activates and deactivates a provider.</span></span> <span data-ttu-id="0ec96-802">例如，tracelog.exe 或 logman.exe。</span><span class="sxs-lookup"><span data-stu-id="0ec96-802">For example, tracelog.exe or logman.exe.</span></span>  
  
    <span data-ttu-id="0ec96-803">设置 PATH 环境变量以指向 tracelog.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="0ec96-803">You set your PATH environment variable to point to the location of tracelog.exe.</span></span> <span data-ttu-id="0ec96-804">这可确保该 BTA < 适配器名称\>跟踪调用可以在系统中找到 tracelog.exe。</span><span class="sxs-lookup"><span data-stu-id="0ec96-804">This makes sure that BTA<Adapter Name\>Trace calls can locate tracelog.exe in the system.</span></span> <span data-ttu-id="0ec96-805">默认情况下，BTA < 适配器名称\>跟踪搜索当前路径。</span><span class="sxs-lookup"><span data-stu-id="0ec96-805">By default, BTA<Adapter Name\>Trace searches the current path.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ec96-806">tracelog.exe 可以从 Microsoft SDK，并与提供的 Microsoft BizTalk 适配器用于企业应用程序的命令兼容。</span><span class="sxs-lookup"><span data-stu-id="0ec96-806">tracelog.exe is available from the Microsoft SDK and is compatible with the commands provided by Microsoft BizTalk Adapters for Enterprise Applications.</span></span> <span data-ttu-id="0ec96-807">若要使用 logman.exe，请参阅 logman 文档。</span><span class="sxs-lookup"><span data-stu-id="0ec96-807">To use logman.exe, see the logman documentation.</span></span>  
  
* <span data-ttu-id="0ec96-808">**使用者应用程序：** 读取记录的事件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-808">**Consumer application:** Reads logged events.</span></span>  
  
    <span data-ttu-id="0ec96-809">为了让使用者应用程序能够读取 .etl 文件中的事件，Windows 事件跟踪必须将其转储到该文件中。</span><span class="sxs-lookup"><span data-stu-id="0ec96-809">For the consumer application to be able to read the event in the .etl file, Event Tracing for Windows must dump them into that file.</span></span> <span data-ttu-id="0ec96-810">通常，当控制器停用跟踪时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0ec96-810">Typically this is done when the controller deactivates the tracing.</span></span>  
  
    <span data-ttu-id="0ec96-811">若要使用使用者应用程序不停用跟踪的情况下，控制器必须激活使用实时选项时，跟踪 **< 实时\>=-rt**。</span><span class="sxs-lookup"><span data-stu-id="0ec96-811">To use the consumer application without deactivating the trace, the controller must activate the trace with the real-time option, **<Real time\> = -rt**.</span></span>  
  
* <span data-ttu-id="0ec96-812">**提供程序：** 用于提供事件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-812">**Provider:** Used to provide the event.</span></span>  
  
    <span data-ttu-id="0ec96-813">每个适配器包括五个不同的提供程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-813">Each adapter includes five different providers.</span></span> <span data-ttu-id="0ec96-814">它们在 Windows Management Instrumentation (WMI) 中进行注册。</span><span class="sxs-lookup"><span data-stu-id="0ec96-814">They are registered in Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="0ec96-815">若要在根 \WMI\EventTrace 路径中找到已注册的提供程序，您可以使用诸如 WMI CIM Studio 之类的工具。</span><span class="sxs-lookup"><span data-stu-id="0ec96-815">To find the registered providers in the root\WMI\EventTrace path, you can use tools such as WMI CIM Studio.</span></span>  
  
    <span data-ttu-id="0ec96-816">五个提供程序允许你记录不同种类的消息：</span><span class="sxs-lookup"><span data-stu-id="0ec96-816">The five providers enable you to log different kinds of messages:</span></span>  
  
        -   **Receiver Logging Provider**: The <Trace element\> switch is - **receiver**.    
        -   **Receiver CastDetails Provider**: The <Trace element\> switch is - **castDetailsReceive**.    
        -   **Transmitter Logging Provider**: The <Trace element\> switch is - **transmitter**.    
        -   **Transmitter CastDetails Provider**: The <Trace element\> switch is - **castDetailsTransmit**.    
        -   **Management Logging Provider**: The <Trace element\> switch is - **management**.  
  
<span data-ttu-id="0ec96-817">若要使用 ETW，运行该命令为特定的适配器： `BTA<Adapter Name\>Trace.cmd`。</span><span class="sxs-lookup"><span data-stu-id="0ec96-817">To use ETW, run the command for the specific adapter: `BTA<Adapter Name\>Trace.cmd`.</span></span> <span data-ttu-id="0ec96-818">如下所示使用此命令：</span><span class="sxs-lookup"><span data-stu-id="0ec96-818">You use this command as follows:</span></span>  
  
```  
BTA<Adapter Name>Trace <Trace element> -start [-cir <MB>|   
    -seq <MB>] [-rt] logfile  
BTA<Adapter Name>Trace <Trace element> -stop  
  
```  
  
 <span data-ttu-id="0ec96-819">其中：</span><span class="sxs-lookup"><span data-stu-id="0ec96-819">Where:</span></span>  
  
<span data-ttu-id="0ec96-820">**< 跟踪元素\>** （必需） 是一种的提供程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-820">**<Trace element\>** (required) is the kind of provider.</span></span> <span data-ttu-id="0ec96-821">相应的选项包括：</span><span class="sxs-lookup"><span data-stu-id="0ec96-821">The options are:</span></span>  
  
 <span data-ttu-id="0ec96-822">**-castDetailsTransmit**</span><span class="sxs-lookup"><span data-stu-id="0ec96-822">**-castDetailsTransmit**</span></span>  
  
 <span data-ttu-id="0ec96-823">**-发送器**</span><span class="sxs-lookup"><span data-stu-id="0ec96-823">**-transmitter**</span></span>  
  
 <span data-ttu-id="0ec96-824">**-castDetailsReceive**</span><span class="sxs-lookup"><span data-stu-id="0ec96-824">**-castDetailsReceive**</span></span>  
  
 <span data-ttu-id="0ec96-825">**-接收方**</span><span class="sxs-lookup"><span data-stu-id="0ec96-825">**-receiver**</span></span>  
  
 <span data-ttu-id="0ec96-826">**-管理**</span><span class="sxs-lookup"><span data-stu-id="0ec96-826">**-management**</span></span>  
  
 <span data-ttu-id="0ec96-827">**-启动、-停止：** 激活或停用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="0ec96-827">**-start, -stop:** Activate or deactivate the provider.</span></span>  
  
 <span data-ttu-id="0ec96-828">**-cir < MB\>:** 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="0ec96-828">**-cir <MB\>:** Size and kind of file.</span></span> <span data-ttu-id="0ec96-829">**-cir**是循环文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-829">**-cir** is a circular file.</span></span> <span data-ttu-id="0ec96-830">**< MB\>:** 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="0ec96-830">**<MB\>:** Size in megabytes.</span></span>  
  
 <span data-ttu-id="0ec96-831">**-seq < MB\>:** 文件的大小和类型。</span><span class="sxs-lookup"><span data-stu-id="0ec96-831">**-seq <MB\>:** Size and kind of file.</span></span> <span data-ttu-id="0ec96-832">**-seq**是顺序文件。</span><span class="sxs-lookup"><span data-stu-id="0ec96-832">**-seq** is a sequential file.</span></span> <span data-ttu-id="0ec96-833">**< MB\>:** 大小以兆字节为单位。</span><span class="sxs-lookup"><span data-stu-id="0ec96-833">**<MB\>:** Size in megabytes.</span></span>  
  
 <span data-ttu-id="0ec96-834">**-rt:** 上设置实时模式。</span><span class="sxs-lookup"><span data-stu-id="0ec96-834">**-rt:** Set the real-time mode on.</span></span>  
  
 <span data-ttu-id="0ec96-835">**日志文件：** 日志文件的名称 （c:\rtlog.etl 是默认值）。</span><span class="sxs-lookup"><span data-stu-id="0ec96-835">**Logfile:** Name of the log file (c:\rtlog.etl is the default).</span></span>  
  
 <span data-ttu-id="0ec96-836">例如：</span><span class="sxs-lookup"><span data-stu-id="0ec96-836">For example:</span></span>  
  
```  
BTAXXXTrace -transmitter -start -cir 10 -rt c:\log\mylog.etl  
BTAXXXTrace -transmitter -stop  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="0ec96-837">使用 tracerpt.exe 命令设置 .etl 文件的格式。</span><span class="sxs-lookup"><span data-stu-id="0ec96-837">You use the tracerpt.exe command to format the .etl files.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="0ec96-838">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0ec96-838">Next steps</span></span>
* [<span data-ttu-id="0ec96-839">JD Edwards EnterpriseOne 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-839">JD Edwards EnterpriseOne adapter</span></span>](../core/jd-edwards-enterpriseone-adapter.md)
* [<span data-ttu-id="0ec96-840">JD Edwards OneWorld 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-840">JD Edwards OneWorld adapter</span></span>](../core/jd-edwards-oneworld-adapter.md)
* [<span data-ttu-id="0ec96-841">PeopleSoft Enterprise 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-841">PeopleSoft Enterprise adapter</span></span>](../core/peoplesoft-enterprise-adapter.md)
* [<span data-ttu-id="0ec96-842">TIBCO Enterprise Message Service 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-842">TIBCO Enterprise Message Service adapter</span></span>](../core/tibco-enterprise-message-service-adapter.md)
* [<span data-ttu-id="0ec96-843">TIBCO Rendezvous 适配器</span><span class="sxs-lookup"><span data-stu-id="0ec96-843">TIBCO Rendezvous adapter</span></span>](../core/tibco-rendezvous-adapter.md)
