---
title: "生成任务列表中的错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bfd5b9f7b974b00d63831484ecbaa44e2568fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="build-errors-in-the-task-list"></a><span data-ttu-id="023db-102">生成任务列表中的错误</span><span class="sxs-lookup"><span data-stu-id="023db-102">Build Errors in the Task List</span></span>
<span data-ttu-id="023db-103">在生成项目或解决方案时，其结果将显示在“输出”窗口中，而各个错误和警告将显示在任务列表中。</span><span class="sxs-lookup"><span data-stu-id="023db-103">When you build your project, or solution, the results will appear in the Output window, while individual errors and warnings will appear in the task list.</span></span>  
  
 <span data-ttu-id="023db-104">错误和警告将显示在任务列表中。</span><span class="sxs-lookup"><span data-stu-id="023db-104">Errors and warnings appear in the task list.</span></span> <span data-ttu-id="023db-105">你可以双击错误，焦点将指向未正确配置的对象。</span><span class="sxs-lookup"><span data-stu-id="023db-105">You can double-click the error, and the focus will be applied to the object that is not correctly configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="023db-106">在生成过程中，编译器将不会验证 XPath。</span><span class="sxs-lookup"><span data-stu-id="023db-106">When you build, the compiler does not validate XPaths.</span></span> <span data-ttu-id="023db-107">所以，请谨慎使用有效的 XPath 语法。</span><span class="sxs-lookup"><span data-stu-id="023db-107">Take care to use valid XPath syntax.</span></span>  
  
## <a name="insufficient-configuration-action"></a><span data-ttu-id="023db-108">不完全的配置操作</span><span class="sxs-lookup"><span data-stu-id="023db-108">Insufficient configuration Action</span></span>  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  <span data-ttu-id="023db-109">尽管业务流程设计器将在发生配置不完全时提供配置不完全警告，但这并不能确保没有此类警告业务流程的编译就是正确的。</span><span class="sxs-lookup"><span data-stu-id="023db-109">While Orchestration Designer will provide insufficient configuration warnings where it can, there is no guarantee that your orchestration will compile correctly in the absence of such warnings.</span></span>  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a><span data-ttu-id="023db-110">编译器询问是否缺少程序集引用</span><span class="sxs-lookup"><span data-stu-id="023db-110">Compiler asks if you are missing an assembly reference</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-111">问题</span><span class="sxs-lookup"><span data-stu-id="023db-111">Problem</span></span>  
 <span data-ttu-id="023db-112">在编译业务流程时，你收到一条错误消息，该错误消息的末尾询问“是否缺少程序集引用?”</span><span class="sxs-lookup"><span data-stu-id="023db-112">When you compile your orchestration you get an error message that ends with the question "are you missing an assembly reference?"</span></span> <span data-ttu-id="023db-113">最常见的两条消息是：</span><span class="sxs-lookup"><span data-stu-id="023db-113">Two of the more common messages are:</span></span>  
  
-   <span data-ttu-id="023db-114">命名空间“Y”中不存在类型或命名空间名称“X”(是否缺少程序集引用?)</span><span class="sxs-lookup"><span data-stu-id="023db-114">The type or namespace name 'X' does not exist in the namespace 'Y' (are you missing an assembly reference?)</span></span>  
  
-   <span data-ttu-id="023db-115">标识符“X”在“Y”中不存在；是否缺少程序集引用?</span><span class="sxs-lookup"><span data-stu-id="023db-115">Identifier 'X' does not exist in 'Y'; are you missing an assembly reference?</span></span>  
  
### <a name="cause"></a><span data-ttu-id="023db-116">原因</span><span class="sxs-lookup"><span data-stu-id="023db-116">Cause</span></span>  
 <span data-ttu-id="023db-117">下面任何一项都可能是导致此错误的原因。</span><span class="sxs-lookup"><span data-stu-id="023db-117">Any of the following could be the cause of this error.</span></span>  
  
-   <span data-ttu-id="023db-118">你的项目不能引用一个或多个所需程序集。</span><span class="sxs-lookup"><span data-stu-id="023db-118">Your project does not reference one or more required assemblies.</span></span>  
  
-   <span data-ttu-id="023db-119">你的项目具有与项目同名的映射或其他对象类型。</span><span class="sxs-lookup"><span data-stu-id="023db-119">Your project has a map or other object type that has the same name as the project.</span></span>  
  
