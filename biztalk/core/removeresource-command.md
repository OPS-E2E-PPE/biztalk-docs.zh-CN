---
title: "RemoveResource 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d091c46ea25cbb2489264316239b6763d841a47e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="removeresource-command"></a><span data-ttu-id="7e99c-102">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="7e99c-102">RemoveResource Command</span></span>
<span data-ttu-id="7e99c-103">从 BizTalk 管理数据库中删除项目。</span><span class="sxs-lookup"><span data-stu-id="7e99c-103">Removes (deletes) an artifact from the BizTalk Management database.</span></span> <span data-ttu-id="7e99c-104">运行此命令不会从全局程序集缓存 (GAC)、文件系统、证书存储、Internet 信息服务或 Windows 注册表中删除项目（如果项目存在于这些位置中）。</span><span class="sxs-lookup"><span data-stu-id="7e99c-104">Running this command does not remove the artifact from the global assembly cache (GAC), file system, certificate store, Internet Information Services, or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="7e99c-105">该命令不会从 BAM 主导入数据库中删除 BAM 定义，也不会从规则引擎数据库中删除策略。</span><span class="sxs-lookup"><span data-stu-id="7e99c-105">It does not remove a BAM definition from the BAM Primary Import database nor does it remove policies from the Rule Engine database.</span></span> <span data-ttu-id="7e99c-106">如果您运行此命令来删除绑定文件，则绑定保持不变，仅删除绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7e99c-106">If you run this command to remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
 <span data-ttu-id="7e99c-107">使用此命令可以删除以下项目类型：</span><span class="sxs-lookup"><span data-stu-id="7e99c-107">You can use this command to remove the following artifact types:</span></span>  
  
-   <span data-ttu-id="7e99c-108">.NET 程序集 (System.BizTalk:Assembly)</span><span class="sxs-lookup"><span data-stu-id="7e99c-108">.NET assembly (System.BizTalk:Assembly)</span></span>  
  
-   <span data-ttu-id="7e99c-109">BAM 定义 (System.BizTalk:Bam)</span><span class="sxs-lookup"><span data-stu-id="7e99c-109">BAM definition (System.BizTalk:Bam)</span></span>  
  
