---
title: 补偿 （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- compensations, examples
- examples, compensations
- compensations, orchestrations
ms.assetid: 9d10c7be-6a4c-44cc-bf29-78ecdf147bd1
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9752fced7e1b889c41b6e981be6c2858f0411b7b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975123"
---
# <a name="compensation-biztalk-server-sample"></a><span data-ttu-id="3c19c-102">补偿 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="3c19c-102">Compensation (BizTalk Server Sample)</span></span>
<span data-ttu-id="3c19c-103">补偿示例演示如何使用**Compensate**形状中业务流程。</span><span class="sxs-lookup"><span data-stu-id="3c19c-103">The Compensation sample demonstrates how to use the **Compensate** shape in an orchestration.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="3c19c-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="3c19c-104">What This Sample Does</span></span>  
 <span data-ttu-id="3c19c-105">本示例演示如何补偿业务流程中已提交的事务，步骤顺序如下：</span><span class="sxs-lookup"><span data-stu-id="3c19c-105">This sample demonstrates how to compensate the transaction that has already been committed in the orchestration using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="3c19c-106">在 InfoPath 表单中输入客户数据，然后向已公开为 Web Services 的业务流程提交该数据。</span><span class="sxs-lookup"><span data-stu-id="3c19c-106">Enter the customer data in the InfoPath form and submit the data to an orchestration that has been exposed as a Web service.</span></span>  
  
2.  <span data-ttu-id="3c19c-107">该业务流程有两个并行操作。</span><span class="sxs-lookup"><span data-stu-id="3c19c-107">The orchestration has two parallel actions.</span></span> <span data-ttu-id="3c19c-108">一个将返回 InfoPath 表单的确认，另一个将更新 Northwind 和 BTSCompensationSampleMailingList 数据库。</span><span class="sxs-lookup"><span data-stu-id="3c19c-108">One returns an acknowledgment to the InfoPath form and the other updates the Northwind and BTSCompensationSampleMailingList databases.</span></span>  
  
3.  <span data-ttu-id="3c19c-109">在第二个操作，业务流程将传入的消息映射到客户关系管理 (CRM) 应用程序消息格式，然后更新**客户**Northwind 数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="3c19c-109">In the second action, the orchestration maps the incoming message to a customer relationship management (CRM) application message format and then updates the **Customers** table in the Northwind database.</span></span> <span data-ttu-id="3c19c-110">此更新完成后，将会更新 BTSCompensationSampleMailingList 数据库中的 Mailing List 表。</span><span class="sxs-lookup"><span data-stu-id="3c19c-110">After this, the Mailing List table in the BTSCompensationSampleMailingList database is updated.</span></span>  
  