-   <span data-ttu-id="023db-120">你的项目使用基于 XML 架构定义语言 (XSD) 的合作伙伴接口流程 (PIP) 架构并在名为“System”的子文件夹中包含 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="023db-120">Your project uses XML Schema definition language (XSD)-based Partner Interface Process (PIP) schemas and contains XSD schemas in a subfolder that is named System.</span></span>  
  
-   <span data-ttu-id="023db-121">你的项目使用命名空间为当前项目命名空间子集的全局属性。</span><span class="sxs-lookup"><span data-stu-id="023db-121">Your project is using a Global Property whose namespace is a subset of the current project's namespace.</span></span> <span data-ttu-id="023db-122">例如，在项目“Accounts.FILE”包含的业务流程中使用全局属性命名空间“File.ReceivedFileName”。</span><span class="sxs-lookup"><span data-stu-id="023db-122">For example, using the Global Property namespace "File.ReceivedFileName" in an orchestration contained in the project "Accounts.FILE".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-123">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-123">Resolution</span></span>  
 <span data-ttu-id="023db-124">根据导致问题的原因，解决方法可为以下某一种：</span><span class="sxs-lookup"><span data-stu-id="023db-124">Depending upon the cause of the problem, the resolution could be any of the following:</span></span>  
  
-   <span data-ttu-id="023db-125">添加指向你的项目需要但缺少了的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="023db-125">Add a reference to the missing assemblies your project requires.</span></span>  
  
-   <span data-ttu-id="023db-126">将映射或其他对象的名称更改为项目名称以外的其他名称。</span><span class="sxs-lookup"><span data-stu-id="023db-126">Change the name of the map or other object to something other than the project name.</span></span> <span data-ttu-id="023db-127">通常，这可通过对象的属性页完成（例如，“映射属性”页包含“名称”属性）。</span><span class="sxs-lookup"><span data-stu-id="023db-127">This can typically be done through the object's property page (for example, the Map property page contains a Name property).</span></span>  
  
