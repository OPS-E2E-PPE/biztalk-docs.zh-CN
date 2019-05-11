---
title: 演练：修改策略 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dd74440-2a45-4a1a-8e36-98796e1e1392
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0c6027d4aea6aa522b506845cba9f64baf4208d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395324"
---
# <a name="walkthrough-modifying-the-policy"></a>演练：修改策略
本演练提供了创建的新版本的分步说明**POVocabulary**，创建的新版本**ProcessPurchaseOrder**策略，以及使用的最新版本**POVocabulary**中的新版本**ProcessPurchaseOrder**策略。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练：向策略添加规则](../core/walkthrough-adding-a-rule-to-the-policy.md)执行本演练中之前的演练。  
  
## <a name="overview-of-this-walkthrough"></a>本演练概述  
 本演练包含三个过程，如下表中所述。  
  
|过程标题|过程说明|  
|---------------------|---------------------------|  
|若要修改 POVocabulary 词汇|提供用于创建新的词汇版本的分步说明，若要修改的值**项允许的最大数**从**500**到**1000年**。|  
|若要修改 ProcessPurchaseOrder 策略以使用更新后的词汇|提供创建的新版本的分步说明**ProcessPurchaseOrder**策略使用的新版本**POVocabulary**。|  
|若要测试解决方案|提供分步说明了测试解决方案和验证新策略会生效。|  
  
### <a name="to-modify-the-povocabulary-vocabulary"></a>若要修改 POVocabulary 词汇  
  
1.  上**启动**菜单中，打开**业务规则编辑器**。 如果您有业务规则编辑器已打开，请按 F5 或单击**重新加载**上**文件**菜单进行刷新。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2.  在事实浏览器窗口中，展开**词汇**，然后展开**POVocabulary**。  
  
3.  右键单击**版本 1.0-已发布**，然后单击**副本**。  
  
4.  右键单击**POVocabulary**，然后单击**粘贴词汇版本**。  
  
5.  双击**最大允许的项数**中**版本 1.1 （未保存）** 启动词汇定义向导。  
  
6.  单击“下一步” 。  
  
7.  单击“下一步” 。  
  
8.  将值从**500**到**1000年**。  
  
9. 单击 **“完成”**。  
  
10. 右键单击**版本 1.1 （未保存）**，然后单击**保存**。  
  
11. 右键单击**1.1 版**，然后单击**发布**。  
  
### <a name="to-modify-the-processpurchaseorder-policy-to-use-the-updated-vocabulary"></a>若要修改 ProcessPurchaseOrder 策略以使用更新后的词汇  
  
1.  在策略浏览器中，展开**策略**，然后展开**ProcessPurchaseOrder**。  
  
2.  右键单击**版本 1.2**，然后单击**副本**。  
  
3.  右键单击**ProcessPurchaseOrder**，然后单击**PastePolicyVersion**。  
  
4.  单击**ApprovalRule**中**版本 1.3 （未保存）**。  
  
5.  在事实浏览器中，展开**词汇**，展开**POVocabulary**，然后展开**版本 1.1 的已发布**。  
  
6.  拖动**最大允许的项数**中**版本 1.1 的已发布**替换**最大允许的项数**如果窗格中的版本 1.0。  
  
7.  重复步骤 4 到 6 **DeniedRule**。  
  
8.  右键单击**版本 1.3 （未保存）**，然后单击**保存**。  
  
9. 右键单击**版本 1.3**，然后单击**发布**。  
  
10. 右键单击**版本 1.3**，然后单击**部署**。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  单击**启动**，打开**BizTalk Server 管理**。 如果你有在 BizTalk Server 管理控制台已打开，请按 f5 键刷新。  
  
2.  右键单击**RuleTestApp**，然后单击**启动**。 如果**启动**为禁用状态，已在运行该应用程序，你可以忽略下一步。  
  
3.  单击**启动**。  
  
4.  复制**SamplePO2.xml**文件从 C:\BRE-Walkthroughs 目录的 C:\BRE-Walkthroughs\RuleTestSol\Input 目录到业务流程。  
  
5.  您应看到 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中的输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。  
  
    > [!NOTE]
    >  值**数量**SamplePO2.xml 中的字段为 700。 版本 1.3 **ProcessPurchaseOrder**策略将此值与 1000，而不是像版本 1.2 那样比较其与 500 进行比较。  
  
## <a name="comments"></a>注释  
  
-   不能修改已发布的策略。 必须创建要对其进行修改的策略的新版本。 同样，不能修改已发布的词汇。 必须创建新版本的词汇来对其进行修改。  
  
-   业务流程调用策略的使用**调用规则**形状将使用最新的部署的策略版本。 例如，如果具有版本 1.0、 1.1、 1.2 和 1.3 部署的策略，该业务流程使用版本 1.3。 如果版本 1.3 未部署，版本 1.2 已部署该业务流程使用版本 1.2。 因此如果你想要切换回使用版本 1.2，您只需取消部署版本 1.3，并确保版本 1.2 已部署。  
  
-   若要使用特定版本的业务流程中的策略，应使用**表达式**形状，然后调用规则引擎，以通过使用以编程方式执行策略**Policy.Execute**方法。  
  
-   请注意该策略使用词汇定义从版本 1.0 和 1.1 版 POVocabulary 词汇的 1.3 版。 如果将策略的 1.3 版导出到 XML 文件，并导入，即可在另一台计算机上创建策略时，导入过程将查找词汇的两个版本。 因此，您需要将版本 1.0 和版本 1.1 的词汇都导出和导入策略的 1.3 版之前将其导入。  
  
-   部署策略的较新版本后，应等待大约 60 秒，然后再测试该解决方案。 规则引擎更新服务看起来有任何更新到策略每隔 60 秒 （1 分钟） 默认情况下。 如果有更新，它将刷新缓存的更新的信息。  
  
## <a name="next-steps"></a>后续步骤  
  
-   现在，已完成本演练中，执行[演练：跟踪策略执行](../core/walkthrough-tracking-policy-execution.md)演练中，为您提供用于跟踪策略执行详细信息的分步说明。