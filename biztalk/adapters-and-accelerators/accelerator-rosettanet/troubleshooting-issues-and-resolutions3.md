---
title: "疑难解答： 问题和 Resolutions3 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 40f59f54-183e-43db-afb5-0a45b437697f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed990dd60ab65c7b85284a9eeadd4b27de3136f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-issues-and-resolutions"></a><span data-ttu-id="4d418-102">疑难解答： 问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="4d418-102">Troubleshooting: Issues and Resolutions</span></span>
<span data-ttu-id="4d418-103">本主题讲述与运行 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 相关的问题。</span><span class="sxs-lookup"><span data-stu-id="4d418-103">This topic addresses issues related to running [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="4d418-104">每个问题都详细描述了一种特定的症状、其可能的原因以及解决方案。</span><span class="sxs-lookup"><span data-stu-id="4d418-104">The individual issues detail a specific symptom, a possible cause, and a solution.</span></span>  
  
## <a name="error-publishing-a-batch-of-n-messages"></a><span data-ttu-id="4d418-105">发布一批（“n”条）消息时出错</span><span class="sxs-lookup"><span data-stu-id="4d418-105">Error publishing a batch of "n" messages</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-106">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-106">Symptom</span></span>  
 <span data-ttu-id="4d418-107">在事件日志中接收到以下或类似的错误：</span><span class="sxs-lookup"><span data-stu-id="4d418-107">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4d418-108">消息引擎向传输适配器“BizTalk HTTP Receiver”的 MessageBox 数据库发布包含“n”条消息的批时遇到了错误。</span><span class="sxs-lookup"><span data-stu-id="4d418-108">The Messaging Engine encountered an error publishing a batch of "n" messages to the Message Box database for the transport adapter "BizTalk HTTP Receiver".</span></span> <span data-ttu-id="4d418-109">请使用运行状况与活动跟踪工具来了解有关此故障的详细信息，并检查是否正确配置了终结点绑定。</span><span class="sxs-lookup"><span data-stu-id="4d418-109">Please refer to Health and Activity Tracking tool for more detailed information on this failure and check the endpoint bindings are correctly configured.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-110">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-110">Possible Cause</span></span>  
 <span data-ttu-id="4d418-111">此错误可能由以下某个原因引起：</span><span class="sxs-lookup"><span data-stu-id="4d418-111">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="4d418-112">缺少解密证书</span><span class="sxs-lookup"><span data-stu-id="4d418-112">Missing decryption certificate</span></span>  
  
-   <span data-ttu-id="4d418-113">未正确加密消息</span><span class="sxs-lookup"><span data-stu-id="4d418-113">Incorrectly encrypted message</span></span>  
  
-   <span data-ttu-id="4d418-114">未经授权的消息（未将源识别为有效的合作伙伴）</span><span class="sxs-lookup"><span data-stu-id="4d418-114">Unauthorized message (source not recognized as a valid partner)</span></span>  
  
-   <span data-ttu-id="4d418-115">消息未能通过对任意标头部分（前导头、传递头或服务头）的验证。</span><span class="sxs-lookup"><span data-stu-id="4d418-115">Message failing validation of any header part: preamble, delivery header, or service header.</span></span>  
  
 <span data-ttu-id="4d418-116">此消息之前可能有另一个详细说明原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="4d418-116">This message may be preceded by another error message that details the cause.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-117">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-117">Solution</span></span>  
 <span data-ttu-id="4d418-118">请查看随错误消息提供的详细信息，以获取其他帮助。</span><span class="sxs-lookup"><span data-stu-id="4d418-118">Review the details provided with the error message for additional help.</span></span> <span data-ttu-id="4d418-119">重新启动[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ 可能解决此问题。</span><span class="sxs-lookup"><span data-stu-id="4d418-119">Restarting [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ may resolve this issue.</span></span>  
  
## <a name="you-cannot-unenlist-all-artifacts"></a><span data-ttu-id="4d418-120">无法取消登记所有项目</span><span class="sxs-lookup"><span data-stu-id="4d418-120">You cannot unenlist all artifacts</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-121">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-121">Symptom</span></span>  
 <span data-ttu-id="4d418-122">运行 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean 实用工具不能取消登记所有项目。</span><span class="sxs-lookup"><span data-stu-id="4d418-122">Running the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean utility does not unenlist all artifacts.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-123">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-123">Possible Cause</span></span>  
 <span data-ttu-id="4d418-124">如果在从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]® 管理控制台 (MMC) 中删除协议及合作伙伴之前运行 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Clean 实用工具，则 BtarnClean 实用工具将无法取消登记所有项目，因为这些项目仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="4d418-124">If you run the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean utility before deleting agreements and partners from the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® Management Console (MMC), the BtarnClean utility will not be able to unenlist all artifacts because they are still used.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-125">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-125">Solution</span></span>  
  
##### <a name="to-remove-artifacts-using-the-loopback-utility"></a><span data-ttu-id="4d418-126">使用环回实用工具删除项目</span><span class="sxs-lookup"><span data-stu-id="4d418-126">To remove artifacts using the Loopback utility</span></span>  
  
1.  <span data-ttu-id="4d418-127">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="4d418-127">At the command prompt, type:</span></span>  
  
    ```  
    lookback.exe /disable <home org or partner>  
    ```  
  
2.  <span data-ttu-id="4d418-128">运行 BtarnClean.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="4d418-128">Run the BtarnClean.exe file.</span></span>  
  
3.  <span data-ttu-id="4d418-129">在 BizTalk 浏览器中，删除参与方。</span><span class="sxs-lookup"><span data-stu-id="4d418-129">In BizTalk Explorer, delete the parties.</span></span>  
  
## <a name="installing-btarn-on-a-computer-without-biztalk-server-causes-missing-files"></a><span data-ttu-id="4d418-130">在未安装 BizTalk Server 的计算机上安装 BTARN 会导致文件丢失</span><span class="sxs-lookup"><span data-stu-id="4d418-130">Installing BTARN on a computer without BizTalk Server causes missing files</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-131">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-131">Symptom</span></span>  
 <span data-ttu-id="4d418-132">运行 ConfigFramework.exe 文件生成不具有的计算机上没有结果[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]或[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="4d418-132">Running the ConfigFramework.exe file yields no results on a computer that does not have [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] or [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed.</span></span> <span data-ttu-id="4d418-133">只能将此 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 配置作为 HTTP 客户端使用。</span><span class="sxs-lookup"><span data-stu-id="4d418-133">You can only use this [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration as an HTTP client.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-134">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-134">Possible Cause</span></span>  
 <span data-ttu-id="4d418-135">安装过程中缺少两个 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="4d418-135">Two DLL files are missing from the installation.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-136">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-136">Solution</span></span>  
 <span data-ttu-id="4d418-137">在计算机上安装 SQLXML，然后手动将 Msxml4.dll 和 Atl71.dll 文件复制到 System 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4d418-137">Install SQLXML on the computer, and then manually copy the Msxml4.dll and Atl71.dll files to the System folder.</span></span>  
  
## <a name="you-receive-an-access-error-when-attempting-to-change-the-btarn-configuration"></a><span data-ttu-id="4d418-138">试图更改 BTARN 配置时出现访问错误</span><span class="sxs-lookup"><span data-stu-id="4d418-138">You receive an access error when attempting to change the BTARN configuration</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-139">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-139">Symptom</span></span>  
 <span data-ttu-id="4d418-140">使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台导入配置文件时收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="4d418-140">You receive the following error message when you import a configuration file using the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console:</span></span>  
  
 <span data-ttu-id="4d418-141">无法将发送端口“RNSTT.Async”的主传输的传输类型数据存储到配置存储。</span><span class="sxs-lookup"><span data-stu-id="4d418-141">Could not store transport type data for Primary Transport of Send Port 'RNSTT.Async' to config store.</span></span> <span data-ttu-id="4d418-142">拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="4d418-142">Access is denied.</span></span>  
  
 <span data-ttu-id="4d418-143">在试图通过如创建新的合作伙伴等操作来更改配置时，也可能会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="4d418-143">You can also receive this error when you try to change the configuration, such as by creating a new partner.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-144">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-144">Possible Cause</span></span>  
 <span data-ttu-id="4d418-145">当前用户不是 BizTalk Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="4d418-145">The current user is not a member of the BizTalk Administrators group.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-146">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-146">Solution</span></span>  
 <span data-ttu-id="4d418-147">确保当前用户为 BizTalk Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="4d418-147">Make sure that the current user is a member of the BizTalk Administrators group.</span></span>  
  
## <a name="you-receive-bam-errors"></a><span data-ttu-id="4d418-148">出现 BAM 错误</span><span class="sxs-lookup"><span data-stu-id="4d418-148">You receive BAM errors</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-149">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-149">Symptom</span></span>  
 <span data-ttu-id="4d418-150">事件查看器中出现以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="4d418-150">You receive the following error messages in the Event Viewer:</span></span>  
  
 <span data-ttu-id="4d418-151">跟踪消息活动时出错。</span><span class="sxs-lookup"><span data-stu-id="4d418-151">Error happened in tracking Message activity.</span></span> <span data-ttu-id="4d418-152">错误消息为“存储过程不存在”。</span><span class="sxs-lookup"><span data-stu-id="4d418-152">Error message is Stored Procedure Does Not Exist.</span></span>  
  
 <span data-ttu-id="4d418-153">- 或 -</span><span class="sxs-lookup"><span data-stu-id="4d418-153">-or-</span></span>  
  
 <span data-ttu-id="4d418-154">终止具有 id BAM 消息活动中的错误* \<ID 号 >*。</span><span class="sxs-lookup"><span data-stu-id="4d418-154">Error in terminating BAM message activity with id *\<ID number>*.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-155">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-155">Possible Cause</span></span>  
 <span data-ttu-id="4d418-156">未安装业务活动监视 (BAM) 跟踪工具。</span><span class="sxs-lookup"><span data-stu-id="4d418-156">The Business Activity Monitoring (BAM) tracking tool is not installed.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-157">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-157">Solution</span></span>  
 <span data-ttu-id="4d418-158">安装跟踪工具使用 BAM**自定义安装**选项。</span><span class="sxs-lookup"><span data-stu-id="4d418-158">Install the BAM tracking tool using the **Custom Installation** option.</span></span> <span data-ttu-id="4d418-159">如果不需要 BAM 功能，可忽略这些消息，或使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="4d418-159">If you do not need BAM functionality, you can ignore these messages or disable tracking using the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="4d418-160">禁用跟踪后，必须重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 和 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="4d418-160">After you disable tracking, you must restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Internet and Information Services (IIS).</span></span>  
  
## <a name="your-xsd-schema-does-not-display-properly-in-biztalk-editor"></a><span data-ttu-id="4d418-161">XSD 架构在 BizTalk 编辑器中显示不正确</span><span class="sxs-lookup"><span data-stu-id="4d418-161">Your XSD Schema does not display properly in BizTalk Editor</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-162">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-162">Symptom</span></span>  
 <span data-ttu-id="4d418-163">无法在 BizTalk 编辑器中正确查看架构的内容。</span><span class="sxs-lookup"><span data-stu-id="4d418-163">You cannot view the content of a schema properly in BizTalk Editor.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-164">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-164">Possible Cause</span></span>  
 <span data-ttu-id="4d418-165">该架构缺少 `displayroot_reference` 元素的 `schemaInfo` 属性。</span><span class="sxs-lookup"><span data-stu-id="4d418-165">The schema is missing the `displayroot_reference` attribute for the `schemaInfo` element.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-166">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-166">Solution</span></span>  
 <span data-ttu-id="4d418-167">在记事本或其他文本编辑器中打开该架构，然后将 `displayroot_reference` 属性添加到 `schemaInfo` 元素中。</span><span class="sxs-lookup"><span data-stu-id="4d418-167">Open the schema in Notepad or another text editor and add the `displayroot_reference` attribute to the `schemaInfo` element.</span></span> <span data-ttu-id="4d418-168">`displayroot_reference` 属性的值应与 `root_reference` 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="4d418-168">The value of the `displayroot_reference` attribute should be the same as the `root_reference` attribute.</span></span>  
  
 <span data-ttu-id="4d418-169">例如：</span><span class="sxs-lookup"><span data-stu-id="4d418-169">For example:</span></span>  
  
 <span data-ttu-id="4d418-170">\<schemaInfo document_type ="4A1"版本 ="V02_00"xmlns ="http://schemas.microsoft.com/BizTalk/2003" *displayroot_reference ="Pip4A1StrategicForecastNotification"* root_reference ="Pip4A1StrategicForecastNotification"/ ></span><span class="sxs-lookup"><span data-stu-id="4d418-170">\<schemaInfo document_type="4A1" version="V02_00" xmlns="http://schemas.microsoft.com/BizTalk/2003" *displayroot_reference="Pip4A1StrategicForecastNotification"* root_reference="Pip4A1StrategicForecastNotification" /></span></span>  
  
## <a name="404-not-found-error-when-sending-a-http-request"></a><span data-ttu-id="4d418-171">发送 HTTP 请求时出现“404 找不到”错误</span><span class="sxs-lookup"><span data-stu-id="4d418-171">404 Not found error when sending a HTTP request</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-172">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-172">Symptom</span></span>  
 <span data-ttu-id="4d418-173">发送 HTTP 请求时收到以下或类似的错误：</span><span class="sxs-lookup"><span data-stu-id="4d418-173">You receive the following or similar errors when sending a HTTP request:</span></span>  
  
 <span data-ttu-id="4d418-174">远程服务器返回错误：(404) 找不到。</span><span class="sxs-lookup"><span data-stu-id="4d418-174">The remote server returned an error: (404) Not Found.</span></span>  
  
 <span data-ttu-id="4d418-175">无法将消息发送到 ../BTSHttpReceive.dll。</span><span class="sxs-lookup"><span data-stu-id="4d418-175">Message cannot be sent to ../BTSHttpReceive.dll.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-176">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-176">Possible Cause</span></span>  
 <span data-ttu-id="4d418-177">Internet 信息服务 (IIS) 中未配置 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) 扩展 DLL (BTSHttpReceive.dll)。</span><span class="sxs-lookup"><span data-stu-id="4d418-177">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) extension DLL (BTSHttpReceive.dll) has not been configured in Internet Information Services (IIS).</span></span> <span data-ttu-id="4d418-178">如果未配置 HwsMessages HttpReceive Web Services 扩展或配置了此 Web Services 扩展但不允许使用它，则发生此错误。</span><span class="sxs-lookup"><span data-stu-id="4d418-178">This occurs if the HwsMessages HttpReceive web service extension is not configured and if this web service extension is configured, but not allowed.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-179">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-179">Solution</span></span>  
 <span data-ttu-id="4d418-180">若要确定是否配置了 HwsMessages HttpReceive Web Services 扩展，以及在配置后如何允许使用它，请执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="4d418-180">To determine whether the HwsMessages HttpReceive web service extension is configured, and if it is not configured, to allow it, perform the following procedure.</span></span>  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a><span data-ttu-id="4d418-181">在 IIS 中配置 BizTalk ISAPI 扩展 DLL</span><span class="sxs-lookup"><span data-stu-id="4d418-181">To configure the BizTalk ISAPI extension DLL in IIS</span></span>  
  
1.  <span data-ttu-id="4d418-182">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="4d418-182">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="4d418-183">展开**\<计算机名称 > （本地计算机）**，然后单击**Web 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="4d418-183">Expand **\<computer name> (local computer)**, and then click **Web Service Extensions**.</span></span>  
  
3.  <span data-ttu-id="4d418-184">在**Web 服务扩展**窗格中，验证是否允许 HwsMessages HttpReceive 的状态。</span><span class="sxs-lookup"><span data-stu-id="4d418-184">In the **Web Service Extension** pane, verify that the status for HwsMessages HttpReceive is Allowed.</span></span> <span data-ttu-id="4d418-185">如果没有，请右键单击**HwsMessages HttpReceive**，然后单击**允许**。</span><span class="sxs-lookup"><span data-stu-id="4d418-185">If not, right-click **HwsMessages HttpReceive**, and then click **Allow**.</span></span>  
  
 <span data-ttu-id="4d418-186">如果未配置 HwsMessages HttpReceive Web Services 扩展（它没有包含在 IIS 管理器的“Web Services 扩展”列表中），则请执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="4d418-186">If the HwsMessages HttpReceive web service extension is not configured (it is not included in the Web Service Extensions list in IIS Manager), perform the following procedure.</span></span>  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a><span data-ttu-id="4d418-187">在 IIS 中配置 BizTalk ISAPI 扩展 DLL</span><span class="sxs-lookup"><span data-stu-id="4d418-187">To configure the BizTalk ISAPI extension DLL in IIS</span></span>  
  
1.  <span data-ttu-id="4d418-188">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="4d418-188">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="4d418-189">展开**\<计算机名称 > （本地计算机）**，右键单击**Web 服务扩展**，然后单击**添加一个新的 Web 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="4d418-189">Expand **\<computer name> (local computer)**, right-click **Web Service Extensions**, and then click **Add a new Web service extension**.</span></span>  
  
3.  <span data-ttu-id="4d418-190">在**新建 Web 服务扩展**对话框中，在**扩展名**框中，键入**BizTalk ISAPI 扩展**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="4d418-190">In the **New Web Service Extension** dialog box, in the **Extension Name** box, type **BizTalk ISAPI Extension**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="4d418-191">在**Add File**对话框中，在**文件路径**框中，键入**\<驱动器 >: files\microsoft BizTalk Server\<版本 > \HttpReceive\BTSHttpReceive.dll**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4d418-191">In the **Add File** dialog box, in the **Path to file** box, type **\<drive>:\Program Files\Microsoft BizTalk Server \<version>\HttpReceive\BTSHttpReceive.dll**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4d418-192">在**新建 Web 服务扩展**对话框中，选择**设置扩展状态为允许**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4d418-192">In the **New Web Service Extension** dialog box, select **Set extension status to Allowed**, and then click **OK**.</span></span>  
  
## <a name="an-access-violation-occurs-when-running-the-configuration-wizard"></a><span data-ttu-id="4d418-193">运行配置向导时出现访问冲突</span><span class="sxs-lookup"><span data-stu-id="4d418-193">An access violation occurs when running the Configuration Wizard</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-194">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-194">Symptom</span></span>  
 <span data-ttu-id="4d418-195">在事件日志中接收到以下或类似的错误：</span><span class="sxs-lookup"><span data-stu-id="4d418-195">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4d418-196">使用用户帐户“\HostSvc”配置的 BizTalk 独立主机实例要么未运行，要么在此计算机上不存在。</span><span class="sxs-lookup"><span data-stu-id="4d418-196">A BizTalk isolated host instance configured with the user account '\HostSvc' was either not running or does not exist on this computer.</span></span> <span data-ttu-id="4d418-197">请使用 BizTalk 管理控制台新建一个独立主机，或者重新配置一个现有主机，使其以“\hostsvc”的身份运行。</span><span class="sxs-lookup"><span data-stu-id="4d418-197">Use the BizTalk Administration Console to create a new isolated host or reconfigure an existing to run as '\hostsvc'.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-198">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-198">Possible Cause</span></span>  
 <span data-ttu-id="4d418-199">若要运行配置向导，用户应配置为\<*计算机名称*> \hostsvc，不是 \hostsvc。</span><span class="sxs-lookup"><span data-stu-id="4d418-199">To run the Configuration Wizard, the user should be configured as '\<*machine name*>\hostsvc', not '\hostsvc'.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-200">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-200">Solution</span></span>  
 <span data-ttu-id="4d418-201">打开 BizTalk 管理控制台中，并更改 \hostsvc 的帐户下运行的主机，以便它们在帐户下运行\<*计算机名称*> \hostsvc。</span><span class="sxs-lookup"><span data-stu-id="4d418-201">Open the BizTalk Administration Console, and change hosts that are running under the account '\hostsvc', so that they run under the account '\<*machine name*>\hostsvc'.</span></span>  
  
## <a name="you-receive-an-error-when-importing-and-compiling-a-rosettanet-next-generation-pip-schema"></a><span data-ttu-id="4d418-202">导入和编译 RosettaNet 下一代 PIP 架构时出现错误</span><span class="sxs-lookup"><span data-stu-id="4d418-202">You receive an error when importing and compiling a RosettaNet Next Generation PIP schema</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-203">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-203">Symptom</span></span>  
 <span data-ttu-id="4d418-204">在事件日志中接收到以下或类似的错误：</span><span class="sxs-lookup"><span data-stu-id="4d418-204">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4d418-205">错误 CS0234：类或命名空间“RosettaNet.Schemas.System”中不存在类型名或命名空间名“SerializableAttribute”（是否缺少程序集引用？）。</span><span class="sxs-lookup"><span data-stu-id="4d418-205">error CS0234: The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'RosettaNet.Schemas.System' (are you missing an assembly reference?).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-206">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-206">Possible Cause</span></span>  
 <span data-ttu-id="4d418-207">例如，其中一个架构 StandardDocumentHeader.xsd 有一个名为 RosettaNet.Schemas.System 的 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4d418-207">One of your schemas, for example, StandardDocumentHeader.xsd, has a [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] namespace of RosettaNet.Schemas.System.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-208">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-208">Solution</span></span>  
 <span data-ttu-id="4d418-209">删除此架构的 [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 命名空间中的“System”，以便命名空间名为 RosettaNet.Schemas。</span><span class="sxs-lookup"><span data-stu-id="4d418-209">Remove the "System" from the [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] namespace for the schema, so that the namespace is RosettaNet.Schemas.</span></span>  
  
## <a name="you-receive-an-error-when-trying-to-manually-deploy-the-bam-package"></a><span data-ttu-id="4d418-210">试图手动部署 BAM 软件包时出现错误</span><span class="sxs-lookup"><span data-stu-id="4d418-210">You receive an error when trying to manually deploy the BAM Package</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-211">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-211">Symptom</span></span>  
 <span data-ttu-id="4d418-212">当你手动尝试部署的 BAM 包[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，你收到一个错误，指示不能将部署包。</span><span class="sxs-lookup"><span data-stu-id="4d418-212">When you manually try to deploy the BAM package for [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], you receive an error indicating that you cannot deploy the package.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-213">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-213">Possible Cause</span></span>  
 <span data-ttu-id="4d418-214">系统上所安装的 DTS 软件包 BAM_DM_Process 和 BAM_DM_Message 妨碍了 BAM 软件包的部署。</span><span class="sxs-lookup"><span data-stu-id="4d418-214">The DTS packages BAM_DM_Process and BAM_DM_Message are installed on your system, preventing deployment of the BAM package.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-215">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-215">Solution</span></span>  
  
##### <a name="to-recover-from-the-error-condition-and-deploy-the-bam-package"></a><span data-ttu-id="4d418-216">从错误情况中恢复并部署 BAM 软件包</span><span class="sxs-lookup"><span data-stu-id="4d418-216">To recover from the error condition and deploy the BAM package</span></span>  
  
1.  <span data-ttu-id="4d418-217">单击**启动**，指向**所有程序**，指向**Microsoft SQL Server**，然后单击**企业管理器**。</span><span class="sxs-lookup"><span data-stu-id="4d418-217">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Enterprise Manager**.</span></span>  
  
2.  <span data-ttu-id="4d418-218">在企业管理器中，展开**Microsoft SQL Server**， **SQL Server 组**， **（本地） (Windows NT)**，和**Data Transformation Services**.</span><span class="sxs-lookup"><span data-stu-id="4d418-218">In Enterprise Manager, expand **Microsoft SQL Servers**, **SQL Server Group**, **(local) (Windows NT)**, and **Data Transformation Services**.</span></span>  
  
3.  <span data-ttu-id="4d418-219">单击**本地包**，右键单击**BAM_DM_Message**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="4d418-219">Click **Local Packages**, right-click **BAM_DM_Message**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="4d418-220">右键单击**BAM_DM_Process**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="4d418-220">Right-click **BAM_DM_Process**, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="4d418-221">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4d418-221">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="4d418-222">在命令提示符下键入以下代码以将跟踪文件中，部署，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4d418-222">At the command prompt, type the following code to deploy the tracking file, and then click **OK**.</span></span>  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server <version>\Tracking  
    bm deploy all  "%ProgramFiles%\Microsoft BizTalk <version> Accelerator for RosettaNet\BAMTracking\tracking.xml"  
    ```  
  
## <a name="you-receive-an-error-when-adding-a-new-pip"></a><span data-ttu-id="4d418-223">添加新的 PIP 时出现错误</span><span class="sxs-lookup"><span data-stu-id="4d418-223">You receive an error when adding a new PIP</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-224">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-224">Symptom</span></span>  
 <span data-ttu-id="4d418-225">在事件日志中接收到以下或类似的错误：</span><span class="sxs-lookup"><span data-stu-id="4d418-225">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4d418-226">UNP.SCON.VALERR：验证服务内容时出错。</span><span class="sxs-lookup"><span data-stu-id="4d418-226">UNP.SCON.VALERR: A failure occurred while validating the service content.</span></span>  
  
 <span data-ttu-id="4d418-227">详细信息：按消息类型查找文档规范失败。</span><span class="sxs-lookup"><span data-stu-id="4d418-227">Details: Finding document specification by message type failed.</span></span> <span data-ttu-id="4d418-228">请验证已正确部署架构。</span><span class="sxs-lookup"><span data-stu-id="4d418-228">Verify that the schema is deployed properly.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-229">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-229">Possible Cause</span></span>  
 <span data-ttu-id="4d418-230">实例 Pip4A5NotifyofForecastReply 的已部署架构的文档命名空间或根节点属性不正确。</span><span class="sxs-lookup"><span data-stu-id="4d418-230">Either the document namespace or the root node property the deployed schema for the instance Pip4A5NotifyofForecastReply is incorrect.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-231">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-231">Solution</span></span>  
 <span data-ttu-id="4d418-232">请验证实例 Pip4A5NotifyofForecastReply 的已部署架构的文档命名空间和根节点属性正确。</span><span class="sxs-lookup"><span data-stu-id="4d418-232">Verify that the document namespace and the root node property for the deployed schema for instance Pip4A5NotifyofForecastReply is correct.</span></span>  
  
## <a name="error-during-the-configuration-of-btarn-at-installation-time-caused-by-presumed-network-connectivity-issues"></a><span data-ttu-id="4d418-233">安装时配置 BTARN 的过程中出错，这是由假设存在的网络连接问题造成的</span><span class="sxs-lookup"><span data-stu-id="4d418-233">Error during the configuration of BTARN at installation time, caused by presumed network connectivity issues</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-234">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-234">Symptom</span></span>  
 <span data-ttu-id="4d418-235">在配置过程中，错误对话框中出现一个错误，指出计算机与网络的连接不正确，而实际上连接正确。</span><span class="sxs-lookup"><span data-stu-id="4d418-235">During the configuration process, you receive an error in the error dialog box indicating that the computer is not properly connected to the network, when in fact it is.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-236">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-236">Possible Cause</span></span>  
 <span data-ttu-id="4d418-237">此错误可能是由于 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 配置程序错误解释 IP 地址造成的。</span><span class="sxs-lookup"><span data-stu-id="4d418-237">This error may be caused by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration program misinterpreting IP addresses.</span></span> <span data-ttu-id="4d418-238">C:\Windows\system32\drivers\etc 下的主机文件中包含一个将 localhost 主机名映射为 IP 地址 127.0.0.1 的条目。</span><span class="sxs-lookup"><span data-stu-id="4d418-238">The hosts file in C:\Windows\system32\drivers\etc contains an entry mapping the localhost host name to the IP address 127.0.0.1.</span></span> <span data-ttu-id="4d418-239">配置程序可能将这个值与环回地址相混淆，因而假定计算机与网络的连接不正确。</span><span class="sxs-lookup"><span data-stu-id="4d418-239">The configuration program may confuse this value with the loopback address, and assume that the computer is not connected properly to the network.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-240">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-240">Solution</span></span>  
  
##### <a name="to-avoid-this-error-and-complete-the-configuration-process"></a><span data-ttu-id="4d418-241">避免此错误并完成配置过程</span><span class="sxs-lookup"><span data-stu-id="4d418-241">To avoid this error and complete the configuration process</span></span>  
  
1.  <span data-ttu-id="4d418-242">在 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 浏览器中，切换到 C:\Windows\system32\drivers\etc，然后使用记事本打开主机文件。</span><span class="sxs-lookup"><span data-stu-id="4d418-242">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Windows\system32\drivers\etc, and open the hosts file using Notepad.</span></span>  
  
2.  <span data-ttu-id="4d418-243">注释禁止行"127.0.0.1 localhost"通过将"#"放置在行的开头。</span><span class="sxs-lookup"><span data-stu-id="4d418-243">Comment out the line "127.0.0.1        localhost" by placing "# " at the start of the line.</span></span> <span data-ttu-id="4d418-244">保存更改过的主机文件。</span><span class="sxs-lookup"><span data-stu-id="4d418-244">Save the changed hosts file.</span></span>  
  
3.  <span data-ttu-id="4d418-245">单击**重试**在错误对话框中。</span><span class="sxs-lookup"><span data-stu-id="4d418-245">Click **Retry** in the error dialog box.</span></span>  
  
4.  <span data-ttu-id="4d418-246">配置成功完成后，重新在记事本中打开主机文件，删除映射 localhost 的行前的注释标记，然后保存主机文件。</span><span class="sxs-lookup"><span data-stu-id="4d418-246">After configuration has completed successfully, re-open the hosts file in Notepad, remove the comment mark at the start of the line mapping localhost, and then save the hosts file.</span></span>  
  
## <a name="you-receive-an-error-regarding-incorrect-signature-length"></a><span data-ttu-id="4d418-247">出现指出签名长度不正确的错误</span><span class="sxs-lookup"><span data-stu-id="4d418-247">You receive an error regarding incorrect signature length</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-248">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-248">Symptom</span></span>  
 <span data-ttu-id="4d418-249">在事件日志中接收到以下或类似的错误：</span><span class="sxs-lookup"><span data-stu-id="4d418-249">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="4d418-250">执行接收管道时失败：“Microsoft.Solutions.BTARN.Pipelines.Receive”源：“MIME/SMIME 解码器”接收位置：“/BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async”原因：签名长度不正确，值 = 1935897193。</span><span class="sxs-lookup"><span data-stu-id="4d418-250">There was a failure executing the receive pipeline: "Microsoft.Solutions.BTARN.Pipelines.Receive" Source: "MIME/SMIME decoder" Receive Location: "/BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async" Reason: Incorrect signature length, value = 1935897193.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-251">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-251">Possible Cause</span></span>  
 <span data-ttu-id="4d418-252">此错误消息指出，签名长度不正确。</span><span class="sxs-lookup"><span data-stu-id="4d418-252">This error message indicates that the signature length is incorrect.</span></span> <span data-ttu-id="4d418-253">除了上述原因以外，不正确或不完整的头内容长度会导致签名长度的字节读数错误，这也可能造成此错误。</span><span class="sxs-lookup"><span data-stu-id="4d418-253">In addition to the above cause, this error could also due to the incorrect or incomplete header content length which leads to the wrong bytes read on the signature length.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-254">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-254">Solution</span></span>  
 <span data-ttu-id="4d418-255">请验证签名长度和头内容长度正确。</span><span class="sxs-lookup"><span data-stu-id="4d418-255">Verify that both of the signature length and header content length is correct.</span></span>  
  
## <a name="you-receive-503-service-unavailable-from-internet-explorer-on-64-bit-machine"></a><span data-ttu-id="4d418-256">在 64 位计算机上从 Internet Explorer 收到“503：服务不可用”</span><span class="sxs-lookup"><span data-stu-id="4d418-256">You receive "503: Service Unavailable" from Internet Explorer on 64-bit machine</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-257">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-257">Symptom</span></span>  
 <span data-ttu-id="4d418-258">后[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]完成配置，当你尝试访问时[http://localhost](http://localhost/)或[http://localhost/BtarnApp/RnifSend.aspx](http://localhost/BtarnApp/RnifSend.aspx)，你可能会收到以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="4d418-258">After [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] configuration is completed, when you try to access [http://localhost](http://localhost/) or [http://localhost/BtarnApp/RnifSend.aspx](http://localhost/BtarnApp/RnifSend.aspx), you may receive the following or similar error:</span></span>  
  
 <span data-ttu-id="4d418-259">503：服务不可用</span><span class="sxs-lookup"><span data-stu-id="4d418-259">503: Service Unavailable</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-260">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-260">Possible Cause</span></span>  
 <span data-ttu-id="4d418-261">此错误可能是由 ISAPI 筛选器造成的，该筛选器可在 IIS 网站上设置的 C:\windows\system32\rpcproxy\rpcproxy.dll 下找到。</span><span class="sxs-lookup"><span data-stu-id="4d418-261">This error may be caused by the ISAPI filter found under C:\windows\system32\rpcproxy\rpcproxy.dll being set on IIS Web Sites.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-262">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-262">Solution</span></span>  
  
##### <a name="to-remove-rpcproxy-filter-entry-in-iis"></a><span data-ttu-id="4d418-263">删除 IIS 中的 RpcProxy 筛选器条目</span><span class="sxs-lookup"><span data-stu-id="4d418-263">To remove RpcProxy filter entry in IIS</span></span>  
  
1.  <span data-ttu-id="4d418-264">单击**启动**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="4d418-264">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="4d418-265">展开**\<计算机名称 > （本地计算机）**，右键单击**网站**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4d418-265">Expand **\<computer name> (local computer)**, right-click **Web Sites**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4d418-266">选择**ISAPI 筛选器**选项卡。</span><span class="sxs-lookup"><span data-stu-id="4d418-266">Select **ISAPI Filters** tab.</span></span>  
  
4.  <span data-ttu-id="4d418-267">选择**RpcProxy 筛选器**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="4d418-267">Select **RpcProxy filter**, and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="4d418-268">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="4d418-268">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="4d418-269">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4d418-269">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4d418-270">在命令提示符处，键入以下代码，以重置 IIS。</span><span class="sxs-lookup"><span data-stu-id="4d418-270">At the command prompt, type the following code to reset IIS.</span></span>  
  
    ```  
    iisreset  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="4d418-271">执行上述步骤后，如果试图再次访问 http://localhost 或 http://localhost/BtarnApp/RnifSend.aspx，会收到从 Internet Explorer 返回的 HTTP 400 消息，这意味着现在 IIS 已正常运行。</span><span class="sxs-lookup"><span data-stu-id="4d418-271">If you try to access http://localhost or http://localhost/BtarnApp/RnifSend.aspx again after performing the above steps, you will receive HTTP 400 message back from the Internet Explorer which means that IIS is now functioning properly.</span></span>  
  
## <a name="the-hubscenario-sample-will-not-be-installed-correctly-if-the-assembly-key-files-are-not-entered-for-the-projects"></a><span data-ttu-id="4d418-272">如果没有为项目输入程序集密钥文件，则 HubScenario 示例将无法正确安装</span><span class="sxs-lookup"><span data-stu-id="4d418-272">The HubScenario sample will not be installed correctly if the assembly key files are not entered for the projects</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-273">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-273">Symptom</span></span>  
 <span data-ttu-id="4d418-274">当你运行 setup.bat *\<驱动器 >*: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > Accelerator for RosettaNet\SDK\HubScenario 设置 HubScenario 示例中，操作将失败。</span><span class="sxs-lookup"><span data-stu-id="4d418-274">When you run setup.bat in *\<drive>*:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version> Accelerator for RosettaNet\SDK\HubScenario to set up the HubScenario sample, the operation fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-275">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-275">Possible Cause</span></span>  
 <span data-ttu-id="4d418-276">由于项目中没有设置程序集密钥文件，HubScenario 和 HubHelper 程序集没有正确部署。</span><span class="sxs-lookup"><span data-stu-id="4d418-276">The HubScenario and HubHelper assemblies were not deployed correctly because the assembly key files were not set in the projects.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-277">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-277">Solution</span></span>  
 <span data-ttu-id="4d418-278">为 HubScenario 和 HubHelper 项目设置程序集密钥文件。</span><span class="sxs-lookup"><span data-stu-id="4d418-278">Set the assembly key files for the HubScenario and HubHelper projects.</span></span> <span data-ttu-id="4d418-279">有关详细信息，请参阅[HubScenario 示例](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="4d418-279">For more information, see [HubScenario Sample](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md).</span></span>  
  
## <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample-on-sql-server-2008-r22008-sp1"></a><span data-ttu-id="4d418-280">在 SQL Server 2008 R2/2008 SP1 上运行 setupx64.bat 设置“双操作 PIPAutomation 业务流程”示例</span><span class="sxs-lookup"><span data-stu-id="4d418-280">Run setupx64.bat to set up the Double Action PIPAutomation Orchestration sample on SQL Server 2008 R2/2008 SP1</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="4d418-281">故障现象</span><span class="sxs-lookup"><span data-stu-id="4d418-281">Symptom</span></span>  
 <span data-ttu-id="4d418-282">当你运行 setup.bat 以生成和初始化“双操作 PIPAutomation 业务流程”示例时，BTARNData 数据库中未创建 PipAutomationGetAction 存储过程。</span><span class="sxs-lookup"><span data-stu-id="4d418-282">When you run setup.bat to build and initialize the Double Action PIPAutomation Orchestration sample, the PipAutomationGetAction stored procedure in the BTARNData database is not created.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="4d418-283">可能的原因</span><span class="sxs-lookup"><span data-stu-id="4d418-283">Possible Cause</span></span>  
 <span data-ttu-id="4d418-284">你在 64 位计算机上或在 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 系统（它在 SQL Server 2008 R2/2008 SP1 上运行）运行了 setup.bat。</span><span class="sxs-lookup"><span data-stu-id="4d418-284">You ran setup.bat on a 64-bit computer or on a [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] installation that is running on SQL Server 2008 R2/2008 SP1.</span></span> <span data-ttu-id="4d418-285">这两种情况要求你运行 setupx64.bat。</span><span class="sxs-lookup"><span data-stu-id="4d418-285">Both of these instances require you to run setupx64.bat.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="4d418-286">解决方案</span><span class="sxs-lookup"><span data-stu-id="4d418-286">Solution</span></span>  
 <span data-ttu-id="4d418-287">运行 setupx64.bat 以创建该存储过程。</span><span class="sxs-lookup"><span data-stu-id="4d418-287">Run setupx64.bat to create the stored procedure.</span></span> <span data-ttu-id="4d418-288">有关详细信息，请参阅[Double 操作 PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="4d418-288">For more information, see [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span></span>  
  
## <a name="enable-the-btarn-application-pools-for-32-bit-on-windows-server-2008-64-bit-windows-operating-system-os"></a><span data-ttu-id="4d418-289">为 Windows Server 2008（64 位 Windows 操作系统 (OS)）上的 32 位程序启用 BTARN 应用程序池</span><span class="sxs-lookup"><span data-stu-id="4d418-289">Enable the BTARN Application Pools for 32 bit on Windows Server 2008, 64-bit Windows Operating System (OS)</span></span>  
 <span data-ttu-id="4d418-290">要在 Windows Server 2008（64 位 Windows 操作系统 (OS)）、Internet 信息服务管理器 7.5/7.0 上运行 BTARN 端对端方案：</span><span class="sxs-lookup"><span data-stu-id="4d418-290">To run the BTARN End to End scenario on Windows Server 2008,64-bit Windows Operating System (OS), Internet Information Services Manager 7.5/7.0.</span></span>  
  
 1. <span data-ttu-id="4d418-291">启用 32 位程序的 BTARN 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="4d418-291">Enable the BTARN Application Pools for 32 bit.</span></span>  
  
 2. <span data-ttu-id="4d418-292">为引用 IsapiModule 筛选器的 *.dll 添加 HTTP 处理程序。</span><span class="sxs-lookup"><span data-stu-id="4d418-292">Add a HTTP Handler for *.dll refering the IsapiModule Filters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d418-293">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d418-293">See Also</span></span>  
 <span data-ttu-id="4d418-294">[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md) </span><span class="sxs-lookup"><span data-stu-id="4d418-294">[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md) </span></span>  
 [<span data-ttu-id="4d418-295">环回</span><span class="sxs-lookup"><span data-stu-id="4d418-295">Loopback</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)