---
title: 启用银行标识代码验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), enabling
ms.assetid: d268a892-f304-44cb-b590-28ef359c8d99
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 582fde7ad899360aaa74a5fee1ece46ef068e56b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377963"
---
# <a name="enabling-validation-of-bank-identifier-codes"></a><span data-ttu-id="d5d4d-102">启用银行标识代码验证</span><span class="sxs-lookup"><span data-stu-id="d5d4d-102">Enabling Validation of Bank Identifier Codes</span></span>
<span data-ttu-id="d5d4d-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]架构确保银行标识代码 (BICs) SWIFT 交换文档中指定符合 SWIFT 定义 BIC 数据格式。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] schemas ensure that the Bank Identifier Codes (BICs) specified in the SWIFT interchange document conform to the SWIFT-defined BIC data format.</span></span> <span data-ttu-id="d5d4d-104">A4SWIFT 还支持验证与数据库中的客户指定 BIC 列表 BICs。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-104">A4SWIFT also supports validating the BICs against a customer-specified BIC list in a database.</span></span>  

 <span data-ttu-id="d5d4d-105">如果已启用 BRE 验证并启用 BIC 验证，可以执行此验证。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-105">You can perform this validation if you have enabled BRE validation and then enabled BIC validation.</span></span>  

 <span data-ttu-id="d5d4d-106">默认情况下，A4SWIFT 安装程序会禁用 BRE 验证。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-106">By default, A4SWIFT Setup disables BRE validation.</span></span> <span data-ttu-id="d5d4d-107">若要启用它，必须为可用于使用 A4SWIFT 拆装器的接收管道设置 BRE 验证配置参数。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-107">To enable it, you must set the BRE validation configuration parameter to true for a receive pipeline that uses the A4SWIFT disassembler.</span></span> <span data-ttu-id="d5d4d-108">您还必须运行 BRE 部署实用工具部署的主策略和验证策略特定于该消息以进行验证 (MT*xxx*_Master_policy.xml 和 MT*xxx*_Validation_Policy.xml)。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-108">You must also run the BRE Deployment Utility to deploy the master policy and validation policy specific to the message to be validated (MT*xxx*_Master_policy.xml and MT*xxx*_Validation_Policy.xml).</span></span> <span data-ttu-id="d5d4d-109">有关详细信息，请参阅[使用 BRE 策略](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)并[部署 BRE 规则](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-109">For more information, see [Working with BRE Policies](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) and [Deploying BRE Rules](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md).</span></span>  

 <span data-ttu-id="d5d4d-110">启用了 BRE 验证之后，必须使用发布和部署这两种 BIC 验证策略 （BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml） 使用规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-110">After you have enabled BRE validation, you must use publish and deploy both BIC validation policies (BIC_Master_Policy.xml and BIC_Validation_Policy.xml) using the Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="d5d4d-111">这样做之前必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d5d4d-111">Before doing so, you must do the following:</span></span>  

