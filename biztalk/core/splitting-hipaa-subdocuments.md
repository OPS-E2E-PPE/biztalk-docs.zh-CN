---
title: 拆分 HIPAA 子文档 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66d9badd-00c6-43a3-807e-0ad313983adc
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ea3ceaf708db8620915337de5133644b6eafe87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258625"
---
# <a name="splitting-hipaa-subdocuments"></a>拆分 HIPAA 子文档
HIPAA 的 EDI 交换通常具有单个事务集内的多个子文档受限于 ST/SE 标头。 EDI 接收管道支持单独的 HIPAA 子文档创建从这样的事务集。 这是不同于非 HIPAA EDI 交换，在其中一个事务集被处理为一条消息。  
  
## <a name="subdocument-splitting-schemas"></a>子文档拆分架构  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持通过本机架构下列 HIPAA 文档类型的拆分：  
  
- HIPAA 版本 4010 文档：834 登记、 835 索赔付款和 837 索赔的三个变体  
  
- HIPAA 版本 5010 文档：276/277 索赔状态-请求和响应、 834 登记和 837 索赔的三个变体  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 这三种文档类型的每个提供两个版本的架构。 对于每个文档类型，由文件名称中的多个标记标识支持拆分的架构。 其他架构不支持子文档拆分。  
  
  在某些情况下，可能需要拆分和非拆分架构。 将通过使用自定义目标命名空间的架构的一种变体支持此功能。  
  
## <a name="how-subdocument-splitting-is-enabled"></a>如何启用子文档拆分  
 通过的 HIPAA 架构中的三个批注项启用 HIPAA 子文档的拆分。 前两个架构必须设置为在 appinfo 批注中的条目**是**:  
  
```  
subdocument_break = "yes" Split_Without_Sibling_Data = "Yes"  
```  
  
 第三个批注项位于 HIPAA 架构中的相应记录级别。 此属性还必须设置为**是**。  
  
```  
subdocument_creation_break = "yes"  
```  
  
 仅当 HIPAA 架构中的子文档创建中断批注设置为"yes"，并且入站的批处理选项参与方属性设置为"交换拆分为事务集"，HIPAA 交换将拆分为子文档。 如果入站的批处理选项参与方属性设置为保留交换，EDI 拆装器将不会拆分为子文档交换。 在这种情况下，EDI 拆装器将忽略该批注。 如果此查看器发生的事件中，将会不引发任何警告。  
  
> [!NOTE]
>  子文档创建中断批注不能嵌套。 如果架构包含对其应用了子文档批注的循环，该循环不能包含对其应用了子文档批注的另一个循环。  
  
## <a name="how-subdocuments-are-processed"></a>如何处理子文档  
 EDI 拆装器在 EDI 接收管道拆分为子文档。 接收管道将验证传入的交换并生成相应确认之后，它将每个单独的子文档路由到 MessageBox。 每个子文档是结构和语法上都有效，则为但是，业务级别摘要、 事务集总计和事务集控制编号都将是不同步。 发送管道将覆盖在每个子文档的 （它来自原始事务集） 的子文档中包括的段计数的 SE01 中现有段计数的值。 接收管道还将重置每个子文档中的事务集控制编号，以便为子文档没有重复的控制编号。 这可确保发送端处理不会失败。  
  
 如果事务集未能通过 EDI 或扩展验证在子文档拆分期间，单个失败的事务集被挂起。  
  
 订阅子文档的发送端口将从 MessageBox 获取每个子文档，序列化 XML 子文档，批处理 （如果启用），验证它们，并发送它们。 发送管道会更新段数据元素 (SE01) 的计数。  
  
## <a name="how-subdocuments-are-split"></a>如何拆分子文档  
 子文档创建中断批注通常应用于包含 HIPAA 架构中的一个或多个元素的循环。 在每个多个子文档中复制其他元素之前和之后在架构中位于中断循环。  
  
 下表显示了子文档拆分的示例。 在此示例中，子文档创建中断批注设置为"是"对于 CC 元素循环。 因此，事务集中的 CC 元素被分割单独文档，同时 AA、 BB 和 DD 元素中的事务集都包含在每个单独的子文档。  
  
|架构 （最小值和最大出现次数）|原始实例|子文档 #1|子文档 #2|子文档 #3|  
|---------------------------------------|-----------------------|---------------------|---------------------|---------------------|  
|ST (1，0)|ST|ST|ST|ST|  
|AA (1,1)|AA|AA|AA|AA|  
|BB 循环 (1，n)<br /><br /> BB1 (1,n)<br /><br /> 抄送循环 (1，n)-subdocument_break ="yes"<br /><br /> CC1 (1,n)<br /><br /> CC2 (0,n)<br /><br /> BB2 (0,n)|BB1*1<br /><br /> CC1\*1<br /><br /> CC2\*1<br /><br /> BB2\*1<br /><br /> BB1\*2<br /><br /> CC1\*2<br /><br /> CC2\*2<br /><br /> BB1\*3<br /><br /> CC1\*3<br /><br /> CC2\*3|BB1*1<br /><br /> CC1\*1<br /><br /> CC2\*1<br /><br /> BB2\*1|BB1*2<br /><br /> CC1\*2<br /><br /> CC2\*2|BB1*3<br /><br /> CC1\*3<br /><br /> CC2\*3|  
|DD (0，n)|DD|DD|DD|DD|  
|SE|SE|SE|SE|SE|