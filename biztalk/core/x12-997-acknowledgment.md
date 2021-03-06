---
title: X12 997 确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62a352fb-635c-4f0e-9844-4b250159333d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff45d228a9e92905a141b2997c0035326fa01b01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298621"
---
# <a name="x12-997-acknowledgment"></a>X12 997 确认
X12 997 功能确认报告已接收交换的状态。 它报告每个处理收到的文档时遇到错误。 BizTalk EDI 接收管道将始终生成 4010 符合 997;但是，EDI 接收管道和 EDI 发送管道还可以验证符合 5010 的 997。  
  
 像所有的 X12 事务集，997 确认在 GS/GE 信封内部发送。 ST 和 SE 与任何其他事务集没有什么不同。  
  
 下表中显示了 997 确认事务集内的分段。  
  
|位置|段<br />ID|“属性”|Req.<br />Des。|最大值。 改用|循环<br />重复|  
|--------------|-----------------|----------|----------------|--------------|------------------|  
|010|ST|事务集的标头 （用于确认）|M|1|-|  
|020|AK1|功能组响应标头|M|1|-|  
|030|AK2|事务集响应标头|O|1|999999 <br />(循环 ID = AK2)|  
|040|AK3|数据分段注释|O|1|999999 <br />(循环 ID = AK2/AK3)|  
|050|AK4|数据元素注释|O|99|-|  
|060|AK5|事务集响应尾部|M|1|-|  
|070|AK9|功能组响应尾部|M|1|-|  
|080|SE|事务集尾部 （用于确认）|M|1|-|  
  
- Req.Des。 = Requirement 指定内容  
  
- M = 必需  
  
- O = 可选  
  
  下面介绍 AK 段。 AK2 到 AK5 循环中的各段提供有关事务集与错误的信息。  
  
## <a name="ak1"></a>AK1  
 必需的 AK1 分段标识要确认具有以下数据元素的功能组：  
  
-   AK101 是要确认的功能组的功能组 ID (GS01)。  
  
-   AK102 是要确认的功能组的组控制编号 （GS06 和 GE02）。  
  
-   AK103 可选，是在原始事务的 GS08 中发送的 EDI 实现版本。 AK103 支持入站符合 5010 的 997。  
  
## <a name="ak2"></a>AK2  
 可选的 AK2 段包含接收功能组内事务集的确认。 如果有多个 AK2 分段，它们将作为一系列循环发送。 每个 AK2 循环标识事务集已被接收的顺序。 AK2 段标识的两个数据元素的事务集：  
  
- AK201 是事务的事务集的被确认集 ID (ST01)。  
  
- AK202 是事务的事务集控制编号 （ST02 和 SE02） 的正在确认集。  
  
- AK203 可选，是在原始事务的 ST03 中发送的 EDI 实现版本。 AK203 支持入站符合 5010 的 997。  
  
  如果事务集出错，AK2 循环将包含 AK3、 AK4 和 AK5 段。 有关详细信息，请参阅下面对这些分段的说明。  
  
  您可以指定是否接受或拒绝，或仅针对拒绝的事务集，为所有的事务集生成 AK2 分段。 BizTalk Server 将生成 AK2 分段为接受的事务集 (其中 AK501 = = A) 如果选择**为已接受的事务集包含 AK2 循环**中的复选框**确认**页两个业务配置文件之间的协议的协议属性对话框 (或**确认**X12 的页设置为业务配置文件的选项卡)。 否则为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成仅为拒绝的事务集的 AK2 循环。 如果没有为响应到后备协议设置，则 997 生成设置默认的交换解析协议，并且不会为接受的事务集生成 AK2 分段。  
  
## <a name="ak3"></a>AK3  
 可选的 AK3 分段报告数据段中的错误，并标识数据分段的位置。 为每个段中包含一个或多个错误的事务集创建一个 AK3 分段。 如果有多个 AK3 分段，它们将作为一系列循环 （每个循环一个分段） 发送。 AK3 分段包含四个数据元素用于指定错误中的每个段的位置，并报告的在该位置找到的语法错误的类型：  
  
