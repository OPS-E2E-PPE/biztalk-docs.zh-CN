---
title: RemoveResource 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e2c6046-43d4-4ac1-a1b1-3795b4e44038
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc7b5e6f5d254624f295aef16761d074379f3ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397915"
---
# <a name="removeresource-command"></a><span data-ttu-id="d4366-102">RemoveResource 命令</span><span class="sxs-lookup"><span data-stu-id="d4366-102">RemoveResource Command</span></span>
<span data-ttu-id="d4366-103">移除 （删除） 从 BizTalk 管理数据库项目。</span><span class="sxs-lookup"><span data-stu-id="d4366-103">Removes (deletes) an artifact from the BizTalk Management database.</span></span> <span data-ttu-id="d4366-104">运行此命令不会删除该项目从全局程序集缓存 (GAC)、 文件系统、 证书存储区、 Internet 信息服务或 Windows 注册表中，如果它存在于这些位置中。</span><span class="sxs-lookup"><span data-stu-id="d4366-104">Running this command does not remove the artifact from the global assembly cache (GAC), file system, certificate store, Internet Information Services, or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="d4366-105">不会从 BAM 主导入数据库中删除 BAM 定义，也不会删除策略从规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="d4366-105">It does not remove a BAM definition from the BAM Primary Import database nor does it remove policies from the Rule Engine database.</span></span> <span data-ttu-id="d4366-106">如果运行此命令删除绑定文件，则绑定保持不变，删除只绑定文件。</span><span class="sxs-lookup"><span data-stu-id="d4366-106">If you run this command to remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
 <span data-ttu-id="d4366-107">您可以使用此命令删除以下项目类型：</span><span class="sxs-lookup"><span data-stu-id="d4366-107">You can use this command to remove the following artifact types:</span></span>  
  
- <span data-ttu-id="d4366-108">.NET 程序集 (system.biztalk: assembly)</span><span class="sxs-lookup"><span data-stu-id="d4366-108">.NET assembly (System.BizTalk:Assembly)</span></span>  
  
- <span data-ttu-id="d4366-109">BAM 定义 (system.biztalk: bam)</span><span class="sxs-lookup"><span data-stu-id="d4366-109">BAM definition (System.BizTalk:Bam)</span></span>  
  