4.  <span data-ttu-id="3c19c-111">如果以上两个更新中有一个失败，则会通过调用外部程序集将原始客户数据重新写入数据库来补偿对 Northwind 数据库所做的更改。</span><span class="sxs-lookup"><span data-stu-id="3c19c-111">If either update fails, the changes made to the Northwind database are compensated by calling an external assembly to write the original customer data back to the database.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="3c19c-112">本示例旨在如何以及为何</span><span class="sxs-lookup"><span data-stu-id="3c19c-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="3c19c-113">A**作用域**形状主要用于事务的执行和异常处理，包括补偿。</span><span class="sxs-lookup"><span data-stu-id="3c19c-113">A **Scope** shape is primarily used for transactional execution and exception handling, including compensation.</span></span> <span data-ttu-id="3c19c-114">作用域由两个模块组成。</span><span class="sxs-lookup"><span data-stu-id="3c19c-114">A scope consists of two blocks.</span></span> <span data-ttu-id="3c19c-115">第一个模块为上下文模块，第二个模块为一个或多个异常处理模块或补偿模块。</span><span class="sxs-lookup"><span data-stu-id="3c19c-115">The first block is the context block and the second block can be one or more exception-handling or compensation blocks.</span></span> <span data-ttu-id="3c19c-116">这与 .NET 编程语言中的 try-catch 语句类似。</span><span class="sxs-lookup"><span data-stu-id="3c19c-116">This is similar to the try-catch statement in the .NET programming language.</span></span> <span data-ttu-id="3c19c-117">在 UpdateContact.odx 业务流程中有两个并行操作。</span><span class="sxs-lookup"><span data-stu-id="3c19c-117">In the UpdateContact.odx orchestration, there are two parallel actions.</span></span> <span data-ttu-id="3c19c-118">在右侧分支，try 块是**作用域**名为更新后端系统，它具有长时间运行事务键入和 Upd_Backend 事务标识符的形状。</span><span class="sxs-lookup"><span data-stu-id="3c19c-118">At the right-side branch, the try block is the **Scope** shape named Updated Backend Systems, which has a Long-Running transaction type and an Upd_Backend transaction identifier.</span></span> <span data-ttu-id="3c19c-119">沿流继续向下，有一个 catch 模块，用于捕获常规异常并启动补偿。</span><span class="sxs-lookup"><span data-stu-id="3c19c-119">Further down in the flow, there is a catch block that catches the general exception and initiates the compensation.</span></span>  
  
 <span data-ttu-id="3c19c-120">有关详细信息**作用域**形状，请参阅[作用域](../core/scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="3c19c-120">For more information about the **Scope** shape, see [Scopes](../core/scopes.md).</span></span> <span data-ttu-id="3c19c-121">另请参阅[如何配置作用域形状](../core/how-to-configure-the-scope-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="3c19c-121">Also see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c19c-122">业务流程本身必须为长期事务才能将事务类型设置为“原子”或“长期”。</span><span class="sxs-lookup"><span data-stu-id="3c19c-122">The orchestration must itself be a long-running transaction for you to set the transaction type to Atomic or Long-Running.</span></span>  
  
 <span data-ttu-id="3c19c-123">Try 块中，有两个名为的作用域**更新 CRM**和**更新邮件**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-123">In the try block, there are two scopes named **Update CRM** and **Update Mailing**.</span></span> <span data-ttu-id="3c19c-124">这两个作用域都是原子事务。</span><span class="sxs-lookup"><span data-stu-id="3c19c-124">Both of these scopes are atomic transactions.</span></span> <span data-ttu-id="3c19c-125">在 Update CRM 作用域中，有一个 try 模块和一个补偿模块。</span><span class="sxs-lookup"><span data-stu-id="3c19c-125">In the Update CRM scope, there is a try block and a compensation block.</span></span> <span data-ttu-id="3c19c-126">try 模块通过调用外部程序集中的方法来更新 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="3c19c-126">The try block updates the Northwind database through a method call to an external assembly.</span></span> <span data-ttu-id="3c19c-127">补偿模块执行补偿操作。</span><span class="sxs-lookup"><span data-stu-id="3c19c-127">The compensation block is where the compensation action takes place.</span></span> <span data-ttu-id="3c19c-128">当 Update Backend Systems 作用域中发生异常时，Undo CRM 表达式形状中的代码将把记录重新更新为它的原始状态。</span><span class="sxs-lookup"><span data-stu-id="3c19c-128">When an exception happens in the Update Backend Systems scope, the code in Undo CRM Expression Shape updates the record back to its original state.</span></span> <span data-ttu-id="3c19c-129">这由触发**Compensate**捕获异常块中的形状。</span><span class="sxs-lookup"><span data-stu-id="3c19c-129">This is triggered by the **Compensate** shape in the Catch Exception block.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c19c-130">原子事务保证在事务性更新期间发生故障时可自动回滚任何部分更新，并且消除事务的影响（事务中进行的任何 .NET 调用的影响除外）。</span><span class="sxs-lookup"><span data-stu-id="3c19c-130">Atomic transactions guarantee that any partial updates are rolled back automatically in the event of a failure during the transactional update, and that the effects of the transaction are erased (except for the effects of any .NET calls that are made in the transaction).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c19c-131">长期事务中的最后一个语句完成时，代表该事务已提交。</span><span class="sxs-lookup"><span data-stu-id="3c19c-131">A long-running transaction is considered committed when the last statement in it has completed.</span></span> <span data-ttu-id="3c19c-132">事务中止的情况下，不会自动回滚状态。</span><span class="sxs-lookup"><span data-stu-id="3c19c-132">There is no automatic rollback of state in case of a transaction abort.</span></span> <span data-ttu-id="3c19c-133">这种回滚可以通过编写如本示例所示的异常处理程序和补偿处理程序来实现。</span><span class="sxs-lookup"><span data-stu-id="3c19c-133">You can achieve this programmatically through the exception and compensation handlers demonstrated in this sample.</span></span>  
  
 <span data-ttu-id="3c19c-134">在 catch 块中，还有一个**延迟**形状设置为十秒。</span><span class="sxs-lookup"><span data-stu-id="3c19c-134">In the catch block, there is one **Delay** shape set for ten seconds.</span></span> <span data-ttu-id="3c19c-135">它用于延迟补偿操作。</span><span class="sxs-lookup"><span data-stu-id="3c19c-135">This delays the compensation action.</span></span> <span data-ttu-id="3c19c-136">此外，还有**Compensate**启动 Upd_Backend 事务中的补偿操作的形状。</span><span class="sxs-lookup"><span data-stu-id="3c19c-136">There is also a **Compensate** shape that initiates the compensation action in the Upd_Backend transaction.</span></span>  
  
 <span data-ttu-id="3c19c-137">业务流程接收到输入消息后，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="3c19c-137">The following happens after the orchestration receives the input message:</span></span>  
  
1.  <span data-ttu-id="3c19c-138">UpdateCrm 程序集更新 Northwind 数据库中的行。</span><span class="sxs-lookup"><span data-stu-id="3c19c-138">The UpdateCrm assembly updates a row in the Northwind database.</span></span>  
  
2.  <span data-ttu-id="3c19c-139">UpdateMailingList 程序集更新 BTSCompensationSampleMailingList 数据库中的匹配记录。</span><span class="sxs-lookup"><span data-stu-id="3c19c-139">The UpdateMailingList assembly updates a matching record in the BTSCompensationSampleMailingList database.</span></span>  
  
3.  <span data-ttu-id="3c19c-140">如果更新 Northwind 数据库时发生故障，将会引发异常并且业务流程会退出进程。</span><span class="sxs-lookup"><span data-stu-id="3c19c-140">In the event of a failure while updating the Northwind database, an exception is raised and the orchestration exits the process.</span></span>  
  
4.  <span data-ttu-id="3c19c-141">如果更新 BTSCompensationSampleMailingList 数据库时发生故障，将会引发异常，并且在延迟十秒钟后将原始客户数据重新写回 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="3c19c-141">In the event of a failure while updating the BTSCompensationSampleMailingList database, an exception is raised and a ten-second delay takes place before rewriting the original customer data back to the Northwind database.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="3c19c-142">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="3c19c-142">Where to Find This Sample</span></span>  
 <span data-ttu-id="3c19c-143">\<*示例路径*\>\Orchestrations\Compensation\\</span><span class="sxs-lookup"><span data-stu-id="3c19c-143">\<*Samples Path*\>\Orchestrations\Compensation\\</span></span>  
  
 <span data-ttu-id="3c19c-144">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="3c19c-144">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="3c19c-145">文件</span><span class="sxs-lookup"><span data-stu-id="3c19c-145">File(s)</span></span>|<span data-ttu-id="3c19c-146">Description</span><span class="sxs-lookup"><span data-stu-id="3c19c-146">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c19c-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="3c19c-147">Cleanup.bat</span></span>|<span data-ttu-id="3c19c-148">用于卸载示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-148">Batch file used to uninstall the sample.</span></span>|  
|<span data-ttu-id="3c19c-149">CompensationOrchestration.btproj</span><span class="sxs-lookup"><span data-stu-id="3c19c-149">CompensationOrchestration.btproj</span></span>|<span data-ttu-id="3c19c-150">业务流程项目。</span><span class="sxs-lookup"><span data-stu-id="3c19c-150">Orchestration project.</span></span>|  
|<span data-ttu-id="3c19c-151">CompensationSample.sln</span><span class="sxs-lookup"><span data-stu-id="3c19c-151">CompensationSample.sln</span></span>|<span data-ttu-id="3c19c-152">示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="3c19c-152">Sample solution.</span></span>|  
|<span data-ttu-id="3c19c-153">CompensationSampleBinding.xml</span><span class="sxs-lookup"><span data-stu-id="3c19c-153">CompensationSampleBinding.xml</span></span>|<span data-ttu-id="3c19c-154">业务流程的绑定数据（安装期间使用）。</span><span class="sxs-lookup"><span data-stu-id="3c19c-154">Binding data for the orchestration (used during installation).</span></span>|  
|<span data-ttu-id="3c19c-155">ContactInfo.xsd</span><span class="sxs-lookup"><span data-stu-id="3c19c-155">ContactInfo.xsd</span></span>|<span data-ttu-id="3c19c-156">联系人信息消息架构。</span><span class="sxs-lookup"><span data-stu-id="3c19c-156">Contact information message schema.</span></span>|  
|<span data-ttu-id="3c19c-157">ContactInfo.xsx</span><span class="sxs-lookup"><span data-stu-id="3c19c-157">ContactInfo.xsx</span></span>|<span data-ttu-id="3c19c-158">业务流程设计器布局文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-158">Orchestration Designer layout file.</span></span>|  
|<span data-ttu-id="3c19c-159">CreateSQLDataStore.sql</span><span class="sxs-lookup"><span data-stu-id="3c19c-159">CreateSQLDataStore.sql</span></span>|<span data-ttu-id="3c19c-160">用于创建和填充示例数据库的 SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="3c19c-160">SQL script to create and populate the sample database.</span></span>|  
|<span data-ttu-id="3c19c-161">CrmSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="3c19c-161">CrmSchema.xsd</span></span>|<span data-ttu-id="3c19c-162">CRM 更新消息架构。</span><span class="sxs-lookup"><span data-stu-id="3c19c-162">CRM update message schema.</span></span>|  
|<span data-ttu-id="3c19c-163">MailingListSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="3c19c-163">MailingListSchema.xsd</span></span>|<span data-ttu-id="3c19c-164">邮件列表消息更新架构。</span><span class="sxs-lookup"><span data-stu-id="3c19c-164">Mailing list message update schema.</span></span>|  
|<span data-ttu-id="3c19c-165">RemoveVirDir.vbs</span><span class="sxs-lookup"><span data-stu-id="3c19c-165">RemoveVirDir.vbs</span></span>|<span data-ttu-id="3c19c-166">Microsoft Visual Basic Scripting Edition (VBScript) 脚本，用于删除 Web Services 虚拟目录和物理目录（卸载期间使用）。</span><span class="sxs-lookup"><span data-stu-id="3c19c-166">Microsoft Visual Basic Scripting Edition (VBScript) script to remove Web service virtual and physical directories (used during uninstallation).</span></span>|  
|<span data-ttu-id="3c19c-167">Request2Crm.btm</span><span class="sxs-lookup"><span data-stu-id="3c19c-167">Request2Crm.btm</span></span>|<span data-ttu-id="3c19c-168">用于将请求（联系信息）翻译为 CRM 更新消息的消息映射。</span><span class="sxs-lookup"><span data-stu-id="3c19c-168">Message map to translate from request (contact info) to CRM update message.</span></span>|  
|<span data-ttu-id="3c19c-169">Request2MailingList.btm</span><span class="sxs-lookup"><span data-stu-id="3c19c-169">Request2MailingList.btm</span></span>|<span data-ttu-id="3c19c-170">用于将请求（联系信息）翻译为邮件列表消息的消息映射。</span><span class="sxs-lookup"><span data-stu-id="3c19c-170">Message map to translate from request (contact info) to mailing list message.</span></span>|  
|<span data-ttu-id="3c19c-171">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="3c19c-171">Setup.bat</span></span>|<span data-ttu-id="3c19c-172">用于安装此示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-172">Batch file to install this sample.</span></span>|  
|<span data-ttu-id="3c19c-173">UpdateContact.odx</span><span class="sxs-lookup"><span data-stu-id="3c19c-173">UpdateContact.odx</span></span>|<span data-ttu-id="3c19c-174">业务流程文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-174">Orchestration file.</span></span>|  
|<span data-ttu-id="3c19c-175">UpdateRequest2UpdateResponse.btm</span><span class="sxs-lookup"><span data-stu-id="3c19c-175">UpdateRequest2UpdateResponse.btm</span></span>|<span data-ttu-id="3c19c-176">用于将请求（联系信息）翻译为响应消息的消息映射。</span><span class="sxs-lookup"><span data-stu-id="3c19c-176">Message map to translate from request (contact info) to a response message.</span></span>|  
|<span data-ttu-id="3c19c-177">UpdateResponse.xsd</span><span class="sxs-lookup"><span data-stu-id="3c19c-177">UpdateResponse.xsd</span></span>|<span data-ttu-id="3c19c-178">响应消息架构。</span><span class="sxs-lookup"><span data-stu-id="3c19c-178">Response message schema.</span></span>|  
|<span data-ttu-id="3c19c-179">InfoPath\Contact Info Update.xsn</span><span class="sxs-lookup"><span data-stu-id="3c19c-179">InfoPath\Contact Info Update.xsn</span></span>|<span data-ttu-id="3c19c-180">用于将表单提交给业务流程 Web Services 的 Microsoft InfoPath 文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-180">Microsoft InfoPath file used to submit forms to the orchestration Web service.</span></span>|  
|<span data-ttu-id="3c19c-181">UpdateCrm\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="3c19c-181">UpdateCrm\AssemblyInfo.cs</span></span>|<span data-ttu-id="3c19c-182">UpdateCrm 程序集的程序集信息源文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-182">Assembly information source file for the UpdateCrm assembly.</span></span> <span data-ttu-id="3c19c-183">（UpdateCrm 程序集更新 Northwind 数据库。）</span><span class="sxs-lookup"><span data-stu-id="3c19c-183">(The UpdateCrm assembly updates the Northwind database.)</span></span>|  
|<span data-ttu-id="3c19c-184">UpdateCrm\UpdateCrm.cs</span><span class="sxs-lookup"><span data-stu-id="3c19c-184">UpdateCrm\UpdateCrm.cs</span></span>|<span data-ttu-id="3c19c-185">UpdateCrm 程序集的源代码主文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-185">Main source code for the UpdateCrm assembly.</span></span>|  
|<span data-ttu-id="3c19c-186">UpdateCrm\UpdateCRM.csproj</span><span class="sxs-lookup"><span data-stu-id="3c19c-186">UpdateCrm\UpdateCRM.csproj</span></span>|<span data-ttu-id="3c19c-187">UpdateCrm 项目文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-187">UpdateCrm project file.</span></span>|  
|<span data-ttu-id="3c19c-188">UpdateMailingList\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="3c19c-188">UpdateMailingList\AssemblyInfo.cs</span></span>|<span data-ttu-id="3c19c-189">UpdateMailingList 程序集的程序集信息源文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-189">Assembly information source file for the UpdateMailingList assembly.</span></span> <span data-ttu-id="3c19c-190">（UpdateMailingList 程序集更新示例数据库。）</span><span class="sxs-lookup"><span data-stu-id="3c19c-190">(The UpdateMailingList assembly updates the sample database.)</span></span>|  
|<span data-ttu-id="3c19c-191">UpdateMailingList\UpdateMailingList.cs</span><span class="sxs-lookup"><span data-stu-id="3c19c-191">UpdateMailingList\UpdateMailingList.cs</span></span>|<span data-ttu-id="3c19c-192">UpdateMailingList 程序集的源代码主文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-192">Main source code for the UpdateMailingList assembly.</span></span>|  
|<span data-ttu-id="3c19c-193">UpdateMailingList\UpdateMailingList.csproj</span><span class="sxs-lookup"><span data-stu-id="3c19c-193">UpdateMailingList\UpdateMailingList.csproj</span></span>|<span data-ttu-id="3c19c-194">UpdateMailingList 项目文件。</span><span class="sxs-lookup"><span data-stu-id="3c19c-194">UpdateMailingList project file.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="3c19c-195">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="3c19c-195">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-compensation-sample"></a><span data-ttu-id="3c19c-196">生成并初始化补偿示例</span><span class="sxs-lookup"><span data-stu-id="3c19c-196">To build and initialize the Compensation sample</span></span>  
  
1.  <span data-ttu-id="3c19c-197">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="3c19c-197">In a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="3c19c-198">\<*示例路径*\>\Orchestrations\Compensation\\</span><span class="sxs-lookup"><span data-stu-id="3c19c-198">\<*Samples Path*\>\Orchestrations\Compensation\\</span></span>  
  
2.  <span data-ttu-id="3c19c-199">运行 Setup.bat，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3c19c-199">Run Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="3c19c-200">生成并部署示例程序集。</span><span class="sxs-lookup"><span data-stu-id="3c19c-200">Build and deploy the sample assembly.</span></span>  
  
    -   <span data-ttu-id="3c19c-201">当 BizTalk Web Services 发布向导启动时，请手动执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3c19c-201">When the BizTalk Web Services Publishing Wizard launches, do the following manually:</span></span>  
  
    1.  <span data-ttu-id="3c19c-202">上**欢迎 BizTalk Web 服务发布向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-202">On the **Welcome to the BizTalk Web Services Publishing Wizard** page, click **Next**.</span></span>  
  
    2.  <span data-ttu-id="3c19c-203">上**创建 Web 服务**页上，选择**作为 web 服务的发布 BizTalk 业务流程**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-203">On the **Create Web Service** page, select **Publish BizTalk orchestration as web services**, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="3c19c-204">上**BizTalk 程序集**页上，浏览并选择\<*示例路径*\>\Orchestrations\Compensation\bin\Release\CompensationOrchestration.dll，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-204">On the **BizTalk Assembly** page, browse and select \<*Samples Path*\>\Orchestrations\Compensation\bin\Release\CompensationOrchestration.dll, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="3c19c-205">上**业务流程和端口**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-205">On the **Orchestrations and Ports** page, click **Next**.</span></span>  
  
    5.  <span data-ttu-id="3c19c-206">上**Web 服务属性**页上，在**的 web 服务的目标命名空间**，类型**http://Microsoft.BizTalk.Samples.Compensation/**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-206">On the **Web Service Properties** page, in **Target namespace of web service**, type **http://Microsoft.BizTalk.Samples.Compensation/**, and then click **Next**.</span></span>  
  
    6.  <span data-ttu-id="3c19c-207">上**Web 服务项目**页上，在**位置**，类型**http://localhost/CompensationOrchestrationWebServiceProxy**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-207">On the **Web Service Project** page, in **Location**, type **http://localhost/CompensationOrchestrationWebServiceProxy**.</span></span>  
  
    7.  <span data-ttu-id="3c19c-208">选择**允许匿名访问 web 服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="3c19c-208">Select the **Allow anonymous access to web service** check box.</span></span>  
  
    8.  <span data-ttu-id="3c19c-209">选择**创建 BizTalk 以下应用程序中接收位置**复选框。</span><span class="sxs-lookup"><span data-stu-id="3c19c-209">Select the **Create BizTalk receive location in the following application** check box.</span></span>  
  
    9. <span data-ttu-id="3c19c-210">在**创建 BizTalk 以下应用程序中接收位置**下拉列表菜单上，选择**BizTalk 应用程序 1**从下拉列表，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-210">In the **Create BizTalk receive location in the following application** drop-down menu, select **BizTalk Application 1** from the drop-down list, and then click **Next**.</span></span>  
  
    10. <span data-ttu-id="3c19c-211">上**Web 服务项目摘要**页上，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-211">On the **Web Service Project Summary** page, click **Create**.</span></span>  
  
    11. <span data-ttu-id="3c19c-212">上**完成 BizTalk Web 服务发布向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-212">On the **Completing the BizTalk Web Services Publishing Wizard** page, click **Finish**.</span></span>  
  
3.  <span data-ttu-id="3c19c-213">安装程序会创建并绑定端口，为该示例创建后端数据库，还会将 C# 程序集添加到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="3c19c-213">Setup creates and binds ports, creates the back-end database for the sample, and adds C# assemblies to the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c19c-214">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="3c19c-214">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="3c19c-215">运行本示例</span><span class="sxs-lookup"><span data-stu-id="3c19c-215">Running This Sample</span></span>  
 <span data-ttu-id="3c19c-216">生成并初始化本示例后，请先考虑以下情况，然后再运行本示例：</span><span class="sxs-lookup"><span data-stu-id="3c19c-216">After you build and initialize this sample, consider the following before you run it:</span></span>  
  
-   <span data-ttu-id="3c19c-217">如果要在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 上运行本示例，必须创建 IIS 应用程序池并将其身份设置为揃“BizTalk Application Users Windows”组的成员帐户。</span><span class="sxs-lookup"><span data-stu-id="3c19c-217">If you are running this sample on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], you must create an IIS application pool and set its identity to an account that is a member of the BizTalk Application Users Windows group.</span></span> <span data-ttu-id="3c19c-218">在此应用程序池内运行还需要更新业务流程 Web Services 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="3c19c-218">You also need to update the orchestration Web service virtual directory to run within this application pool.</span></span>  
  
-   <span data-ttu-id="3c19c-219">将“ASPNET”帐户添加到“Biztalk Isolated Host Users”组。</span><span class="sxs-lookup"><span data-stu-id="3c19c-219">Add the ASPNET account to the BizTalk Isolated Host Users group.</span></span>  
  
-   <span data-ttu-id="3c19c-220">将该 BizTalk 应用程序用户组 db_owner 权限授予**BTSCompensationSampleMailingList**和**Northwind**数据库。</span><span class="sxs-lookup"><span data-stu-id="3c19c-220">Give the BizTalk Application Users group db_owner permission to the **BTSCompensationSampleMailingList** and **Northwind** databases.</span></span>  
  
-   <span data-ttu-id="3c19c-221">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未安装在默认位置 (驱动器： files\microsoft BizTalk Server\<版本\>\\)，你必须在使用它之前发布联系人信息 Update.xsn 窗体。</span><span class="sxs-lookup"><span data-stu-id="3c19c-221">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is not installed in the default location (drive:\Program Files\Microsoft BizTalk Server \<version\>\\), you must publish the Contact Info Update.xsn form before using it.</span></span> <span data-ttu-id="3c19c-222">若要这样做，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="3c19c-222">To do so, do the following.</span></span>  
  
    #### <a name="to-publish-the-infopath-form"></a><span data-ttu-id="3c19c-223">发布 InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="3c19c-223">To publish the InfoPath form</span></span>  
  
    1.  <span data-ttu-id="3c19c-224">在 Internet Explorer 中，在**工具**菜单上，单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-224">In Internet Explorer, on the **Tools** menu, click **Internet Options**.</span></span>  
  
    2.  <span data-ttu-id="3c19c-225">上**安全**选项卡上，单击**Internet**，然后单击**自定义级别**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-225">On the **Security** tab, click **Internet**, and then click **Custom Level**.</span></span>  
  
    3.  <span data-ttu-id="3c19c-226">在**杂项**部分中，确保**跨域访问数据源**设置已启用，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-226">In the **Miscellaneous** section, ensure that the **Access data sources across domains** setting is enabled, and then click **OK**.</span></span> <span data-ttu-id="3c19c-227">InfoPath 用户界面解决方案脚本代码需要此设置才能运行。</span><span class="sxs-lookup"><span data-stu-id="3c19c-227">This setting is required for the InfoPath user interface solution scripting code to run.</span></span>  
  
    4.  <span data-ttu-id="3c19c-228">在 Windows 资源管理器，导航到\<*示例路径*\>\Orchestrations\Compensation\InfoPath，右键单击**联系人信息 Update.xsn** ，然后单击**设计**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-228">In Windows Explorer, navigate to \<*Samples Path*\>\Orchestrations\Compensation\InfoPath, right-click **Contact Info Update.xsn** and then click **Design**.</span></span>  
  
    5.  <span data-ttu-id="3c19c-229">InfoPath Contact Info Update 解决方案以设计模式打开。</span><span class="sxs-lookup"><span data-stu-id="3c19c-229">The InfoPath Contact Info Update solution opens in design mode.</span></span>  
  
    6.  <span data-ttu-id="3c19c-230">在 InfoPath 联系信息更新应用程序上**文件**菜单上，单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-230">In the InfoPath Contact Info Update application, on the **File** menu, click **Publish**.</span></span>  
  
    7.  <span data-ttu-id="3c19c-231">此时，将显示发布向导。</span><span class="sxs-lookup"><span data-stu-id="3c19c-231">The Publish Wizard appears.</span></span>  
  
    8.  <span data-ttu-id="3c19c-232">选择**到此计算机上或在网络上的共享文件夹**并将解决方案发布到路径\<*示例路径*\>\Orchestrations\Compensation\InfoPath\Contact 信息Update.xsn。</span><span class="sxs-lookup"><span data-stu-id="3c19c-232">Select **To a shared folder on this computer or on a network** and publish the solution to the path \<*Samples Path*\>\Orchestrations\Compensation\InfoPath\Contact Info Update.xsn.</span></span>  
  
    9. <span data-ttu-id="3c19c-233">关闭设计模式下的 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="3c19c-233">Close the design mode InfoPath.</span></span>  
  
-   <span data-ttu-id="3c19c-234">现在可以运行本示例了。</span><span class="sxs-lookup"><span data-stu-id="3c19c-234">You are ready to run this sample.</span></span>  
  
    #### <a name="to-run-the-compensation-sample"></a><span data-ttu-id="3c19c-235">运行补偿示例</span><span class="sxs-lookup"><span data-stu-id="3c19c-235">To run the Compensation sample</span></span>  
  
    1.  <span data-ttu-id="3c19c-236">双击**联系人信息 Update.xsn**在 InfoPath 中打开它。</span><span class="sxs-lookup"><span data-stu-id="3c19c-236">Double-click **Contact Info Update.xsn** to open it in InfoPath.</span></span>  
  
    2.  <span data-ttu-id="3c19c-237">使用在两个数据库中都存在的某一帐户填写该表单。</span><span class="sxs-lookup"><span data-stu-id="3c19c-237">Fill out the form for an account that exists in both databases.</span></span> <span data-ttu-id="3c19c-238">例如，使用 Northwind Customers 表中的现有帐户 ID“ALFKI”。</span><span class="sxs-lookup"><span data-stu-id="3c19c-238">For example, use an existing account ID "ALFKI" from the Northwind Customers table.</span></span>  
  
    3.  <span data-ttu-id="3c19c-239">上**文件**菜单上，选择**提交**，然后单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="3c19c-239">On the **File** menu, select **Submit**, and click **Submit**.</span></span>  
  
    4.  <span data-ttu-id="3c19c-240">响应文档应出现在\<*示例路径*\>\Orchestrations\Compensation\Out 文件夹和 Northwind 和 BTSCompensationSampleMailingList 数据库都应更新InfoPath 窗体中的新数据。</span><span class="sxs-lookup"><span data-stu-id="3c19c-240">The response document should appear in the \<*Samples Path*\>\Orchestrations\Compensation\Out folder, and both the Northwind and the BTSCompensationSampleMailingList databases should be updated with the new data from the InfoPath form.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3c19c-241">你可以分离 BTSCompensationSampleMailingList 数据库或将其脱机以测试该业务流程执行的补偿操作。</span><span class="sxs-lookup"><span data-stu-id="3c19c-241">You can detach the BTSCompensationSampleMailingList database or take it offline to test the compensation action that the orchestration performs.</span></span> <span data-ttu-id="3c19c-242">观察相应记录是否先在 Northwind 数据库中进行了更新。</span><span class="sxs-lookup"><span data-stu-id="3c19c-242">Observe that the record is updated in the Northwind database first.</span></span> <span data-ttu-id="3c19c-243">然后，在该业务流程尝试更新 BTSCompensationSampleMailingList 数据库时，因为该数据库已经分离，更新将失败。</span><span class="sxs-lookup"><span data-stu-id="3c19c-243">Then, when the orchestration tries to update the BTSCompensationSampleMailingList database, because that database is detached, the update fails.</span></span> <span data-ttu-id="3c19c-244">因此，将引发异常，并在 10 秒钟的延迟后，就会采取补偿操作将原始客户数据写回 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="3c19c-244">Therefore, an exception is raised and there is a ten-second delay before the compensation action takes place to write the original customer data back to the Northwind database.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3c19c-245">你可能会收到“用户‘IIS APPPOOL\DefaultAppPool’登录失败”错误。</span><span class="sxs-lookup"><span data-stu-id="3c19c-245">You may get a "Login failed for user 'IIS APPPOOL\DefaultAppPool' error.</span></span> <span data-ttu-id="3c19c-246">这可能是因为基于令牌的服务器访问验证失败所致。</span><span class="sxs-lookup"><span data-stu-id="3c19c-246">It might be because of the token-based server access validation failure.</span></span> <span data-ttu-id="3c19c-247">若要解决此错误，请创建一个新的应用程序池并在该池中使用管理帐户。</span><span class="sxs-lookup"><span data-stu-id="3c19c-247">To resolve this error, create a new application pool and use the administrator account in it.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="3c19c-248">卸载本示例</span><span class="sxs-lookup"><span data-stu-id="3c19c-248">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-compensation-sample"></a><span data-ttu-id="3c19c-249">卸载补偿示例</span><span class="sxs-lookup"><span data-stu-id="3c19c-249">To uninstall the Compensation sample</span></span>  
  
1.  <span data-ttu-id="3c19c-250">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="3c19c-250">In a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="3c19c-251">\<*示例路径*\>\Orchestrations\Compensation\\</span><span class="sxs-lookup"><span data-stu-id="3c19c-251">\<*Samples Path*\>\Orchestrations\Compensation\\</span></span>  
  
2.  <span data-ttu-id="3c19c-252">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="3c19c-252">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c19c-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c19c-253">See Also</span></span>  
 [<span data-ttu-id="3c19c-254">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="3c19c-254">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)