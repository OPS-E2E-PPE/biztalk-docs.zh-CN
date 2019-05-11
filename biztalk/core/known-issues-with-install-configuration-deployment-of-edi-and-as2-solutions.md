---
title: 有关安装、 配置和部署的 EDI 和 AS2 解决方案的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dee03f0-2447-4cc2-90f4-e9b73caa0f39
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c376709ab9abcd5859e122d9c70a413f4fc89054
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329133"
---
# <a name="known-issues-with-installation-configuration-and-deployment-of-edi-and-as2-solutions"></a><span data-ttu-id="d47fb-102">安装、 配置和部署的 EDI 和 AS2 解决方案的已知的问题</span><span class="sxs-lookup"><span data-stu-id="d47fb-102">Known Issues with Installation, Configuration, and Deployment of EDI and AS2 Solutions</span></span>
<span data-ttu-id="d47fb-103">本主题介绍了部署和管理的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2 解决方案。</span><span class="sxs-lookup"><span data-stu-id="d47fb-103">This topic describes known issues with deployment and management of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 solutions.</span></span>  
  
## <a name="blank-strings-were-imported-for-party-properties"></a><span data-ttu-id="d47fb-104">为参与方属性导入空白字符串</span><span class="sxs-lookup"><span data-stu-id="d47fb-104">Blank Strings Were Imported for Party Properties</span></span>  
 <span data-ttu-id="d47fb-105">**症状**</span><span class="sxs-lookup"><span data-stu-id="d47fb-105">**Symptom**</span></span>  
  
 <span data-ttu-id="d47fb-106">当您从绑定文件将 EDI/AS2 绑定导入 BizTalk 应用程序上时，未导入敏感的参与方属性，如密码或安全/身份验证信息。</span><span class="sxs-lookup"><span data-stu-id="d47fb-106">When you imported EDI/AS2 bindings from a binding file into a BizTalk application, sensitive party properties, such as passwords or security/authentication information, were not imported.</span></span> <span data-ttu-id="d47fb-107">这些属性被设置为空白字符串。</span><span class="sxs-lookup"><span data-stu-id="d47fb-107">Those properties were set to blank strings.</span></span>  
  
 <span data-ttu-id="d47fb-108">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d47fb-108">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d47fb-109">BizTalk Server 不会导入敏感字段的设置。</span><span class="sxs-lookup"><span data-stu-id="d47fb-109">BizTalk Server will not import the settings of sensitive fields.</span></span> <span data-ttu-id="d47fb-110">导入这些设置可以创建一个安全问题。</span><span class="sxs-lookup"><span data-stu-id="d47fb-110">Importing those settings could create a security issue.</span></span>  
  
 <span data-ttu-id="d47fb-111">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d47fb-111">**Resolution**</span></span>  
  
 <span data-ttu-id="d47fb-112">导入到另一台计算机上的绑定后，必须手动设置 EDI 敏感字段的值。</span><span class="sxs-lookup"><span data-stu-id="d47fb-112">You must manually set the values for EDI sensitive fields after importing the bindings onto another computer.</span></span>  
  