- <span data-ttu-id="d4366-110">BizTalk 程序集 (system.biztalk: biztalkassembly</span><span class="sxs-lookup"><span data-stu-id="d4366-110">BizTalk assembly (System.BizTalk:BizTalkAssembly</span></span>  
  
- <span data-ttu-id="d4366-111">BizTalk 绑定文件 (system.biztalk: biztalkbinding)</span><span class="sxs-lookup"><span data-stu-id="d4366-111">BizTalk binding file (System.BizTalk:BizTalkBinding)</span></span>  
  
- <span data-ttu-id="d4366-112">安全证书 (system.biztalk: certificate)</span><span class="sxs-lookup"><span data-stu-id="d4366-112">Security certificate (System.BizTalk:Certificate)</span></span>  
  
- <span data-ttu-id="d4366-113">COM 组件 (system.biztalk: com)</span><span class="sxs-lookup"><span data-stu-id="d4366-113">COM component (System.BizTalk:Com)</span></span>  
  
- <span data-ttu-id="d4366-114">特别文件 (system.biztalk: file)</span><span class="sxs-lookup"><span data-stu-id="d4366-114">Ad hoc file (System.BizTalk:File)</span></span>  
  
- <span data-ttu-id="d4366-115">后续处理脚本 (system.biztalk: postprocessingscript)</span><span class="sxs-lookup"><span data-stu-id="d4366-115">Postprocessing script (System.BizTalk:PostProcessingScript)</span></span>  
  
- <span data-ttu-id="d4366-116">预处理脚本 (system.biztalk: preprocessingscript)</span><span class="sxs-lookup"><span data-stu-id="d4366-116">Preprocessing script (System.BizTalk:PreProcessingScript)</span></span>  
  
- <span data-ttu-id="d4366-117">策略或规则 (system.biztalk: rules)</span><span class="sxs-lookup"><span data-stu-id="d4366-117">Policy or rule (System.BizTalk:Rules)</span></span>  
  
- <span data-ttu-id="d4366-118">虚拟目录 (system.biztalk: webdirectory)</span><span class="sxs-lookup"><span data-stu-id="d4366-118">Virtual directory (System.BizTalk:WebDirectory)</span></span>  
  
  <span data-ttu-id="d4366-119">在以下情况下，删除操作将失败：</span><span class="sxs-lookup"><span data-stu-id="d4366-119">The remove operation will fail in the following cases:</span></span>  
  
- <span data-ttu-id="d4366-120">尝试删除 BizTalk 程序集到另一个程序集具有的引用。</span><span class="sxs-lookup"><span data-stu-id="d4366-120">You attempt to remove a BizTalk assembly to which another assembly has a reference.</span></span>  
  
- <span data-ttu-id="d4366-121">尝试删除包含由发送管道的 BizTalk 程序集或接收端口。</span><span class="sxs-lookup"><span data-stu-id="d4366-121">You attempt to remove a BizTalk assembly that includes a pipeline that is used by a send or receive port.</span></span>  
  
- <span data-ttu-id="d4366-122">尝试删除包含发送端口所使用的映射的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="d4366-122">You attempt to remove a BizTalk assembly that includes a map used by a send port.</span></span>  
  
- <span data-ttu-id="d4366-123">尝试删除包含业务流程的未处于已取消登记状态或具有挂起的实例的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="d4366-123">You attempt to remove a BizTalk assembly that includes an orchestration that is not in an unenlisted state or that has a suspended instance.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="d4366-124">用法</span><span class="sxs-lookup"><span data-stu-id="d4366-124">Usage</span></span>  
 <span data-ttu-id="d4366-125">**BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="d4366-125">**BTSTask RemoveResource /ApplicationName:** *value* **/Luid:** *value* [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="d4366-126">Parameters</span><span class="sxs-lookup"><span data-stu-id="d4366-126">Parameters</span></span>  
  
|<span data-ttu-id="d4366-127">参数</span><span class="sxs-lookup"><span data-stu-id="d4366-127">Parameter</span></span>|<span data-ttu-id="d4366-128">Required</span><span class="sxs-lookup"><span data-stu-id="d4366-128">Required</span></span>|<span data-ttu-id="d4366-129">Description</span><span class="sxs-lookup"><span data-stu-id="d4366-129">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="d4366-130">**/ ApplicationName** (或 **/A**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="d4366-130">**/ApplicationName** (or **/A**, see Remarks)</span></span>|<span data-ttu-id="d4366-131">是</span><span class="sxs-lookup"><span data-stu-id="d4366-131">Yes</span></span>|<span data-ttu-id="d4366-132">包含的资源项目的 BizTalk 应用程序若要删除的名称。</span><span class="sxs-lookup"><span data-stu-id="d4366-132">Name of the BizTalk application containing the resource artifact to delete.</span></span> <span data-ttu-id="d4366-133">如果名称包含空格，必须将其用双引号 （"）。</span><span class="sxs-lookup"><span data-stu-id="d4366-133">If the name includes spaces, you must enclose it with double quotation marks (").</span></span>|  
|<span data-ttu-id="d4366-134">**/ Luid** (或 **/L**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="d4366-134">**/Luid** (or **/L**, see Remarks)</span></span>|<span data-ttu-id="d4366-135">是</span><span class="sxs-lookup"><span data-stu-id="d4366-135">Yes</span></span>|<span data-ttu-id="d4366-136">项目的本地唯一标识符 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="d4366-136">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="d4366-137">可通过获得 LUID [ListApp 命令](../core/listapp-command.md)。</span><span class="sxs-lookup"><span data-stu-id="d4366-137">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
|<span data-ttu-id="d4366-138">**/ 服务器**(或 **/S**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="d4366-138">**/Server** (or **/S**, see Remarks)</span></span>|<span data-ttu-id="d4366-139">否</span><span class="sxs-lookup"><span data-stu-id="d4366-139">No</span></span>|<span data-ttu-id="d4366-140">承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="d4366-140">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="d4366-141">实例名称仅是所需的实例名称不同于服务器名称时。</span><span class="sxs-lookup"><span data-stu-id="d4366-141">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="d4366-142">端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。</span><span class="sxs-lookup"><span data-stu-id="d4366-142">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="d4366-143">示例：</span><span class="sxs-lookup"><span data-stu-id="d4366-143">Examples:</span></span><br /><br /> <span data-ttu-id="d4366-144">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="d4366-144">Server=MyServer</span></span><br /><br /> <span data-ttu-id="d4366-145">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="d4366-145">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="d4366-146">如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="d4366-146">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
|<span data-ttu-id="d4366-147">**/ 数据库**(或 **/D**，请参阅备注)</span><span class="sxs-lookup"><span data-stu-id="d4366-147">**/Database** (or **/D**, see Remarks)</span></span>|<span data-ttu-id="d4366-148">否</span><span class="sxs-lookup"><span data-stu-id="d4366-148">No</span></span>|<span data-ttu-id="d4366-149">BizTalk 管理数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="d4366-149">Name of the BizTalk Management database.</span></span> <span data-ttu-id="d4366-150">如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="d4366-150">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="d4366-151">示例</span><span class="sxs-lookup"><span data-stu-id="d4366-151">Sample</span></span>  
 <span data-ttu-id="d4366-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="d4366-152">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4366-153">备注</span><span class="sxs-lookup"><span data-stu-id="d4366-153">Remarks</span></span>  
 <span data-ttu-id="d4366-154">参数不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d4366-154">Parameters are not case-sensitive.</span></span> <span data-ttu-id="d4366-155">不需要键入整个参数名称来指定它;您可以键入明确标识参数名称的第几个字母。</span><span class="sxs-lookup"><span data-stu-id="d4366-155">You do not need to type the entire parameter name to specify it; you can type the first few letters of the parameter name that identify it unambiguously.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4366-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4366-156">See Also</span></span>  
 <span data-ttu-id="d4366-157">[BTSTask 命令行参考](../core/btstask-command-line-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d4366-157">[BTSTask Command-Line Reference](../core/btstask-command-line-reference.md) </span></span>  
 [<span data-ttu-id="d4366-158">如何从应用程序中删除项目</span><span class="sxs-lookup"><span data-stu-id="d4366-158">How to Remove an Artifact from an Application</span></span>](../core/how-to-remove-an-artifact-from-an-application.md)