---
title: "企业单一登录故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb54af9f-a6ef-46c1-b987-2019cff3f837
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 450b2df7ec043dfd4bc775cfec7acdec0fb3ca1f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-enterprise-single-sign-on"></a><span data-ttu-id="3f0ee-102">企业单一登录故障排除</span><span class="sxs-lookup"><span data-stu-id="3f0ee-102">Troubleshooting Enterprise Single Sign-On</span></span>
<span data-ttu-id="3f0ee-103">本主题提供有关使用企业单一登录 (SSO) 时所遇到的常见问题的信息。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-103">This topic describes information about common problems you may encounter while using Enterprise Single Sign-On (SSO).</span></span>  
  
 <span data-ttu-id="3f0ee-104">开始对 SSO 环境进行故障排除时，逐一排查下表中的各项可能会很有用，以确保所有组件按预期正常工作：</span><span class="sxs-lookup"><span data-stu-id="3f0ee-104">As you begin to troubleshoot your SSO environment, it may be useful to walk through the items in the following table to ensure all components are working as expected:</span></span>  
  
|<span data-ttu-id="3f0ee-105">问题</span><span class="sxs-lookup"><span data-stu-id="3f0ee-105">Question</span></span>|<span data-ttu-id="3f0ee-106">注释</span><span class="sxs-lookup"><span data-stu-id="3f0ee-106">Comments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="3f0ee-107">应用程序事件日志中是否有来自 SSO 系统的任何内容？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-107">Is there anything in the Application event log from the SSO system?</span></span>|<span data-ttu-id="3f0ee-108">事件日志中的 SSO 消息可帮助您缩小 SSO 系统中问题的范围。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-108">The SSO messages in the event log can help you narrow down the problem in the SSO system.</span></span> <span data-ttu-id="3f0ee-109">SSO 系统中消息的源为 ENTSSO。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-109">The source of the messages from the SSO system is ENTSSO.</span></span> <span data-ttu-id="3f0ee-110">**重要说明：**的许多 SSO 错误和事件显示为警告在事件日志中，不为错误。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-110">**Important:**  Many of the SSO errors and events appear as Warnings in the event log, not as Errors.</span></span> <span data-ttu-id="3f0ee-111">当问题影响 SSO 服务的单个客户端时，SSO 系统生成警告，而问题影响整个 SSO 系统（所有客户端）时，则生成错误。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-111">The SSO system generates a Warning when the problem affects a single client of the SSO service, whereas it generates Errors when the problem affects the entire SSO system (all clients).</span></span>|  
|<span data-ttu-id="3f0ee-112">是否正确安装了SSO 服务？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-112">Is the SSO service installed correctly?</span></span><br /><br /> <span data-ttu-id="3f0ee-113">SSO 服务是否按预期启动？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-113">Does it start as expected?</span></span><br /><br /> <span data-ttu-id="3f0ee-114">SSO 服务在哪个服务帐户下运行？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-114">Under which service account is the SSO service running?</span></span>|<span data-ttu-id="3f0ee-115">确保 SSO 服务正确安装，并且服务帐户是 SSO 管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-115">Ensure the SSO service is correctly installed, and that the service account is member of the SSO administrators group.</span></span>|  
|<span data-ttu-id="3f0ee-116">SSO 数据库位于何处？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-116">Where is the SSO database?</span></span>|<span data-ttu-id="3f0ee-117">使用命令行 **ssoconfig -showdb**。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-117">Use the command line **ssoconfig -showdb**.</span></span> <span data-ttu-id="3f0ee-118">有关此命令的详细信息，请参阅[如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-118">For more information about this command, see [How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md).</span></span>|  
|<span data-ttu-id="3f0ee-119">正在使用哪个 SSO 服务器？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-119">Which SSO server is being used?</span></span>|<span data-ttu-id="3f0ee-120">使用命令行 **ssomanage -showserver**。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-120">Use the command line **ssomanage -showserver**.</span></span> <span data-ttu-id="3f0ee-121">有关此命令的详细信息，请参阅[如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-121">For more information about this command, see [How to Set the SSO Server](../core/how-to-set-the-sso-server.md).</span></span>|  
|<span data-ttu-id="3f0ee-122">SSO 管理员帐户是什么？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-122">What is the SSO Administrator account?</span></span>|<span data-ttu-id="3f0ee-123">使用命令行 **ssomanage –displaydb**。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-123">Use the command line **ssomanage –displaydb**.</span></span> <span data-ttu-id="3f0ee-124">有关此命令的详细信息，请参阅[如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-124">For more information about this command, see [How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md).</span></span>|  
|<span data-ttu-id="3f0ee-125">是否所有项都正确启用？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-125">Is everything correctly enabled?</span></span>|<span data-ttu-id="3f0ee-126">使用命令行 **ssomanage –displaydb**。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-126">Use the command line **ssomanage –displaydb**.</span></span> <span data-ttu-id="3f0ee-127">有关此命令的详细信息，请参阅[如何显示 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-127">For more information about this command, see [How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md).</span></span>|  
|<span data-ttu-id="3f0ee-128">关联应用程序是否存在？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-128">Do the affiliate applications exist?</span></span>|<span data-ttu-id="3f0ee-129">使用命令行 **ssomanage –listapps all**。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-129">Use the command line **ssomanage –listapps all**.</span></span> <span data-ttu-id="3f0ee-130">有关此命令的详细信息，请参阅[列表 Affiliate 应用程序如何](../core/how-to-list-affiliate-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-130">For more information about this command, see [How to List Affiliate Applications](../core/how-to-list-affiliate-applications.md).</span></span>|  
|<span data-ttu-id="3f0ee-131">从外观上看，特定关联应用程序是否正确？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-131">Does the specific affiliate application look correct?</span></span><br /><br /> <span data-ttu-id="3f0ee-132">哪些帐户在使用此关联应用程序？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-132">What accounts are using this affiliate application?</span></span>|<span data-ttu-id="3f0ee-133">使用命令行**ssomanage-displayapp***\<应用程序名称\>*。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-133">Use the command line **ssomanage –displayapp***\<application name\>*.</span></span> <span data-ttu-id="3f0ee-134">有关此命令的详细信息，请参阅[如何列出 Affiliate 应用程序属性](../core/how-to-list-the-properties-of-an-affiliate-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-134">For more information about this command, see [How to List the Properties of an Affiliate Application](../core/how-to-list-the-properties-of-an-affiliate-application.md).</span></span>|  
|<span data-ttu-id="3f0ee-135">此关联应用程序是否有任何映射？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-135">Are there any mappings for this affiliate application?</span></span>|<span data-ttu-id="3f0ee-136">使用命令行**ssomanage-listmappings***\<应用程序名称\>*。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-136">Use the command line **ssomanage –listmappings***\<application name\>*.</span></span> <span data-ttu-id="3f0ee-137">有关此命令的详细信息，请参阅[如何列表用户映射](../core/how-to-list-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-137">For more information about this command, see [How to List User Mappings](../core/how-to-list-user-mappings.md).</span></span>|  
|<span data-ttu-id="3f0ee-138">哪些帐户是 SSO 组的成员？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-138">What accounts are members of the SSO groups?</span></span>|<span data-ttu-id="3f0ee-139">验证所有 SSO 组和帐户的组成员关系。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-139">Verify the group membership for all SSO groups and accounts.</span></span>|  
|<span data-ttu-id="3f0ee-140">SSO 服务器的 COM+ 应用程序是否按预期运行？</span><span class="sxs-lookup"><span data-stu-id="3f0ee-140">Is the COM+ application for the SSO server running as expected?</span></span>|<span data-ttu-id="3f0ee-141">验证 SSO 服务器的 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-141">Verify the COM+ application SSO server.</span></span> <span data-ttu-id="3f0ee-142">**注意：**还可以检查事件日志的详细信息，如事件和警告消息。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-142">**Note:**  You can also check the event log for detailed information, such as event and warning messages.</span></span>|  
  
## <a name="known-issues"></a><span data-ttu-id="3f0ee-143">已知问题</span><span class="sxs-lookup"><span data-stu-id="3f0ee-143">Known Issues</span></span>  
  
#### <a name="entsso-service-fails-to-start"></a><span data-ttu-id="3f0ee-144">ENTSSO 服务启动失败</span><span class="sxs-lookup"><span data-stu-id="3f0ee-144">ENTSSO Service Fails to Start</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3f0ee-145">问题</span><span class="sxs-lookup"><span data-stu-id="3f0ee-145">Problem</span></span>  
 <span data-ttu-id="3f0ee-146">ENTSSO 服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-146">The ENTSSO service fails to start.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3f0ee-147">原因</span><span class="sxs-lookup"><span data-stu-id="3f0ee-147">Cause</span></span>  
 <span data-ttu-id="3f0ee-148">如果 ENTSSO 服务没有在有效的 SSO 管理员帐户下运行，将无法启动。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-148">If the ENTSSO service is not running under a valid SSO Administrator account, it will fail to start.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3f0ee-149">解决方法</span><span class="sxs-lookup"><span data-stu-id="3f0ee-149">Resolution</span></span>  
 <span data-ttu-id="3f0ee-150">请为 ENTSSO 服务指定有效的 SSO 管理员帐户，然后从服务控制管理器 (SCM) 管理单元重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-150">Specify a valid SSO administrator account for the ENTSSO Service and restart the service from Services Control Manager (SCM) snap-in.</span></span>  
  
#### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a><span data-ttu-id="3f0ee-151">依赖于企业单一登录服务 (ENTSSO) 的 BizTalk 服务在重新启动之后无法启动</span><span class="sxs-lookup"><span data-stu-id="3f0ee-151">BizTalk Services Dependent on the Enterprise Single Sign-On Service (ENTSSO) fail to start after a reboot</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3f0ee-152">问题</span><span class="sxs-lookup"><span data-stu-id="3f0ee-152">Problem</span></span>  
 <span data-ttu-id="3f0ee-153">BTSSvc$BizTalkServerApplication 依赖于企业单一登录服务 (ENTSSO)，且在重新启动之后的启动过程中可能超时。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-153">BTSSvc$BizTalkServerApplication has a dependency on the Enterprise Single Sign-On Service (ENTSSO) and may timeout during start up after a reboot.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3f0ee-154">原因</span><span class="sxs-lookup"><span data-stu-id="3f0ee-154">Cause</span></span>  
 <span data-ttu-id="3f0ee-155">企业单一登录服务可能需要约 3 分钟时间才能启动。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-155">The Enterprise Single Sign-On Service may take around 3 minutes to start.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3f0ee-156">解决方法</span><span class="sxs-lookup"><span data-stu-id="3f0ee-156">Resolution</span></span>  
 <span data-ttu-id="3f0ee-157">通过“自动(延迟的启动)”启动类型选项配置“BizTalk 服务 BizTalk 组: BizTalkServerApplication”服务。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-157">Configure the “BizTalk Service BizTalk Group: BizTalkServerApplication” service with the Automatic (Delayed Start) startup type option.</span></span> <span data-ttu-id="3f0ee-158">这将在所有自动服务完成其启动例程后开始启动服务。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-158">This will initiate the start of the service after all Automatic services have completed their startup routines.</span></span>  
  
#### <a name="cannot-access-an-affiliate-application"></a><span data-ttu-id="3f0ee-159">无法访问关联应用程序</span><span class="sxs-lookup"><span data-stu-id="3f0ee-159">Cannot Access an Affiliate Application</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3f0ee-160">问题</span><span class="sxs-lookup"><span data-stu-id="3f0ee-160">Problem</span></span>  
 <span data-ttu-id="3f0ee-161">如果与关联应用程序关联的应用程序管理员帐户无效，则企业单一登录禁用关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-161">The Enterprise Single Sign-On service disables an affiliate application if the application administrator account associated with it is not valid.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3f0ee-162">原因</span><span class="sxs-lookup"><span data-stu-id="3f0ee-162">Cause</span></span>  
 <span data-ttu-id="3f0ee-163">SSO 应用程序管理员帐户无效。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-163">The SSO application administrator account is not valid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3f0ee-164">解决方法</span><span class="sxs-lookup"><span data-stu-id="3f0ee-164">Resolution</span></span>  
 <span data-ttu-id="3f0ee-165">在创建关联应用程序之前，请确保 SSO 应用程序管理员帐户有效。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-165">Ensure that the SSO application administrator account is valid before you create an affiliate application.</span></span> <span data-ttu-id="3f0ee-166">然后，您必须使关联应用程序能够使用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-166">You must then enable the affiliate application to use the application.</span></span>  
  
#### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a><span data-ttu-id="3f0ee-167">连接到客户端计算机时发生 RPC 错误</span><span class="sxs-lookup"><span data-stu-id="3f0ee-167">RPC Error Occurs When Connecting to a Client Computer</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3f0ee-168">问题</span><span class="sxs-lookup"><span data-stu-id="3f0ee-168">Problem</span></span>  
 <span data-ttu-id="3f0ee-169">当用户运行命令，如**ssomanage-displayapp***\<applicationname\>*，其中计算机尝试连接到远程的 SSO 服务器以检索信息，它们收到以下错误： 错误： 0x800706BA: RPC 服务器不可用。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-169">When a user runs a command such as **ssomanage -displayapp***\<applicationname\>*, where the computer attempt to connect to a remote SSO Server to retrieve the information, they receive the following error: ERROR: 0x800706BA: The RPC server is unavailable.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3f0ee-170">原因</span><span class="sxs-lookup"><span data-stu-id="3f0ee-170">Cause</span></span>  
 <span data-ttu-id="3f0ee-171">当用户指定了错误的服务器信息时，或者当 SSO 服务在远程服务器上不可用时，会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-171">This error occurs when the user specifies the wrong server information, or when the SSO Service is not available on the remote server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3f0ee-172">解决方法</span><span class="sxs-lookup"><span data-stu-id="3f0ee-172">Resolution</span></span>  
  
-   <span data-ttu-id="3f0ee-173">按照中的步骤[如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md)若要确保你连接到正确的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-173">Follow the steps in [How to Set the SSO Server](../core/how-to-set-the-sso-server.md) to make sure you are connected to the correct SSO Server.</span></span>  
  
-   <span data-ttu-id="3f0ee-174">确保 SSO 服务已启用并且运行在您要连接到的 SSO 服务器中。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-174">Make sure the SSO Service is enabled and running in the SSO Server to which you are connecting.</span></span>  
  
#### <a name="master-secret-is-missing-or-corrupt"></a><span data-ttu-id="3f0ee-175">缺少主密钥，或者主密钥已损坏</span><span class="sxs-lookup"><span data-stu-id="3f0ee-175">Master Secret Is Missing or Corrupt</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="3f0ee-176">问题</span><span class="sxs-lookup"><span data-stu-id="3f0ee-176">Problem</span></span>  
 <span data-ttu-id="3f0ee-177">缺少主密钥，或者主密钥已损坏。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-177">The master secret is missing or corrupt.</span></span> <span data-ttu-id="3f0ee-178">主密钥通常在配置期间生成。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-178">It normally generates during configuration.</span></span> <span data-ttu-id="3f0ee-179">如果缺少该密钥，当企业单一登录服务启动时事件日志中便会显示下列消息之一。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-179">If the secret is missing, one of the following messages will display in the event log as the Enterprise Single Sign-On service starts.</span></span>  
  
 <span data-ttu-id="3f0ee-180">MessageId=10520</span><span class="sxs-lookup"><span data-stu-id="3f0ee-180">MessageId=10520</span></span>  
  
 <span data-ttu-id="3f0ee-181">Severity=Warning</span><span class="sxs-lookup"><span data-stu-id="3f0ee-181">Severity=Warning</span></span>  
  
 <span data-ttu-id="3f0ee-182">SSO_WARN_NO_SECRETS</span><span class="sxs-lookup"><span data-stu-id="3f0ee-182">SSO_WARN_NO_SECRETS</span></span>  
  
 <span data-ttu-id="3f0ee-183">MessageId=10565</span><span class="sxs-lookup"><span data-stu-id="3f0ee-183">MessageId=10565</span></span>  
  
 <span data-ttu-id="3f0ee-184">Severity=Error</span><span class="sxs-lookup"><span data-stu-id="3f0ee-184">Severity=Error</span></span>  
  
 <span data-ttu-id="3f0ee-185">SSO_ERROR_SECRET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="3f0ee-185">SSO_ERROR_SECRET_VALIDATE_FAILED</span></span>  
  
 <span data-ttu-id="3f0ee-186">MessageId=10521</span><span class="sxs-lookup"><span data-stu-id="3f0ee-186">MessageId=10521</span></span>  
  
 <span data-ttu-id="3f0ee-187">Severity=Error</span><span class="sxs-lookup"><span data-stu-id="3f0ee-187">Severity=Error</span></span>  
  
 <span data-ttu-id="3f0ee-188">SSO_ERROR_SECRETS_NOT_LOADED</span><span class="sxs-lookup"><span data-stu-id="3f0ee-188">SSO_ERROR_SECRETS_NOT_LOADED</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="3f0ee-189">原因</span><span class="sxs-lookup"><span data-stu-id="3f0ee-189">Cause</span></span>  
 <span data-ttu-id="3f0ee-190">如果企业单一登录服务 (SSO) 在某个服务帐户下运行时生成密钥，又更改了该服务帐户，则可能出现此问题。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-190">This problem can occur if a secret is generated while the Enterprise Single Sign-On service (SSO) was running under one service account, and then the service account was changed.</span></span> <span data-ttu-id="3f0ee-191">但是，该密钥以加密的形式存储在注册表中，并且使用基于此服务帐户标识（ENTSSO 在该帐户下运行）的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-191">The secret is stored in the registry in encrypted form, and is encrypted using a key based on the identity of the service account (which ENTSSO runs under).</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="3f0ee-192">解决方法</span><span class="sxs-lookup"><span data-stu-id="3f0ee-192">Resolution</span></span>  
 <span data-ttu-id="3f0ee-193">将 ENTSSO 在其下运行的服务帐户更改为创建主密钥时的原始服务帐户。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-193">Change the service account ENTSSO is running under to the original service account when the master secret was created.</span></span>  
  
 <span data-ttu-id="3f0ee-194">更改 ENTSSO 服务帐户：</span><span class="sxs-lookup"><span data-stu-id="3f0ee-194">To change the ENTSSO service account:</span></span>  
  
1.  <span data-ttu-id="3f0ee-195">备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-195">Back up the master secret.</span></span> <span data-ttu-id="3f0ee-196">有关详细信息，请参阅[如何返回向上主密钥](../core/how-to-back-up-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-196">For more information, see [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2.  <span data-ttu-id="3f0ee-197">停止企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-197">Stop Enterprise Single Sign-On Services.</span></span>  
  
3.  <span data-ttu-id="3f0ee-198">更改服务帐户。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-198">Change the service account.</span></span>  
  
4.  <span data-ttu-id="3f0ee-199">重新启动 SSO，并忽略有关受损密钥的任何事件日志错误。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-199">Restart SSO and ignore any event log errors about a corrupted secret.</span></span>  
  
5.  <span data-ttu-id="3f0ee-200">还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-200">Restore the master secret.</span></span> <span data-ttu-id="3f0ee-201">有关详细信息，请参阅[如何还原主密钥](../core/how-to-restore-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0ee-201">For more information, see [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0ee-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0ee-202">See Also</span></span>  
 [<span data-ttu-id="3f0ee-203">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3f0ee-203">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)