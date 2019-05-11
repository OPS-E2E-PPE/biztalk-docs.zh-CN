---
title: 任务列表中生成错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cc22550629d8ae66652e0afe1da61b1443dc580
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357780"
---
# <a name="build-errors-in-the-task-list"></a><span data-ttu-id="db1ef-102">任务列表中生成错误</span><span class="sxs-lookup"><span data-stu-id="db1ef-102">Build Errors in the Task List</span></span>
<span data-ttu-id="db1ef-103">在生成项目或解决方案时，结果将显示在输出窗口中，而各个错误和警告将显示任务列表中。</span><span class="sxs-lookup"><span data-stu-id="db1ef-103">When you build your project, or solution, the results will appear in the Output window, while individual errors and warnings will appear in the task list.</span></span>  
  
 <span data-ttu-id="db1ef-104">任务列表中会显示错误和警告。</span><span class="sxs-lookup"><span data-stu-id="db1ef-104">Errors and warnings appear in the task list.</span></span> <span data-ttu-id="db1ef-105">你可以双击错误，并且焦点将适用于未正确配置的对象。</span><span class="sxs-lookup"><span data-stu-id="db1ef-105">You can double-click the error, and the focus will be applied to the object that is not correctly configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db1ef-106">在生成时，编译器不会验证 Xpath。</span><span class="sxs-lookup"><span data-stu-id="db1ef-106">When you build, the compiler does not validate XPaths.</span></span> <span data-ttu-id="db1ef-107">请务必使用有效的 XPath 语法。</span><span class="sxs-lookup"><span data-stu-id="db1ef-107">Take care to use valid XPath syntax.</span></span>  
  
## <a name="insufficient-configuration-action"></a><span data-ttu-id="db1ef-108">缺少配置的操作</span><span class="sxs-lookup"><span data-stu-id="db1ef-108">Insufficient configuration Action</span></span>  
 <span data-ttu-id="db1ef-109">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span><span class="sxs-lookup"><span data-stu-id="db1ef-109">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="db1ef-110">尽管业务流程设计器将提供可以在其中配置不完全警告，则您的业务流程能够正确编译中没有此类警告无法保证。</span><span class="sxs-lookup"><span data-stu-id="db1ef-110">While Orchestration Designer will provide insufficient configuration warnings where it can, there is no guarantee that your orchestration will compile correctly in the absence of such warnings.</span></span>  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a><span data-ttu-id="db1ef-111">编译器询问是否缺少程序集引用</span><span class="sxs-lookup"><span data-stu-id="db1ef-111">Compiler asks if you are missing an assembly reference</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-112">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-112">Problem</span></span>  
 <span data-ttu-id="db1ef-113">在编译您的业务流程时你收到错误消息的末尾询问"缺少程序集引用？"</span><span class="sxs-lookup"><span data-stu-id="db1ef-113">When you compile your orchestration you get an error message that ends with the question "are you missing an assembly reference?"</span></span> <span data-ttu-id="db1ef-114">两个更常见的消息是：</span><span class="sxs-lookup"><span data-stu-id="db1ef-114">Two of the more common messages are:</span></span>  
  
-   <span data-ttu-id="db1ef-115">命名空间 Y 中不存在类型或命名空间名称 X （是否缺少程序集引用？）</span><span class="sxs-lookup"><span data-stu-id="db1ef-115">The type or namespace name 'X' does not exist in the namespace 'Y' (are you missing an assembly reference?)</span></span>  
  
-   <span data-ttu-id="db1ef-116">Y; 中不存在标识符 X是否缺少程序集引用？</span><span class="sxs-lookup"><span data-stu-id="db1ef-116">Identifier 'X' does not exist in 'Y'; are you missing an assembly reference?</span></span>  
  
### <a name="cause"></a><span data-ttu-id="db1ef-117">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-117">Cause</span></span>  
 <span data-ttu-id="db1ef-118">以下任何可能导致此错误的原因。</span><span class="sxs-lookup"><span data-stu-id="db1ef-118">Any of the following could be the cause of this error.</span></span>  
  
-   <span data-ttu-id="db1ef-119">你的项目不会引用一个或多个所需的程序集。</span><span class="sxs-lookup"><span data-stu-id="db1ef-119">Your project does not reference one or more required assemblies.</span></span>  
  
