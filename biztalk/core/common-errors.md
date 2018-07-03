---
title: 常见错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fe48a8e-def0-4a00-aa7f-9a49ae555351
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01c5dfe58f7b31bb5ef461249765d527f78d9264
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009054"
---
# <a name="common-errors"></a><span data-ttu-id="381b8-102">常见错误</span><span class="sxs-lookup"><span data-stu-id="381b8-102">Common Errors</span></span>
<span data-ttu-id="381b8-103">本主题列出来在使用 BizTalk 映射器创建映射时可能遇到的常见错误消息。</span><span class="sxs-lookup"><span data-stu-id="381b8-103">This topic lists out common error messages you may encounter while creating maps using BizTalk Mapper.</span></span>  
  
## <a name="you-receive-error-event-id-324-when-parsing-dates"></a><span data-ttu-id="381b8-104">分析日期时收到错误事件 ID 324</span><span class="sxs-lookup"><span data-stu-id="381b8-104">You receive error event ID 324 when parsing dates</span></span>  
  
### <a name="problem"></a><span data-ttu-id="381b8-105">问题</span><span class="sxs-lookup"><span data-stu-id="381b8-105">Problem</span></span>  
 <span data-ttu-id="381b8-106">当使用数据库**值提取程序**functoid 映射提取日期字段，在文档中的对出站文档定义的验证可能会失败。</span><span class="sxs-lookup"><span data-stu-id="381b8-106">When you use the Database **Value Extractor** functoid in a map to extract a date field, your document may fail validation against the outbound document definition.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="381b8-107"> 可能会在事件日志中记录类似于以下的验证错误：</span><span class="sxs-lookup"><span data-stu-id="381b8-107"> may log a validation error similar to the following in the event log:</span></span>  
  
 <span data-ttu-id="381b8-108">事件源： BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="381b8-108">Event Source: BizTalk Server</span></span>  
  
 <span data-ttu-id="381b8-109">事件类别： 文档处理</span><span class="sxs-lookup"><span data-stu-id="381b8-109">Event Category: Document Processing</span></span>  
  
 <span data-ttu-id="381b8-110">事件 ID: 324</span><span class="sxs-lookup"><span data-stu-id="381b8-110">Event ID: 324</span></span>  
  
 <span data-ttu-id="381b8-111">说明:</span><span class="sxs-lookup"><span data-stu-id="381b8-111">Description:</span></span>  
  
 <span data-ttu-id="381b8-112">在 BizTalk Server 中出错。</span><span class="sxs-lookup"><span data-stu-id="381b8-112">An error occurred in BizTalk Server.</span></span>  
  
 <span data-ttu-id="381b8-113">详细信息：</span><span class="sxs-lookup"><span data-stu-id="381b8-113">Details:</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="381b8-114">XML 文档验证失败的原因如下： 错误分析"10/12/1995年作为日期数据类型。</span><span class="sxs-lookup"><span data-stu-id="381b8-114">The XML document has failed validation for the following reason: Error parsing '10/12/1995' as date datatype.</span></span>  
  
 <span data-ttu-id="381b8-115">挂起的队列 ID:"{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span><span class="sxs-lookup"><span data-stu-id="381b8-115">Suspended Queue ID: "{A1127909-CA36-4359-B672-7CBA8B60BDAF}"</span></span>  
  
### <a name="cause"></a><span data-ttu-id="381b8-116">原因</span><span class="sxs-lookup"><span data-stu-id="381b8-116">Cause</span></span>  
 <span data-ttu-id="381b8-117">日期格式 （如从数据源返回） 不是采用 ISO 8601 格式，这是所需的 XML 的格式。</span><span class="sxs-lookup"><span data-stu-id="381b8-117">The date format (as it is returned from the data source) is not in ISO 8601 format, which is the format required by XML.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="381b8-118">解决方法</span><span class="sxs-lookup"><span data-stu-id="381b8-118">Resolution</span></span>  
 <span data-ttu-id="381b8-119">若要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="381b8-119">To resolve this issue, do one of the following:</span></span>  
  
- <span data-ttu-id="381b8-120">编辑出站文档定义使用而不是日期数据类型的字符串数据类型。</span><span class="sxs-lookup"><span data-stu-id="381b8-120">Edit your outbound document definition to use a string datatype instead of a date datatype.</span></span>  
  
