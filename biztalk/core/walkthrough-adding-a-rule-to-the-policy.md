---
title: 演练： 将规则添加到策略 |Microsoft 文档
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
ms.openlocfilehash: b08fc197c16f04f3eb738468421db340060b9613
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975699"
---
# <a name="walkthrough-adding-a-rule-to-the-policy"></a>演练： 将规则添加到策略
本演练提供了分步过程添加一个名为规则**DeniedRule**到**ProcessPurchaseOrder**策略。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练： 创建和使用该策略中的词汇](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)执行本演练之前的演练。  
  
## <a name="overview-of-this-walkthrough"></a>本演练的概述  
 本演练包含三个过程，如下表所述。  
  
|过程标题|过程说明|  
|---------------------|---------------------------|  
|若要将 DeniedRule 添加到 ProcessPurchaseOrder 策略|提供将添加一个名为的新规则的分步说明**DeniedRule**到**ProcessPurchaseOrder**策略。 **DeniedRule**规则设置的值**状态**字段**拒绝**如果的值**数量**大于 500。|  
|若要使用业务规则编辑器进行测试|提供用于测试的分步说明**ProcessPurchaseOrder**通过业务规则编辑器的策略。|  
|若要测试解决方案|提供用于测试解决方案的分步说明。|  
  
### <a name="to-add-deniedrule-to-the-processpurchaseorder-policy"></a>若要将 DeniedRule 添加到 ProcessPurchaseOrder 策略  
  
1.  上**启动**菜单上，打开**业务规则编辑器**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.1**，然后单击**复制**.  
  
3.  右键单击**ProcessPurchaseOrder**，然后单击**粘贴的策略版本**。  
  
4.  右键单击 **（不保存） 1.2 版**，单击**添加新规则**，然后将更改到规则的名称**DeniedRule**。  
  
5.  如果你忘记更改到规则的名称**DeniedRule**在步骤 4 中，单击**规则 1**，和名称更改为**DeniedRule**属性窗口中。  
  
6.  在 IF 窗格中，右键单击**条件**，指向**谓词**，然后单击**大于**。  
  
7.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
8.  展开**词汇**，展开**POVocabulary**，展开**版本 1.0-发布**，然后拖动**请求数量**到**argument1**如果窗格中。  
  
9. 拖动**项允许的最大数目**到**argument2**如果窗格中。  
  
10. 拖动**请求状态**到然后窗格。  
  
11. 单击**\<空字符串\>** 然后键入**拒绝**。  
  
12. 右键单击 **（不保存） 1.2 版**，然后单击**保存**。  
  
13. 右键单击**版本 1.2**，然后单击**发布**。  
  
14. 右键单击**版本 1.2**，然后单击**部署**。  
  
### <a name="to-test-with-business-rule-composer"></a>若要使用业务规则编辑器进行测试  
  
1.  在记事本中打开的 SamplePO.xml 和 SamplePO2.xml 文件并将更改的值**状态**字段**XYZ**。  
  
2.  在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.2**，然后单击**测试策略**.  
  
3.  下**XMLDocuments**节点中，选择**RuleTest.PO**，然后单击**添加实例**。  
  
4.  选择**SamplePO.xml**，然后单击**打开**。  
  
5.  单击**测试**。  
  
6.  查看**安排更新**部分在输出中，并请注意，只有**ApprovalRule**添加到安排。 因此，它是引发的唯一规则（执行与该规则关联的操作）。  
  
7.  打开**SamplePO.xml**中记事本，并请注意，值**状态**字段设置为**已批准**。  
  
8.  在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.2**，然后单击**测试策略。**  
  
9. 选择**SamplePO.xml**，单击**删除实例**，然后单击**添加实例**。  
  
10. 选择**SamplePO2.xml**，然后单击**打开**。  
  
11. 单击**测试**。  
  
12. 查看**安排更新**部分在输出中，并请注意，只有**DeniedRule**添加到安排。 因此，它是引发的唯一规则。  
  
13. 打开**SamplePO2.xml**中记事本，并请注意，值**状态**字段是**拒绝**。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  打开**SamplePO.xml**和**SamplePO2.xml**在记事本中，将的值更改**状态**字段**XYZ**。  
  
2.  复制**SamplePO.xml**文件从 C:\BRE-Walkthroughs 目录到 C:\BRE-Walkthroughs\RuleTestSol\Input 目录业务流程。  
  
3.  你应该在业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。  
  
4.  重复步骤 2 和 3 的**SamplePO2.xml**，请注意，和的值**状态**字段设置为**拒绝**输出文档中。 这样可证明业务流程使用的 1.2 版**ProcessPurchaseOrder**策略。 业务流程使用最新部署的版本的**ProcessPurchaseOrder**策略，即**1.2**。 为了使用该策略的 1.2 版，您无需取消部署该策略的 1.1 版。 但是，您需要等待大约 60 秒，然后再测试该解决方案。 有关详细信息，请参阅备注部分。  
  
## <a name="comments"></a>注释  
  
-   一个策略可拥有一个或多个规则。 对于策略中规则的数目，不存在逻辑限制。  
  
-   规则引擎使用“条件评估-冲突解决-执行操作”算法。 在**条件计算**阶段中，规则引擎计算中的所有规则的条件。 其条件评估结果为 true 的规则将成为用于执行的候选规则。 在**冲突解决**阶段，在将规则添加到规则的优先级别顺序安排的候选。 在**操作执行**阶段，在执行规则的候选的操作。 如果候选规则具有相同的优先级，则不存在执行这些规则的操作的明确顺序。 您应该假定它们并行执行。  
  
-   在此情况下，对于任何给定的示例文件，只引发其中一个规则。 请确保更改的值**状态**字段之前运行测试。  
  
-   在部署策略的新版本时，在测试前应该等待大约 60 秒。 规则引擎更新服务将定期轮询规则引擎数据库（默认情况下为每 60 秒轮询一次），以便查找新部署的策略。 规则引擎更新服务将用与来自规则引擎数据库的策略的最新部署版本有关的信息来更新内存中的策略对象。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你已完成本演练中，执行[演练： 修改策略](../core/walkthrough-modifying-the-policy.md)演练中，提供有关修改的策略以批准与的值的采购订单的分步说明**数量**小于或等于 1000 （而不是 500)。  
  
## <a name="see-also"></a>另请参阅  
 [条件计算和操作执行](../core/condition-evaluation-and-action-execution.md)   
 [议程和优先级](../core/agenda-and-priority.md)