## <a name="ftp-adapter-is-not-supported-natively-in-64-bit-mode"></a><span data-ttu-id="d47fb-113">FTP 适配器不支持本机 64 位模式</span><span class="sxs-lookup"><span data-stu-id="d47fb-113">FTP Adapter Is Not Supported Natively in 64-bit Mode</span></span>  
 <span data-ttu-id="d47fb-114">FTP 适配器不能在本机 64 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="d47fb-114">The FTP adapter cannot run in native 64-bit mode.</span></span> <span data-ttu-id="d47fb-115">如果使用 FTP 适配器在 EDI 解决方案中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须在 64 位 Windows 上在 WOW64 上运行它。</span><span class="sxs-lookup"><span data-stu-id="d47fb-115">If you use an FTP adapter in your EDI solution in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you will have to run it on WOW64 on 64-bit Windows.</span></span>  
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="d47fb-116">某些 EDI/AS2 项目是取消配置后仍处于活动状态</span><span class="sxs-lookup"><span data-stu-id="d47fb-116">Some EDI/AS2 Artifacts Are Still Active After Unconfiguring</span></span>  
 <span data-ttu-id="d47fb-117">取消配置的 Microsoft edi/as2 功能后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，与 EDI 和 AS2 处理相关的某些 BizTalk Server 项目仍将在 BizTalk 组配置的上下文中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="d47fb-117">After you unconfigure the Microsoft EDI/AS2 feature of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="d47fb-118">这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="d47fb-118">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="d47fb-119">因此，您将仍然能够执行基本的 EDI 和 AS2 处理后取消 Microsoft EDI/AS2 功能的配置。</span><span class="sxs-lookup"><span data-stu-id="d47fb-119">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the Microsoft EDI/AS2 feature.</span></span> <span data-ttu-id="d47fb-120">若要禁用此功能，应禁用、 停止或删除与 EDI 和 AS2 处理关联的端口。</span><span class="sxs-lookup"><span data-stu-id="d47fb-120">To disable this functionality, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="you-receive-the-error-failed-to-configure-edias2-status-reporting-functionalities"></a><span data-ttu-id="d47fb-121">收到错误"未能配置 'EDI/AS2 状态报告' 功能"</span><span class="sxs-lookup"><span data-stu-id="d47fb-121">You Receive the Error "Failed to Configure EDI/AS2 Status Reporting Functionalities"</span></span>  
 <span data-ttu-id="d47fb-122">**症状**</span><span class="sxs-lookup"><span data-stu-id="d47fb-122">**Symptom**</span></span>  
  
 <span data-ttu-id="d47fb-123">在配置 EDI/AS2 运行时状态报告时，你将收到错误"未能为配置 EDI/AS2 状态报告 ' 功能"。</span><span class="sxs-lookup"><span data-stu-id="d47fb-123">When configuring EDI/AS2 Runtime Status Reporting, you receive error "Failed to Configure EDI/AS2 Status Reporting Functionalities".</span></span>  
  
 <span data-ttu-id="d47fb-124">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d47fb-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d47fb-125">如果以前的配置，然后取消配置 BAM 工具时，会收到此错误。</span><span class="sxs-lookup"><span data-stu-id="d47fb-125">You can receive this error if BAM Tools was previously configured and then unconfigured.</span></span>  
  
 <span data-ttu-id="d47fb-126">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d47fb-126">**Resolution**</span></span>  
  
 <span data-ttu-id="d47fb-127">配置 EDI 和/或 AS2 状态报告前配置 BAM 工具。</span><span class="sxs-lookup"><span data-stu-id="d47fb-127">Configure BAM Tools prior to configuring EDI and/or AS2 status reporting.</span></span>  
  
## <a name="recovering-a-deleted-artifact-from-the-biztalk-edi-application-requires-you-to-reconfigure-the-edias2-runtime"></a><span data-ttu-id="d47fb-128">从 BizTalk EDI 应用程序恢复已删除的项目，需要重新配置 EDI/AS2 运行时</span><span class="sxs-lookup"><span data-stu-id="d47fb-128">Recovering a Deleted Artifact From the BizTalk EDI Application Requires You to Reconfigure the EDI/AS2 Runtime</span></span>  
 <span data-ttu-id="d47fb-129">应避免使用 BizTalk EDI 应用程序用于自己的项目。</span><span class="sxs-lookup"><span data-stu-id="d47fb-129">You should avoid using the BizTalk EDI Application for your own artifacts.</span></span> <span data-ttu-id="d47fb-130">此应用程序包含在 edi/as2 配置期间部署的 EDI/AS2 项目。</span><span class="sxs-lookup"><span data-stu-id="d47fb-130">This application contains the EDI/AS2 artifacts that are deployed during EDI/AS2 configuration.</span></span> <span data-ttu-id="d47fb-131">建议的方法是创建单独的应用程序并添加对 BizTalk EDI 应用程序到应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="d47fb-131">The recommended approach is to create a separate application and add a reference to BizTalk EDI Application to your application.</span></span> <span data-ttu-id="d47fb-132">但是，如果从 BizTalk EDI 应用程序中删除任何 EDI/AS2 项目，则可以恢复从该状态由取消配置 BizTalk edi/as2 运行时从组中每个运行时计算机 （或取消配置 EDI/AS2 运行时从组和取消配置的EDI/AS2 运行时在每个可访问运行时计算机上）。</span><span class="sxs-lookup"><span data-stu-id="d47fb-132">However, if you delete any EDI/AS2 artifact from BizTalk EDI Application, you can recover from that state by unconfiguring the BizTalk EDI/AS2 runtime from each runtime computer in the group (or by unconfiguring the EDI/AS2 runtime from the group and unconfiguring the EDI/AS2 runtime on each of the reachable runtime computers).</span></span> <span data-ttu-id="d47fb-133">建议您不要删除自己的数据库或 EDI/AS2 BAM 活动，以防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="d47fb-133">It is recommended that you do not delete your databases or the EDI/AS2 BAM activities to prevent data loss.</span></span> <span data-ttu-id="d47fb-134">然后可以重新配置要恢复已删除的 edi/as2 项目的组中的所有运行时计算机上的 EDI/AS2 运行时。</span><span class="sxs-lookup"><span data-stu-id="d47fb-134">You can then reconfigure the EDI/AS2 runtime on all the runtime computers in the group to recover the deleted EDI/AS2 artifacts.</span></span>  
  