-   <span data-ttu-id="db1ef-120">你的项目已映射或其他对象类型具有与项目相同的名称。</span><span class="sxs-lookup"><span data-stu-id="db1ef-120">Your project has a map or other object type that has the same name as the project.</span></span>  
  
-   <span data-ttu-id="db1ef-121">你的项目使用 XML 架构定义语言 (XSD) 的基础合作伙伴接口流程 (PIP) 架构，并包含名为系统的子文件夹中的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="db1ef-121">Your project uses XML Schema definition language (XSD)-based Partner Interface Process (PIP) schemas and contains XSD schemas in a subfolder that is named System.</span></span>  
  
-   <span data-ttu-id="db1ef-122">你的项目使用的命名空间为当前项目的命名空间子集的全局属性。</span><span class="sxs-lookup"><span data-stu-id="db1ef-122">Your project is using a Global Property whose namespace is a subset of the current project's namespace.</span></span> <span data-ttu-id="db1ef-123">例如，使用在项目"Accounts.FILE"包含的业务流程中的全局属性命名空间"File.ReceivedFileName"。</span><span class="sxs-lookup"><span data-stu-id="db1ef-123">For example, using the Global Property namespace "File.ReceivedFileName" in an orchestration contained in the project "Accounts.FILE".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-124">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-124">Resolution</span></span>  
 <span data-ttu-id="db1ef-125">根据问题的原因，解决方法可能是以下任一项：</span><span class="sxs-lookup"><span data-stu-id="db1ef-125">Depending upon the cause of the problem, the resolution could be any of the following:</span></span>  
  
-   <span data-ttu-id="db1ef-126">添加对缺失的引用你的项目需要的程序集。</span><span class="sxs-lookup"><span data-stu-id="db1ef-126">Add a reference to the missing assemblies your project requires.</span></span>  
  
-   <span data-ttu-id="db1ef-127">将代码图或其他对象的名称更改为项目名称以外的内容。</span><span class="sxs-lookup"><span data-stu-id="db1ef-127">Change the name of the map or other object to something other than the project name.</span></span> <span data-ttu-id="db1ef-128">这通常可以通过对象的属性页 （例如，映射属性页包含一个 Name 属性）。</span><span class="sxs-lookup"><span data-stu-id="db1ef-128">This can typically be done through the object's property page (for example, the Map property page contains a Name property).</span></span>  
  
