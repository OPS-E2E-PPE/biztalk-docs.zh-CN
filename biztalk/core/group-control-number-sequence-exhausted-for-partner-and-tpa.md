---
title: "面向合作伙伴和 TPA 组控制编号的规则已耗尽 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf341f8d-02ec-4618-a980-c8ac90654b1a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1850b968a2c9b4c8d2c16fd90d9e37d80b60f8b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="group-control-number-sequence-exhausted-for-partner-and-tpa"></a>组控制编号序列的合作伙伴和 TPA 耗尽
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EdiControlNumberExhaustedForParty|  
|消息正文|TPA {2} 的情况下，组控制编号规则耗尽合作伙伴 {1} 状态。 重置 {2}-EDI 属性使用 BizTalk Server 管理中的序列。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示 BizTalk Server 无法处理该文档，因为组控件范围已用完在 {2} 协议。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请点击重置 {2} 协议的控制编号或增大控制编号范围或协议中点击针对控制编号范围规范的重置按钮的复选框。