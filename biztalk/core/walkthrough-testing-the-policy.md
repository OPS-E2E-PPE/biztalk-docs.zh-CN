---
title: 演练： 测试策略 |Microsoft Docs
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
ms.openlocfilehash: 0ddf9dcc459fbee7494a913846f1c9d2a7137579
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001760"
---
# <a name="walkthrough-testing-the-policy"></a>演练： 测试策略
本演练中提供的测试中创建的策略的分步过程[演练： 创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练。  

## <a name="prerequisites"></a>必要條件  
 必须完成[演练： 创建简单业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练在执行本演练之前。  

## <a name="overview-of-this-walkthrough"></a>本演练概述  
 本概览包含两个过程，如下表所述。  

|过程标题|过程说明|  
|---------------------|---------------------------|  
|若要创建测试文件|提供了用于创建两个示例 XML 文件，其中的值为 400 Quantity 字段的分步说明 (\<= 500)，另一个为 700 (> 500) 的 Quantity 字段的值。|  
|测试 ProcessPurchaseOrder 策略|提供使用业务规则编辑器来测试该策略的逐步说明。|  

### <a name="to-create-the-test-files"></a>若要创建测试文件  

1.  上**启动**菜单中，打开**记事本**。  

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

3.  上**文件**菜单上，单击**TextFile1.txt 保存为**。  

4.  更改的值**另存为类型**从**文本文档 (\*.txt)** 到**的所有文件**。  

5.  将目录更改为**C:\BRE-Walkthroughs**。  

6.  类型**SamplePO.xml**有关**文件名**，然后单击**保存**。  

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

9. 上**文件**菜单上，单击**TextFile1.txt 保存为**。  

10. 更改的值**另存为类型**从**文本文档 (\*.txt)** 到**的所有文件**。  

11. 将目录更改为**C:\BRE-Walkthroughs**。  

12. 类型**SamplePO2.xml**有关**文件名**，然后单击**保存**。  

13. 关闭记事本。  

### <a name="to-test-the-processpurchaseorder-policy"></a>测试 ProcessPurchaseOrder 策略  

1.  上**启动**菜单中，打开**业务规则编辑器**。 如果你有业务规则编辑器已打开，请按 f5 键刷新。  

    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  

2.  在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**测试策略**.  

3.  在中**XMLDocuments**节点中，选择**RuleTest.PO**，然后单击**添加实例**。  

     ![业务规则编辑器&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")  

4.  选择**SamplePO.xml**文件之前，创建，然后单击**打开**。  

5.  单击**测试**。  

6.  查看“输出”窗口中的输出。 查看“来自第一个测试的输出分析 (samplepo.xml)”部分，它解释了您所看到的输出。  

7.  打开**SamplePO.xml**记事本和通知中的值**状态**字段设置为**已批准**。  

8.  右键单击**版本 1.0**，然后单击**测试策略**。  

9. 选择**SamplePO.xml**，单击**删除实例**，然后单击**添加实例**。  

10. 选择**SamplePO2.xml**文件之前，创建，然后单击**打开**。  

11. 单击**测试**。 查看“来自第二个测试的输出分析 (samplepo2.xml)”部分，它解释了您所看到的输出。  

12. 打开**SamplePO2.xml**文件在记事本中，可以看到的值**状态**字段是仍**XYZ**。  

## <a name="analysis-of-the-output-from-the-first-test-samplepoxml"></a>来自第一个测试的输出分析 (samplepo.xml)  

> [!NOTE]
>  输出文本为粗体并且在输出文本后跟有解释。  

 **规则集的规则引擎跟踪： ProcessPurchaseOrder 2006 年 8 月 31 日下午 1:33:10**  

 执行策略的规则引擎跟踪**ProcessPurchaseOrder**在 2006 年 8 月 31 日开始的 1:33:10 PM。  

 **事实活动 2006 年 8 月 31 日下午 1:33:10**  

 **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **规则集名称： ProcessPurchaseOrder**  

 **操作： 断言**  

 **对象类型： TypedXmlDocument:PurchaseOrder**  

 **对象实例标识符： 14626574**  

 当您单击**测试**，将发生以下情况：  

1. 业务规则编辑器创建**RuleEngine.Policy**对象，它又创建一个新的规则引擎实例或获取从规则引擎缓存规则引擎实例。  

2. 业务规则编辑器创建**TypedXmlDocument**对象基于 SamplePO.xml 文件。  

3. 业务规则编辑器将调用**Policy.Execute**方法替换**TypedXmlDocument**对象作为参数。  

4. **Policy.Execute**方法断言 （添加） **TypedXmlDocument**对象作为事实到规则引擎工作内存。  

5. 使用规则引擎**TypedXmlDocument**对象作为事实，并执行**ProcessPurchaseOrder**策略。  

   **事实活动 2006 年 8 月 31 日下午 1:33:10**  

   **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

   **规则集名称： ProcessPurchaseOrder**  

   **操作： 断言**  

   **对象类型： TypedXmlDocument:PurchaseOrder: / PurchaseOrder**  

   **对象实例标识符： 64530307**  

   **事实活动 2006 年 8 月 31 日下午 1:33:10**  

   **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

   **规则集名称： ProcessPurchaseOrder**  

   **操作： 断言**  

   **对象类型： TypedXmlDocument:PurchaseOrder: / PurchaseOrder/项**  

   **对象实例标识符： 43901854**  

6. 规则引擎将确定哪些子**TypedXmlDocument**对象以创建基于在规则中定义的 XPath 选择器。 在生成业务规则编辑器中的规则时，XPath 选择器值默认为在所选节点上方的节点**XML 架构**在事实浏览器选项卡。 XPath 字段值默认为所选节点本身，相对于其父节点。 但是，如果所选节点具有子节点，则只创建指向所选节点的 XPath 选择器绑定，而不创建任何 XPath 字段绑定。  

7. 下表显示了 XPath 选择器和 XPath 字段绑定中使用的字段的值**ProcessPurchaseOrder**策略。 （该策略只具有一个规则，即 ApprovalRule。）  

| 字段名称 |                                                             XPath 选择器                                                              |                    XPath 字段                     | XPath 选择器（简化形式） | XPath 字段<br /><br /> （简化形式） |
|------------|-----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|----------------------------------|-------------------------------------------|
|  Quantity  | /\*[本地名称 （) = 'PurchaseOrder' and namespace-uri （) ='http://EAISolution.PurchaseOrder'] /\*[本地名称 （) = Item and namespace-uri （) ='] | \*[本地名称 （) 的数量 and namespace-uri （) = = '] |       / PurchaseOrder/项        |                 Quantity                  |
|   “登录属性”   |                       /\*[本地名称 （) = 'PurchaseOrder' and namespace-uri （) ='<http://EAISolution.PurchaseOrder>']                        |  \*[本地名称 （) = 'Status' and namespace-uri （) = ']  |          / PurchaseOrder          |                  “登录属性”                   |