-   <span data-ttu-id="7e99c-110">BizTalk 程序集 (System.BizTalk:BizTalkAssembly)</span><span class="sxs-lookup"><span data-stu-id="7e99c-110">BizTalk assembly (System.BizTalk:BizTalkAssembly</span></span>  
  
-   <span data-ttu-id="7e99c-111">BizTalk 绑定文件 (System.BizTalk:BizTalkBinding)</span><span class="sxs-lookup"><span data-stu-id="7e99c-111">BizTalk binding file (System.BizTalk:BizTalkBinding)</span></span>  
  
-   <span data-ttu-id="7e99c-112">安全证书 (System.BizTalk:Certificate)</span><span class="sxs-lookup"><span data-stu-id="7e99c-112">Security certificate (System.BizTalk:Certificate)</span></span>  
  
-   <span data-ttu-id="7e99c-113">COM 组件 (System.BizTalk:Com)</span><span class="sxs-lookup"><span data-stu-id="7e99c-113">COM component (System.BizTalk:Com)</span></span>  
  
-   <span data-ttu-id="7e99c-114">特别文件 (System.BizTalk:File)</span><span class="sxs-lookup"><span data-stu-id="7e99c-114">Ad hoc file (System.BizTalk:File)</span></span>  
  
-   <span data-ttu-id="7e99c-115">后续处理脚本 (System.BizTalk:PostProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="7e99c-115">Postprocessing script (System.BizTalk:PostProcessingScript)</span></span>  
  
-   <span data-ttu-id="7e99c-116">预处理脚本 (System.BizTalk:PreProcessingScript)</span><span class="sxs-lookup"><span data-stu-id="7e99c-116">Preprocessing script (System.BizTalk:PreProcessingScript)</span></span>  
  
-   <span data-ttu-id="7e99c-117">策略或规则 (System.BizTalk:Rules)</span><span class="sxs-lookup"><span data-stu-id="7e99c-117">Policy or rule (System.BizTalk:Rules)</span></span>  
  
-   <span data-ttu-id="7e99c-118">虚拟目录 (System.BizTalk:WebDirectory)</span><span class="sxs-lookup"><span data-stu-id="7e99c-118">Virtual directory (System.BizTalk:WebDirectory)</span></span>  
  
 <span data-ttu-id="7e99c-119">在以下情况下，删除操作会失败：</span><span class="sxs-lookup"><span data-stu-id="7e99c-119">The remove operation will fail in the following cases:</span></span>  
  
-   <span data-ttu-id="7e99c-120">尝试删除其他程序集要引用的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="7e99c-120">You attempt to remove a BizTalk assembly to which another assembly has a reference.</span></span>  
  
-   <span data-ttu-id="7e99c-121">尝试删除包含发送端口或接收端口所使用的管道的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="7e99c-121">You attempt to remove a BizTalk assembly that includes a pipeline that is used by a send or receive port.</span></span>  
  
-   <span data-ttu-id="7e99c-122">尝试删除包含发送端口所使用的映射的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="7e99c-122">You attempt to remove a BizTalk assembly that includes a map used by a send port.</span></span>  
  
-   <span data-ttu-id="7e99c-123">尝试删除包含不处于未登记状态或具有挂起实例的业务流程的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="7e99c-123">You attempt to remove a BizTalk assembly that includes an orchestration that is not in an unenlisted state or that has a suspended instance.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="7e99c-124">用法</span><span class="sxs-lookup"><span data-stu-id="7e99c-124">Usage</span></span>  
 <span data-ttu-id="7e99c-125">**BTSTask RemoveResource /ApplicationName:** *值* **/Luid:** *值*[**/Server:** *值*] [**/数据库：***值*]</span><span class="sxs-lookup"><span data-stu-id="7e99c-125">**BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="7e99c-126">Parameters</span><span class="sxs-lookup"><span data-stu-id="7e99c-126">Parameters</span></span>  
  
|<span data-ttu-id="7e99c-127">参数</span><span class="sxs-lookup"><span data-stu-id="7e99c-127">Parameter</span></span>|<span data-ttu-id="7e99c-128">必需</span><span class="sxs-lookup"><span data-stu-id="7e99c-128">Required</span></span>|<span data-ttu-id="7e99c-129">Description</span><span class="sxs-lookup"><span data-stu-id="7e99c-129">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="7e99c-130">**/ ApplicationName** (或**/A**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="7e99c-130">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="7e99c-131">是</span><span class="sxs-lookup"><span data-stu-id="7e99c-131">Yes</span></span>|<span data-ttu-id="7e99c-132">包含要删除的资源项目的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="7e99c-132">Name of the BizTalk application containing the resource artifact to delete.</span></span> <span data-ttu-id="7e99c-133">如果名称包含空格，则必须将它用双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="7e99c-133">If the name includes spaces, you must enclose it with double quotation marks (").</span></span>|  
|<span data-ttu-id="7e99c-134">**/ Luid** (或**/L**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="7e99c-134">**/Luid** (or **/L**, see Remarks)</span></span>|<span data-ttu-id="7e99c-135">是</span><span class="sxs-lookup"><span data-stu-id="7e99c-135">Yes</span></span>|<span data-ttu-id="7e99c-136">项目的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="7e99c-136">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="7e99c-137">你可以通过使用获取而定[ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="7e99c-137">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
|<span data-ttu-id="7e99c-138">**/ 服务器**(或**/S**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="7e99c-138">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="7e99c-139">是</span><span class="sxs-lookup"><span data-stu-id="7e99c-139">No</span></span>|<span data-ttu-id="7e99c-140">BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。</span><span class="sxs-lookup"><span data-stu-id="7e99c-140">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="7e99c-141">只在实例名称与服务器名称不相同时才需要指定实例名称。</span><span class="sxs-lookup"><span data-stu-id="7e99c-141">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="7e99c-142">只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。</span><span class="sxs-lookup"><span data-stu-id="7e99c-142">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="7e99c-143">示例：</span><span class="sxs-lookup"><span data-stu-id="7e99c-143">Examples:</span></span><br /><br /> <span data-ttu-id="7e99c-144">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="7e99c-144">Server=MyServer</span></span><br /><br /> <span data-ttu-id="7e99c-145">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="7e99c-145">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="7e99c-146">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="7e99c-146">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="7e99c-147">**/ 数据库**(或**/D**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="7e99c-147">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="7e99c-148">是</span><span class="sxs-lookup"><span data-stu-id="7e99c-148">No</span></span>|<span data-ttu-id="7e99c-149">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="7e99c-149">Name of the BizTalk Management database.</span></span> <span data-ttu-id="7e99c-150">如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="7e99c-150">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="7e99c-151">示例</span><span class="sxs-lookup"><span data-stu-id="7e99c-151">Sample</span></span>  
 <span data-ttu-id="7e99c-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations，版本 = 1.0.0.0，Culture = neutral，PublicKeyToken = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="7e99c-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e99c-153">注释</span><span class="sxs-lookup"><span data-stu-id="7e99c-153">Remarks</span></span>  
 <span data-ttu-id="7e99c-154">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="7e99c-154">Parameters are not case-sensitive.</span></span> <span data-ttu-id="7e99c-155">指定参数无需键入整个参数名，只需键入可明确标识该参数的参数名的前几个字母即可。</span><span class="sxs-lookup"><span data-stu-id="7e99c-155">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e99c-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e99c-156">See Also</span></span>  
 <span data-ttu-id="7e99c-157">[BTSTask 命令行参考](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7e99c-157">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="7e99c-158">如何从应用程序中删除项目</span><span class="sxs-lookup"><span data-stu-id="7e99c-158">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)