## <a name="numeric-transaction-set-group-control-and-interchange-control-values-may-be-truncated"></a><span data-ttu-id="d47fb-135">数字事务集、 组控制和交换控制值可能会被截断</span><span class="sxs-lookup"><span data-stu-id="d47fb-135">Numeric Transaction Set, Group Control and Interchange Control Values May be Truncated</span></span>  
 <span data-ttu-id="d47fb-136">交换控制编号的值范围字段，事务集参考编号和组控制编号允许您输入超过最大允许值的值。</span><span class="sxs-lookup"><span data-stu-id="d47fb-136">The value range fields for interchange control numbers, transaction set reference numbers, and group control numbers allow you to enter values that exceed the maximum allowed value.</span></span> <span data-ttu-id="d47fb-137">当您保存该配置时，这些值将被截断的最大值。</span><span class="sxs-lookup"><span data-stu-id="d47fb-137">When you save the configuration, these values will be truncated to the maximum value.</span></span>  
  
 <span data-ttu-id="d47fb-138">适用于 X12 的最大值属性字段是 999999999。</span><span class="sxs-lookup"><span data-stu-id="d47fb-138">The maximum value for X12 property fields is 999999999.</span></span>  
  
 <span data-ttu-id="d47fb-139">EDIFACT 属性字段的最大值是 99999999999999。</span><span class="sxs-lookup"><span data-stu-id="d47fb-139">The maximum value for EDIFACT property fields is 99999999999999.</span></span>  
  
## <a name="control-numbers-are-reset-to-1-after-upgrade"></a><span data-ttu-id="d47fb-140">控制编号重置为 1 的升级后</span><span class="sxs-lookup"><span data-stu-id="d47fb-140">Control Numbers are Reset to 1 After Upgrade</span></span>  
 <span data-ttu-id="d47fb-141">升级后，你可能会注意到所有显示的参与方 EDI 属性中的控制编号已重置为 1 的默认最小值和显示默认最大值为 999999999 (X12) 或 99999999999999 (EDIFACT)。</span><span class="sxs-lookup"><span data-stu-id="d47fb-141">After upgrading, you may notice that all control numbers displayed in the EDI Properties of a party have been reset to the default minimum value of 1 and display a default maximum value of 999999999 (X12) or 99999999999999 (EDIFACT).</span></span> <span data-ttu-id="d47fb-142">任何前缀或后缀值将升级后保持相同。</span><span class="sxs-lookup"><span data-stu-id="d47fb-142">Any prefix or suffix values will remain the same after upgrade.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d47fb-143">显示要用于控制编号的最小值和最大值。</span><span class="sxs-lookup"><span data-stu-id="d47fb-143">shows the minimum and maximum values to be used for the control number.</span></span> <span data-ttu-id="d47fb-144">将升级; 过程中保留当前的控制编号但是它不被显示在参与方的 EDI 属性。</span><span class="sxs-lookup"><span data-stu-id="d47fb-144">The current control number will be preserved during upgrade; however it is not displayed in the EDI Properties of the party.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47fb-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="d47fb-145">See Also</span></span>  
 <span data-ttu-id="d47fb-146">[EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="d47fb-146">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="d47fb-147">[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="d47fb-147">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="d47fb-148">[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72) </span><span class="sxs-lookup"><span data-stu-id="d47fb-148">[Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72) </span></span>  
 [<span data-ttu-id="d47fb-149">用于优化环境的配置后步骤</span><span class="sxs-lookup"><span data-stu-id="d47fb-149">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)