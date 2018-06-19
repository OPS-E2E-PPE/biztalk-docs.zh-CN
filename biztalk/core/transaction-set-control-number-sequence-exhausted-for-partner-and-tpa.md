---
title: 事务集控制编号顺序面向合作伙伴和 TPA 已耗尽 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40d87b1f2681bb07816721971cfbd17d2c3a0b91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278333"
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a>事务集控制编号序列的合作伙伴和 TPA 已耗尽
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EdiControlNumberExhaustedForParty|  
|消息正文|事务集控制编号规则的合作伙伴 {1} TPA {2} 为已耗尽。 重置 {2}-EDI 属性使用 BizTalk Server 管理中的序列。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示 BizTalk Server 找不到文档因为事务设置控件范围已用完在 {2} 协议的进程。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请点击重置 {2} 协议的控制编号或增大控制编号范围或协议中点击针对控制编号范围规范的重置按钮的复选框。