---
title: 通信模式错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36677694b8f2d0973c04d942a196d055b696bd5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232205"
---
# <a name="communication-pattern-errors"></a>通信模式错误
用于诊断和解决 WCF 通信模式错误的信息。  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a>单向端口不支持错误消息
  
||错误详细信息|  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|单向端口上不支持错误消息。 更正服务说明"{0}"端口类型"{1}"，然后重新运行该向导|  
  
## <a name="explanation"></a>解释  
 此错误表示尝试使用的服务是单向服务，并且指定了错误。  
  
## <a name="user-action"></a>用户操作  
 通过将通信模式从单向模式切换到请求-响应模式来更正服务。 或者从代码中删除此错误。
 
 