-   <span data-ttu-id="db1ef-129">更改 Visual Studio 中的架构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="db1ef-129">Change the namespace for the schemas in Visual Studio.</span></span> <span data-ttu-id="db1ef-130">若要执行此操作使用 Visual Studio，请单击**显示所有文件**上**项目**菜单中，然后展开**系统**在解决方案资源管理器中的节点。</span><span class="sxs-lookup"><span data-stu-id="db1ef-130">To do this using Visual Studio, click **Show All Files** on the **Project** menu, and then expand the **System** node in Solution Explorer.</span></span> <span data-ttu-id="db1ef-131">单击每个文件系统文件夹及其任何子文件夹，然后更改属性窗口中的命名空间条目，以使所有匹配项**系统**变为 _**系统**。</span><span class="sxs-lookup"><span data-stu-id="db1ef-131">Click each file in the System folder and in any subfolders, and then change the namespace entry in the Properties window so that any occurrence of **System** becomes _**System**.</span></span> <span data-ttu-id="db1ef-132">例如，更改**MyProject.System.SubFolder**命名空间**MyProject._System.Subfolder**命名空间。</span><span class="sxs-lookup"><span data-stu-id="db1ef-132">For example, change the **MyProject.System.SubFolder** namespace to **the MyProject._System.Subfolder** namespace.</span></span> <span data-ttu-id="db1ef-133">详细了解此问题，请参阅知识库文章[916649](http://support.microsoft.com/?kbid=916649)。</span><span class="sxs-lookup"><span data-stu-id="db1ef-133">For more information about this issue, see KB article [916649](http://support.microsoft.com/?kbid=916649).</span></span>  
  
-   <span data-ttu-id="db1ef-134">从项目中删除冲突的全局属性命名空间。</span><span class="sxs-lookup"><span data-stu-id="db1ef-134">Remove the conflicting Global Property namespace from the project.</span></span>  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a><span data-ttu-id="db1ef-135">生成项目时，收到"未初始化消息构造语句中"错误</span><span class="sxs-lookup"><span data-stu-id="db1ef-135">You receive a "Message has not been initialized in construct statement" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-136">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-136">Problem</span></span>  
 <span data-ttu-id="db1ef-137">当编译 BizTalk 应用程序时，则会收到错误"消息尚未初始化 construct 语句中"。</span><span class="sxs-lookup"><span data-stu-id="db1ef-137">When you compile your BizTalk application, you get the error "Message has not been initialized in construct statement".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="db1ef-138">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-138">Cause</span></span>  
 <span data-ttu-id="db1ef-139">在构造一条消息时，你指定所有消息变量。</span><span class="sxs-lookup"><span data-stu-id="db1ef-139">When you construct a message, you specify all the message variables.</span></span> <span data-ttu-id="db1ef-140">然后对该消息或其各个部分进行赋值。</span><span class="sxs-lookup"><span data-stu-id="db1ef-140">Then you make assignments to the message or its parts.</span></span> <span data-ttu-id="db1ef-141">如果特定消息赋值的一部分包含在单独**构造消息**形状，可能会收到初始化错误消息。</span><span class="sxs-lookup"><span data-stu-id="db1ef-141">If part of a specific message assignment is included in a separate **Construct Message** shape, you may receive the initialization error message.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-142">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-142">Resolution</span></span>  
 <span data-ttu-id="db1ef-143">若要解决此问题，请确保在同一个包括特定的消息分配的所有部分**构造消息**形状。</span><span class="sxs-lookup"><span data-stu-id="db1ef-143">To resolve this behavior, make sure that you include all parts of a specific message assignment in the same **Construct Message** shape.</span></span> <span data-ttu-id="db1ef-144">对于相关的支持问题，请参阅知识库文章[870606](http://support.microsoft.com/?kbid=870606)。</span><span class="sxs-lookup"><span data-stu-id="db1ef-144">For a related support issue, see KB article [870606](http://support.microsoft.com/?kbid=870606).</span></span>  
  
 <span data-ttu-id="db1ef-145">您也可以通过创建您的消息中解决此行为**构造**然后才能使用它在中的一个实例的形状**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="db1ef-145">You can also resolve this behavior by creating your message in a **Construct** shape before using an instance of it in an **Expression** shape.</span></span> <span data-ttu-id="db1ef-146">例如，下面的代码将导致出错，如果按放置**表达式**形状：</span><span class="sxs-lookup"><span data-stu-id="db1ef-146">For example, the following code will cause an error if placed in an **Expression** shape:</span></span>  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 <span data-ttu-id="db1ef-147">若要解决问题，请创建在 XMLDOM 的实例**构造**形状，然后再进行分配在下游**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="db1ef-147">To fix, create the instance of XMLDOM in a **Construct** shape, and then do the assignment in a downstream **Expression** shape.</span></span>  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a><span data-ttu-id="db1ef-148">生成项目时，收到了"使用未构造的消息"错误</span><span class="sxs-lookup"><span data-stu-id="db1ef-148">You receive a "use of unconstructed message" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-149">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-149">Problem</span></span>  
 <span data-ttu-id="db1ef-150">在编译 BizTalk 项目时，收到错误"使用未构造的消息\<消息\>'"。</span><span class="sxs-lookup"><span data-stu-id="db1ef-150">When you compile your BizTalk project, you receive the error "use of unconstructed message '\<message\>'".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="db1ef-151">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-151">Cause</span></span>  
 <span data-ttu-id="db1ef-152">在中使用未构造的消息时出现此错误**发送**形状。</span><span class="sxs-lookup"><span data-stu-id="db1ef-152">This error occurs when an unconstructed message is used in a **Send** shape.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-153">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-153">Resolution</span></span>  
 <span data-ttu-id="db1ef-154">若要解决此问题，请添加**构造消息**向业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="db1ef-154">To resolve this issue, add a **Construct Message** shape to the orchestration.</span></span> <span data-ttu-id="db1ef-155">包括**构造消息**前**发送**形状绑定到 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="db1ef-155">Include the **Construct Message** shape before the **Send** shape that is bound to the Web service.</span></span>  
  
 <span data-ttu-id="db1ef-156">有关详细信息，有关此错误和 Web 服务，请参阅知识库文章[921043](http://support.microsoft.com/?kbid=921043)。</span><span class="sxs-lookup"><span data-stu-id="db1ef-156">For more information about this error and Web services, see KB article [921043](http://support.microsoft.com/?kbid=921043).</span></span>  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a><span data-ttu-id="db1ef-157">在错误中设置结果范围的事务级别</span><span class="sxs-lookup"><span data-stu-id="db1ef-157">Setting a transaction level for a scope results in an error</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-158">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-158">Problem</span></span>  
 <span data-ttu-id="db1ef-159">配置事务的作用域键入或其他业务流程中支持事务的实体，您会收到错误后是"非事务性业务流程不能包含任何其他事务"。</span><span class="sxs-lookup"><span data-stu-id="db1ef-159">After configuring the transaction type for a scope or other entity supporting transactions in an orchestration, you receive the error "A Non-transactional Orchestration cannot contain any other Transactions".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="db1ef-160">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-160">Cause</span></span>  
 <span data-ttu-id="db1ef-161">此错误时发生 when you try to 配置作用域 （或其他实体） 的事务类型为"原子"或"长期"业务流程中业务流程本身具有事务类型为"None"。</span><span class="sxs-lookup"><span data-stu-id="db1ef-161">This error occurs when you try to configure the transaction type of a scope (or other entity) in an orchestration to "Atomic" or "Long-Running" when the orchestration itself has a transaction type of "None".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-162">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-162">Resolution</span></span>  
 <span data-ttu-id="db1ef-163">确保您的业务流程和构成对象的事务类型设置兼容。</span><span class="sxs-lookup"><span data-stu-id="db1ef-163">Ensure that the transaction type settings of your orchestration and constituent objects are compatible.</span></span>  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a><span data-ttu-id="db1ef-164">项目生成导致错误"必须指定至少一个已初始化的相关集的非激活接收非自相关端口上"</span><span class="sxs-lookup"><span data-stu-id="db1ef-164">Project build results in the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-165">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-165">Problem</span></span>  
 <span data-ttu-id="db1ef-166">在编译 BizTalk 项目时，你收到错误"必须指定至少一个已初始化的相关集的非激活接收非自相关端口上"。</span><span class="sxs-lookup"><span data-stu-id="db1ef-166">When you compile your BizTalk project, you receive the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="db1ef-167">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-167">Cause</span></span>  
 <span data-ttu-id="db1ef-168">如果您的业务流程没有激活，会出现此错误**接收**形状 (Activate = true) 或者没有激活**接收**形状并且不由另一个业务流程直接调用。</span><span class="sxs-lookup"><span data-stu-id="db1ef-168">This error can occur if your orchestration has no activating **Receive** shapes (Activate = true) or has no activating **Receive** shapes and is not called directly by another orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-169">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-169">Resolution</span></span>  
 <span data-ttu-id="db1ef-170">如果您的业务流程不由另一个业务流程调用的则必须配置之一**接收**已激活的接收形状。</span><span class="sxs-lookup"><span data-stu-id="db1ef-170">If your orchestration is not called by another orchestration, you must configure one of the **Receive** shapes to be an activated receive.</span></span> <span data-ttu-id="db1ef-171">有关配置详细信息**接收**形状，其中包括指向相关的更多信息，请参阅[如何配置接收形状](../core/how-to-configure-the-receive-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="db1ef-171">For more information about configuring the **Receive** shape, including links to correlation, see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a><span data-ttu-id="db1ef-172">收到错误"程序集生成失败--引用的程序集 '\<程序集\>不具有强名称"生成解决方案时</span><span class="sxs-lookup"><span data-stu-id="db1ef-172">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly\>' does not have a strong name" when building your solution</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-173">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-173">Problem</span></span>  
 <span data-ttu-id="db1ef-174">收到错误"程序集生成失败--引用的程序集 '\<程序集\>不具有强名称"时，生成你的解决方案包含一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="db1ef-174">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly\>' does not have a strong name" when building your solution that has an orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="db1ef-175">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-175">Cause</span></span>  
 <span data-ttu-id="db1ef-176">当业务流程中使用从无符号的引用程序集的类型时，将发生此问题。</span><span class="sxs-lookup"><span data-stu-id="db1ef-176">This problem occurs when a type from an unsigned referenced assembly is used within an orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-177">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-177">Resolution</span></span>  
 <span data-ttu-id="db1ef-178">适用于引用的程序集的强名称。</span><span class="sxs-lookup"><span data-stu-id="db1ef-178">Apply a strong name to the referenced assembly.</span></span> <span data-ttu-id="db1ef-179">如果它是可以重新编译的自定义程序集，使用强名称工具创建.snk （密钥） 文件，然后引用程序集属性中的项目的该密钥文件。</span><span class="sxs-lookup"><span data-stu-id="db1ef-179">If it is a custom assembly that you can recompile, use the strong name tool to create an .snk (key) file and then reference that key file in the assembly properties for the project.</span></span> <span data-ttu-id="db1ef-180">有关强命名程序集的详细信息，请参阅[如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)。</span><span class="sxs-lookup"><span data-stu-id="db1ef-180">For more information about strong naming an assembly, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a><span data-ttu-id="db1ef-181">错误"无法添加资源。</span><span class="sxs-lookup"><span data-stu-id="db1ef-181">The error "Failed to add resource(s).</span></span> <span data-ttu-id="db1ef-182">更改对某些资源失败的请求"时发生部署业务流程</span><span class="sxs-lookup"><span data-stu-id="db1ef-182">Change requests failed for some resources" occurs when deploying an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-183">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-183">Problem</span></span>  
 <span data-ttu-id="db1ef-184">在部署业务流程时，将显示类似于以下的错误，业务流程的部署失败：</span><span class="sxs-lookup"><span data-stu-id="db1ef-184">When deploying an orchestration, an error similar to the following is displayed and deployment of the orchestration fails:</span></span>  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a><span data-ttu-id="db1ef-185">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-185">Cause</span></span>  
 <span data-ttu-id="db1ef-186">如果该业务流程包含使用的所有对象可能发生此错误C#关键字。</span><span class="sxs-lookup"><span data-stu-id="db1ef-186">This error can occur if the orchestration contains any objects that use C# keywords.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-187">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-187">Resolution</span></span>  
 <span data-ttu-id="db1ef-188">删除任何C#关键字从业务流程。</span><span class="sxs-lookup"><span data-stu-id="db1ef-188">Remove any C# keywords from the orchestration.</span></span> <span data-ttu-id="db1ef-189">有关列表的C#关键字，请参见[ http://go.microsoft.com/fwlink/?LinkId=74346 ](http://go.microsoft.com/fwlink/?LinkId=74346)。</span><span class="sxs-lookup"><span data-stu-id="db1ef-189">For a list of C# keywords, see [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span></span>  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a><span data-ttu-id="db1ef-190">编译您的业务流程时收到"无效的属性值"错误</span><span class="sxs-lookup"><span data-stu-id="db1ef-190">You receive an "invalid property value" error when compiling your orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="db1ef-191">问题</span><span class="sxs-lookup"><span data-stu-id="db1ef-191">Problem</span></span>  
 <span data-ttu-id="db1ef-192">出现错误对话框"无效的属性值"构建您的业务流程时。</span><span class="sxs-lookup"><span data-stu-id="db1ef-192">You receive the error dialog "Invalid property value" when building your orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="db1ef-193">原因</span><span class="sxs-lookup"><span data-stu-id="db1ef-193">Cause</span></span>  
 <span data-ttu-id="db1ef-194">一个或多个解决方案中的对象具有相同名称与另一个对象。</span><span class="sxs-lookup"><span data-stu-id="db1ef-194">One or more of the objects in your solution has the same name as another object.</span></span> <span data-ttu-id="db1ef-195">例如，消息名称是与端口名称相同。</span><span class="sxs-lookup"><span data-stu-id="db1ef-195">For example, a message name is the same as a port name.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="db1ef-196">解决方法</span><span class="sxs-lookup"><span data-stu-id="db1ef-196">Resolution</span></span>  
 <span data-ttu-id="db1ef-197">请确保你的解决方案中的每个对象具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="db1ef-197">Ensure that every object in your solution has a unique name.</span></span> <span data-ttu-id="db1ef-198">可以通过遵守命名约定此错误的风险降至最低。</span><span class="sxs-lookup"><span data-stu-id="db1ef-198">You can minimize the risk of this error by adhering to a naming convention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1ef-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="db1ef-199">See Also</span></span>  
 [<span data-ttu-id="db1ef-200">如何生成业务流程</span><span class="sxs-lookup"><span data-stu-id="db1ef-200">How to Build Orchestrations</span></span>](../core/how-to-build-orchestrations.md)