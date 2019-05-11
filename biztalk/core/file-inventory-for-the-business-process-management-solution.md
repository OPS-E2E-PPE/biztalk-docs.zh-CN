---
title: 业务流程管理解决方案的文件清单 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, file inventory
ms.assetid: 3efb7495-9543-4fe0-8f4b-26c19b3b6db9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2f01ad1c8d0f9cafae6ade68de653f609827353
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388033"
---
# <a name="file-inventory-for-the-business-process-management-solution"></a><span data-ttu-id="1e494-102">业务流程管理解决方案的文件清单</span><span class="sxs-lookup"><span data-stu-id="1e494-102">File Inventory for the Business Process Management Solution</span></span>
<span data-ttu-id="1e494-103">本部分列出了子目录和业务流程管理解决方案的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-103">This section lists subdirectories and source files for the Business Process Management solution.</span></span> <span data-ttu-id="1e494-104">业务流程管理解决方案源文件的默认安装目录[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\BPM。</span><span class="sxs-lookup"><span data-stu-id="1e494-104">The default installation directory for the Business Process Management solution source files is [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\BPM.</span></span> <span data-ttu-id="1e494-105">下表来代替此路径与之前的说明\<安装目录\>。</span><span class="sxs-lookup"><span data-stu-id="1e494-105">Descriptions before the following tables replace this path with \<Install Directory\>.</span></span>  
  
 <span data-ttu-id="1e494-106">中的文件\<安装目录\></span><span class="sxs-lookup"><span data-stu-id="1e494-106">Files in \<Install Directory\></span></span>  
  
