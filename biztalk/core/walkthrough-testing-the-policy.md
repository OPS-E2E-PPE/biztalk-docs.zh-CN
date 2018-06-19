---
title: 演练： 测试策略 |Microsoft 文档
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53ed915d-0f3a-48ea-bfd5-a1f89b9b689c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36d7ecf6e469ae6c3edd9b3d7cadc0068ba0d021
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31008595"
---
# <a name="walkthrough-testing-the-policy"></a>演练： 测试策略
本演练中提供的测试中创建的策略的分步过程[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练。  
  
## <a name="prerequisites"></a>先决条件  
 必须完成[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练在执行本演练之前。  
  
## <a name="overview-of-this-walkthrough"></a>本演练的概述  
 本概览包含两个过程，如下表所述。  
  
|过程标题|过程说明|  
|---------------------|---------------------------|  
|若要创建测试文件|提供分步说明，创建两个示例 XML 文件，另一个使用为 400 数量字段的值 (\<= 500) 和另一个为 700 (> 500) 数量字段的值。|  
|测试 ProcessPurchaseOrder 策略|提供使用业务规则编辑器来测试该策略的逐步说明。|  
  
### <a name="to-create-the-test-files"></a>若要创建测试文件  
  
1.  上 **启动** 菜单上，打开 **记事本**。  
  
2.  将下列 XML 复制到记事本中：  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>400</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>    
    ```  
  
3.  上 **文件** 菜单上，单击 **TextFile1.txt 另存为**。  
  
4.  值更改 **另存为类型** 从 **文本文档 (\*.txt)** 到 **所有文件**。  
  
5.  将目录更改为 **C:\BRE-Walkthroughs**。  
  
6.  类型 **SamplePO.xml** 为 **文件名**, ，然后单击 **保存**。  
  
7.  在“文件”  菜单上，单击“新建” 。  
  
8.  将下列 XML 复制到记事本中：  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>700</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>   
    ```  
  
9. 上 **文件** 菜单上，单击 **TextFile1.txt 另存为**。  
  
10. 值更改 **另存为类型** 从 **文本文档 (\*.txt)** 到 **所有文件**。  
  
11. 将目录更改为 **C:\BRE-Walkthroughs**。  
  
12. 类型 **SamplePO2.xml** 为 **文件名**, ，然后单击 **保存**。  
  
13. 关闭记事本。  
  
### <a name="to-test-the-processpurchaseorder-policy"></a>测试 ProcessPurchaseOrder 策略  
  
1.  上 **启动** 菜单上，打开 **业务规则编辑器**。 如果已開啟 [商務規則編輯器]，請按下 F5 重新整理。  
  
    > [!NOTE]
    >  在支援使用者帳戶控制 (UAC) 的系統上，您可能需要使用系統管理權限來執行工具。 要执行此操作，右键单击该应用程序，，然后选择 **以管理员身份运行**。  
  
2.  在策略资源管理器窗口中，展开 **策略**, ，展开 **ProcessPurchaseOrder**, ，右键单击 **版本 1.0**, ，然后单击 **测试策略**。  
  
3.  在 **XMLDocuments** 节点中，选择 **RuleTest.PO**, ，然后单击 **添加实例**。  
  
     ![业务规则编辑器&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")  
  
4.  选择 **SamplePO.xml** 文件之前创建，然后单击 **打开**。  
  
5.  单击 **测试**。  
  
6.  查看“输出”窗口中的输出。 查看“来自第一个测试的输出分析 (samplepo.xml)”部分，它解释了您所看到的输出。  
  
7.  打开 **SamplePO.xml** 中记事本，并请注意，值 **状态** 字段设置为 **已批准**。  
  
8.  右键单击 **版本 1.0**, ，然后单击 **测试策略**。  
  
9. 选择 **SamplePO.xml**, ，单击 **删除实例**, ，然后单击 **添加实例**。  
  
10. 选择 **SamplePO2.xml** 文件之前创建，然后单击 **打开**。  
  
11. 单击 **测试**。 查看“来自第二个测试的输出分析 (samplepo2.xml)”部分，它解释了您所看到的输出。  
  
12. 打开 **SamplePO2.xml** 文件在记事本中，可以看到的值 **状态** 字段仍是 **XYZ**。  
  
## <a name="analysis-of-the-output-from-the-first-test-samplepoxml"></a>来自第一个测试的输出分析 (samplepo.xml)  
  
> [!NOTE]
>  输出文本为粗体并且在输出文本后跟有解释。  
  
 **对于 RULESET 的规则引擎跟踪︰ ProcessPurchaseOrder 2006 年 8 月 31 日下午 1:33:10**  
  
 策略执行的规则引擎跟踪 **ProcessPurchaseOrder** 启动 2006 年 8 月 31 日下午 1:33:10。  
  
 **事实活动 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **操作︰ 断言**  
  
 **对象类型︰ TypedXmlDocument:PurchaseOrder**  
  
 **对象实例标识符︰ 14626574**  
  
 当你单击 **测试**, ，都会发生以下情况︰  
  
1.  业务规则编辑器创建 **RuleEngine.Policy** 对象，它能反过来创建新的规则引擎实例或获取从规则引擎缓存的规则引擎实例。  
  
2.  业务规则编辑器创建 **TypedXmlDocument** 对象基于 SamplePO.xml 文件。  
  
3.  业务规则编辑器时，将调用 **Policy.Execute** 方法替换 **TypedXmlDocument** 对象作为参数。  
  
4.  **Policy.Execute** 方法断言 （添加） **TypedXmlDocument** 与的事实数据到规则引擎的工作内存的对象。  
  
5.  规则引擎会使用 **TypedXmlDocument** 对象与的事实数据并执行 **ProcessPurchaseOrder** 策略。  
  
 **事实活动 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **操作︰ 断言**  
  
 **对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder**  
  
 **对象实例标识符︰ 64530307**  
  
 **事实活动 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **操作︰ 断言**  
  
 **对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder/项**  
  
 **对象实例标识符︰ 43901854**  
  
1.  规则引擎确定哪些子 **TypedXmlDocument** 对象来创建基于在规则中定义的 XPath 选择器。 XPath 选择器值生成业务规则编辑器中的规则时，默认为上方中所选节点的节点 **XML 架构** 事实数据资源管理器中的选项卡。 XPath 的字段值默认为所选节点本身，相对于其父节点。 但是，如果所选节点具有子节点，则只创建指向所选节点的 XPath 选择器绑定，而不创建任何 XPath 字段绑定。  
  
2.  下表显示了 XPath 选择器和 XPath 字段中使用的字段的绑定值 **ProcessPurchaseOrder** 策略。 （该策略只具有一个规则，即 ApprovalRule。）  
  
|字段名称|XPath 选择器|XPath 字段|XPath 选择器（简化形式）|XPath 字段<br /><br /> （简化形式）|  
|----------------|--------------------|-----------------|----------------------------------------|-----------------------------------------|  
|数量|/*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']/\*[local-name()='Item' and namespace-uri()='']|* [本地名称 （) = 数量和 namespace-uri() = ']|/ PurchaseOrder/项|数量|  
|状态|/*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']|* [本地名称 （) = 'Status' 和 namespace-uri() = ']|/ PurchaseOrder|状态|
<!---Loc Comment: Please, verify strucutre in line 183 and 184--->
  
#### <a name="to-view-the-xpath-selector-and-xpath-field-bindings-for-the-quantity-and-status-fields"></a>查看“数量”字段和“状态”字段的 Xpath 选择器和 Xpath 字段绑定  
  
1.  在策略资源管理器窗口中，展开 **策略**, ，展开 **ProcessPurchaseOrder**, ，然后展开 **版本 1.0**。  
  
2.  单击 **ApprovalRule**。  
  
3.  在右侧的 IF 窗格中，单击 **PO: / PurchaseOrder/项/数量**。  
  
4.  验证是否能看到显示有关前面的表中的值 **XPath 选择器** 和 **XPath 字段** 属性窗口中的绑定。  
  
5.  重复步骤 3 和 4 **PO: / PurchaseOrder/状态** 字段。  
  
 规则引擎创建子 **TypedXmlDocument** 对象与原始 **TypedXmlDocument** 提交每个 XPath 选择器。 由于没有使用策略中的两个不同 XPath 选择器 (**/PurchaseOrder/项** 为 **数量** 字段和 **/PurchaseOrder** 为 **状态** 字段)，该规则引擎会创建两个子 **TypedXmlDocument** 对象和断言它们到工作内存的规则引擎。  
  
> [!NOTE]
>  若要查看跟踪输出试，请单击 **版本 1.0** 策略浏览器窗口中。  
  
 **条件评估测试 （匹配） 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **测试表达式︰ TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  
  
 **左操作数的值︰ 400**  
  
 **右操作数的值︰ 500**  
  
 **测试结果︰ True**  
  
 **安排更新 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **操作︰ 添加**  
  
 **规则名称︰ ApprovalRule**  
  
 **冲突解决标准︰ 0**  
  
 规则引擎使用三阶段的算法（条件评估-冲突解决-执行操作）来执行策略。 在条件计算阶段中，规则引擎中的策略中的所有规则的条件的计算结果，并将其条件计算结果为规则添加 `true` 到安排。 在此简单示例中， **ProcessPurchaseOrder** 策略具有只有一个规则， **ApprovalRule**。 因此，规则引擎计算条件， **数量 < = 500**, 中 **ApprovalRule** 使用的值 **数量** 字段在提交 XML 文档中，这是 **400**。 上面的输出显示左操作数、右操作数和测试结果的值。  
  
 在第二个阶段中，冲突解决标准阶段，其条件计算结果为规则 `true` 添加到基于它们的优先级别顺序的安排。 在此方案中，添加规则引擎 **ApprovalRule** 安排到因为的条件 **ApprovalRule** 计算结果为 `true`。 上面的输出中显示的冲突解决方法条件是仅对规则优先级 (**ApprovalRule**)。 如果你单击 **ApprovalRule** 策略资源管理器窗口中的节点，你可以看到的值 **优先级** 属性作为属性窗口中的规则 **0**, ，这是一条规则的默认值。 如果您在某个策略中具有多个规则，并且想要确保一个规则中的操作在另一个规则中的操作后执行，则应相应设置优先级。 该数字越大，规则的优先级就越高。  
  
 **规则触发 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **规则名称︰ ApprovalRule**  
  
 **冲突解决标准︰ 0**  
  
 在最后一个阶段（执行操作阶段）中，规则引擎将开始执行规则中的操作。 中的一个操作 **ApprovalRule**, ，这会设置的值 **状态** 字段到提交的 XML 文档中 **已批准**。  
  
 **事实活动 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **操作︰ 收回**  
  
 **对象类型︰ TypedXmlDocument:PurchaseOrder**  
  
 **对象实例标识符︰ 14626574**  
  
 **事实活动 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **操作︰ 收回**  
  
 **对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder/项**  
  
 **对象实例标识符︰ 43901854**  
  
 **事实活动 2006 年 8 月 31 日下午 1:33:10**  
  
 **规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **操作︰ 收回**  
  
 **对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder**  
  
 **对象实例标识符︰** 64530307  
  
 提交的所有事实 (**PurchaseOrder**) 向规则引擎和规则引擎创建的子事实数据基于 XPath 选择器 (**\PurchaseOrder** 和 **\PurchaseOrder\Item**) 收回 （删除） 从规则引擎的工作内存。  
  
## <a name="analysis-of-the-output-from-the-second-test-samplepo2xml"></a>来自第二个测试的输出分析 (samplepo2.xml)  
 **条件评估测试 （匹配） 9/5/2006年下午 5:24:42**  
  
 **规则引擎实例标识符︰ b749d2fd-a883-4c2f-9974-5cf688010622**  
  
 **Ruleset 名称︰ ProcessPurchaseOrder**  
  
 **测试表达式︰ TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  
  
 **左操作数的值︰ 700**  
  
 **右操作数的值︰ 500**  
  
 **测试结果︰** False  
  
 规则引擎计算条件 (**数量 < = 500**) 中 **ApprovalRule** 使用唯一 **项** 对象。 你可以看到左的操作数的值是值 **数量** 在 XML 文档中，元素 **700**。 测试结果是 `false` 因为 **700 < = 500**, ，因此该规则不添加到规则引擎的安排。 议程中没有任何规则。 因此，有无操作若要执行和的值 **状态** 字段保持 **XYZ**。  
  
## <a name="comments"></a>注释  
  
-   建议您在客户端应用程序（例如 BizTalk 应用程序）中使用策略之前对策略进行测试。  
  
-   当测试使用与数据库事实数据的策略 **该组** 中业务规则编辑器中，绑定 **该组** 对象将自动为您生成。 但是，当你调用相同的策略从业务流程使用 **调用规则** 形状，否 **该组** 自动对象传递给策略。 应创建 **该组** 业务流程中的对象并将其作为参数传递或创建的事实检索器组件，它断言 **该组** 对象，并配置要使用的事实检索器组件的策略。  
  
-   若要测试使用.NET 事实的策略，你应创建事实创建者组件，并指定它在 **选择事实** 对话框。 有关创建事实创建者的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。 当该策略使用数据库事实数据时，可以执行相同的操作 (**TypedDataConnection** 或 **TypedDataTable** 或 **TypedDataRow**) 或 XML 事实 (**TypedXmlDocument**)。  
  
## <a name="next-steps"></a>后续步骤  
 现在，你已完成本演练中，执行[演练： 调用从业务流程策略](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)演练中，为你调用的分步说明**ProcessPurchaseOrder**从业务流程的策略。  
  
## <a name="see-also"></a>另请参阅  
 [策略测试跟踪输出](../core/policy-test-trace-output.md)   
 [条件计算和操作执行](../core/condition-evaluation-and-action-execution.md)   
 [议程和优先级](../core/agenda-and-priority.md)
