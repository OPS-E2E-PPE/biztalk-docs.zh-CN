---
title: Edifact 交换应具有包含 UNA 或作为第一条线段的 UNB |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673df728dea00852e9713aed12f8ced902a4fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240029"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a>EDIFACT 交换应该包含 UNA 或 UNB 作为第一个段
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|Edifact 交换应该包含 UNA 或 UNB 作为第一个段。 实际找到的是 {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示 EDI 接收管道无法处理传入的 EDIFACT 交换，因为第一条线段 UNA 和 UNB 段都不。 UNA 段是可选的；UNB 段是必需的。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换的发送方包含 UNA 或 UNB 段作为交换的第一个段，然后重新发送交换。