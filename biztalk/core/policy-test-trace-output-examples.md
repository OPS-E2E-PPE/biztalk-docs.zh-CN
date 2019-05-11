---
title: 策略测试跟踪输出示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 365d962c7a21721e75eb3c0c5abd6e2d93bfd5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394951"
---
# <a name="policy-test-trace-output-examples"></a>策略测试跟踪输出示例
本部分包含不同类型的事实的策略测试输出的示例。  
  
## <a name="net-class"></a>.Net 类  
 策略"LoanProcessing"中的示例规则"TestRule1":  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 **输出：**  
  
 规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 16 日上午 9:50:28  
  
 事实活动 2004 年 3 月 16 日上午 9:50:28  
  
 规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：MyTest.test  
  
 对象实例标识符：872  
  
 条件评估测试 （匹配） 2004 年 3 月 16 日上午 9:50:28  
  
 规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 规则集名称：LoanProcessing  
  
 测试表达式：MyTest.test.get_ID > 0  
  
 左的操作数的值：100  
  
 右操作数的值：0  
  
 测试结果：True  
  
 议程更新 2004 年 3 月 16 日上午 9:50:28  
  
 规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 16 日上午 9:50:28  
  
 规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 16 日上午 9:50:28  
  
 规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：MyTest.test  
  
 对象实例标识符：872  
  
## <a name="dataconnectiontypeddatarow"></a>DataConnection/TypedDataRow  
 策略"LoanProcessing"中的示例规则"TestRule1":  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **输出：**  
  
 规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 16 日上午 8:30:16  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：DataConnection:Northwind:CustInfo  
  
 对象实例标识符：874  
  
 条件评估测试 （匹配） 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 测试表达式： 选择 * 从 [CustInfo] 其中 [CreditCardBalance] > 0  
  
 左的操作数的值：  
  
 右操作数的值：  
  
 测试结果：True  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：177556  
  
 议程更新 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：177559  
  
 议程更新 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：177558  
  
 议程更新 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：DataConnection:Northwind:CustInfo  
  
 对象实例标识符：874  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：177559  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：177558  
  
 事实活动 2004 年 3 月 16 日上午 8:30:16  
  
 规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：177556  
  
 上面的示例指示 CustInfo 表中的三个行满足规则中的条件。  这导致三个唯一的 Typeddatarow 被添加到引擎和议程更新和规则触发对每个实例。  
  
## <a name="typedatatabletypeddatarow"></a>TypeDataTable/TypedDataRow  
 策略"LoanProcessing"中的示例规则"TestRule1":  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **输出：**  
  
 规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 17 日上午 11:27:35  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedDataTable:Northwind:CustInfo  
  
 对象实例标识符：377  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：376  
  
 条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 测试表达式：TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左的操作数的值：500  
  
 右操作数的值：0  
  
 测试结果：True  
  
 议程更新 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：375  
  
 条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 测试表达式：TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左的操作数的值：1000  
  
 右操作数的值：0  
  
 测试结果：True  
  
 议程更新 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：374  
  
 条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 测试表达式：TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左的操作数的值：35000  
  
 右操作数的值：0  
  
 测试结果：True  
  
 议程更新 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedDataTable:Northwind:CustInfo  
  
 对象实例标识符：377  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：375  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：374  
  
 事实活动 2004 年 3 月 17 日上午 11:27:35  
  
 规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedDataRow:Northwind:CustInfo  
  
 对象实例标识符：376  
  
