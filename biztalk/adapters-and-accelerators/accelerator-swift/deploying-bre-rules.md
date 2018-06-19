---
title: 部署 BRE 规则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, BRE policies
- BRE policies, deploying
ms.assetid: 3a66aa57-e7f9-400f-963c-eda12fb1e659
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5627731bd84a761ffb62b95646876c768e3298ea
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967882"
---
# <a name="deploying-bre-rules"></a>部署 BRE 规则
必须将部署使用的 BRE 规则[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]业务流程来处理 SWIFT 消息。  
  
 **摘要**  
  
 发布以下词汇：  
  
-   A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇。 这些建议位于*\<驱动器\>*: files\microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base Policies\Vocabulary。 发布和部署这些使用 BRE 部署实用工具。  
  
 发布和部署以下策略：  
  
-   消息架构的 SWIFT 基策略，包括 SWIFT_Reference_Policy.xml、 SWIFT_PartyIdentifier_Policy.xml 和网络规则策略 (SWIFT_NetworkRulexxx_Policy.xml) 部署架构。 这些建议位于\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略。 发布和部署这些使用 BRE 部署实用工具。  
  
-   与已部署的消息架构 （MTxxx_Master_Policy.xml 和 MTxxx_Validation_Policy.xml） 相关联的 Master 和验证策略。 这些建议位于\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MTxxx。 发布和部署这些使用 BRE 部署实用工具。  
  
-   如果需要 BIC 验证与 BIC 验证 （BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml） 相关联的 Master 和验证策略。 这些建议位于\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略。 之前发布和部署这些策略，你必须使用的 SQL Server，BIC 数据库名称，名称来自定义 BIC_Master_Policy.xml 和集成安全值。 有关详细信息，请参阅[启用验证 Bank 标识符代码的](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)。 发布和部署这些使用规则引擎部署向导。  
  
### <a name="to-deploy-bre-rules"></a>若要部署 BRE 规则  
  
1.  运行 BRE 部署实用工具。 有关详细信息，请参阅"部署 BRE 规则所有在一次"下面。 此实用程序将发布和部署以下：  
  
    -   A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇  
  
    -   对于消息架构，包括 SWIFT_Reference_Policy.xml、 SWIFT_PartyIdentifier_Policy.xml 和网络规则策略 (SWIFT_NetworkRulexxx_Policy.xml) SWIFT 基策略  
  
    -   与已部署的消息架构 （MTxxx_Master_Policy.xml 和 MTxxx_Validation_Policy.xml） 相关联的 Master 和验证策略  
  
2.  利用 SQL server，BIC 数据库名称和集成的安全值的名称自定义 BIC_Master_Policy.xml。 有关详细信息，请参阅[启用验证 Bank 标识符代码的](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)。  
  
3.  运行规则引擎部署向导来发布和部署 BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml (在\<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略)。 有关详细信息，请参阅"部署 BRE 规则一次"下面。  
  
## <a name="tools-for-deploying-the-policies"></a>部署策略的工具  
 发布词汇和部署策略的最简单方法是使用业务规则引擎 (BRE) 部署实用工具在 A4SWIFT 软件开发工具包 (SDK)。 你还可以通过执行这样[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]规则引擎部署向导，这一次执行相同任务的一个词汇或策略。  
  
> [!NOTE]
>  BRE 部署实用工具不部署 BIC Master 策略和 BIC 验证策略。 你必须部署这些使用规则引擎部署向导。  
  
### <a name="deploying-bre-rules-all-at-once"></a>在一次部署 BRE 规则  
 业务规则引擎 (BRE) 部署实用工具执行一个步骤中的一系列的发布和部署任务。 你必须重新运行部署实用工具随时架构添加到你的项目。  
  
##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a>若要将 BRE 规则使用 BRE 部署实用工具部署  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**.  
  
2.  在 BRE 部署实用工具的对话框中，单击**浏览**。  
  
3.  在.NET 全局程序集缓存对话框中，选择项目程序集，部署在[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)，然后单击**确定**。  
  