|<span data-ttu-id="1e494-107">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-107">File</span></span>|<span data-ttu-id="1e494-108">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-109">Microsoft.Samples.BizTalk.SouthridgeVideo.sln</span><span class="sxs-lookup"><span data-stu-id="1e494-109">Microsoft.Samples.BizTalk.SouthridgeVideo.sln</span></span>|<span data-ttu-id="1e494-110">Visual Studio 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-110">Visual Studio solution file.</span></span>|  
|<span data-ttu-id="1e494-111">readme.html</span><span class="sxs-lookup"><span data-stu-id="1e494-111">readme.html</span></span>|<span data-ttu-id="1e494-112">该解决方案的自述文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-112">Readme file for the solution.</span></span>|  
|<span data-ttu-id="1e494-113">ReplacePKToken.vbs</span><span class="sxs-lookup"><span data-stu-id="1e494-113">ReplacePKToken.vbs</span></span>|<span data-ttu-id="1e494-114">若要修复解决方案文件中的公钥标记，构建解决方案时的 VBScript。</span><span class="sxs-lookup"><span data-stu-id="1e494-114">VBScript to fix public key tokens in solution files when solution is built.</span></span>|  
|<span data-ttu-id="1e494-115">ReplacePKToken.wsf</span><span class="sxs-lookup"><span data-stu-id="1e494-115">ReplacePKToken.wsf</span></span>|<span data-ttu-id="1e494-116">ReplacePKToken VBScript 的 Windows 脚本文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-116">Windows Script File for the ReplacePKToken VBScript.</span></span>|  
|<span data-ttu-id="1e494-117">SetupBPM.bat</span><span class="sxs-lookup"><span data-stu-id="1e494-117">SetupBPM.bat</span></span>|<span data-ttu-id="1e494-118">创建一个公共密钥、 更新引用的公钥，并编译解决方案。</span><span class="sxs-lookup"><span data-stu-id="1e494-118">Creates a public key, updates references to the public key, and compiles the solution.</span></span> <span data-ttu-id="1e494-119">部署解决方案的信息，请参阅[部署业务流程管理解决方案](../core/deploying-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="1e494-119">For information about deploying the solution, see [Deploying the Business Process Management Solution](../core/deploying-the-business-process-management-solution.md).</span></span>|  
  
 <span data-ttu-id="1e494-120">中的文件\<安装目录\>\BAM</span><span class="sxs-lookup"><span data-stu-id="1e494-120">Files in \<Install Directory\>\BAM</span></span>  
  
|<span data-ttu-id="1e494-121">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-121">File</span></span>|<span data-ttu-id="1e494-122">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-122">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-123">BAMServiceOrder.xls</span><span class="sxs-lookup"><span data-stu-id="1e494-123">BAMServiceOrder.xls</span></span>|<span data-ttu-id="1e494-124">BAM 数据的 Excel 电子表格。</span><span class="sxs-lookup"><span data-stu-id="1e494-124">Excel spreadsheet for the BAM data.</span></span>|  
|<span data-ttu-id="1e494-125">BAMServiceOrder.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-125">BAMServiceOrder.xml</span></span>|<span data-ttu-id="1e494-126">定义 BAM 数据项类型的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-126">Schema defining the types of the BAM data items.</span></span>|  
  
 <span data-ttu-id="1e494-127">中的文件\<安装目录\>\Bindings</span><span class="sxs-lookup"><span data-stu-id="1e494-127">Files in \<Install Directory\>\Bindings</span></span>  
  
|<span data-ttu-id="1e494-128">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-128">File</span></span>|<span data-ttu-id="1e494-129">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-129">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-130">CableOrderAppBindings-test.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-130">CableOrderAppBindings-test.xml</span></span>|<span data-ttu-id="1e494-131">绑定文件的测试版本**CableOrderApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e494-131">Binding file for the test version of the **CableOrderApp** application.</span></span>|  
|<span data-ttu-id="1e494-132">CableOrderAppBindings.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-132">CableOrderAppBindings.xml</span></span>|<span data-ttu-id="1e494-133">绑定文件**CableOrderAPP**应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e494-133">Binding file for the **CableOrderAPP** application.</span></span>|  
|<span data-ttu-id="1e494-134">MessagingAppBindings-test.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-134">MessagingAppBindings-test.xml</span></span>|<span data-ttu-id="1e494-135">绑定文件的测试版本**MessagingApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e494-135">Binding file for the test version of the **MessagingApp** application.</span></span>|  
|<span data-ttu-id="1e494-136">MessagingAppBindings.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-136">MessagingAppBindings.xml</span></span>|<span data-ttu-id="1e494-137">绑定文件**MessagingApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e494-137">Binding file for the **MessagingApp** application.</span></span>|  
|<span data-ttu-id="1e494-138">OrderBrokerAppBindings-test.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-138">OrderBrokerAppBindings-test.xml</span></span>|<span data-ttu-id="1e494-139">绑定文件的测试版本**OrderBrokerApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e494-139">Binding file for the test version of the **OrderBrokerApp** application.</span></span>|  
|<span data-ttu-id="1e494-140">OrderBrokerAppBindings.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-140">OrderBrokerAppBindings.xml</span></span>|<span data-ttu-id="1e494-141">绑定文件**OrderBrokerApp**应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e494-141">Binding file for the **OrderBrokerApp** application.</span></span>|  
  
 <span data-ttu-id="1e494-142">中的文件\<安装目录\>\CableProvisioningSystemClient</span><span class="sxs-lookup"><span data-stu-id="1e494-142">Files in \<Install Directory\>\CableProvisioningSystemClient</span></span>  
  
|<span data-ttu-id="1e494-143">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-143">File</span></span>|<span data-ttu-id="1e494-144">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-144">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-145">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-145">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-146">模拟订单系统的组件的客户端的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-146">Assembly file for the client side of the components simulating the order system.</span></span>|  
|<span data-ttu-id="1e494-147">CableProvisioningSystemClient.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-147">CableProvisioningSystemClient.csproj</span></span>|<span data-ttu-id="1e494-148">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-148">C# project file.</span></span>|  
|<span data-ttu-id="1e494-149">CPSClient.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-149">CPSClient.cs</span></span>|<span data-ttu-id="1e494-150">客户端的源。</span><span class="sxs-lookup"><span data-stu-id="1e494-150">Source for the client.</span></span> <span data-ttu-id="1e494-151">包括**OrderHandlerWrapper**类代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-151">Includes the **OrderHandlerWrapper** class code.</span></span>|  
|<span data-ttu-id="1e494-152">OrderException.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-152">OrderException.cs</span></span>|<span data-ttu-id="1e494-153">C#类定义的文件**OrderException**。</span><span class="sxs-lookup"><span data-stu-id="1e494-153">C# file for the class defining the **OrderException**.</span></span>|  
  
 <span data-ttu-id="1e494-154">中的文件\<安装目录\>\CableProvisioningSystemServer</span><span class="sxs-lookup"><span data-stu-id="1e494-154">Files in \<Install Directory\>\CableProvisioningSystemServer</span></span>  
  
|<span data-ttu-id="1e494-155">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-155">File</span></span>|<span data-ttu-id="1e494-156">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-156">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-157">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-157">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-158">模拟订单系统的组件的服务器端的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-158">Assembly file for the server side of the components simulating the order system.</span></span>|  
|<span data-ttu-id="1e494-159">CableProvisioningSystemServer.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-159">CableProvisioningSystemServer.csproj</span></span>|<span data-ttu-id="1e494-160">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-160">C# project file.</span></span>|  
|<span data-ttu-id="1e494-161">CableProvisioningSystemServer.csproj.user</span><span class="sxs-lookup"><span data-stu-id="1e494-161">CableProvisioningSystemServer.csproj.user</span></span>|<span data-ttu-id="1e494-162">Visual Studio 项目用户选项文件</span><span class="sxs-lookup"><span data-stu-id="1e494-162">Visual Studio Project User Options file</span></span>|  
|<span data-ttu-id="1e494-163">CPSServer.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-163">CPSServer.cs</span></span>|<span data-ttu-id="1e494-164">源服务器。</span><span class="sxs-lookup"><span data-stu-id="1e494-164">Source for the server.</span></span>|  
  
 <span data-ttu-id="1e494-165">中的文件\<安装目录\>\CSRWebApp</span><span class="sxs-lookup"><span data-stu-id="1e494-165">Files in \<Install Directory\>\CSRWebApp</span></span>  
  
|<span data-ttu-id="1e494-166">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-166">File</span></span>|<span data-ttu-id="1e494-167">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-167">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-168">CSRMainForm.aspx</span><span class="sxs-lookup"><span data-stu-id="1e494-168">CSRMainForm.aspx</span></span>|<span data-ttu-id="1e494-169">客户服务输入的 ASP 窗体。</span><span class="sxs-lookup"><span data-stu-id="1e494-169">Customer service input ASP form.</span></span>|  
|<span data-ttu-id="1e494-170">CSRMainForm.aspx.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-170">CSRMainForm.aspx.cs</span></span>|<span data-ttu-id="1e494-171">C#窗体后面的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-171">C# code behind form.</span></span>|  
|<span data-ttu-id="1e494-172">Web.Config</span><span class="sxs-lookup"><span data-stu-id="1e494-172">Web.Config</span></span>|<span data-ttu-id="1e494-173">在窗体的配置文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-173">Configuration file for the form.</span></span>|  
  
 <span data-ttu-id="1e494-174">中的文件\<安装目录\>\CSRWebApp\App_WebReferences\SouthridgeVideo_OrderBroker</span><span class="sxs-lookup"><span data-stu-id="1e494-174">Files in \<Install Directory\>\CSRWebApp\App_WebReferences\SouthridgeVideo_OrderBroker</span></span>  
  
|<span data-ttu-id="1e494-175">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-175">File</span></span>|<span data-ttu-id="1e494-176">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-176">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-177">orderbrokerorch_orderport.disco</span><span class="sxs-lookup"><span data-stu-id="1e494-177">orderbrokerorch_orderport.disco</span></span>|<span data-ttu-id="1e494-178">Disco 文件**OrderBroker**显示为 web 服务。</span><span class="sxs-lookup"><span data-stu-id="1e494-178">Disco file for the **OrderBroker** presented as a web service.</span></span>|  
|<span data-ttu-id="1e494-179">orderbrokerorch_orderport.discomap</span><span class="sxs-lookup"><span data-stu-id="1e494-179">orderbrokerorch_orderport.discomap</span></span>|<span data-ttu-id="1e494-180">生成的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-180">Generated file.</span></span>|  
|<span data-ttu-id="1e494-181">orderbrokerorch_orderport.wsdl</span><span class="sxs-lookup"><span data-stu-id="1e494-181">orderbrokerorch_orderport.wsdl</span></span>|<span data-ttu-id="1e494-182">WSDL 文件**OrderBroker**显示为 web 服务。</span><span class="sxs-lookup"><span data-stu-id="1e494-182">WSDL file for the **OrderBroker** presented as a web service.</span></span>|  
  
 <span data-ttu-id="1e494-183">中的文件\<安装目录\>\FacilitiesSimulator</span><span class="sxs-lookup"><span data-stu-id="1e494-183">Files in \<Install Directory\>\FacilitiesSimulator</span></span>  
  
|<span data-ttu-id="1e494-184">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-184">File</span></span>|<span data-ttu-id="1e494-185">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-185">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-186">FacilitiesSimulator.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-186">FacilitiesSimulator.csproj</span></span>|<span data-ttu-id="1e494-187">C#功能模拟程序的项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-187">C# project file for the facilities simulator.</span></span>|  
|<span data-ttu-id="1e494-188">FacilitiesSimulator.csproj.user</span><span class="sxs-lookup"><span data-stu-id="1e494-188">FacilitiesSimulator.csproj.user</span></span>|<span data-ttu-id="1e494-189">Visual Studio 项目用户选项文件</span><span class="sxs-lookup"><span data-stu-id="1e494-189">Visual Studio Project User Options file</span></span>|  
|<span data-ttu-id="1e494-190">FacilitiesSimulatorForm.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-190">FacilitiesSimulatorForm.cs</span></span>|<span data-ttu-id="1e494-191">C#功能模拟程序的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-191">C# code for the facilities simulator.</span></span>|  
|<span data-ttu-id="1e494-192">FacilitiesSimulatorForm.resx</span><span class="sxs-lookup"><span data-stu-id="1e494-192">FacilitiesSimulatorForm.resx</span></span>|<span data-ttu-id="1e494-193">资源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-193">Resource file.</span></span>|  
  
 <span data-ttu-id="1e494-194">中的文件\<安装目录\>\HistoryDB</span><span class="sxs-lookup"><span data-stu-id="1e494-194">Files in \<Install Directory\>\HistoryDB</span></span>  
  
|<span data-ttu-id="1e494-195">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-195">File</span></span>|<span data-ttu-id="1e494-196">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-196">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-197">CreateDatabase.cmd</span><span class="sxs-lookup"><span data-stu-id="1e494-197">CreateDatabase.cmd</span></span>|<span data-ttu-id="1e494-198">来驱动创建历史记录数据库的 SQL 文件的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-198">File to drive the SQL file that creates the history database.</span></span>|  
|<span data-ttu-id="1e494-199">SouthridgeVideoHistory.sql</span><span class="sxs-lookup"><span data-stu-id="1e494-199">SouthridgeVideoHistory.sql</span></span>|<span data-ttu-id="1e494-200">若要创建历史记录数据库的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="1e494-200">SQL commands to create the history database.</span></span>|  
  
 <span data-ttu-id="1e494-201">中的文件\<安装目录\>\IOperationsSystem</span><span class="sxs-lookup"><span data-stu-id="1e494-201">Files in \<Install Directory\>\IOperationsSystem</span></span>  
  
|<span data-ttu-id="1e494-202">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-202">File</span></span>|<span data-ttu-id="1e494-203">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-203">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-204">IOperationsSystem.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-204">IOperationsSystem.cs</span></span>|<span data-ttu-id="1e494-205">接口定义操作系统。</span><span class="sxs-lookup"><span data-stu-id="1e494-205">Interface definition for the operations system.</span></span>|  
|<span data-ttu-id="1e494-206">IOperationsSystem.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-206">IOperationsSystem.csproj</span></span>|<span data-ttu-id="1e494-207">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-207">C# project file.</span></span>|  
|<span data-ttu-id="1e494-208">IOperationsSystem.csproj.user</span><span class="sxs-lookup"><span data-stu-id="1e494-208">IOperationsSystem.csproj.user</span></span>|<span data-ttu-id="1e494-209">Visual Studio 项目用户选项文件</span><span class="sxs-lookup"><span data-stu-id="1e494-209">Visual Studio Project User Options file</span></span>|  
  
 <span data-ttu-id="1e494-210">中的文件\<安装目录\>\IOrderHandler</span><span class="sxs-lookup"><span data-stu-id="1e494-210">Files in \<Install Directory\>\IOrderHandler</span></span>  
  
|<span data-ttu-id="1e494-211">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-211">File</span></span>|<span data-ttu-id="1e494-212">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-212">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-213">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-213">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-214">程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-214">Assembly information file.</span></span>|  
|<span data-ttu-id="1e494-215">IOrderHandler.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-215">IOrderHandler.cs</span></span>|<span data-ttu-id="1e494-216">接口定义**OrderHandler**。</span><span class="sxs-lookup"><span data-stu-id="1e494-216">Interface definition for the **OrderHandler**.</span></span>|  
|<span data-ttu-id="1e494-217">IOrderHandler.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-217">IOrderHandler.csproj</span></span>|<span data-ttu-id="1e494-218">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-218">C# project file.</span></span>|  
  
 <span data-ttu-id="1e494-219">中的文件\<安装目录\>\Maps</span><span class="sxs-lookup"><span data-stu-id="1e494-219">Files in \<Install Directory\>\Maps</span></span>  
  
|<span data-ttu-id="1e494-220">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-220">File</span></span>|<span data-ttu-id="1e494-221">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-221">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-222">Maps.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-222">Maps.btproj</span></span>|<span data-ttu-id="1e494-223">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-223">BizTalk project file.</span></span>|  
|<span data-ttu-id="1e494-224">Order_To_SQLUpdateStatus.btm</span><span class="sxs-lookup"><span data-stu-id="1e494-224">Order_To_SQLUpdateStatus.btm</span></span>|<span data-ttu-id="1e494-225">用于将订单转换为消息以更新状态的映射。</span><span class="sxs-lookup"><span data-stu-id="1e494-225">Map to convert an order to message to update status.</span></span>|  
  
 <span data-ttu-id="1e494-226">中的文件\<安装目录\>\MessagingSchemas</span><span class="sxs-lookup"><span data-stu-id="1e494-226">Files in \<Install Directory\>\MessagingSchemas</span></span>  
  
|<span data-ttu-id="1e494-227">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-227">File</span></span>|<span data-ttu-id="1e494-228">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-228">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-229">ErrorEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-229">ErrorEnvelope.xsd</span></span>|<span data-ttu-id="1e494-230">定义错误消息的信封的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-230">Schema defining the envelope for the error message.</span></span>|  
|<span data-ttu-id="1e494-231">MessagingSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-231">MessagingSchemas.btproj</span></span>|<span data-ttu-id="1e494-232">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-232">BizTalk project file.</span></span>|  
|<span data-ttu-id="1e494-233">OrderEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-233">OrderEnvelope.xsd</span></span>|<span data-ttu-id="1e494-234">定义订单的信封的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-234">Schema defining the envelope for an order.</span></span>|  
|<span data-ttu-id="1e494-235">OrderStatusEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-235">OrderStatusEnvelope.xsd</span></span>|<span data-ttu-id="1e494-236">定义订单状态消息的信封的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-236">Schema defining the envelope for an order status message.</span></span>|  
|<span data-ttu-id="1e494-237">SQLUpdateStatus.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-237">SQLUpdateStatus.xsd</span></span>|<span data-ttu-id="1e494-238">定义 SQL 状态更新消息的信封的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-238">Schema defining the envelope for a SQL status update message.</span></span>|  
  
 <span data-ttu-id="1e494-239">中的文件\<安装目录\>\OperationsClient</span><span class="sxs-lookup"><span data-stu-id="1e494-239">Files in \<Install Directory\>\OperationsClient</span></span>  
  
|<span data-ttu-id="1e494-240">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-240">File</span></span>|<span data-ttu-id="1e494-241">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-241">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-242">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-242">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-243">程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-243">Assembly information file.</span></span>|  
|<span data-ttu-id="1e494-244">OperationsClient.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-244">OperationsClient.csproj</span></span>|<span data-ttu-id="1e494-245">C#操作客户端项目。</span><span class="sxs-lookup"><span data-stu-id="1e494-245">C# project for the operations client.</span></span>|  
|<span data-ttu-id="1e494-246">OpsClient.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-246">OpsClient.cs</span></span>|<span data-ttu-id="1e494-247">C#操作客户端代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-247">C# code for the operations client.</span></span>|  
|<span data-ttu-id="1e494-248">OpsExceptions.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-248">OpsExceptions.cs</span></span>|<span data-ttu-id="1e494-249">C#定义操作异常的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-249">C# code defining the operations exception.</span></span>|  
  
 <span data-ttu-id="1e494-250">中的文件\<安装目录\>\OperationsHandler</span><span class="sxs-lookup"><span data-stu-id="1e494-250">Files in \<Install Directory\>\OperationsHandler</span></span>  
  
|<span data-ttu-id="1e494-251">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-251">File</span></span>|<span data-ttu-id="1e494-252">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-252">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-253">OperationsHandler.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-253">OperationsHandler.csproj</span></span>|<span data-ttu-id="1e494-254">C#操作处理程序的项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-254">C# project file for the operations handler.</span></span>|  
|<span data-ttu-id="1e494-255">OpsHandler.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-255">OpsHandler.cs</span></span>|<span data-ttu-id="1e494-256">C#为代码**OpsHandler**。</span><span class="sxs-lookup"><span data-stu-id="1e494-256">C# code for the **OpsHandler**.</span></span> <span data-ttu-id="1e494-257">通过使用**OpsClient**发出请求的操作系统。</span><span class="sxs-lookup"><span data-stu-id="1e494-257">Used by the **OpsClient** to make requests of the operations system.</span></span>|  
  
 <span data-ttu-id="1e494-258">中的文件\<安装目录\>\OperationsServer</span><span class="sxs-lookup"><span data-stu-id="1e494-258">Files in \<Install Directory\>\OperationsServer</span></span>  
  
|<span data-ttu-id="1e494-259">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-259">File</span></span>|<span data-ttu-id="1e494-260">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-260">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-261">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-261">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-262">程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-262">Assembly information file.</span></span>|  
|<span data-ttu-id="1e494-263">OperationsServer.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-263">OperationsServer.csproj</span></span>|<span data-ttu-id="1e494-264">C#操作服务器的项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-264">C# project file for the operations server.</span></span>|  
|<span data-ttu-id="1e494-265">OpsServer.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-265">OpsServer.cs</span></span>|<span data-ttu-id="1e494-266">C#提供的实例的操作服务器代码**OpsHandler**对象。</span><span class="sxs-lookup"><span data-stu-id="1e494-266">C# code for the operations server that provides instances of the **OpsHandler** object.</span></span>|  
  
 <span data-ttu-id="1e494-267">中的文件\<安装目录\>\OpsAdapter</span><span class="sxs-lookup"><span data-stu-id="1e494-267">Files in \<Install Directory\>\OpsAdapter</span></span>  
  
|<span data-ttu-id="1e494-268">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-268">File</span></span>|<span data-ttu-id="1e494-269">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-269">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-270">OpsAdapter.sln</span><span class="sxs-lookup"><span data-stu-id="1e494-270">OpsAdapter.sln</span></span>|<span data-ttu-id="1e494-271">Ops 适配器的 visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="1e494-271">Visual Studio solution for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-272">Register_Ops_Adapter.vbs</span><span class="sxs-lookup"><span data-stu-id="1e494-272">Register_Ops_Adapter.vbs</span></span>|<span data-ttu-id="1e494-273">用于注册 Ops 适配器的 VBScript。</span><span class="sxs-lookup"><span data-stu-id="1e494-273">VBScript to register the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-274">SetupOpsAdapter.bat</span><span class="sxs-lookup"><span data-stu-id="1e494-274">SetupOpsAdapter.bat</span></span>|<span data-ttu-id="1e494-275">用于安装 Ops 适配器的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-275">Batch file to setup the Ops adapter.</span></span>|  
  
 <span data-ttu-id="1e494-276">中的文件\<安装目录\>\OpsAdapter\IOpsAIC</span><span class="sxs-lookup"><span data-stu-id="1e494-276">Files in \<Install Directory\>\OpsAdapter\IOpsAIC</span></span>  
  
|<span data-ttu-id="1e494-277">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-277">File</span></span>|<span data-ttu-id="1e494-278">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-278">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-279">IOpsAIC.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-279">IOpsAIC.cs</span></span>|<span data-ttu-id="1e494-280">C#接口定义的代码文件**初始化**并**Execute** Ops 适配器调用的方法。</span><span class="sxs-lookup"><span data-stu-id="1e494-280">C# code file for the interface defining the **Initialize** and **Execute** methods called by the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-281">IOpsAIC.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-281">IOpsAIC.csproj</span></span>|<span data-ttu-id="1e494-282">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-282">C# project file.</span></span>|  
  
 <span data-ttu-id="1e494-283">中的文件\<安装目录\>\OpsAdapter\OpsAdapterMgmt</span><span class="sxs-lookup"><span data-stu-id="1e494-283">Files in \<Install Directory\>\OpsAdapter\OpsAdapterMgmt</span></span>  
  
|<span data-ttu-id="1e494-284">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-284">File</span></span>|<span data-ttu-id="1e494-285">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-285">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-286">AdapterManagement.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-286">AdapterManagement.cs</span></span>|<span data-ttu-id="1e494-287">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-287">C# source file for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-288">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-288">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-289">程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-289">Assembly information file.</span></span>|  
|<span data-ttu-id="1e494-290">OpsAdapterMgmt.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-290">OpsAdapterMgmt.csproj</span></span>|<span data-ttu-id="1e494-291">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-291">C# source file for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-292">TransmitHandler.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-292">TransmitHandler.xsd</span></span>|<span data-ttu-id="1e494-293">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-293">C# source file for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-294">TransmitLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-294">TransmitLocation.xsd</span></span>|<span data-ttu-id="1e494-295">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-295">C# source file for the Ops adapter.</span></span>|  
  
 <span data-ttu-id="1e494-296">中的文件\<安装目录\>\OpsAdapter\OpsTxAdapter</span><span class="sxs-lookup"><span data-stu-id="1e494-296">Files in \<Install Directory\>\OpsAdapter\OpsTxAdapter</span></span>  
  
|<span data-ttu-id="1e494-297">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-297">File</span></span>|<span data-ttu-id="1e494-298">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-298">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-299">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-299">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-300">程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-300">Assembly information file.</span></span>|  
|<span data-ttu-id="1e494-301">OpsAdapterExceptions.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-301">OpsAdapterExceptions.cs</span></span>|<span data-ttu-id="1e494-302">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-302">C# source file for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-303">OpsAdapterProperties.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-303">OpsAdapterProperties.cs</span></span>|<span data-ttu-id="1e494-304">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-304">C# source file for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-305">OpsTransmitAdapterBatch.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-305">OpsTransmitAdapterBatch.cs</span></span>|<span data-ttu-id="1e494-306">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-306">C# source file for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-307">OpsTransmitter.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-307">OpsTransmitter.cs</span></span>|<span data-ttu-id="1e494-308">C#Ops 适配器的源文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-308">C# source file for the Ops adapter.</span></span>|  
|<span data-ttu-id="1e494-309">OpsTxAdapter.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-309">OpsTxAdapter.csproj</span></span>|<span data-ttu-id="1e494-310">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-310">C# project file.</span></span>|  
  
 <span data-ttu-id="1e494-311">中的文件\<安装目录\>\Orchestrations\CableOrderActions</span><span class="sxs-lookup"><span data-stu-id="1e494-311">Files in \<Install Directory\>\Orchestrations\CableOrderActions</span></span>  
  
|<span data-ttu-id="1e494-312">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-312">File</span></span>|<span data-ttu-id="1e494-313">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-313">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-314">Activate.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-314">Activate.odx</span></span>|<span data-ttu-id="1e494-315">**激活**由订单处理阶段使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-315">The **Activate** orchestration used by the order processing stages.</span></span>|  
|<span data-ttu-id="1e494-316">Analyze.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-316">Analyze.odx</span></span>|<span data-ttu-id="1e494-317">**分析**由订单处理阶段使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-317">The **Analyze** orchestration used by the order processing stages.</span></span>|  
|<span data-ttu-id="1e494-318">CableOrderActions.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-318">CableOrderActions.btproj</span></span>|<span data-ttu-id="1e494-319">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-319">BizTalk project file.</span></span>|  
|<span data-ttu-id="1e494-320">Cancel.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-320">Cancel.odx</span></span>|<span data-ttu-id="1e494-321">**取消**由订单处理阶段使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-321">The **Cancel** orchestration used by the order processing stages.</span></span>|  
|<span data-ttu-id="1e494-322">Change.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-322">Change.odx</span></span>|<span data-ttu-id="1e494-323">**更改**由订单处理阶段使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-323">The **Change** orchestration used by the order processing stages.</span></span>|  
|<span data-ttu-id="1e494-324">Complete.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-324">Complete.odx</span></span>|<span data-ttu-id="1e494-325">**完成**由订单处理阶段使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-325">The **Complete** orchestration used by the order processing stages.</span></span>|  
|<span data-ttu-id="1e494-326">Validate.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-326">Validate.odx</span></span>|<span data-ttu-id="1e494-327">**验证**由订单处理阶段使用业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-327">The **Validate** orchestration used by the order processing stages.</span></span>|  
  
 <span data-ttu-id="1e494-328">中的文件\<安装目录\>\Orchestrations\CableOrderStage1</span><span class="sxs-lookup"><span data-stu-id="1e494-328">Files in \<Install Directory\>\Orchestrations\CableOrderStage1</span></span>  
  
|<span data-ttu-id="1e494-329">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-329">File</span></span>|<span data-ttu-id="1e494-330">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-330">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-331">CableOrder1.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-331">CableOrder1.odx</span></span>|<span data-ttu-id="1e494-332">第一个订单处理阶段业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-332">Orchestration for the first order processing stage.</span></span>|  
|<span data-ttu-id="1e494-333">CableOrderStage1.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-333">CableOrderStage1.btproj</span></span>|<span data-ttu-id="1e494-334">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-334">BizTalk project file.</span></span>|  
  
 <span data-ttu-id="1e494-335">中的文件\<安装目录\>\Orchestrations\CableOrderStage2</span><span class="sxs-lookup"><span data-stu-id="1e494-335">Files in \<Install Directory\>\Orchestrations\CableOrderStage2</span></span>  
  
|<span data-ttu-id="1e494-336">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-336">File</span></span>|<span data-ttu-id="1e494-337">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-337">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-338">CableOrder2.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-338">CableOrder2.odx</span></span>|<span data-ttu-id="1e494-339">第二个订单处理阶段的业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-339">Orchestration for the second order processing stage.</span></span>|  
|<span data-ttu-id="1e494-340">CableOrderStage2.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-340">CableOrderStage2.btproj</span></span>|<span data-ttu-id="1e494-341">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-341">BizTalk project file.</span></span>|  
  
 <span data-ttu-id="1e494-342">中的文件\<安装目录\>\Orchestrations\OrderBroker</span><span class="sxs-lookup"><span data-stu-id="1e494-342">Files in \<Install Directory\>\Orchestrations\OrderBroker</span></span>  
  
|<span data-ttu-id="1e494-343">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-343">File</span></span>|<span data-ttu-id="1e494-344">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-344">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-345">OrderBroker.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-345">OrderBroker.btproj</span></span>|<span data-ttu-id="1e494-346">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-346">BizTalk project file.</span></span>|  
|<span data-ttu-id="1e494-347">OrderBroker.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-347">OrderBroker.odx</span></span>|<span data-ttu-id="1e494-348">**OrderBroker**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-348">The **OrderBroker** orchestration.</span></span>|  
  
 <span data-ttu-id="1e494-349">中的文件\<安装目录\>\Orchestrations\OrderManager</span><span class="sxs-lookup"><span data-stu-id="1e494-349">Files in \<Install Directory\>\Orchestrations\OrderManager</span></span>  
  
|<span data-ttu-id="1e494-350">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-350">File</span></span>|<span data-ttu-id="1e494-351">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-351">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-352">CheckInterrupt.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-352">CheckInterrupt.odx</span></span>|<span data-ttu-id="1e494-353">**CheckInterrupt**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-353">The **CheckInterrupt** orchestration.</span></span>|  
|<span data-ttu-id="1e494-354">ErrorHandler.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-354">ErrorHandler.odx</span></span>|<span data-ttu-id="1e494-355">**ErrorHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-355">The **ErrorHandler** orchestration.</span></span>|  
|<span data-ttu-id="1e494-356">ExceptionHandler.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-356">ExceptionHandler.odx</span></span>|<span data-ttu-id="1e494-357">**ExceptionHandler**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-357">The **ExceptionHandler** orchestration.</span></span>|  
|<span data-ttu-id="1e494-358">Interrupter.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-358">Interrupter.odx</span></span>|<span data-ttu-id="1e494-359">**Interrupter**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-359">The **Interrupter** orchestration.</span></span>|  
|<span data-ttu-id="1e494-360">OrderManager.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-360">OrderManager.btproj</span></span>|<span data-ttu-id="1e494-361">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-361">BizTalk project file.</span></span>|  
|<span data-ttu-id="1e494-362">OrderManager.odx</span><span class="sxs-lookup"><span data-stu-id="1e494-362">OrderManager.odx</span></span>|<span data-ttu-id="1e494-363">**OrderManager**业务流程。</span><span class="sxs-lookup"><span data-stu-id="1e494-363">The **OrderManager** orchestration.</span></span>|  
  
 <span data-ttu-id="1e494-364">中的文件\<安装目录\>\OrderBrokerMaps</span><span class="sxs-lookup"><span data-stu-id="1e494-364">Files in \<Install Directory\>\OrderBrokerMaps</span></span>  
  
|<span data-ttu-id="1e494-365">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-365">File</span></span>|<span data-ttu-id="1e494-366">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-366">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-367">CSR_OrderRequest_To_Order.btm</span><span class="sxs-lookup"><span data-stu-id="1e494-367">CSR_OrderRequest_To_Order.btm</span></span>|<span data-ttu-id="1e494-368">若要将客户服务订单请求转换为订单消息的映射。</span><span class="sxs-lookup"><span data-stu-id="1e494-368">Map to convert a customer service order request to an order message.</span></span>|  
|<span data-ttu-id="1e494-369">CSR_OrderRequest_To_Servicing_OrderRequest.btm</span><span class="sxs-lookup"><span data-stu-id="1e494-369">CSR_OrderRequest_To_Servicing_OrderRequest.btm</span></span>|<span data-ttu-id="1e494-370">用于将客户服务订单请求转换到为服务消息映射</span><span class="sxs-lookup"><span data-stu-id="1e494-370">Map to convert a customer service order request to a message to the servicing</span></span>|  
|<span data-ttu-id="1e494-371">CSR_OrderRequest_To_SQLHistoryInsert.btm</span><span class="sxs-lookup"><span data-stu-id="1e494-371">CSR_OrderRequest_To_SQLHistoryInsert.btm</span></span>|<span data-ttu-id="1e494-372">若要将客户服务订单请求转换为历史记录更新消息的映射。</span><span class="sxs-lookup"><span data-stu-id="1e494-372">Map to convert a customer service order request to a history update message.</span></span>|  
|<span data-ttu-id="1e494-373">OrderBrokerMaps.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-373">OrderBrokerMaps.btproj</span></span>|<span data-ttu-id="1e494-374">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-374">BizTalk project file.</span></span>|  
|<span data-ttu-id="1e494-375">Order_To_CSR_OrderRequest.btm</span><span class="sxs-lookup"><span data-stu-id="1e494-375">Order_To_CSR_OrderRequest.btm</span></span>|<span data-ttu-id="1e494-376">用于将订单消息转换为客户服务订单请求的映射。</span><span class="sxs-lookup"><span data-stu-id="1e494-376">Map to convert an order message to a customer service order request.</span></span>|  
  
 <span data-ttu-id="1e494-377">中的文件\<安装目录\>\OrderBrokerSchemas</span><span class="sxs-lookup"><span data-stu-id="1e494-377">Files in \<Install Directory\>\OrderBrokerSchemas</span></span>  
  
|<span data-ttu-id="1e494-378">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-378">File</span></span>|<span data-ttu-id="1e494-379">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-379">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-380">CSR_OrderRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-380">CSR_OrderRequest.xsd</span></span>|<span data-ttu-id="1e494-381">客户服务请求的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-381">Schema for the customer service request.</span></span>|  
|<span data-ttu-id="1e494-382">OrderBrokerSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-382">OrderBrokerSchemas.btproj</span></span>|<span data-ttu-id="1e494-383">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-383">BizTalk project file.</span></span>|  
|<span data-ttu-id="1e494-384">Servicing_OrderRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-384">Servicing_OrderRequest.xsd</span></span>|<span data-ttu-id="1e494-385">定义发送到服务系统的消息架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-385">Schema defining the message sent to the servicing system.</span></span>|  
|<span data-ttu-id="1e494-386">SQLHistoryInsert.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-386">SQLHistoryInsert.xsd</span></span>|<span data-ttu-id="1e494-387">SQL 历史记录消息的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-387">Schema for the SQL history message.</span></span>|  
  
 <span data-ttu-id="1e494-388">中的文件\<安装目录\>\OrderBroker_Proxy</span><span class="sxs-lookup"><span data-stu-id="1e494-388">Files in \<Install Directory\>\OrderBroker_Proxy</span></span>  
  
|<span data-ttu-id="1e494-389">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-389">File</span></span>|<span data-ttu-id="1e494-390">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-390">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-391">Global.asax</span><span class="sxs-lookup"><span data-stu-id="1e494-391">Global.asax</span></span>|<span data-ttu-id="1e494-392">生成的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-392">Generated file.</span></span>|  
|<span data-ttu-id="1e494-393">Index.htm</span><span class="sxs-lookup"><span data-stu-id="1e494-393">Index.htm</span></span>|<span data-ttu-id="1e494-394">生成的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-394">Generated file.</span></span>|  
|<span data-ttu-id="1e494-395">OrderBrokerOrch_OrderPort.asmx</span><span class="sxs-lookup"><span data-stu-id="1e494-395">OrderBrokerOrch_OrderPort.asmx</span></span>|<span data-ttu-id="1e494-396">生成的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-396">Generated file.</span></span>|  
|<span data-ttu-id="1e494-397">Web.config</span><span class="sxs-lookup"><span data-stu-id="1e494-397">Web.config</span></span>|<span data-ttu-id="1e494-398">生成的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-398">Generated file.</span></span>|  
  
 <span data-ttu-id="1e494-399">中的文件\<安装目录\>\OrderBroker_Proxy\App_Code</span><span class="sxs-lookup"><span data-stu-id="1e494-399">Files in \<Install Directory\>\OrderBroker_Proxy\App_Code</span></span>  
  
|<span data-ttu-id="1e494-400">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-400">File</span></span>|<span data-ttu-id="1e494-401">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-401">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-402">DataTypes.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-402">DataTypes.cs</span></span>|<span data-ttu-id="1e494-403">生成的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-403">Generated file.</span></span>|  
|<span data-ttu-id="1e494-404">OrderBrokerOrch_OrderPort.asmx.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-404">OrderBrokerOrch_OrderPort.asmx.cs</span></span>|<span data-ttu-id="1e494-405">生成的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-405">Generated file.</span></span>|  
  
 <span data-ttu-id="1e494-406">中的文件\<安装目录\>\OrderHandler</span><span class="sxs-lookup"><span data-stu-id="1e494-406">Files in \<Install Directory\>\OrderHandler</span></span>  
  
|<span data-ttu-id="1e494-407">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-407">File</span></span>|<span data-ttu-id="1e494-408">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-408">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-409">OrderHandler.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-409">OrderHandler.cs</span></span>|<span data-ttu-id="1e494-410">C#为代码**OrderHandler**对象。</span><span class="sxs-lookup"><span data-stu-id="1e494-410">C# code for the **OrderHandler** object.</span></span>|  
|<span data-ttu-id="1e494-411">OrderHandler.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-411">OrderHandler.csproj</span></span>|<span data-ttu-id="1e494-412">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-412">C# project file.</span></span>|  
  
 <span data-ttu-id="1e494-413">中的文件\<安装目录\>\Rules</span><span class="sxs-lookup"><span data-stu-id="1e494-413">Files in \<Install Directory\>\Rules</span></span>  
  
|<span data-ttu-id="1e494-414">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-414">File</span></span>|<span data-ttu-id="1e494-415">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-415">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-416">DecodeAndValidateOrderRules.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-416">DecodeAndValidateOrderRules.xml</span></span>|<span data-ttu-id="1e494-417">业务规则引擎的规则文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-417">Rules file for the Business Rules Engine.</span></span>|  
  
 <span data-ttu-id="1e494-418">中的文件\<安装目录\>\SampleMessages</span><span class="sxs-lookup"><span data-stu-id="1e494-418">Files in \<Install Directory\>\SampleMessages</span></span>  
  
|<span data-ttu-id="1e494-419">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-419">File</span></span>|<span data-ttu-id="1e494-420">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-420">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-421">CSR_OrderRequest.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-421">CSR_OrderRequest.xml</span></span>|<span data-ttu-id="1e494-422">示例客户服务订单请求。</span><span class="sxs-lookup"><span data-stu-id="1e494-422">Sample customer service order request.</span></span>|  
|<span data-ttu-id="1e494-423">OrderEnvelope.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-423">OrderEnvelope.xml</span></span>|<span data-ttu-id="1e494-424">示例订单信封。</span><span class="sxs-lookup"><span data-stu-id="1e494-424">Sample order envelope.</span></span>|  
  
 <span data-ttu-id="1e494-425">中的文件\<安装目录\>\SchemaClasses</span><span class="sxs-lookup"><span data-stu-id="1e494-425">Files in \<Install Directory\>\SchemaClasses</span></span>  
  
|<span data-ttu-id="1e494-426">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-426">File</span></span>|<span data-ttu-id="1e494-427">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-427">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-428">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-428">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-429">程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-429">Assembly information file.</span></span>|  
|<span data-ttu-id="1e494-430">InternalMessages.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-430">InternalMessages.cs</span></span>|<span data-ttu-id="1e494-431">C#定义用于在解决方案的组件之间进行通信的消息的类的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-431">C# code for classes defining messages used to communicate among components of the solution.</span></span>|  
|<span data-ttu-id="1e494-432">SchemaClasses.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-432">SchemaClasses.csproj</span></span>|<span data-ttu-id="1e494-433">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-433">C# project file.</span></span>|  
  
 <span data-ttu-id="1e494-434">中的文件\<安装目录\>\Schemas</span><span class="sxs-lookup"><span data-stu-id="1e494-434">Files in \<Install Directory\>\Schemas</span></span>  
  
|<span data-ttu-id="1e494-435">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-435">File</span></span>|<span data-ttu-id="1e494-436">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-436">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-437">Order.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-437">Order.xsd</span></span>|<span data-ttu-id="1e494-438">订单消息的架构。</span><span class="sxs-lookup"><span data-stu-id="1e494-438">Schema for the order message.</span></span>|  
|<span data-ttu-id="1e494-439">OrderPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="1e494-439">OrderPropertySchema.xsd</span></span>|<span data-ttu-id="1e494-440">升级属性架构的订单消息。</span><span class="sxs-lookup"><span data-stu-id="1e494-440">Promoted properties schema for the order message.</span></span>|  
|<span data-ttu-id="1e494-441">Schemas.btproj</span><span class="sxs-lookup"><span data-stu-id="1e494-441">Schemas.btproj</span></span>|<span data-ttu-id="1e494-442">BizTalk 项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-442">BizTalk project file.</span></span>|  
  
 <span data-ttu-id="1e494-443">中的文件\<安装目录\>\Scripts</span><span class="sxs-lookup"><span data-stu-id="1e494-443">Files in \<Install Directory\>\Scripts</span></span>  
  
|<span data-ttu-id="1e494-444">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-444">File</span></span>|<span data-ttu-id="1e494-445">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-445">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-446">CleanDirs.cmd</span><span class="sxs-lookup"><span data-stu-id="1e494-446">CleanDirs.cmd</span></span>|<span data-ttu-id="1e494-447">若要删除文件仅执行的测试版本的解决方案结合使用的目录的命令文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-447">Command file to delete directories used with files only exercising of the test version of the solution.</span></span>|  
|<span data-ttu-id="1e494-448">CreateAppReferences.vbs</span><span class="sxs-lookup"><span data-stu-id="1e494-448">CreateAppReferences.vbs</span></span>|<span data-ttu-id="1e494-449">VBScript 来创建应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="1e494-449">VBScript to create application references.</span></span>|  
|<span data-ttu-id="1e494-450">CreateQueues.vbs</span><span class="sxs-lookup"><span data-stu-id="1e494-450">CreateQueues.vbs</span></span>|<span data-ttu-id="1e494-451">若要创建 MSMQ 队列的 VBScript。</span><span class="sxs-lookup"><span data-stu-id="1e494-451">VBScript to create MSMQ queues.</span></span>|  
|<span data-ttu-id="1e494-452">CreateSouthridgeVideoApplication.cmd</span><span class="sxs-lookup"><span data-stu-id="1e494-452">CreateSouthridgeVideoApplication.cmd</span></span>|<span data-ttu-id="1e494-453">若要在 SSO 配置存储区中创建的配置值的命令文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-453">Command file to create the configuration values in the SSO configuration store.</span></span>|  
|<span data-ttu-id="1e494-454">CreateTestDirectories.cmd</span><span class="sxs-lookup"><span data-stu-id="1e494-454">CreateTestDirectories.cmd</span></span>|<span data-ttu-id="1e494-455">创建解决方案的测试版本的目录的命令文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-455">Command file to create directories for the test version of the solution.</span></span>|  
|<span data-ttu-id="1e494-456">DeployBPM.cmd</span><span class="sxs-lookup"><span data-stu-id="1e494-456">DeployBPM.cmd</span></span>|<span data-ttu-id="1e494-457">若要将解决方案部署的命令文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-457">Command file to deploy the solution.</span></span>|  
|<span data-ttu-id="1e494-458">regac.bat</span><span class="sxs-lookup"><span data-stu-id="1e494-458">regac.bat</span></span>|<span data-ttu-id="1e494-459">若要在全局程序集缓存 (GAC) 中注册程序集的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-459">Batch file to register assemblies in the global assembly cache (GAC).</span></span>|  
|<span data-ttu-id="1e494-460">SouthridgeVideoSSOConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="1e494-460">SouthridgeVideoSSOConfiguration.xml</span></span>|<span data-ttu-id="1e494-461">包含初始 SSO 配置值的文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-461">File containing the initial SSO configuration values.</span></span>|  
  
 <span data-ttu-id="1e494-462">中的文件\<安装目录\>\ServiceLevelTracking</span><span class="sxs-lookup"><span data-stu-id="1e494-462">Files in \<Install Directory\>\ServiceLevelTracking</span></span>  
  
|<span data-ttu-id="1e494-463">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-463">File</span></span>|<span data-ttu-id="1e494-464">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-464">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-465">Activity_CustomerOrderRequest.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-465">Activity_CustomerOrderRequest.cs</span></span>|<span data-ttu-id="1e494-466">C#若要定义客户订单请求 BAM 活动的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-466">C# code to define the customer order request BAM activities.</span></span>|  
|<span data-ttu-id="1e494-467">Activity_OrderManager.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-467">Activity_OrderManager.cs</span></span>|<span data-ttu-id="1e494-468">C#若要定义订单管理器 BAM 活动的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-468">C# code to define the order manager BAM activities.</span></span>|  
|<span data-ttu-id="1e494-469">Activity_ServiceOrderRequest.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-469">Activity_ServiceOrderRequest.cs</span></span>|<span data-ttu-id="1e494-470">C#若要定义服务订单请求 BAM 活动的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-470">C# code to define the service order request BAM activities.</span></span>|  
|<span data-ttu-id="1e494-471">ServiceLevelTracking.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-471">ServiceLevelTracking.cs</span></span>|<span data-ttu-id="1e494-472">C#代码以定义活动的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="1e494-472">C# code to define the abstract base class for activities.</span></span>|  
|<span data-ttu-id="1e494-473">ServiceLevelTracking.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-473">ServiceLevelTracking.csproj</span></span>|<span data-ttu-id="1e494-474">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-474">C# project file.</span></span>|  
  
 <span data-ttu-id="1e494-475">中的文件\<安装目录\>\Utilities</span><span class="sxs-lookup"><span data-stu-id="1e494-475">Files in \<Install Directory\>\Utilities</span></span>  
  
|<span data-ttu-id="1e494-476">文件</span><span class="sxs-lookup"><span data-stu-id="1e494-476">File</span></span>|<span data-ttu-id="1e494-477">Description</span><span class="sxs-lookup"><span data-stu-id="1e494-477">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1e494-478">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-478">AssemblyInfo.cs</span></span>|<span data-ttu-id="1e494-479">程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-479">Assembly information file.</span></span>|  
|<span data-ttu-id="1e494-480">CableOrderException.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-480">CableOrderException.cs</span></span>|<span data-ttu-id="1e494-481">C#定义电缆 order 异常类的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-481">C# code defining the cable order exception class.</span></span>|  
|<span data-ttu-id="1e494-482">Helper.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-482">Helper.cs</span></span>|<span data-ttu-id="1e494-483">C#各种助手类和方法的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-483">C# code for various helper classes and methods.</span></span>|  
|<span data-ttu-id="1e494-484">Recaller.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-484">Recaller.cs</span></span>|<span data-ttu-id="1e494-485">C#为代码**Recaller**对象。</span><span class="sxs-lookup"><span data-stu-id="1e494-485">C# code for the **Recaller** object.</span></span>|  
|<span data-ttu-id="1e494-486">SSOConfigHelper.cs</span><span class="sxs-lookup"><span data-stu-id="1e494-486">SSOConfigHelper.cs</span></span>|<span data-ttu-id="1e494-487">C#SSO 配置助手对象和方法的代码。</span><span class="sxs-lookup"><span data-stu-id="1e494-487">C# code for the SSO configuration helper objects and methods.</span></span>|  
|<span data-ttu-id="1e494-488">Utilities.csproj</span><span class="sxs-lookup"><span data-stu-id="1e494-488">Utilities.csproj</span></span>|<span data-ttu-id="1e494-489">C#项目文件。</span><span class="sxs-lookup"><span data-stu-id="1e494-489">C# project file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e494-490">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e494-490">See Also</span></span>  
 <span data-ttu-id="1e494-491">[业务流程管理解决方案参考](../core/business-process-management-solution-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1e494-491">[Business Process Management Solution Reference](../core/business-process-management-solution-reference.md) </span></span>  
 [<span data-ttu-id="1e494-492">业务流程管理解决方案的组件</span><span class="sxs-lookup"><span data-stu-id="1e494-492">Components of the Business Process Management Solution</span></span>](../core/components-of-the-business-process-management-solution.md)