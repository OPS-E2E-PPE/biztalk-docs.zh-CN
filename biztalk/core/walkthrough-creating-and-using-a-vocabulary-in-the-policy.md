---
title: 演练：创建和使用策略中的某一词汇 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c306a6e-3384-4f43-9c75-c5407cd9aed2
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 915e7dcaf9f777f9e9f621456d1050e509a1fd01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244086"
---
# <a name="walkthrough-creating-and-using-a-vocabulary-in-the-policy"></a>演练：创建和使用策略中的某一词汇
本演练提供了创建词汇和使用词汇的分步过程**ProcessPurchaseOrder**策略。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练：创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)执行本演练中之前的演练。 但是，我们建议你完成所有文档中本演练之前列出的演练。  
  
## <a name="overview-of-this-walkthrough"></a>本演练概述  
 本演练包含三个过程，如下表中所述。  
  
|过程标题|过程 descritpion|  
|---------------------|---------------------------|  
|若要创建 POVocabulary 词汇|提供创建的分步说明**POVocabulary**词汇具有三个定义：请求的数量，最大允许项数，并且请求状态。|  
|若要在 ProcessPurchaseOrder 策略中使用 POVocabulary|提供创建的新版本的分步说明**ProcessPurchaseOrder**策略使用**POVocabulary**。|  
|若要测试解决方案|提供用于测试该解决方案的分步说明。|  
  
### <a name="to-create-the-povocabulary-vocabulary"></a>若要创建 POVocabulary 词汇  
  
1.  上**启动**菜单中，打开**业务规则编辑器**。 如果你有业务规则编辑器已打开，请按 f5 键刷新。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
3.  右键单击**词汇**，单击**添加新词汇**，然后键入**POVocabulary**作为该词汇的名称。  
  
4.  如果你未在步骤 3 中为 POVocabulary 更改词汇的名称，更改到词汇的名称**POVocabulary**属性窗口中。  
  
5.  右键单击**版本 1.0 （未保存）** 中**POVocabulary**，然后单击**添加新定义**。  
  
6.  在词汇定义向导中，选择**XML 文档元素或属性**，然后单击**下一步**。  
  
7.  有关**定义名称**，类型**请求的数量**。  
  
8.  单击**浏览**，然后选择**PO.xsd**文件中创建[演练：创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)。  
  
9. 在中**选择绑定**对话框框中，展开**PurchaseOrder**，展开**项**，然后双击**数量**。  
  