- <span data-ttu-id="d5d4d-112">从 SWIFT BIC 值与数据库中填充。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-112">Populate the database with BIC values from SWIFT.</span></span> <span data-ttu-id="d5d4d-113">您可以使用 Bicplus 表在 A4SWIFT 数据库中，通过 A4SWIFT 安装程序安装，或者可以使用自定义数据库。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-113">You can use the Bicplus table in the A4SWIFT database, which is installed by A4SWIFT Setup, or you can use your own custom database.</span></span> <span data-ttu-id="d5d4d-114">有关详细信息，请参阅[管理 Bicplus 表 A4SWIFT 数据库中](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-114">For more information, see [Managing the Bicplus Table in the A4SWIFT Database](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md).</span></span>  

- <span data-ttu-id="d5d4d-115">BIC 数据库设置和启用的自定义 BIC Master 策略 BIC 验证。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-115">Set the BIC database and enable BIC validation by customizing the BIC Master Policy.</span></span> <span data-ttu-id="d5d4d-116">请参阅下面的过程。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-116">See the procedure below.</span></span>  

  <span data-ttu-id="d5d4d-117">为了提高性能，您不应部署 BIC 验证策略如果 BIC 验证不需要。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-117">For better performance, you should not deploy the BIC validation policies if BIC validation is not required.</span></span>  

> [!NOTE]
>  <span data-ttu-id="d5d4d-118">您可以发布和部署 BIC 验证策略，仅当已发布 A4SWIFT_Codelist 和 A4SWIFT_Functions 词汇。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-118">You can publish and deploy the BIC validation policy only if you have published the A4SWIFT_Codelist and A4SWIFT_Functions vocabularies.</span></span> <span data-ttu-id="d5d4d-119">通过运行 swift 架构程序集上的 BRE 部署实用工具来发布这些词汇。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-119">Publish these vocabularies by running the BRE Deployment Utility on the SWIFTSchemas assembly.</span></span> <span data-ttu-id="d5d4d-120">有关详细信息，请参阅[第 1 课：部署相关的业务规则](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-120">For more information, see [Lesson 1: Deploying the Related Business Rules](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md).</span></span>  

### <a name="to-customize-the-bic-master-policy"></a><span data-ttu-id="d5d4d-121">若要自定义 BIC Master 策略</span><span class="sxs-lookup"><span data-stu-id="d5d4d-121">To customize the BIC Master Policy</span></span>  

1. <span data-ttu-id="d5d4d-122">打开 XML 编辑器 （如记事本)，并浏览到 **<*驱动器*Program Files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-122">Open an XML editor (such as Notepad), and browse to **<*drive*Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies**.</span></span>  

2. <span data-ttu-id="d5d4d-123">打开**BIC_Master_Policy.xml**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-123">Open **BIC_Master_Policy.xml**.</span></span> <span data-ttu-id="d5d4d-124">将新值替换为以下现有字符串。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-124">Replace the following existing strings with new values.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d5d4d-125">必须为 A4SWIFT 数据库中的 Bicplus 表或您自己的自定义数据库输入值。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-125">You must enter values for either the Bicplus table in the A4SWIFT database or your own custom database.</span></span> <span data-ttu-id="d5d4d-126">A4SWIFT 数据库不是 BIC_Master_Policy.xml 中的默认值。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-126">The A4SWIFT database is not the default in BIC_Master_Policy.xml.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d5d4d-127">以下字符串必须不包含在双引号中。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-127">The following strings must not be contained within double quotes.</span></span>  

   |            <span data-ttu-id="d5d4d-128">现有的字符串</span><span class="sxs-lookup"><span data-stu-id="d5d4d-128">Existing string</span></span>            |                                                              <span data-ttu-id="d5d4d-129">替换为</span><span class="sxs-lookup"><span data-stu-id="d5d4d-129">Replace with</span></span>                                                              |
   |---------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
   |      <span data-ttu-id="d5d4d-130">**指定 SQL SERVER 名称**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-130">**SPECIFY SQL SERVER NAME**</span></span>      | <span data-ttu-id="d5d4d-131">名称[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]包含保存 BIC 的数据库。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-131">The name of the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] containing the database holding the BIC.</span></span> |
   |     <span data-ttu-id="d5d4d-132">**指定 BIC 数据库名称**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-132">**SPECIFY BIC DATABASE NAME**</span></span>     |                                         <span data-ttu-id="d5d4d-133">包含 BIC 表的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-133">The name of the database that contains the BIC table.</span></span>                                          |
   | <span data-ttu-id="d5d4d-134">**指定集成的安全性值**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-134">**SPECIFY INTEGRATED SECURITY VALUE**</span></span> |                                                                <span data-ttu-id="d5d4d-135">**SSPI**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-135">**SSPI**</span></span>                                                                |


3. <span data-ttu-id="d5d4d-136">保存修改后的主策略。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-136">Save the modified Master Policy.</span></span>  

4. <span data-ttu-id="d5d4d-137">单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则引擎部署向导**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-137">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  

5. <span data-ttu-id="d5d4d-138">在欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-138">On the Welcome page, click **Next**.</span></span>  

6. <span data-ttu-id="d5d4d-139">在部署任务页上，单击**导入策略/词汇并发布到数据库文件从**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-139">On the Deployment Task page, click **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  

7. <span data-ttu-id="d5d4d-140">在策略存储区页上，在**SQL Server 名称**，选择[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]包含 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-140">On the Policy Store page, in **SQL Server Name**, select the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] that contains your BizTalk databases.</span></span> <span data-ttu-id="d5d4d-141">在中**选定的服务器上配置数据库**，选择**BizTalkRuleEngineDb**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-141">In **Configuration Database on selected server**, select **BizTalkRuleEngineDb**, and then click **Next**.</span></span>  

8. <span data-ttu-id="d5d4d-142">在导入规则引擎策略/词汇文件页中，浏览到 **<*驱动器*files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFTMessages\A4SWIFT SRG\<版本\>\Base 策略**，单击**BIC_Master_Policy.xml**，单击**打开**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-142">In the Import Rules Engine Policy/Vocabulary file page, browse to **<*drive*\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies**, click **BIC_Master_Policy.xml**, click **Open**, and then click **Next**.</span></span>  

9. <span data-ttu-id="d5d4d-143">在准备就绪的页上，验证数据，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-143">On the Ready page, verify the data, and then click **Next**.</span></span>  

10. <span data-ttu-id="d5d4d-144">在导入策略/词汇页上，验证该命令已成功，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-144">On the Importing Policy/Vocabulary page, verify that the command succeeded, and then click **Next**.</span></span>  

11. <span data-ttu-id="d5d4d-145">在完成规则引擎部署向导页上，单击**再次运行此向导**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-145">On the Completing the Rules Engine Deployment Wizard page, click **Run this wizard again**, and then click **Finish**.</span></span>  

12. <span data-ttu-id="d5d4d-146">在欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-146">On the Welcome page, click **Next**.</span></span>  

