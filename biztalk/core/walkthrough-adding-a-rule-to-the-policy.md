---
title: 演练：向策略添加规则 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2a682c0-a5d7-4550-924d-be9fa29b84d2
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b5a19b02429f946a282ed5609beb3155310c8fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320782"
---
# <a name="walkthrough-adding-a-rule-to-the-policy"></a>演练：向策略添加规则
本演练提供了分步操作过程中添加一个名为规则**DeniedRule**到**ProcessPurchaseOrder**策略。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练：创建和使用策略中的某一词汇](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)执行本演练中之前的演练。  
  
## <a name="overview-of-this-walkthrough"></a>本演练概述  
 本演练包含三个过程，如下表中所述。  
  
|过程标题|过程说明|  
|---------------------|---------------------------|  
|若要将 DeniedRule 添加到 ProcessPurchaseOrder 策略|提供用于添加一个名为的新规则的分步说明**DeniedRule**到**ProcessPurchaseOrder**策略。 **DeniedRule**规则设置的值**状态**字段**拒绝**如果的值**数量**大于 500。|  
|若要使用业务规则编辑器测试|提供用于测试的分步说明**ProcessPurchaseOrder**策略通过使用业务规则编辑器。|  
|若要测试解决方案|提供用于测试该解决方案的分步说明。|  
  
### <a name="to-add-deniedrule-to-the-processpurchaseorder-policy"></a>若要将 DeniedRule 添加到 ProcessPurchaseOrder 策略  
  
1.  上**启动**菜单中，打开**业务规则编辑器**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2.  在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.1**，然后单击**复制**.  
  
3.  右键单击**ProcessPurchaseOrder**，然后单击**粘贴策略版本**。  
  
4.  右键单击**版本 1.2 （未保存）** ，单击**添加新规则**，然后将更改到规则的名称**DeniedRule**。  
  
5.  如果你忘记更改到规则的名称**DeniedRule**在步骤 4 中，单击**Rule1**，并将名称更改为**DeniedRule**属性窗口中。  
  
6.  在如果窗格中，右键单击**条件**，依次指向**谓词**，然后单击**大于**。  
  
7.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
8.  展开**词汇**，展开**POVocabulary**，展开**版本 1.0-已发布**，然后将拖**请求数量**到**argument1**如果窗格中。  
  
9. 拖动**项允许的最大数**到**argument2**如果窗格中。  
  
10. 拖动**请求状态**到那么窗格。  
  
11. 单击 **\<空字符串\>** ，然后键入**拒绝**。  
  
12. 右键单击**版本 1.2 （未保存）** ，然后单击**保存**。  
  
13. 右键单击**版本 1.2**，然后单击**发布**。  
  
14. 右键单击**版本 1.2**，然后单击**部署**。  
  
### <a name="to-test-with-business-rule-composer"></a>若要使用业务规则编辑器测试  
  
1.  在记事本中打开 SamplePO.xml 和 SamplePO2.xml 文件并将更改的值**状态**字段**XYZ**。  
  
2.  在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.2**，然后单击**测试策略**.  
  
3.  下**XMLDocuments**节点中，选择**RuleTest.PO**，然后单击**添加实例**。  
  
4.  选择**SamplePO.xml**，然后单击**打开**。  
  
5.  单击**测试**。  
  
6.  看看**议程更新**部分在输出中，并注意到只有**ApprovalRule**添加到该议程。 因此，它是引发的唯一规则 （执行与规则关联的操作）。  
  
7.  打开**SamplePO.xml**记事本和通知中的值**状态**字段设置为**已批准**。  
  
8.  在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.2**，然后单击**测试策略。**  
  
9. 选择**SamplePO.xml**，单击**删除实例**，然后单击**添加实例**。  
  
10. 选择**SamplePO2.xml**，然后单击**打开**。  
  
11. 单击**测试**。  
  
12. 看看**议程更新**部分在输出中，并注意到只有**DeniedRule**添加到该议程。 因此，它是引发的唯一规则。  
  
13. 打开**SamplePO2.xml**记事本和通知中的值**状态**字段是**拒绝**。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  打开**SamplePO.xml**并**SamplePO2.xml**在记事本中，将的值更改**状态**字段**XYZ**。  
  
2.  复制**SamplePO.xml**文件从 C:\BRE-Walkthroughs 目录的 C:\BRE-Walkthroughs\RuleTestSol\Input 目录到业务流程。  
  
3.  您应看到业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。  
  
4.  重复步骤 2 和 3，但**SamplePO2.xml**，您会发现的值**状态**字段设置为**拒绝**输出文档中。 这证明在业务流程正在使用的 1.2 版**ProcessPurchaseOrder**策略。 该业务流程使用的最新部署的版本**ProcessPurchaseOrder**策略，这是**1.2**。 不需要取消部署策略以使用该策略的 1.2 版的 1.1 版。 但是，你需要等待大约 60 秒，然后再测试该解决方案。 有关详细信息，请参阅备注部分。  
  
## <a name="comments"></a>注释  
  
-   策略可以有一个或多个规则。 没有逻辑限制在策略中的规则数。  
  
-   规则引擎使用条件评估-冲突解决-操作执行算法。 在中**条件计算**阶段中，规则引擎的计算结果中的所有规则的条件。 其条件评估结果为 true 的规则将成为执行的候选规则。 在中**冲突解决**阶段中，的候选规则添加到议程按规则的优先顺序。 在中**操作执行**阶段，会执行规则的候选项中的操作。 如果候选规则具有相同的优先级，则这些规则的操作的执行不确定顺序。 您应该假定它们并行执行。  
  
-   在此方案中，对于任何给定的示例文件，触发的规则之一。 请确保更改的值**状态**字段之前运行测试。  
  
-   当部署策略的新版本时，应该等待大约 60 秒，然后再测试。 规则引擎更新服务轮询定期更新 （默认情况下每隔 60 秒） 的规则引擎数据库来寻找新部署的策略。 规则引擎更新服务使用最新的部署策略从规则引擎数据库版本有关的信息更新内存中的策略对象。  
  
## <a name="next-steps"></a>后续步骤  
 现在，已完成本演练中，执行[演练：修改策略](../core/walkthrough-modifying-the-policy.md)演练中，为您提供修改策略的分步说明批准采购订单的值与**quantity**小于或等于 1000 （而不是 500)。  
  
## <a name="see-also"></a>请参阅  
 [条件评估和操作执行](../core/condition-evaluation-and-action-execution.md)   
 [议程和优先级](../core/agenda-and-priority.md)