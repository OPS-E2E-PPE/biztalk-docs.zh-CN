---
title: Doctype 无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 316413265084e2df64bf2ef5c2e4227f9a886829
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530819"
---
# <a name="doctype-is-invalid"></a>Doctype 无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  产品名称   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| 产品版本 |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    事件 ID     |                                                        -                                                        |
|  事件源   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI              |
|    组件    |                                                   EDI 引擎                                                    |
|  符号名称  |                                              DocTypeInvalidFormat                                               |
|  消息正文   | Doctype{0}无效。 不能确定一个或多个命名空间、 版本或事务集 id |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为未正确发现架构。  
  
 对于 X12，确定目标命名空间是在"启用自定义事务集定义"网格中的 x12 交换处理属性页的 EDI 属性对话框。 消息中的 GS02 和 ST01 值必须与某行网格中，若要正确标识目标命名空间中进行匹配。 通过在传入的事务集标识的目标命名空间中添加的版本 （GS08 的前五个字符） 和 doctype (ST01) 创建要用于该事务集的架构的名称。  
  
 对于 EDIFACT，在 EDI 属性对话框的 EDIFACT 交换处理属性页的"启用自定义事务集定义"网格中确定目标命名空间。 消息中的 UNH2.1、 UNH2.2、 UNH2.3、 UNH2.5、 UNG2.1 和 UNG2.2 值必须与某行网格中，若要正确标识目标命名空间中进行匹配。 通过在 UNH2.2、 UNH2.3 中的消息发行版号以及 UNH2.1 中的传入事务集标识的目标命名空间中的消息类型中添加的消息版本号创建要用于该事务集的架构的名称。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行，如下所示：  
  
1.  请确保"启用自定义事务集定义"网格中的交换处理属性页的 EDI 属性对话框中的行正确标识事务集的架构的命名空间。 如果没有，请更改网格中的值。  
  
2.  如果已正确标识命名空间，确定用于标识架构的值是否正确。 对于 X12，它们的版本 （GS08 的前五个字符） 和 doctype (ST01) 中传入的事务集。 对于 EDIFACT，它们是在 UNH2.2、 UNH2.3 中的消息发行版号和消息类型 UNH2.1 中的传入事务集中的消息版本号。 如果这些值不正确，请让发送方的事务集更改这些字段的值然后重新发送消息。