13. <span data-ttu-id="d5d4d-147">在部署任务页上，单击**部署策略**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-147">On the Deployment Task page, click **Deploy Policy**, and then click **Next**.</span></span>  

14. <span data-ttu-id="d5d4d-148">上**策略存储区**页上，在**SQL Server 名称**，选择[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]包含 BizTalk 数据库。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-148">On the **Policy Store** page, in **SQL Server Name**, select the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] that contains your BizTalk databases.</span></span> <span data-ttu-id="d5d4d-149">在中**选定的服务器上配置数据库**，选择**BizTalkRuleEngineDb**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-149">In **Configuration Database on selected server**, select **BizTalkRuleEngineDb**, and then click **Next**.</span></span>  

15. <span data-ttu-id="d5d4d-150">上**部署策略**页上，选择**BIC_Master_Policy.1.0**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-150">On the **Deploy Policy** page, select **BIC_Master_Policy.1.0**, and then click **Next**.</span></span>  

16. <span data-ttu-id="d5d4d-151">上**准备好**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-151">On the **Ready** page, click **Next**.</span></span>  

17. <span data-ttu-id="d5d4d-152">在部署策略页中，如果成功部署后，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-152">On the Deploying Policy page, if the deployment has succeeded, click **Next**.</span></span> <span data-ttu-id="d5d4d-153">单击**再次运行此向导**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-153">Click **Run this wizard again**, and then click **Finish**.</span></span>  

18. <span data-ttu-id="d5d4d-154">重复步骤 5 到 17 **BIC_Validation_Policy.xml**输入**BIC_Validation_Policy**而不是**BIC_Master_Policy**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-154">Repeat steps 5 through 17 for **BIC_Validation_Policy.xml**, entering **BIC_Validation_Policy** instead of **BIC_Master_Policy**.</span></span>  

19. <span data-ttu-id="d5d4d-155">退出规则引擎部署向导。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-155">Exit the Rules Engine Deployment Wizard.</span></span>  

20. <span data-ttu-id="d5d4d-156">单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-156">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span> <span data-ttu-id="d5d4d-157">确认**策略**列表中包括**BIC_Master_Policy**并**BIC_Validation_Policy**下**策略**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-157">Verify that the **Policies** list includes **BIC_Master_Policy** and **BIC_Validation_Policy** under **Policies**.</span></span>  

21. <span data-ttu-id="d5d4d-158">展开**版本 1.0-部署**下**BIC_Master_Policy**，然后单击**BIC_Master_Rule**。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-158">Expand **Version 1.0 - Deployed** under **BIC_Master_Policy**, and then click **BIC_Master_Rule**.</span></span>  

22. <span data-ttu-id="d5d4d-159">在那么窗格中，验证列出的 SQL 连接属性正确。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-159">In the THEN pane, verify that the SQL Connection properties listed are correct.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="d5d4d-160">A4SWIFT 不提取之前重新启动承载当前配置为使用 SWIFT 反汇编程序的接收管道的 BizTalk 服务，对主 BIC 验证策略进行的更改。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-160">A4SWIFT does not pick up changes made to the master BIC validation policy until you restart the BizTalk service that hosts the receive pipeline that is currently configured to use the SWIFT disassembler.</span></span> <span data-ttu-id="d5d4d-161">A4SWIFT 验证通过 BIC 主策略中指定的 BIC 列中包含的 BIC 值此管道的所有文档。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-161">A4SWIFT validates all documents that pass through this pipeline for the BIC values that are contained in the BIC column specified in the BIC master policy.</span></span> <span data-ttu-id="d5d4d-162">用于启动此 BizTalk 服务 (BTSNTSvc.exe) 的用户帐户必须有权 BIC 数据库和表。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-162">The user account used to start this BizTalk service (BTSNTSvc.exe) must have access to the BIC database and table.</span></span> <span data-ttu-id="d5d4d-163">为提高安全性，建议您授予对 BIC 数据库和表的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-163">For better security, it is recommended that you grant read-only access to the BIC database and table.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="d5d4d-164">如果使用消息修复和新提交，World Wide Web Publishing 服务必须重新启动 （通过运行 iisreset.exe） BIC 验证正常工作，从 InfoPath。</span><span class="sxs-lookup"><span data-stu-id="d5d4d-164">If you are using Message Repair and New Submission, the World Wide Web Publishing service must be restarted (by running iisreset.exe) for BIC validation to work from InfoPath.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d5d4d-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5d4d-165">See Also</span></span>  
 <span data-ttu-id="d5d4d-166">[使用 BRE 策略](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) </span><span class="sxs-lookup"><span data-stu-id="d5d4d-166">[Working with BRE Policies](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) </span></span>  
 [<span data-ttu-id="d5d4d-167">在 A4SWIFT 数据库中管理 Bicplus 表</span><span class="sxs-lookup"><span data-stu-id="d5d4d-167">Managing the Bicplus Table in the A4SWIFT Database</span></span>](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)