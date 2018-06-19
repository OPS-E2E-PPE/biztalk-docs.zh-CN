---
title: 面向合作伙伴和 TPA 交换控制编号的规则已耗尽 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e77c0574-bc51-4690-a7f6-5702f6486f05
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4744a8db00985db3e85c1cb8843f07b3488544b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257037"
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a>面向合作伙伴和 TPA 交换控制编号的规则已耗尽
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EdiControlNumberExhaustedForParty|  
|消息正文|TPA {2} 的情况下，交换控制编号规则耗尽合作伙伴 {1} 状态。 重置 {2}-EDI 属性使用 BizTalk Server 管理中的序列。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示 BizTalk Server 无法处理该文档，因为在 {2} 协议已占用的交换控制范围。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请点击重置 {2} 协议的控制编号或增大控制编号范围或协议中点击针对控制编号范围规范的重置按钮的复选框。