- <span data-ttu-id="381b8-121">创建自定义[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**脚本**functoid 会将转换数据库的输出**值提取程序**为 ISO 8601 格式的 functoid。</span><span class="sxs-lookup"><span data-stu-id="381b8-121">Create a custom [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsVBNoVersion](../includes/btsvbnoversion-md.md)]**Script** functoid that will convert the output of the Database **Value Extractor** functoid into the ISO 8601 format.</span></span>  
  
  <span data-ttu-id="381b8-122">有关详细信息，请参阅知识库文章[278737](http://support.microsoft.com/kb/278737/en-us)。</span><span class="sxs-lookup"><span data-stu-id="381b8-122">For more information, see KB article [278737](http://support.microsoft.com/kb/278737/en-us).</span></span>  
  
## <a name="you-receive-internal-compiler-error-0xc0000005-at-address-53624fd6-when-compiling-the-maps"></a><span data-ttu-id="381b8-123">当收到内部编译器错误 (在地址 53624FD6 0xc0000005) 编译映射</span><span class="sxs-lookup"><span data-stu-id="381b8-123">You receive Internal Compiler Error (0xc0000005 at address 53624FD6) when compiling the maps</span></span>  
  
### <a name="problem"></a><span data-ttu-id="381b8-124">问题</span><span class="sxs-lookup"><span data-stu-id="381b8-124">Problem</span></span>  
 <span data-ttu-id="381b8-125">当编译包含大型架构、 映射或业务流程的单个 BizTalk 项目时，编译器可能会生成如下错误：</span><span class="sxs-lookup"><span data-stu-id="381b8-125">When you compile a single BizTalk project that consists of large schemas, maps, or orchestrations, the compiler may generate an error similar to the following:</span></span>  
  
 <span data-ttu-id="381b8-126">内部编译器错误 (在地址 53624FD6 0xc0000005): 可能的原因是代码生成。</span><span class="sxs-lookup"><span data-stu-id="381b8-126">Internal Compiler Error (0xc0000005 at address 53624FD6): likely culprit is 'CODEGEN'.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="381b8-127">原因</span><span class="sxs-lookup"><span data-stu-id="381b8-127">Cause</span></span>  
 <span data-ttu-id="381b8-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器中的单个项目的所有字符串的总大小具有 16 兆字节的限制。</span><span class="sxs-lookup"><span data-stu-id="381b8-128">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="381b8-129">而编译 BizTalk 项目，编译器将序列化架构、 映射和业务流程创建程序集，而这会增大可能会超出此限制的所有字符串的总大小。</span><span class="sxs-lookup"><span data-stu-id="381b8-129">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="381b8-130">解决方法</span><span class="sxs-lookup"><span data-stu-id="381b8-130">Resolution</span></span>  
 <span data-ttu-id="381b8-131">若要解决此问题，可以分隔架构或映射到不同的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="381b8-131">To resolve this issue, you can separate schemas or maps into different BizTalk projects.</span></span>  
  
## <a name="you-receive-errors-about-the-type-name-of-a-biztalk-artifact"></a><span data-ttu-id="381b8-132">接收有关类型名称的 BizTalk 项目的错误</span><span class="sxs-lookup"><span data-stu-id="381b8-132">You receive errors about the Type Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="381b8-133">问题</span><span class="sxs-lookup"><span data-stu-id="381b8-133">Problem</span></span>  
 <span data-ttu-id="381b8-134">在 BizTalk 项目中，使用文件名创建地图**System.btm**或**Microsoft.btm**。</span><span class="sxs-lookup"><span data-stu-id="381b8-134">In a BizTalk project, create a map with filename **System.btm** or **Microsoft.btm**.</span></span> <span data-ttu-id="381b8-135">生成项目时，BizTalk 映射器将生成类似于以下任一错误：</span><span class="sxs-lookup"><span data-stu-id="381b8-135">When you build the project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="381b8-136">“类型名称‘SerializableAttribute’不存在…”</span><span class="sxs-lookup"><span data-stu-id="381b8-136">“The typename ‘SerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="381b8-137">“类型名称‘NonSerializableAttribute’不存在…”</span><span class="sxs-lookup"><span data-stu-id="381b8-137">“The typename ‘NonSerializableAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="381b8-138">“类型名称‘SerializableAttributeAttribute’不存在…”</span><span class="sxs-lookup"><span data-stu-id="381b8-138">“The typename ‘SerializableAttributeAttribute’ does not exist…”</span></span>  
  
-   <span data-ttu-id="381b8-139">“类型名称‘XLANs’不存在…”</span><span class="sxs-lookup"><span data-stu-id="381b8-139">“The typename ‘XLANs’ does not exist…”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="381b8-140">原因</span><span class="sxs-lookup"><span data-stu-id="381b8-140">Cause</span></span>  
 <span data-ttu-id="381b8-141">**类型名称**中**属性**网格不应具有任何保留的.NET 命名空间，如**系统**， **Microsoft**，等等。</span><span class="sxs-lookup"><span data-stu-id="381b8-141">The **Type Name** in the **Properties** grid should not have any reserved .NET namespaces, such as **System**, **Microsoft**, etc.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="381b8-142">解决方法</span><span class="sxs-lookup"><span data-stu-id="381b8-142">Resolution</span></span>  
 <span data-ttu-id="381b8-143">若要解决此问题，可以执行任何以下解决方法：</span><span class="sxs-lookup"><span data-stu-id="381b8-143">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="381b8-144">将映射名称修改为非 .NET 保留字的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="381b8-144">Modify the name of the map to any string which is not a .NET reserved word.</span></span> <span data-ttu-id="381b8-145">默认情况下，创建 BizTalk 项目系统**类型名称**从各自的项目的名称。</span><span class="sxs-lookup"><span data-stu-id="381b8-145">By default, the BizTalk project system creates the **Type Name** from the name of the respective artifact.</span></span>  
  
     <span data-ttu-id="381b8-146">对于如： 具有名称创建新地图**Map1.btm**设置**类型名称**属性值设置为**Map1**。</span><span class="sxs-lookup"><span data-stu-id="381b8-146">For e.g.: Creating a new map with name **Map1.btm** sets the **Type Name** property value to **Map1**.</span></span> <span data-ttu-id="381b8-147">但是，重命名现有 BizTalk 项目不会更改**类型名称**。</span><span class="sxs-lookup"><span data-stu-id="381b8-147">However, renaming an existing BizTalk artifact does not change the **Type Name**.</span></span>  
  
-   <span data-ttu-id="381b8-148">确保 BizTalk 项目中的所有项目的文件名不是 .NET 保留命名空间。</span><span class="sxs-lookup"><span data-stu-id="381b8-148">Ensure the filename of any of the artifacts in the BizTalk project is not a .NET reserved namespace.</span></span>  
  
## <a name="you-receive-errors-about-the-file-name-of-a-biztalk-artifact"></a><span data-ttu-id="381b8-149">收到有关 BizTalk 项目的文件名的错误</span><span class="sxs-lookup"><span data-stu-id="381b8-149">You receive errors about the File Name of a BizTalk artifact</span></span>  
  
### <a name="problem"></a><span data-ttu-id="381b8-150">问题</span><span class="sxs-lookup"><span data-stu-id="381b8-150">Problem</span></span>  
 <span data-ttu-id="381b8-151">生成 BizTalk 项目时，BizTalk 映射器会生成一条类似以下任一内容的错误：</span><span class="sxs-lookup"><span data-stu-id="381b8-151">When you build a BizTalk project, the BizTalk Mapper generates an error similar to any of the following:</span></span>  
  
-   <span data-ttu-id="381b8-152">"文件\<文件名\>具有重复的命名空间和类型名属性的值。"</span><span class="sxs-lookup"><span data-stu-id="381b8-152">“The File \<filename\> has duplicate values for namespace and type name properties.”</span></span>  
  
-   <span data-ttu-id="381b8-153">"命名空间\<名称\>已经包含 '_' 的定义。"</span><span class="sxs-lookup"><span data-stu-id="381b8-153">“The namespace \<name\> already contains a definition for ‘_’.”</span></span>  
  
### <a name="cause"></a><span data-ttu-id="381b8-154">原因</span><span class="sxs-lookup"><span data-stu-id="381b8-154">Cause</span></span>  
 <span data-ttu-id="381b8-155">在 BizTalk 项目中，检查是否存在以下情况：</span><span class="sxs-lookup"><span data-stu-id="381b8-155">In the BizTalk project, check for the following:</span></span>  
  
-   <span data-ttu-id="381b8-156">多个项目具有相同的文件名。</span><span class="sxs-lookup"><span data-stu-id="381b8-156">Multiple artifacts have the same filename.</span></span> <span data-ttu-id="381b8-157">对于如**Map1.xsd**并**Map1.btm**。</span><span class="sxs-lookup"><span data-stu-id="381b8-157">For e.g., **Map1.xsd** and**Map1.btm**.</span></span>  
  
-   <span data-ttu-id="381b8-158">文件名包括只由特殊字符 (**~**， **！**， **@**，等等。)。</span><span class="sxs-lookup"><span data-stu-id="381b8-158">The filename comprises of only special characters (**~**, **!**, **@**, etc.).</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="381b8-159">解决方法</span><span class="sxs-lookup"><span data-stu-id="381b8-159">Resolution</span></span>  
 <span data-ttu-id="381b8-160">若要解决此问题，可以执行任何以下解决方法：</span><span class="sxs-lookup"><span data-stu-id="381b8-160">To resolve this issue, you can follow any of these workarounds:</span></span>  
  
-   <span data-ttu-id="381b8-161">重命名文件。</span><span class="sxs-lookup"><span data-stu-id="381b8-161">Rename the files.</span></span> <span data-ttu-id="381b8-162">确保 BizTalk 项目中所有项目的文件名都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="381b8-162">Ensure the filenames for all artifacts in the BizTalk project are unique.</span></span>  
  
-   <span data-ttu-id="381b8-163">确保 BizTalk 项目中所有项目的类型名称都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="381b8-163">Ensure Type Name for all artifacts in the BizTalk project are unique.</span></span>  
  
## <a name="building-any-c-workflow-project-with-biztalk-mapper-shows-a-warning-regarding-version-conflict-for-envdtedll"></a><span data-ttu-id="381b8-164">构建任何具有 BizTalk 映射器的 C# 工作流项目都会显示一个有关 EnvDTE.dll 的版本冲突的警告</span><span class="sxs-lookup"><span data-stu-id="381b8-164">Building any C# workflow project with BizTalk Mapper shows a warning regarding version conflict for EnvDTE.dll</span></span>  
  
### <a name="problem"></a><span data-ttu-id="381b8-165">问题</span><span class="sxs-lookup"><span data-stu-id="381b8-165">Problem</span></span>  
 <span data-ttu-id="381b8-166">构建任何具有 BizTalk 映射器活动的 C# 工作流项目始终会显示以下有关 EnvDTE.dll 的版本冲突的警告。</span><span class="sxs-lookup"><span data-stu-id="381b8-166">Building any C# workflow project with BizTalk Mapper acitivity always shows the following warning about version conflict for EnvDTE.dll.</span></span>  
  
 <span data-ttu-id="381b8-167">没有办法解决“EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”和“EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”之间的冲突。</span><span class="sxs-lookup"><span data-stu-id="381b8-167">No way to resolve conflict between "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" and "EnvDTE, Version=7.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a".</span></span> <span data-ttu-id="381b8-168">任意选择“EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a”。</span><span class="sxs-lookup"><span data-stu-id="381b8-168">Choosing "EnvDTE, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" arbitrarily.</span></span>  <span data-ttu-id="381b8-169">请考虑 app.config 重新映射的程序集"EnvDTE，Culture = neutral，PublicKeyToken = b03f5f7f11d50a3a"版本"7.0.3300.0"[] 到版本"8.0.0.0"[C:\Program Files (x86) \Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll]若要解决冲突并消除警告。</span><span class="sxs-lookup"><span data-stu-id="381b8-169">Consider app.config remapping of assembly "EnvDTE, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" from Version "7.0.3300.0" [] to Version "8.0.0.0" [C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\PublicAssemblies\EnvDTE.dll] to solve conflict and get rid of warning.</span></span> <span data-ttu-id="381b8-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9)： 警告 MSB3247： 同一依赖程序集的不同版本之间出现冲突。</span><span class="sxs-lookup"><span data-stu-id="381b8-170">C:\Windows\Microsoft.NET\Framework\v4.0.30319\Microsoft.Common.targets(1360,9): warning MSB3247: Found conflicts between different versions of the same dependent assembly.</span></span>  
  
 <span data-ttu-id="381b8-171">WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span><span class="sxs-lookup"><span data-stu-id="381b8-171">WorkflowConsoleApplication3 -> C:\Users\btslabs\Desktop\WorkflowConsoleApplication3\bin\Debug\WorkflowConsoleApplication3.exe</span></span>  
  
### <a name="cause"></a><span data-ttu-id="381b8-172">原因</span><span class="sxs-lookup"><span data-stu-id="381b8-172">Cause</span></span>  
 <span data-ttu-id="381b8-173">之所以会发生这种情况是因为映射器活动所引用的 Microsoft.BizTalk.Mapper.OM.dll。</span><span class="sxs-lookup"><span data-stu-id="381b8-173">This happens because of the Microsoft.BizTalk.Mapper.OM.dll which the Mapper activity references.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="381b8-174">解决方法</span><span class="sxs-lookup"><span data-stu-id="381b8-174">Resolution</span></span>  
 <span data-ttu-id="381b8-175">忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="381b8-175">Ignore the warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381b8-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="381b8-176">See Also</span></span>  
 [<span data-ttu-id="381b8-177">排除地图故障</span><span class="sxs-lookup"><span data-stu-id="381b8-177">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)