> [!NOTE]
>  上面的示例显示 TypedDataTable 包含三个行，并且每个均作为 typeddatarow 添加。  每个计算结果为 True 的条件中导致要添加到议程的规则和触发。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 策略"LoanProcessing"中的示例规则"TestRule1":  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 **输出：**  
  
 规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 17 日上午 9:23:05  
  
 事实活动 2004 年 3 月 17 日上午 9:23:05  
  
 规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 对象实例标识符：858  
  
 事实活动 2004 年 3 月 17 日上午 9:23:05  
  
 规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 规则集名称：LoanProcessing  
  
 操作：ActualRebinds  
  
 对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 对象实例标识符：853  
  
 条件评估测试 （匹配） 2004 年 3 月 17 日上午 9:23:05  
  
 规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 规则集名称：LoanProcessing  
  
 测试表达式：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
  
 左的操作数的值：6  
  
 右操作数的值：4  
  
 测试结果：True  
  
 议程更新 2004 年 3 月 17 日上午 9:23:05  
  
 规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 规则集名称：LoanProcessing  
  
 操作：添加  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 17 日上午 9:23:05  
  
 规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 规则集名称：LoanProcessing  
  
 规则名称：TestRule1  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 17 日上午 9:23:05  
  
 规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 对象实例标识符：858  
  
 事实活动 2004 年 3 月 17 日上午 9:23:05  
  
 规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 规则集名称：LoanProcessing  
  
 操作：收回  
  
 对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 对象实例标识符：853  
  
 此示例演示**TypedXmlDocument**已添加到文档类型为"Microsoft.Samples.BizTalk.LoansProcessor.Case"引擎。  引擎根据规则中定义的 XPath 选择器，然后创建和添加"Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType"基于文档类型和选择器字符串类型的子级 TypedXmlDocument。  
  
 此子级 TypedXmlDocument 计算结果为 True 在条件中，从而导致议程更新和规则触发。  父级和子级**TypedXmlDocument**的然后，取消。  
  
## <a name="update-function"></a>Update 函数  
 示例策略"Order"  
  
 **"InventoryCheck" Rule**  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 **"Ship"规则**  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 **输出：**  
  
 规则集的规则引擎跟踪：订购 2004 年 3 月 17 日上午 10:31:17  
  
 事实活动 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：ActualRebinds  
  
 对象类型：TestClasses.Order  
  
 对象实例标识符：448  
  
 条件评估测试 （匹配） 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 测试表达式：TestClasses.Order.inventoryAvailable == True  
  
 左操作数的值： null  
  
 右操作数的值：True  
  
 测试结果：False  
  
 事实活动 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：ActualRebinds  
  
 对象类型：TestClasses.Shipment  
  
 对象实例标识符：447  
  
 事实活动 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：ActualRebinds  
  
 对象类型：TestClasses.Inventory  
  
 对象实例标识符：446  
  
 条件评估测试 （匹配） 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 测试表达式：TestClasses.Inventory.AllocateInventory == True  
  
 左的操作数的值：True  
  
 右操作数的值：True  
  
 测试结果：True  
  
 议程更新 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：添加  
  
 规则名称：InventoryCheck  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 规则名称：InventoryCheck  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：Update  
  
 对象类型：TestClasses.Order  
  
 对象实例标识符：448  
  
 条件评估测试 （匹配） 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 测试表达式：TestClasses.Order.inventoryAvailable == True  
  
 左的操作数的值：True  
  
 右操作数的值：True  
  
 测试结果：True  
  
 议程更新 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：添加  
  
 规则名称：发货  
  
 冲突解决标准：0  
  
 规则触发 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 规则名称：发货  
  
 冲突解决标准：0  
  
 事实活动 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：收回  
  
 对象类型：TestClasses.Order  
  
 对象实例标识符：448  
  
 事实活动 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：收回  
  
 对象类型：TestClasses.Shipment  
  
 对象实例标识符：447  
  
 事实活动 2004 年 3 月 17 日上午 10:31:17  
  
 规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 规则集名称：订单  
  
 操作：收回  
  
 对象类型：TestClasses.Inventory  
  
 对象实例标识符：446  
  
 在此示例中，与 Ship 规则相关联的条件计算结果为 False 第一次对其进行检查。  但是，当在触发 InventoryCheck 规则触发时，更改顺序中的 inventoryavailable 字段，且在引擎上为 Order 对象发出 Update 命令。  这将导致对 Ship 规则重新计算。  此时间条件的计算结果为 true，并且 Ship 规则将触发。  
  
> [!NOTE]
>  如果你的规则编写不正确，则具有 Update 函数的正向链接可能会导致无限循环。  如果发生这种情况，你将收到一条错误消息中包含文本的业务规则编辑器测试策略时"规则引擎检测到执行循环。"