10. 请确保**的文档类型**设置为**RuleTest.PO**。 如果不存在，请将文档类型更改为 RuleTest.PO。 此步骤非常重要。  
  
     ![BRE&#45;Walkthrough&#45;ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")  
  
11. 指定**选择操作**中**选择操作**组作为**执行 Get 操作**。  
  
     ![BRE&#45;演练&#45;SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")  
  
12. 单击 **“完成”**。  
  
13. 右键单击**版本 1.0 （未保存）**，然后单击**添加新定义**。  
  
14. 选择**XML 文档元素或属性**，然后单击**下一步**。  
  
15. 有关**定义名称**，类型**请求状态**。  
  
16. 单击**浏览**，然后选择**PO.xsd**文件。  
  
17. 在中**选择绑定**对话框框中，展开**PurchaseOrder**，然后双击**状态**。  
  
18. 更改**的文档类型**到**RuleTest.PO**。 此步骤非常重要。  
  
19. 请确保**执行 Set 操作**选项选择后，然后依次**下一步。**  
  
20. 单击 **“完成”**。  
  
21. 右键单击**版本 1.0 （未保存）**，然后单击**添加新定义**。  
  
22. 请确保**常数值、 值的范围或值的集合**已选中，然后单击**下一步**。  
  
23. 有关**定义名称**，类型**最大允许的项数**。  
  
24. 请确保**常数值定义类型**已选中，然后单击**下一步**。  
  
25. 类型**500**作为值，然后单击**完成**。  
  
26. 右键单击**版本 1.0 （未保存）**，然后单击**保存**。  
  
27. 右键单击**版本 1.0 （未保存）**，然后单击**发布**。  
  
### <a name="to-use-the-povocabulary-in-the-processpurchaseorder-policy"></a>若要在 ProcessPurchaseOrder 策略中使用 POVocabulary  
  
1.  在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**复制**.  
  
2.  右键单击**ProcessPurchaseOrder** ，然后单击**粘贴策略版本**。  
  
3.  单击**ApprovalRule**中**版本 1.1 （未保存）**。  
  
4.  在事实浏览器窗口中，展开**词汇**，展开**POVocabulary**，展开**版本 1.0**，然后将拖**请求的数量**到如果窗格，以便替代 LessThanOrEqual 谓词的左侧 (LHS) 参数。  
  
     ![BRE&#45;Walkthrough&#45;DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")  
  
     ![BRE&#45;演练&#45;ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")  
  
5.  拖动**最大允许的项数**以便替代条件的右侧 (rhs) 参数 (**500**)。  
  
6.  选择现有操作，然后在窗格中右键单击，然后单击**删除操作**。  
  
    > [!NOTE]
    >  此外可以按 DELETE 选择该操作后，若要删除的操作。  
  
7.  拖动**请求状态**到**然后**窗格。  
  
8.  单击**\<空字符串\>** ，然后键入**已批准**。  
  
9. 右键单击**版本 1.1 （未保存）** 在策略浏览器窗口中，然后单击**保存**。  
  
10. 右键单击**版本 1.1 （未保存）** 在策略浏览器窗口中，然后单击**发布**。  
  
### <a name="to-test-the-solution"></a>若要测试解决方案  
  
1.  在业务规则编辑器中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0-部署**，然后单击**Undeploy**.  
  
    > [!NOTE]
    >  此步骤是可选的因为业务流程始终挑选最新的部署策略，这在执行步骤 2 之后是 1.1 版本。  
  
2.  右键单击**发布版本 1.1-**，然后单击**部署**。  
  
3.  等待大约**60**秒。 规则引擎更新服务刷新其缓存每隔 60 秒如果有一个策略，它可以缓存的任何更新。 并不重要是否执行步骤 1-业务流程将提取最新的部署策略，这是 1.1 版本  
  
4.  打开**SamplePO.xml**并**SamplePO2.xml**在记事本中，将的值更改**状态**字段**XYZ**。  
  
5.  复制**SamplePO.xml**文件从 C:\BRE-Walkthroughs 目录到 C:\BRE-Walkthroughs\RuleTestSol\Input 目录为业务流程。  
  
6.  您应看到业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中输出文件。 打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。  
  
7.  重复步骤 5 和 6 **SamplePO2.xml**，您会发现的值**状态**输出文档中的字段是与输入文档中的相同 (**XYZ**)。  
  
    > [!NOTE]
    >  值**状态**字段仍保持相同 (XYZ)，因为规则引擎不会执行中的操作**ApprovalRule**规则，因为条件被评估为`false`。  
  
## <a name="comments"></a>注释  
  
- 在你保存词汇后，你仍可以修改它。 发布词汇后，不能修改它。  
  
- 如果需要修改定义、 添加新定义，或删除定义，应创建词汇的新版本。  
  
- 仅已发布的词汇用于策略。  
  
- 在"创建 POVocabulary 词汇"过程中，更改到的文档类型**RuleTest.PO**。 若要查看此更改的结果在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，单击**PO.xsd**。 注意，在属性窗口**RuleTest**命名空间的名称和**PO**的名称**类型**。  
  
- 在本演练中，您使用 XML 文档作为事实的策略。 创建策略时，还使用.NET 事实数据库事实  
  
- 当选择**执行 'Set' 操作**在词汇定义向导的第二页，您可以指定**显示格式字符串**遵循的页面上。 例如，可以更改中的显示格式字符串**请求状态{0}** 到**请求状态是： {0}** 然后单击**完成**中在"创建词汇"过程的步骤 20。  
  
## <a name="next-steps"></a>后续步骤  
 现在，已完成本演练中，执行[演练：向策略添加规则](../core/walkthrough-adding-a-rule-to-the-policy.md)演练中，为您提供用于添加到新的规则的分步说明**ProcessPurchaseOrder**策略。  
  
## <a name="see-also"></a>请参阅  
 [词汇](../core/vocabularies.md)   
 [如何制定词汇](../core/how-to-develop-vocabularies.md)   
 [条件评估和操作执行](../core/condition-evaluation-and-action-execution.md)   
 [议程和优先级](../core/agenda-and-priority.md)