-   AK301 用其 X12 标识错误的段分段 ID，例如 NM1。  
  
-   AK302 是段的存在中错误的段计数。 ST 段是"1"，每个段按 1 递增段计数。  
  
-   AK303 用于标识绑定的循环： 由一个 LS 分段和 LE 分段包围的循环。 AK303 包含值的 LS 和 LE 分段的分段绑定错误。  
  
-   AK304 是数据段中的错误的错误代码。 AK304 是可选的但如果标识段存在错误，则，则需要。 有关 AK304 错误代码的列表，请参阅[X12 997 确认错误代码](../core/x12-997-acknowledgment-error-codes.md)。  
  
## <a name="ak4"></a>AK4  
 可选的 AK4 分段报告数据元素或复合数据结构中的错误，并标识数据元素的位置。 发送时的 AK304 数据元素是"8"，"段有数据元素错误"。 它可以最多重复 99 次每个 AK3 分段内。 AK4 分段包含四个数据元素用于指定错误中的每个数据元素或复合数据结构的位置，并报告的在该位置找到的语法错误的类型。  
  
-   AK401 是具有字段 AK41.1、 AK41.2 和 AK41.3 的复合数据元素。 AK401-1 用数值计数标识数据元素或复合数据结构错误。 例如，如果在段中的第二个数据元素中有错误，则 AK401 等于"2"。 AK401 2 标识发生错误的复合数据结构中的组件数据元素的数值计数。 当 AK401 报告不是复合数据结构时出错时，则 AK401 2 不值。  
  
     AK41.3 可选，是重复数据元素的位置。 AK41.3 支持入站符合 5010 的 997。  
  
-   AK402 是可选的标识的简单 X12 数据元素数中错误的元素。 例如，NM101 是简单 X12 数据元素的编号 98。  
  
-   AK403 是必需的报告标识元素的错误。 有关 AK403 错误代码的列表，请参阅[X12 997 确认错误代码](../core/x12-997-acknowledgment-error-codes.md)。  
  
-   AK404 是可选的并且包含在错误中标识的数据元素的副本。 如果错误表示无效的字符，则不使用 AK404。  
  
## <a name="ak5"></a>AK5  
 AK5 段报告是否接受或拒绝 AK2 段中标识的事务集及其原因。 AK5 分段是必需的如果确认中包含可选 AK2 循环。 AK4 分段有一个必需的数据元素，指定事务的状态将设置和一到五个可选的数据元素提供错误代码基于事务的语法编辑设置。  
  
-   AK501 指定是否接受或拒绝标识的事务集。 有关 AK501 错误代码的列表，请参阅[X12 997 确认错误代码](../core/x12-997-acknowledgment-error-codes.md)。  
  
-   AK502 至 AK506 指示错误的性质。 有关 AK501 错误代码的列表，请参阅[X12 997 确认错误代码](../core/x12-997-acknowledgment-error-codes.md)。  
  
## <a name="ak9"></a>AK9  
 必需的 AK9 分段指示是否接受或拒绝 AK1 段中标识的功能组及其原因。 AK9 分段有四个必需的数据元素用于指定状态的事务集和任何的性质错误和一到五个可选元素，用于指定所述的任何错误。  
  
-   AK901 是必需的指定是否接受或拒绝在 AK1 中标识的功能组。 有关 AK901 错误代码的列表，请参阅[X12 997 确认错误代码](../core/x12-997-acknowledgment-error-codes.md)。  
  
-   AK902 指定标识的功能组尾部 (GE01) 中包括的事务集数目。  
  
-   AK903 指定所接收的事务集数目。  
  
-   AK904 指定标识功能组中接受的事务集的数目。  
  
-   AK905 至 AK909 可以指示一到五个标识的功能组错误。 有关 AK905 至 AK909 错误代码的列表，请参阅[X12 997 确认错误代码](../core/x12-997-acknowledgment-error-codes.md)。  
  
## <a name="see-also"></a>请参阅  
 [X12 997 确认错误代码](../core/x12-997-acknowledgment-error-codes.md)