<!---Loc Comment: Please, verify strucutre in line 183 and 184--->

#### <a name="to-view-the-xpath-selector-and-xpath-field-bindings-for-the-quantity-and-status-fields"></a>查看“数量”字段和“状态”字段的 Xpath 选择器和 Xpath 字段绑定  

1. 在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，然后展开**版本 1.0**。  

2. 单击**ApprovalRule**。  

3. 在右侧的 IF 窗格中，单击**PO: / PurchaseOrder/Item/Quantity**。  

4. 验证是否能看到显示为上表中的值**XPath 选择器**并**XPath 字段**属性窗口中的绑定。  

5. 重复步骤 3 和 4 **PO: / PurchaseOrder/状态**字段。  

   规则引擎就会创建一个子**TypedXmlDocument**对象从原始**TypedXmlDocument**提交每个 XPath 选择器。 由于没有策略中使用的两个非重复 XPath 选择器 (**/PurchaseOrder/项**有关**Quantity**字段和 **/PurchaseOrder**为**状态**字段)，规则引擎就会创建两个子**TypedXmlDocument**对象，并将它们添加到规则引擎工作内存。  

> [!NOTE]
>  若要查看跟踪再次输出中，单击**版本 1.0**策略浏览器窗口中。  

 **条件评估测试 （匹配） 2006 年 8 月 31 日下午 1:33:10**  

 **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **规则集名称： ProcessPurchaseOrder**  

 **测试表达式： TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  

 **左操作数的值： 400**  

 **右操作数的值： 500**  

 **测试结果： True**  

 **议程更新 2006 年 8 月 31 日下午 1:33:10**  

 **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **规则集名称： ProcessPurchaseOrder**  

 **操作： 添加**  

 **规则名称： ApprovalRule**  

 **冲突解决标准： 0**  

 规则引擎使用三阶段的算法（条件评估-冲突解决-执行操作）来执行策略。 在条件评估阶段中，规则引擎中的策略中的所有规则的条件的计算结果，并添加其条件计算结果为规则`true`到该议程。 在此简单示例中， **ProcessPurchaseOrder**策略具有只有一个规则**ApprovalRule**。 因此，规则引擎计算条件的结果**数量 < = 500**，在**ApprovalRule**使用的值**Quantity**字段中提交的 XML 文档，这是**400**。 上面的输出显示左操作数、右操作数和测试结果的值。  

 在第二个阶段中，冲突解决标准阶段，其条件评估结果为规则`true`添加到议程中根据优先级顺序。 在此方案中，添加了规则引擎**ApprovalRule**到该议程因为的条件**ApprovalRule**计算结果为`true`。 上面的输出中显示冲突解决标准是只在规则的优先级 (**ApprovalRule**)。 如果单击**ApprovalRule**策略浏览器窗口中的节点，您可以看到值**优先级**上作为属性窗口中的规则的属性**0**，这是规则的默认值。 如果您在某个策略中具有多个规则，并且想要确保一个规则中的操作在另一个规则中的操作后执行，则应相应设置优先级。 该数字越大，规则的优先级就越高。  

 **规则触发 2006 年 8 月 31 日下午 1:33:10**  

 **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **规则集名称： ProcessPurchaseOrder**  

 **规则名称： ApprovalRule**  

 **冲突解决标准： 0**  

 在最后一个阶段（执行操作阶段）中，规则引擎将开始执行规则中的操作。 中的一个操作**ApprovalRule**，用于设置的值**状态**字段中为提交的 XML 文档**已批准**。  

 **事实活动 2006 年 8 月 31 日下午 1:33:10**  

 **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **规则集名称： ProcessPurchaseOrder**  

 **操作： 收回**  

 **对象类型： TypedXmlDocument:PurchaseOrder**  

 **对象实例标识符： 14626574**  

 **事实活动 2006 年 8 月 31 日下午 1:33:10**  

 **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **规则集名称： ProcessPurchaseOrder**  

 **操作： 收回**  

 **对象类型： TypedXmlDocument:PurchaseOrder: / PurchaseOrder/项**  

 **对象实例标识符： 43901854**  

 **事实活动 2006 年 8 月 31 日下午 1:33:10**  

 **规则引擎实例标识符： bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**  

 **规则集名称： ProcessPurchaseOrder**  

 **操作： 收回**  

 **对象类型： TypedXmlDocument:PurchaseOrder: / PurchaseOrder**  

 **对象实例标识符：** 64530307  

 提交的所有事实 (**PurchaseOrder**) 到规则引擎以及由规则引擎创建的子事实根据 XPath 选择器 (**\PurchaseOrder** 和 **\PurchaseOrder\Item**)取消 （删除） 从规则引擎工作内存中。  