-   <span data-ttu-id="023db-128">更改 Visual Studio 中架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="023db-128">Change the namespace for the schemas in Visual Studio.</span></span> <span data-ttu-id="023db-129">若要执行此操作使用 Visual Studio，请单击**显示所有文件**上**项目**菜单，然后展开**系统**在解决方案资源管理器中的节点。</span><span class="sxs-lookup"><span data-stu-id="023db-129">To do this using Visual Studio, click **Show All Files** on the **Project** menu, and then expand the **System** node in Solution Explorer.</span></span> <span data-ttu-id="023db-130">单击每个文件中的系统文件夹和所有子文件夹中，然后更改属性窗口中的命名空间条目这样的任何匹配项**系统**变得 _**系统**。</span><span class="sxs-lookup"><span data-stu-id="023db-130">Click each file in the System folder and in any subfolders, and then change the namespace entry in the Properties window so that any occurrence of **System** becomes _**System**.</span></span> <span data-ttu-id="023db-131">例如，更改**MyProject.System.SubFolder**的命名空间**MyProject._System.Subfolder**命名空间。</span><span class="sxs-lookup"><span data-stu-id="023db-131">For example, change the **MyProject.System.SubFolder** namespace to **the MyProject._System.Subfolder** namespace.</span></span> <span data-ttu-id="023db-132">有关此问题，请参阅知识库文章[916649](http://support.microsoft.com/?kbid=916649)。</span><span class="sxs-lookup"><span data-stu-id="023db-132">For more information about this issue, see KB article [916649](http://support.microsoft.com/?kbid=916649).</span></span>  
  
-   <span data-ttu-id="023db-133">从项目中删除相冲突的全局属性命名空间。</span><span class="sxs-lookup"><span data-stu-id="023db-133">Remove the conflicting Global Property namespace from the project.</span></span>  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a><span data-ttu-id="023db-134">在生成项目时，收到错误“construct 语句中未初始化消息”</span><span class="sxs-lookup"><span data-stu-id="023db-134">You receive a "Message has not been initialized in construct statement" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-135">问题</span><span class="sxs-lookup"><span data-stu-id="023db-135">Problem</span></span>  
 <span data-ttu-id="023db-136">在编译 BizTalk 应用程序时，收到错误“construct 语句中未初始化消息”。</span><span class="sxs-lookup"><span data-stu-id="023db-136">When you compile your BizTalk application, you get the error "Message has not been initialized in construct statement".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="023db-137">原因</span><span class="sxs-lookup"><span data-stu-id="023db-137">Cause</span></span>  
 <span data-ttu-id="023db-138">在构造消息时，应指定所有消息变量。</span><span class="sxs-lookup"><span data-stu-id="023db-138">When you construct a message, you specify all the message variables.</span></span> <span data-ttu-id="023db-139">然后对消息或其成分进行赋值。</span><span class="sxs-lookup"><span data-stu-id="023db-139">Then you make assignments to the message or its parts.</span></span> <span data-ttu-id="023db-140">如果在单独的包含的特定消息分配一部分**构造消息**形状，你可能会收到初始化错误消息。</span><span class="sxs-lookup"><span data-stu-id="023db-140">If part of a specific message assignment is included in a separate **Construct Message** shape, you may receive the initialization error message.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-141">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-141">Resolution</span></span>  
 <span data-ttu-id="023db-142">若要解决此问题，请确保在同一个包括特定消息分配的所有部分**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="023db-142">To resolve this behavior, make sure that you include all parts of a specific message assignment in the same **Construct Message** shape.</span></span> <span data-ttu-id="023db-143">对于相关的支持问题，请参阅知识库文章[870606](http://support.microsoft.com/?kbid=870606)。</span><span class="sxs-lookup"><span data-stu-id="023db-143">For a related support issue, see KB article [870606](http://support.microsoft.com/?kbid=870606).</span></span>  
  
 <span data-ttu-id="023db-144">您也可以通过创建你的消息中解决此行为**构造**在使用中它的实例之前的形状**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="023db-144">You can also resolve this behavior by creating your message in a **Construct** shape before using an instance of it in an **Expression** shape.</span></span> <span data-ttu-id="023db-145">例如，下面的代码会导致错误，如果置于**表达式**形状：</span><span class="sxs-lookup"><span data-stu-id="023db-145">For example, the following code will cause an error if placed in an **Expression** shape:</span></span>  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 <span data-ttu-id="023db-146">若要解决问题，请创建 XMLDOM 中实例**构造**形状，，然后执行中下游的分配**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="023db-146">To fix, create the instance of XMLDOM in a **Construct** shape, and then do the assignment in a downstream **Expression** shape.</span></span>  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a><span data-ttu-id="023db-147">在生成项目时，收到错误“使用未构造的消息”</span><span class="sxs-lookup"><span data-stu-id="023db-147">You receive a "use of unconstructed message" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-148">问题</span><span class="sxs-lookup"><span data-stu-id="023db-148">Problem</span></span>  
 <span data-ttu-id="023db-149">编译你的 BizTalk 项目时，你将收到错误"使用未构造的消息\<消息 >'"。</span><span class="sxs-lookup"><span data-stu-id="023db-149">When you compile your BizTalk project, you receive the error "use of unconstructed message '\<message>'".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="023db-150">原因</span><span class="sxs-lookup"><span data-stu-id="023db-150">Cause</span></span>  
 <span data-ttu-id="023db-151">在使用非的消息时发生此错误**发送**形状。</span><span class="sxs-lookup"><span data-stu-id="023db-151">This error occurs when an unconstructed message is used in a **Send** shape.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-152">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-152">Resolution</span></span>  
 <span data-ttu-id="023db-153">若要解决此问题，将添加**构造消息**形状上的与业务流程。</span><span class="sxs-lookup"><span data-stu-id="023db-153">To resolve this issue, add a **Construct Message** shape to the orchestration.</span></span> <span data-ttu-id="023db-154">包括**构造消息**之前调整**发送**已绑定到 Web 服务的形状。</span><span class="sxs-lookup"><span data-stu-id="023db-154">Include the **Construct Message** shape before the **Send** shape that is bound to the Web service.</span></span>  
  
 <span data-ttu-id="023db-155">有关详细信息，有关此错误和 Web 服务，请参阅知识库文章[921043](http://support.microsoft.com/?kbid=921043)。</span><span class="sxs-lookup"><span data-stu-id="023db-155">For more information about this error and Web services, see KB article [921043](http://support.microsoft.com/?kbid=921043).</span></span>  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a><span data-ttu-id="023db-156">设置作用域的事务级别将导致错误</span><span class="sxs-lookup"><span data-stu-id="023db-156">Setting a transaction level for a scope results in an error</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-157">问题</span><span class="sxs-lookup"><span data-stu-id="023db-157">Problem</span></span>  
 <span data-ttu-id="023db-158">在业务流程中配置作用域或支持事务的其他实体的事务类型时，收到错误“非事务性业务流程不能包含任何其他事务”。</span><span class="sxs-lookup"><span data-stu-id="023db-158">After configuring the transaction type for a scope or other entity supporting transactions in an orchestration, you receive the error "A Non-transactional Orchestration cannot contain any other Transactions".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="023db-159">原因</span><span class="sxs-lookup"><span data-stu-id="023db-159">Cause</span></span>  
 <span data-ttu-id="023db-160">当尝试在业务流程中将作用域（或其他实体）的事务类型配置为“原子”或“长期”，而业务流程本身的业务类型为“无”时，将出现此错误。</span><span class="sxs-lookup"><span data-stu-id="023db-160">This error occurs when you try to configure the transaction type of a scope (or other entity) in an orchestration to "Atomic" or "Long-Running" when the orchestration itself has a transaction type of "None".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-161">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-161">Resolution</span></span>  
 <span data-ttu-id="023db-162">确保业务流程和构成对象的事务类型设置相兼容。</span><span class="sxs-lookup"><span data-stu-id="023db-162">Ensure that the transaction type settings of your orchestration and constituent objects are compatible.</span></span>  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a><span data-ttu-id="023db-163">项目生成导致错误“必须为非自相关端口上的非激活接收指定至少一个已初始化的相关集”</span><span class="sxs-lookup"><span data-stu-id="023db-163">Project build results in the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-164">问题</span><span class="sxs-lookup"><span data-stu-id="023db-164">Problem</span></span>  
 <span data-ttu-id="023db-165">在编译 BizTalk 项目时，收到错误“必须为非自相关端口上的非激活接收指定至少一个已初始化的相关集”。</span><span class="sxs-lookup"><span data-stu-id="023db-165">When you compile your BizTalk project, you receive the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="023db-166">原因</span><span class="sxs-lookup"><span data-stu-id="023db-166">Cause</span></span>  
 <span data-ttu-id="023db-167">如果您的业务流程具有没有激活，会出现此错误**接收**形状 (激活 = true) 或具有没有激活**接收**形状并不直接由另一个业务流程调用。</span><span class="sxs-lookup"><span data-stu-id="023db-167">This error can occur if your orchestration has no activating **Receive** shapes (Activate = true) or has no activating **Receive** shapes and is not called directly by another orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-168">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-168">Resolution</span></span>  
 <span data-ttu-id="023db-169">如果您的业务流程不由另一个业务流程调用，则必须配置之一**接收**形状要激活的接收。</span><span class="sxs-lookup"><span data-stu-id="023db-169">If your orchestration is not called by another orchestration, you must configure one of the **Receive** shapes to be an activated receive.</span></span> <span data-ttu-id="023db-170">有关配置的详细信息**接收**形状，包括指向相关，请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="023db-170">For more information about configuring the **Receive** shape, including links to correlation, see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a><span data-ttu-id="023db-171">你将收到错误"程序集生成失败--引用的程序集\<程序集 > 不具有强名称"生成解决方案时</span><span class="sxs-lookup"><span data-stu-id="023db-171">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly>' does not have a strong name" when building your solution</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-172">问题</span><span class="sxs-lookup"><span data-stu-id="023db-172">Problem</span></span>  
 <span data-ttu-id="023db-173">你将收到错误"程序集生成失败--引用的程序集\<程序集 > 不具有强名称"当生成你的解决方案具有一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="023db-173">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly>' does not have a strong name" when building your solution that has an orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="023db-174">原因</span><span class="sxs-lookup"><span data-stu-id="023db-174">Cause</span></span>  
 <span data-ttu-id="023db-175">当在业务流程中使用未签名的引用程序集中的类型时，将出现此问题。</span><span class="sxs-lookup"><span data-stu-id="023db-175">This problem occurs when a type from an unsigned referenced assembly is used within an orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-176">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-176">Resolution</span></span>  
 <span data-ttu-id="023db-177">对引用的程序集应用强名称。</span><span class="sxs-lookup"><span data-stu-id="023db-177">Apply a strong name to the referenced assembly.</span></span> <span data-ttu-id="023db-178">如果该程序集是可重新编译的自定义程序集，请使用强名称工具创建 .snk（密钥）文件，然后在项目的程序集属性中引用该密钥文件。</span><span class="sxs-lookup"><span data-stu-id="023db-178">If it is a custom assembly that you can recompile, use the strong name tool to create an .snk (key) file and then reference that key file in the assembly properties for the project.</span></span> <span data-ttu-id="023db-179">有关强命名程序集的详细信息，请参阅[如何配置一个强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。</span><span class="sxs-lookup"><span data-stu-id="023db-179">For more information about strong naming an assembly, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a><span data-ttu-id="023db-180">在部署业务流程时，出现错误“无法添加资源。</span><span class="sxs-lookup"><span data-stu-id="023db-180">The error "Failed to add resource(s).</span></span> <span data-ttu-id="023db-181">对某些资源的更改请求失败”</span><span class="sxs-lookup"><span data-stu-id="023db-181">Change requests failed for some resources" occurs when deploying an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-182">问题</span><span class="sxs-lookup"><span data-stu-id="023db-182">Problem</span></span>  
 <span data-ttu-id="023db-183">在部署业务流程时，出现类似下面的错误并且业务流程部署失败：</span><span class="sxs-lookup"><span data-stu-id="023db-183">When deploying an orchestration, an error similar to the following is displayed and deployment of the orchestration fails:</span></span>  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a><span data-ttu-id="023db-184">原因</span><span class="sxs-lookup"><span data-stu-id="023db-184">Cause</span></span>  
 <span data-ttu-id="023db-185">如果业务流程包含使用 C# 关键字的任何对象，则可能会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="023db-185">This error can occur if the orchestration contains any objects that use C# keywords.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-186">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-186">Resolution</span></span>  
 <span data-ttu-id="023db-187">删除业务流程中的任何 C# 关键字。</span><span class="sxs-lookup"><span data-stu-id="023db-187">Remove any C# keywords from the orchestration.</span></span> <span data-ttu-id="023db-188">C# 关键字的列表，请参阅[http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346)。</span><span class="sxs-lookup"><span data-stu-id="023db-188">For a list of C# keywords, see [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span></span>  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a><span data-ttu-id="023db-189">在编译业务流程时，收到错误“无效的属性值”</span><span class="sxs-lookup"><span data-stu-id="023db-189">You receive an "invalid property value" error when compiling your orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="023db-190">问题</span><span class="sxs-lookup"><span data-stu-id="023db-190">Problem</span></span>  
 <span data-ttu-id="023db-191">在生成业务流程时，出现错误对话框“无效的属性值”。</span><span class="sxs-lookup"><span data-stu-id="023db-191">You receive the error dialog "Invalid property value" when building your orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="023db-192">原因</span><span class="sxs-lookup"><span data-stu-id="023db-192">Cause</span></span>  
 <span data-ttu-id="023db-193">解决方案中的一个或多个对象与其他对象同名。</span><span class="sxs-lookup"><span data-stu-id="023db-193">One or more of the objects in your solution has the same name as another object.</span></span> <span data-ttu-id="023db-194">例如，消息名称与端口名称相同。</span><span class="sxs-lookup"><span data-stu-id="023db-194">For example, a message name is the same as a port name.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="023db-195">解决方法</span><span class="sxs-lookup"><span data-stu-id="023db-195">Resolution</span></span>  
 <span data-ttu-id="023db-196">确保解决方案中的每个对象具有唯一名称。</span><span class="sxs-lookup"><span data-stu-id="023db-196">Ensure that every object in your solution has a unique name.</span></span> <span data-ttu-id="023db-197">遵守命名约定可将发生此错误的风险降到最低。</span><span class="sxs-lookup"><span data-stu-id="023db-197">You can minimize the risk of this error by adhering to a naming convention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023db-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="023db-198">See Also</span></span>  
 [<span data-ttu-id="023db-199">如何构建业务流程</span><span class="sxs-lookup"><span data-stu-id="023db-199">How to Build Orchestrations</span></span>](../core/how-to-build-orchestrations.md)