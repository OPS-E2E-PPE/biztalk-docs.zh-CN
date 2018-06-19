---
title: 分隔符无效设置，因为至少一个分隔符超出允许的范围是 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70722adc1a099d340b862d38574b44391954aa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241453"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a>分隔符设置无效，因为至少有一个分隔符在允许的范围之外
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|DelimiterOutOfRange|  
|消息正文|无效的分隔符设置 {0}，至少有一个分隔符超出了允许的 0 到 127 范围|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示接收管道无法交换中的一个或多个分隔符是 ASCII 字符集中的值的范围设置处理传入的交换。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中的每个分隔符都在 ASCII 字符集中，然后重新发送交换。