## <a name="analysis-of-the-output-from-the-second-test-samplepo2xml"></a>来自第二个测试的输出分析 (samplepo2.xml)  
 **条件评估测试 （匹配） 2006 年 9 月 5 日下午 5:24:42**  

 **规则引擎实例标识符： b749d2fd-a883-4c2f-9974-5cf688010622**  

 **规则集名称： ProcessPurchaseOrder**  

 **测试表达式： TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**  

 **左操作数的值： 700**  

 **右操作数的值： 500**  

 **测试结果：** False  

 规则引擎计算条件 (**数量 < = 500**) 中**ApprovalRule**使用单个**项**对象。 您可以看到左的操作数的值是的值**Quantity** XML 文档中的元素**700**。 测试结果`false`因为**700 < = 500**，因此，该规则不会添加到规则引擎的议程。 议程中没有任何规则。 因此，没有任何操作来执行和的值**状态**字段保持**XYZ**。  

## <a name="comments"></a>注释  

-   建议您在客户端应用程序（例如 BizTalk 应用程序）中使用策略之前对策略进行测试。  

-   在您测试使用与数据库事实的策略**DataConnection**绑定在业务规则编辑器**DataConnection**对象将自动为您生成。 但是，在通过调用同一策略从业务流程通过使用**调用规则**形状，无**DataConnection**对象自动传递到该策略。 应创建**DataConnection**业务流程中的对象并将其作为参数传递或创建断言事实检索器组件**DataConnection**对象，并配置要使用的策略事实检索器组件。  

-   若要测试使用.NET 事实的策略，应创建事实创建器组件，并指定它在**选择事实**对话框。 有关创建事实创建器的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。 当该策略会使用数据库事实数据时，可以执行相同的操作 (**TypedDataConnection**或**TypedDataTable**或**TypedDataRow**) 或 XML 事实 (**TypedXmlDocument**)。  

## <a name="next-steps"></a>后续步骤  
 现在，已完成本演练中，执行[演练： 从业务流程调用策略](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)演练中，为你提供分步说明，用于调用**ProcessPurchaseOrder**从业务流程的策略。  

## <a name="see-also"></a>请参阅  
 [策略测试跟踪输出](../core/policy-test-trace-output.md)   
 [条件评估和操作执行](../core/condition-evaluation-and-action-execution.md)   
 [议程和优先级](../core/agenda-and-priority.md)
