---
title: "可接受的 X12 功能组控制编号已达到来宾设置的最大限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05cba774-fa35-4694-aa34-d7151f8cd75c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3210fb773b7093c2e28f98e0cf1aa223e1a63936
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-guest-settings"></a>已达到“来宾”设置的可接受 X12 功能组控制编号最大限制
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|GlobalEdifactUnhNumberError|  
|消息正文|已达到“来宾”设置的可接受 X12 功能组控制编号最大限制。 导航到合作伙伴协议管理器的全局配置接收方角色屏幕中的字段 GS 6 可重置计数器|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在全局设置中指定的 GS06 字段中的组控制编号大于所允许的最大值。 组控制编号的最大字符数为 9。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请按照如下方式重置组控制编号：  
  
1.  在“EDI 全局属性”对话框中，打开“GS 和 ST 段定义”页。  
  
2.  单击与 GS06 字段关联的“编辑”字段。  
  
3.  将组控制编号设置为一个新值，以便该字段具有 9 个或更少的数字。