---
title: 演练： 修改策略 |Microsoft 文档
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
ms.openlocfilehash: 7292d541adaf0ae2242d1c504f1a845dde66f5dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289669"
---
# <a name="walkthrough-modifying-the-policy"></a>演练： 修改策略
本演练提供有关创建的新版本的分步说明**POVocabulary**，创建的新版本**ProcessPurchaseOrder**策略，以及使用的最新版本**POVocabulary**的新版本中**ProcessPurchaseOrder**策略。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练： 将规则添加到策略](../core/walkthrough-adding-a-rule-to-the-policy.md)执行本演练之前的演练。  
  
## <a name="overview-of-this-walkthrough"></a>本演练的概述  
 本演练包含三个过程，如下表所述。  
  
|过程标题|过程说明|  
|---------------------|---------------------------|  
|若要修改的 POVocabulary 词汇|提供创建新的词汇版本以修改的值的指导**项允许的最大数目**从**500**到**1000年**。|  
|若要修改 ProcessPurchaseOrder 策略，以使用更新的词汇|提供有关创建的新版本的分步说明**ProcessPurchaseOrder**要使用新版本的策略**POVocabulary**。|  
|若要测试解决方案|提供测试解决方案和验证新策略是否有效的分步说明。|  
  
### <a name="to-modify-the-povocabulary-vocabulary"></a>若要修改的 POVocabulary 词汇  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。 如果必须业务规则编辑器已打开，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在事实浏览器窗口中，展开**词汇**，然后展开**POVocabulary**。  
  
3.  右键单击**版本 1.0-发布**，然后单击**复制**。  
  
4.  右键单击**POVocabulary**，然后单击**粘贴词汇版本**。  
  
5.  双击**数目的项允许的最大**中 **（不保存） 1.1 版**以启动词汇定义向导。  
  
6.  单击 **“下一步”**。  
  
7.  单击 **“下一步”**。  
  
8.  将值从**500**到**1000年**。  
  
9. 单击 **“完成”**。  
  
10. 右键单击 **（不保存） 1.1 版**，然后单击**保存**。  
  
11. 右键单击**版本 1.1**，然后单击**发布**。  
  
### <a name="to-modify-the-processpurchaseorder-policy-to-use-the-updated-vocabulary"></a>若要修改 ProcessPurchaseOrder 策略，以使用更新的词汇  
  
1.  在策略资源管理器中，展开**策略**，然后展开**ProcessPurchaseOrder**。  
  
2.  右键单击**版本 1.2**，然后单击**复制**。  
  
3.  右键单击**ProcessPurchaseOrder**，然后单击**PastePolicyVersion**。  
  
4.  单击**ApprovalRule**中**版本 1.3 （不保存）**。  
  
5.  在事实数据资源管理器中，展开**词汇**，展开**POVocabulary**，然后展开**版本 1.1-发布**。  
  
6.  拖动**数目的项允许的最大**中**版本 1.1-发布**替换**数目的项允许的最大**如果窗格中的版本 1.0。  
  
7.  重复步骤 4-6 与**DeniedRule**。  
  
8.  右键单击**版本 1.3 （不保存）**，然后单击**保存**。  
  
9. 右键单击**版本 1.3**，然后单击**发布**。  
  
10. 右键单击**版本 1.3**，然后单击**部署**。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  单击**启动**，打开**BizTalk Server 管理**。 如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。  
  
2.  右键单击**RuleTestApp**，然后单击**启动**。 如果**启动**是禁用，应用程序已在运行，你可以忽略下一步。  
  
3.  单击**启动**。  
  
4.  复制**SamplePO2.xml**文件从 C:\BRE-Walkthroughs 目录到 C:\BRE-Walkthroughs\RuleTestSol\Input 目录业务流程。  
  
5.  您应该在 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。  
  
    > [!NOTE]
    >  值**数量**中 SamplePO2.xml 字段是 700。 1.3 版**ProcessPurchaseOrder**策略将使用 1000 个而不是与进行比较来 500 版本 1.2 像此值进行比较。  
  
## <a name="comments"></a>注释  
  
-   已发布的策略不能修改。 必须创建一个新的策略版本才能修改它。 同样，已发布的词汇不能修改。 必须创建一个新的词汇版本才能修改它。  
  
-   业务流程调用通过使用策略**调用规则**形状使用最新的部署策略版本。 例如，如果已部署了策略的版本 1.0、版本 1.1、版本 1.2 和版本 1.3，则业务流程使用版本 1.3。 如果版本 1.3 未部署，版本 1.2 已部署，则业务流程使用版本 1.2。 因此，如果希望转而使用版本 1.2，只需要取消部署版本 1.3，确保版本 1.2 已部署。  
  
-   若要使用来自一个业务流程的策略的特定版本，你应使用**表达式**的形状，然后调用以通过使用以编程方式执行策略所需的规则引擎对**Policy.Execute**方法。  
  
-   注意，策略的版本 1.3 使用来自 POVocabulary 词汇的版本 1.0 和版本 1.1 的词汇定义。 如果将策略的版本 1.3 导出至 XML 文件，然后再将其导入，以便在另一台计算机上创建策略，导入进程将同时查找词汇的两个版本。 因此，您需要在导入策略的版本 1.3 之前导出词汇的版本 1.0 和版本 1.1，再导入这两个版本。  
  
-   在部署策略的较新版本后，在测试解决方案前应该等待大约 60 秒。 默认情况下，规则引擎更新服务每隔 60 秒（1 分钟）就会查找策略的任何更新。 如果有更新，它将用更新信息刷新缓存。  
  
## <a name="next-steps"></a>后续步骤  
  
-   现在，你已完成本演练中，执行[演练： 跟踪策略执行](../core/walkthrough-tracking-policy-execution.md)演练中，这为你提供用于跟踪策略执行详细信息的分步说明。