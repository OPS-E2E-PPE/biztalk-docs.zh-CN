---
title: "与 Oracle E-business Suite 适配器排除操作问题 |Microsoft 文档"
description: "常见的问题和 Oracle EBS 适配器 BizTalk 适配器包 (BAP) 中的解决方法"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4654e228a4ca86c9d89686f826d57777f2353efd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="80c35-103">与 Oracle E-business Suite 适配器排除操作问题</span><span class="sxs-lookup"><span data-stu-id="80c35-103">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="80c35-104">本部分讨论如何使用故障排除方法来解决操作使用时可能遇到的错误[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c35-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="80c35-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="80c35-105">Enabling Tracing</span></span>  
 <span data-ttu-id="80c35-106">有关跟踪中的支持的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，[诊断跟踪和消息日志记录中的 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-106">For more information about tracing support in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], [Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="80c35-107">已知问题</span><span class="sxs-lookup"><span data-stu-id="80c35-107">Known Issues</span></span>  
 <span data-ttu-id="80c35-108">以下是使用时可能遇到的最常见错误[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]，以及其可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="80c35-108">The following are the most common errors you might encounter when using the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_LoadBindings"></a><span data-ttu-id="80c35-109">在加载适配器绑定错误</span><span class="sxs-lookup"><span data-stu-id="80c35-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="80c35-110">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-110">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-111">当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="80c35-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="80c35-112">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-112">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-113">当你尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 加载所有已安装适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="80c35-113">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="80c35-114">反过来，适配器绑定都依赖于企业应用程序的特定客户端软件。</span><span class="sxs-lookup"><span data-stu-id="80c35-114">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="80c35-115">你可能会遇到此问题的一个或两个原因如下：</span><span class="sxs-lookup"><span data-stu-id="80c35-115">You might face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="80c35-116">在安装适配器的计算机上未安装所需的 LOB 客户端软件。</span><span class="sxs-lookup"><span data-stu-id="80c35-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="80c35-117">未将适配器安装中包含的所有适配器的典型或完全安装[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c35-117">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="80c35-118">但是，可能只有一个企业应用程序安装 LOB 客户端库。</span><span class="sxs-lookup"><span data-stu-id="80c35-118">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="80c35-119">因此，GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="80c35-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="80c35-120">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-120">**Resolution**</span></span>  
  
-   <span data-ttu-id="80c35-121">请确保在你安装的计算机上安装了所需的 LOB 客户端版本[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c35-121">Make sure that the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="80c35-122">有关支持的客户端版本的信息，请参阅安装指南位于\<安装驱动器\>: files\microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c35-122">For information about the supported client versions, see the installation guide available at \<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="80c35-123">请确保执行适配器安装需要适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="80c35-123">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_Display"></a><span data-ttu-id="80c35-124">Oracle E-business Suite 适配器不会显示在列表中在 BizTalk Server 管理控制台中的适配器</span><span class="sxs-lookup"><span data-stu-id="80c35-124">The Oracle E-Business Suite adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="80c35-125">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-125">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-126">与不同的是较早版本附带的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在列表中中适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="80c35-126">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="80c35-127">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-127">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-128">最新[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="80c35-128">The latest [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="80c35-129">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c35-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
 <span data-ttu-id="80c35-130">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-130">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-131">你可以显式添加[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-131">You can explicitly add the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the Oracle E-Business Suite adapter to BizTalk Server Administration console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_MissingAction"></a><span data-ttu-id="80c35-132">执行对 Oracle E-business Suite 操作时出错</span><span class="sxs-lookup"><span data-stu-id="80c35-132">Error while performing operations on the Oracle E-Business Suite</span></span>  
 <span data-ttu-id="80c35-133">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-133">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-134">适配器执行针对 Oracle E-business Suite 使用的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c35-134">The adapter gives the following error when performing any operation on the Oracle E-Business Suite using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="80c35-135">**BizTalk server**</span><span class="sxs-lookup"><span data-stu-id="80c35-135">**For BizTalk Server**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="80c35-136">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-136">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-137">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="80c35-137">The WCF action for the message is not specified.</span></span> <span data-ttu-id="80c35-138">WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="80c35-138">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="80c35-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-139">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-140">指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="80c35-140">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="80c35-141">有关说明，请参阅[配置用于 Oracle E-business Suite 的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-141">For instructions, see [Configure the SOAP action for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md).</span></span> <span data-ttu-id="80c35-142">请参阅[消息和 Oracle EBS 适配器的消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)若要查看的每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="80c35-142">See [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_WrongClient"></a><span data-ttu-id="80c35-143">当在接收位置除去请求消息时，BizTalk 进程可能会崩溃由于不正确的 Oracle 客户端版本</span><span class="sxs-lookup"><span data-stu-id="80c35-143">BizTalk process might crash due to an incorrect Oracle client version when a request message is dropped at the receive location</span></span>  
 <span data-ttu-id="80c35-144">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-144">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-145">在 BizTalk 业务流程中定义接收位置删除请求消息后，业务流程使用该消息并 BizTalk 主机 (BTSNTSvc.exe) 发生崩溃并重新启动。</span><span class="sxs-lookup"><span data-stu-id="80c35-145">After a request message is dropped at a receive location defined in a BizTalk orchestration, the orchestration consumes the message and BizTalk host (BTSNTSvc.exe) crashes and restarts.</span></span>  
  
 <span data-ttu-id="80c35-146">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-146">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-147">安装 Oracle 客户端在 PATH 变量中添加对最新的客户端程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="80c35-147">Installing the Oracle client adds the reference to the latest client assemblies in the PATH variable.</span></span> <span data-ttu-id="80c35-148">此外，对最新安装 Oracle 客户端程序集的引用位于之前对现有客户端程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="80c35-148">Also, the references to the most recent installation of the Oracle client assembly precede the reference to the existing client assemblies.</span></span> <span data-ttu-id="80c35-149">因此，如果最新的 Oracle 客户端安装不支持的客户端版本的中，BizTalk 主机发生崩溃，，然后重新启动。</span><span class="sxs-lookup"><span data-stu-id="80c35-149">So, if the most recent Oracle client installation is not of a supported client version, BizTalk host crashes and then restarts.</span></span>  
  
 <span data-ttu-id="80c35-150">例如，假定在计算机上已安装支持的 Oracle 客户端 11.1.0.7 和 PATH 变量具有以下引用：</span><span class="sxs-lookup"><span data-stu-id="80c35-150">For example, assume that the supported Oracle client 11.1.0.7 is already installed on the computer and the PATH variable has the following reference:</span></span>  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 <span data-ttu-id="80c35-151">如果不支持的 Oracle 客户端，例如 10.2.0.3，安装在同一台计算机上，路径变量将拥有以下引用：</span><span class="sxs-lookup"><span data-stu-id="80c35-151">If an unsupported Oracle client, for example 10.2.0.3, is installed on the same computer, the PATH variable will have the following reference:</span></span>  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 <span data-ttu-id="80c35-152">请注意，不受支持的客户端版本引用之前的受支持的版本，因此 BizTalk 主机发生崩溃。</span><span class="sxs-lookup"><span data-stu-id="80c35-152">Note that the unsupported client version is referenced before the supported version and hence BizTalk host crashes.</span></span> <span data-ttu-id="80c35-153">如果有多个 BizTalk 主机运行，承载适配器崩溃。</span><span class="sxs-lookup"><span data-stu-id="80c35-153">If there are more than one BizTalk hosts running, then the one hosting the adapter crashes.</span></span>  
  
 <span data-ttu-id="80c35-154">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-154">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-155">如果同一台计算机上安装多个 Oracle 客户端，请确保在 PATH 变量中的其他 Oracle 客户端版本之前引用的受支持的 Oracle 客户端版本。</span><span class="sxs-lookup"><span data-stu-id="80c35-155">If more than one Oracle client is installed on the same computer, make sure the supported Oracle client version is referenced before the other Oracle client versions in the PATH variable.</span></span> <span data-ttu-id="80c35-156">例如，如果支持的 Oracle 客户端版本，11.1.0.7 PATH 变量中的引用必须如下所示：</span><span class="sxs-lookup"><span data-stu-id="80c35-156">For example, if the supported Oracle client version is 11.1.0.7, the reference in the PATH variable must look like:</span></span>  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a><span data-ttu-id="80c35-157">适配器可能引发上执行运算溢出异常</span><span class="sxs-lookup"><span data-stu-id="80c35-157">Adapter might throw an overflow exception on executing an operation</span></span>  
 <span data-ttu-id="80c35-158">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-158">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-159">如果你尝试执行操作包含在数据集或弱类型 REF CURSOR 的 Oracle 数值数据类型，请使用该适配器，该适配器可能引发溢出异常。</span><span class="sxs-lookup"><span data-stu-id="80c35-159">Using the adapter, if you try to perform an operation containing Oracle numeric data types inside DataSets or weakly-typed REF CURSORS, the adapter might throw an overflow exception.</span></span>  
  
 <span data-ttu-id="80c35-160">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-160">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-161">如果你提供在数据集或弱类型 REF CURSOR，无法容纳到相应的.NET 类型内的 Oracle 数值数据类型为较大的值，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="80c35-161">This happens if you supply a large value for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS that cannot fit into the respective .NET type.</span></span>  
  
 <span data-ttu-id="80c35-162">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-162">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-163">如果你想要将较大的值传递的数据集或弱类型 REF CURSOR 内的 Oracle 数值数据类型，则必须启用安全设置的值键入**EnableSafeTyping**属性绑定到**true**.</span><span class="sxs-lookup"><span data-stu-id="80c35-163">If you want to pass large values for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS, you must enable safe typing by setting the value of the **EnableSafeTyping** binding property to **true**.</span></span> <span data-ttu-id="80c35-164">启用安全键入将在数据集或弱类型 REF CURSOR 内的 Oracle 数值数据类型公开为字符串。</span><span class="sxs-lookup"><span data-stu-id="80c35-164">Enabling safe typing exposes the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS as strings.</span></span>  
  
###  <a name="BKMK_Arithmetic"></a><span data-ttu-id="80c35-165">适配器可能会引发执行 ExecuteScalar 操作出现算术溢出异常</span><span class="sxs-lookup"><span data-stu-id="80c35-165">Adapter might throw an arithmetic overflow exception on executing an ExecuteScalar operation</span></span>  
 <span data-ttu-id="80c35-166">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-166">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-167">使用适配器，如果你尝试在检索大量的 ExecuteScalar 操作中执行 SELECT 语句，该适配器将引发以下异常:"System.OverflowException： 算术运算导致溢出。"</span><span class="sxs-lookup"><span data-stu-id="80c35-167">Using the adapter, if you try to execute a SELECT statement in an ExecuteScalar operation that retrieves a large number, the adapter throws the following exception: “System.OverflowException: Arithmetic operation resulted in an overflow.”</span></span>  
  
 <span data-ttu-id="80c35-168">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-168">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-169">由于在 ODP.NET ExecuteScalar 操作的已知限制发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="80c35-169">This happens due to the known limitation of ExecuteScalar operation in ODP.NET.</span></span> <span data-ttu-id="80c35-170">ODP.NET 尝试进行转换的.NET 十进制数据类型，数据中容纳不下，并且如果结果为太大，.NET 十进制类型中容纳不下，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="80c35-170">ODP.NET tries to fit in the data into the .NET Decimal data type, and if the result is too large to fit in the .NET Decimal type, the exception is thrown.</span></span>  
  
 <span data-ttu-id="80c35-171">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-171">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-172">使用 ExecuteScalar 操作中的 SELECT 语句中 TO_CHAR() 将转换为字符串返回的数据。</span><span class="sxs-lookup"><span data-stu-id="80c35-172">Use TO_CHAR() in the SELECT statement in the ExecuteScalar operation to convert the returned data as string.</span></span>  
  
###  <a name="BKMK_AppContext"></a><span data-ttu-id="80c35-173">适配器客户端可能会引发以下异常上执行操作:"无法检索用户 id、 责任 id、 应用程序 id。检查中是否传递了正确的值。"</span><span class="sxs-lookup"><span data-stu-id="80c35-173">Adapter client might throw the following exception on executing an operation: “Could not retrieve user id, responsibility id, application id.  Check if correct values were passed in.”</span></span>  
 <span data-ttu-id="80c35-174">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-174">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-175">如果您正在执行对 Oracle E-business Suite 项目 （接口表、 界面视图、 并发程序和请求集） 的操作，适配器客户端可能会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="80c35-175">The adapter clients might throw this exception if you are performing operations on Oracle E-Business Suite artifacts (interface tables, interface views, concurrent programs, and request sets).</span></span>  
  
 <span data-ttu-id="80c35-176">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-176">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-177">如果提供了对接口表、 界面视图、 并发程序和请求集执行操作时不正确的 Oracle 用户名、 密码和责任名称组合，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="80c35-177">This happens if you supply an incorrect combination of Oracle user name, password, and responsibility name while performing operations on interface tables, interface views, concurrent programs, and request sets.</span></span> <span data-ttu-id="80c35-178">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]需要这些值才能设置这些项目的应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="80c35-178">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] requires these values in order to set the application context for these artifacts.</span></span> <span data-ttu-id="80c35-179">有关设置应用程序上下文的详细信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-179">For more information about setting application context, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
 <span data-ttu-id="80c35-180">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-180">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-181">你必须指定正确的 Oracle 用户名、 密码和适当设置 Oracle E-business Suite 项目的应用程序上下文有责任组合。</span><span class="sxs-lookup"><span data-stu-id="80c35-181">You must specify a correct combination of the Oracle user name, password, and responsibility to appropriately set application context for an Oracle E-Business Suite artifact.</span></span> <span data-ttu-id="80c35-182">若要指定的 Oracle 用户名和密码的值，必须使用**OracleUserName**和**OraclePassword**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="80c35-182">To specify values for Oracle user name and password, you must use the **OracleUserName** and **OraclePassword** binding properties.</span></span> <span data-ttu-id="80c35-183">若要指定值的 Oracle 责任，则您可以使用**OracleEBSResponsibilityName**绑定属性或消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="80c35-183">To specify value for the Oracle responsibility, you can either use the **OracleEBSResponsibilityName** binding property or message context property.</span></span>  
  
###  <a name="BKMK_RootNode"></a><span data-ttu-id="80c35-184">与 RootNode TypeName BizTalk 项目中的错误</span><span class="sxs-lookup"><span data-stu-id="80c35-184">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="80c35-185">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-185">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-186">在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:</span><span class="sxs-lookup"><span data-stu-id="80c35-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="80c35-187">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="80c35-188">右键单击该错误并选择中引用的 rood 节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="80c35-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="80c35-189">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。</span><span class="sxs-lookup"><span data-stu-id="80c35-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_InvalidBinding"></a><span data-ttu-id="80c35-190">使用 Visual Studio 中的适配器时出现的无效的绑定警告</span><span class="sxs-lookup"><span data-stu-id="80c35-190">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="80c35-191">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-191">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-192">当你使用该适配器创建的应用程序在[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]并打开生成的适配器的配置文件 (app.config)，你看到类似于以下警告：</span><span class="sxs-lookup"><span data-stu-id="80c35-192">When you use the adapter to create an application in [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="80c35-193">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-193">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-194">由于会出现此警告[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]绑定， `oracleEBSBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c35-194">This warning appears because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding, `oracleEBSBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="80c35-195">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-195">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-196">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="80c35-196">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_Notify"></a><span data-ttu-id="80c35-197">BizTalk Server 引发异常，如果你在同一应用程序使用多个通知架构或跨同一个主机上的多个应用程序使用通知架构</span><span class="sxs-lookup"><span data-stu-id="80c35-197">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="80c35-198">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-198">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-199">BizTalk Server 引发 XLANG 异常或异常指出应用程序找不到文档规范，因为多个架构匹配的消息类型。</span><span class="sxs-lookup"><span data-stu-id="80c35-199">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="80c35-200">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-200">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-201">由于以下任一发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="80c35-201">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="80c35-202">在你生成多个通知架构在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，，然后运行应用程序从 Oracle 数据库接收通知。</span><span class="sxs-lookup"><span data-stu-id="80c35-202">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the Oracle database.</span></span> <span data-ttu-id="80c35-203">由于通知架构是公用的冲突之间没有部署 BizTalk Server 应用程序中的架构。</span><span class="sxs-lookup"><span data-stu-id="80c35-203">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="80c35-204">发生多个项目，你已为每个 BizTalk 服务器到单独的 BizTalk Server 应用程序在同一主机上的每个项目部署的项目生成通知架构，然后运行应用程序或应用程序接收来自通知Oracle 数据库中。</span><span class="sxs-lookup"><span data-stu-id="80c35-204">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the Oracle database.</span></span> <span data-ttu-id="80c35-205">因为架构和程序集都可访问 BizTalk Server 中的应用程序，各种 BizTalk Server 应用程序和程序集下部署的常见架构之间存在不冲突。</span><span class="sxs-lookup"><span data-stu-id="80c35-205">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="80c35-206">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-206">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-207">BizTalk Server 应用程序使用单个通知架构文件。</span><span class="sxs-lookup"><span data-stu-id="80c35-207">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="80c35-208">如果你需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的通知架构。</span><span class="sxs-lookup"><span data-stu-id="80c35-208">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_Timeout"></a><span data-ttu-id="80c35-209">浏览 Visual Studio 中的 Oracle E-business Suite 项目时的超时异常</span><span class="sxs-lookup"><span data-stu-id="80c35-209">Timeout Exception while browsing Oracle E-Business Suite Artifacts in Visual Studio</span></span>  
 <span data-ttu-id="80c35-210">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-210">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-211">浏览 Oracle E-business Suite 项目中的同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]项目使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]， [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]可能会遇到超时异常。</span><span class="sxs-lookup"><span data-stu-id="80c35-211">While browsing Oracle E-Business Suite artifacts in a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] project using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] you might encounter a timeout exception.</span></span>  
  
 <span data-ttu-id="80c35-212">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-212">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-213">如果承载 Oracle E-business Suite 的服务器速度缓慢、 服务器位于远程位置，或您要查找下的架构具有大量的项目，则可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="80c35-213">This might happen if the server hosting the Oracle E-Business Suite is slow, server is located at a remote location, or the schema you are looking under has a large number of artifacts.</span></span>  
  
 <span data-ttu-id="80c35-214">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-214">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-215">你可以选择的值增加**SendTimeout**绑定属性或提供搜索表达式中的**类别中的搜索**文本框中，以减少的项目数，该适配器检索。</span><span class="sxs-lookup"><span data-stu-id="80c35-215">You can either choose to increase the value of the **SendTimeout** binding property or provide a search expression in the **Search in category** text box to reduce the number of artifacts that the adapter retrieves.</span></span>  
  
 <span data-ttu-id="80c35-216">有关指定绑定属性的详细信息，请参阅[为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-216">For more information about specifying binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span> <span data-ttu-id="80c35-217">有关在 Oracle E-business Suite 中搜索项目的详细信息，请参阅[浏览、 搜索和 get 元数据用于 Oracle E-business Suite 操作](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-217">For more information about searching artifacts in Oracle E-Business Suite, see [Browse, search, and get metadata for Oracle E-Business Suite operations](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).</span></span>  
  
###  <a name="BKMK_MemUsage"></a><span data-ttu-id="80c35-218">内存使用情况和线程计数的增加而在事务处理的入站操作中使用该适配器时</span><span class="sxs-lookup"><span data-stu-id="80c35-218">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="80c35-219">**问题**</span><span class="sxs-lookup"><span data-stu-id="80c35-219">**Problem**</span></span>  
  
 <span data-ttu-id="80c35-220">在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**和适配器继续轮询，通过一段时间则会遇到内存使用量和线程计数的增加。</span><span class="sxs-lookup"><span data-stu-id="80c35-220">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="80c35-221">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c35-221">**Cause**</span></span>  
  
 <span data-ttu-id="80c35-222">**如果没有数据轮询表中可用**之后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]生成新的线程来继续轮询操作。</span><span class="sxs-lookup"><span data-stu-id="80c35-222">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="80c35-223">因此，通过一段时间会增加线程计数和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="80c35-223">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="80c35-224">但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续的轮询。</span><span class="sxs-lookup"><span data-stu-id="80c35-224">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="80c35-225">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c35-225">**Resolution**</span></span>  
  
 <span data-ttu-id="80c35-226">我们建议设置**ReceiveTimeout**为最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。</span><span class="sxs-lookup"><span data-stu-id="80c35-226">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="80c35-227">这将确保，内存使用情况和线程计数不会增长过多时间太短。</span><span class="sxs-lookup"><span data-stu-id="80c35-227">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
 <span data-ttu-id="80c35-228">有关详细信息**ReceiveTimeout**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-228">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="80c35-229">指定绑定属性的说明，请参阅[为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="80c35-229">For instructions on specifying binding properties, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c35-230">使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，将超时设置为较大的值不会影响的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="80c35-230">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c35-231">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80c35-231">See Also</span></span>  
[<span data-ttu-id="80c35-232">故障排除 Oracle EBS 适配器</span><span class="sxs-lookup"><span data-stu-id="80c35-232">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)