4.  在 BRE 部署实用工具的对话框中，单击**部署**。  
  
    > [!NOTE]
    >  根据使用该程序集部署的架构，部署实用工具标识相关的规则，并将其发布与 BRE 一起使用。 完成后，BRE 部署实用程序显示以下消息：  
  
    > [!NOTE]
    >  "部署已完成。 查看日志文件或业务规则编辑器的详细信息。"  
  
5.  关闭 BRE 部署实用工具的对话框。  
  
6.  打开[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器。 浏览到\<*驱动器*\>: \Documents and Settings\All Users\Application 数据，并确认的日志文件 BREDeploymentLog.txt 是否显示在该驱动器。  
  
7.  重新启动的规则引擎更新服务。 通过单击来做到**启动**、 单击**运行**、 输入**services.msc**，并单击**确定**。 在**服务 （本地）** 窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。  
  
### <a name="deploying-bre-rules-one-at-a-time"></a>一次部署 BRE 规则一个  
 规则引擎部署向导可用于发布的词汇和一次部署一个策略。 有关词汇，此过程涉及到导入和从一个步骤中的文件发布到数据库的词汇。 对于策略，该过程包括导入和在一个步骤中，发布策略并将在另一个步骤中对其进行部署。  
  
##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a>若要部署 BRE 规则使用规则引擎部署向导  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则引擎部署向导**.  
  
2.  在欢迎使用规则引擎部署向导页上，单击**下一步**。  
  
3.  在部署任务页上，单击**导入并将其从文件发布到数据库的策略/词汇**，然后单击**下一步**。  
  
4.  在策略存储区页上，在**SQL Server 名称列表**，选择你的服务器，然后在**选定的服务器上的配置数据库**列表中，选择**BizTalkRuleEngineDb**。 单击 **“下一步”**。  
  
5.  在导入规则引擎策略/词汇文件页上，单击**浏览**。  
  
6.  在从文件页上，导入策略中**查找**下拉列表中，移动到以下文件夹，根据的词汇和策略之一：  
  
    -   \<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>A4SWIFT_ 的 \Base Policies\VocabularyCodeLists.xml 和 A4SWIFT_Functions.xml  
  
    -   \<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base SWIFT_Reference_Policy.xml，策略SWIFT_PartyIdentifier_Policy.xml、 网络规则策略、 BIC_Master_Policy.xml 和 BIC_Validation_Policy.xml  
  
    -   \<驱动器\>: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MTxxx 的 master 和验证与已部署的消息架构关联的策略  
  
7.  选择的策略，你想要部署，然后单击**打开**。  
  
8.  在导入规则引擎策略/词汇文件页上，单击**下一步**。  
  
9. 在准备页上，单击**下一步**。  
  
10. 在导入策略/词汇页上，验证该命令已成功，然后单击**下一步**。  
  
11. 如果你想要部署策略，在完成规则引擎部署向导页上，单击**再次运行此向导**，然后单击**完成**。  
  
12. 在欢迎使用规则引擎部署向导页上，单击**下一步**。  
  
13. 在部署任务页上，单击**部署策略**，然后单击**下一步**。  
  
14. 在策略存储区页上，在**SQL Server 名称列表**，选择你的服务器，然后在**选定的服务器上的配置数据库**列表中，选择**BizTalkRuleEngineDb**。 单击 **“下一步”**。  
  
15. 在部署策略页上，单击向下箭头旁边**规则引擎策略**文本框中，选择你刚策略发布，，然后单击**下一步**。  
  
16. 在准备页上，单击**下一步**。  
  
17. 上**导入策略/词汇**页上，验证该命令成功，然后单击**下一步**。  
  
18. 单击 **“完成”**。  
  
19. 重新启动**规则引擎更新服务**。 通过单击来做到**启动**、 单击**运行**、 输入**services.msc**，并单击**确定**。 在**服务 （本地）** 窗口中，右键单击**规则引擎更新服务**，然后单击**重新启动**。