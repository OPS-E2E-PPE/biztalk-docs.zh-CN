---
title: "拆分 HIPAA 子文档 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66d9badd-00c6-43a3-807e-0ad313983adc
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 799cb5813b3c13339a0c477bf142a467a91b2c94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="splitting-hipaa-subdocuments"></a>拆分 HIPAA 子文档
正如 ST/SE 标头所限定的，用于 HIPAA 的 EDI 交换通常在单个事务集内具有多个子文档。 EDI 接收管道支持从这样的事务集创建单独的 HIPAA 子文档。 这不同于将单个事务集作为单个消息进行处理的非 HIPAA EDI 交换。  
  
## <a name="subdocument-splitting-schemas"></a>子文档拆分架构  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持通过本机架构对下列 HIPAA 文档类型进行拆分：  
  
-   HIPAA 版本 4010 文档： 834 注册、 835 声明付款和 837 声明的三个变体  
  
-   HIPAA 版本 5010 文档： 276/277 声明状态 – 请求和响应、 834 注册和 837 声明的三个变体  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为这三种文档类型的每一种都提供了两个版本的架构。 对于每一种文档类型，通过文件名中的“Mulitple”标签对支持拆分的架构进行标识。 其他架构不支持子文档拆分。  
  
 在某些情况下，拆分和非拆分架构可能都是必需的。 通过为架构的一种变体使用自定义目标命名空间可以对此提供支持。  
  
## <a name="how-subdocument-splitting-is-enabled"></a>如何启用子文档拆分  
 可以通过 HIPAA 架构中的三个批注项启用 HIPAA 子文档的拆分。 前两个是用于中，必须设置为的 appinfo 批注的架构的条目**是**:  
  
```  
subdocument_break = "yes" Split_Without_Sibling_Data = "Yes"  
```  
  
 第三个批注项位于 HIPAA 架构内的相应记录级别。 此属性也必须设置为**是**。  
  
```  
subdocument_creation_break = "yes"  
```  
  
 仅当 HIPAA 架构中的子文档创建中断批注设置为“yes”，并且入站批处理选项参与方属性设置为“将交换拆分为事务集”时，HIPAA 交换才会拆分为子文档。 如果入站批处理选项参与方属性设置为保留该交换，EDI 拆装器将不会把交换拆分为子文档。 在此情况下，EDI 拆装器将忽略该批注。 如果发生此情况，事件查看器中不会产生任何警告。  
  
> [!NOTE]
>  子文档创建中断批注不能进行嵌套。 如果架构包括一个已对其应用了子文档批注的循环，该循环不能包含应用了子文档批注的另一个循环。  
  
## <a name="how-subdocuments-are-processed"></a>如何处理子文档  
 由 EDI 接收管道中的 EDI 拆装器对子文档进行拆分。 在接收管道验证了传入的交换并生成相应确认之后，它将每个单独的子文档路由至 MessageBox。 每个子文档在结构和语法上都是有效的；但是，可以预期的是，业务级别摘要、事务集总计和事务集控制编号是不同步的。 发送管道将覆盖每个子文档的 SE01 中现有段计数的值（来自原始事务集），将其改写为子文档中所包含的段的计数。 接收管道还将重置每个子文档中的事务集控制编号，以免子文档具有重复的控制编号。 这样可确保发送端的处理工作不会失败。  
  
 如果事务集在子文档拆分期间未能通过 EDI 或扩展验证，则单个未通过的事务集将被挂起。  
  
 订阅子文档的发送端口将从 MessageBox 获取每个子文档，序列化 XML 子文档，对它们进行批处理（如果启用），验证它们，然后发送它们。 发送管道会更新段数据元素 (SE01) 的计数。  
  
## <a name="how-subdocuments-are-split"></a>如何拆分子文档  
 子文档创建中断批注通常应用于包含 HIPAA 架构内的一个或多个元素的循环。 架构中位于中断循环之前和之后的其他元素复制到每个子文档中。  
  
 下表显示了子文档拆分的一个例子。 在本例中，子文档创建中断批注对于 CC 元素循环设置为“yes”。 因此，事务集中的 CC 元素被分割为多个单独的子文档，同时每个单独的子文档中都包括了事务集中的 AA、BB 和 DD 元素。  
  
|架构（最小/最大出现次数）|原始实例|子文档 #1|子文档 #2|子文档 #3|  
|---------------------------------------|-----------------------|---------------------|---------------------|---------------------|  
|ST (1,0)|ST|ST|ST|ST|  
|AA (1,1)|AA|AA|AA|AA|  
|BB loop (1,n)<br /><br /> BB1 (1,n)<br /><br /> CC loop (1,n) - subdocument_break = "yes"<br /><br /> CC1 (1,n)<br /><br /> CC2 (0,n)<br /><br /> BB2 (0,n)|BB1*1<br /><br /> CC1\*1<br /><br /> CC2\*1<br /><br /> BB2\*1<br /><br /> BB1\*2<br /><br /> CC1\*2<br /><br /> CC2\*2<br /><br /> BB1\*3<br /><br /> CC1\*3<br /><br /> CC2\*3|BB1*1<br /><br /> CC1\*1<br /><br /> CC2\*1<br /><br /> BB2\*1|BB1*2<br /><br /> CC1\*2<br /><br /> CC2\*2|BB1*3<br /><br /> CC1\*3<br /><br /> CC2\*3|  
|DD (0,n)|DD|DD|DD|DD|  
|SE|SE|SE|SE|SE|