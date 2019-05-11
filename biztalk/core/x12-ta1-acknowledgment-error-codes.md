---
title: X12 TA1 确认错误代码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47eb315f-ec99-4e1e-937b-22199255f14f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f3aeff02563e31e672abb58b12c71ce9339dd0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394768"
---
# <a name="x12-ta1-acknowledgment-error-codes"></a>X12 TA1 确认错误代码
本主题列出了使用 X12 的段中的错误代码的 TA1 确认。 有关这些段的详细信息，请参阅[X12 TA1 确认](../core/x12-ta1-acknowledgment.md)。  
  
 下表指示哪一类错误指定由 X12 规范中支持的代码[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2 以及不支持。 引擎行为 (TA104) 的值如下所示：  
  
-   A = 接受  
  
-   E = 接受存在错误的交换  
  
-   R = 交换被拒绝/已挂起  
  
|条件|引擎行为 （TA104 值）|TA105 值|支持？|  
|---------------|-------------------------------------|-----------------|----------------|  
|成功|A|000|是|  
|标头 ISA 13 和尾部 IEA02 交换控制编号不匹配|E|001|是|  
|标准中 ISA11 （控制标准） 不受支持|E|002|是<br /><br /> （如果 ID 不匹配）|  
|不支持版本的控件|E|003|不<sup>1</sup>|  
|段终止符无效<sup>2</sup>|R|004|是|  
|发件人的无效的交换 ID 限定符|R|005|是<br /><br /> （如果 ID 不匹配）|  
|无效的交换发送方 ID|E|006|是<sup>3</sup>|  
|无效的交换接收方 ID 限定符|R|007|是<br /><br /> （如果 ID 不匹配）|  
|交换接收方 ID 无效|E|008|不<sup>3</sup>|  
|未知的交换接收方 ID|E|009|是|  
|授权信息限定符值无效|R|010|是<br /><br /> （如果 ID 不匹配）|  
|授权信息值无效|R|011|是<br /><br /> （如果参与方配置/赋值）|  
|安全信息限定符值无效|R|012|是<br /><br /> （如果 ID 不匹配）|  
|安全信息值无效|R|013|是<br /><br /> （如果参与方配置/赋值）|  
|交换日期值无效|R|014|是|  
|交换时间值无效|R|015|是|  
|交换标准标识符值无效|R|016|是|  
|交换版本 ID 值无效|R|017|是<sup>4</sup>|  
|交换控制编号值无效|R|018|是|  
|确认请求值无效|E|019|是|  
|测试指示器值无效|E|020|是|  
|包含的组的值无效|E|021|是|  
|控制结构无效|R|022|是|  
|不正确 （过早） 的文件尾 （传输）|R|023|是|  
|交换内容无效 （例如，GS 段无效）|R|024|是|  
|交换控制编号重复|R<br /><br /> （基于设置）|025|是|  
|数据元素分隔符无效|R|026|是|  
|组件元素分隔符无效|R|027|是|  
|延迟的送达请求中的无效的送达日期|不支持|-|-|  
|延迟的送达请求中无效的传递时间|不支持|-|-|  
|延迟的送达请求中的无效的送达时间代码|不支持|-|-|  
|服务的级别无效|不支持|-|-|  
  
 <sup>1</sup>改为使用错误代码 017。  
  
 <sup>2</sup>段终止符的有效组合都是：段终止符字符和段终止符字符后跟后缀 1 和后缀 2。  
  
 <sup>3</sup>如果接收的交换在接收端口要求身份验证支持。 发件人 ID 相关的属性将会进行审核，如果不一致会被拒绝。 如果参与方设置不可用，因为未配置，交换将被拒绝。  
  
 <sup>4</sup>指示枚举值无效。