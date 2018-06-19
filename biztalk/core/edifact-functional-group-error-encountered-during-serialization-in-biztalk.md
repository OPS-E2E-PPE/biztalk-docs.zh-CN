---
title: 在序列化期间遇到错误。 Edifact 功能组具有以下错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8166e5a66038d4cbda3a6fcb9597c7827d1eeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239845"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a>在序列化期间遇到错误。 EDIFACT 功能组发生了以下错误
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EfactFunctionalGroupSendError|  
|消息正文|在序列化期间遇到错误。 Edifact 功能组中 id 为"{0}"，与 id {1} 交换发件人 id {2} 接收方 id {3} 具有以下错误：|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过组指明的错误，在序列化传出的 EDIFACT 交换中的某个功能组时 EDI 发送管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识功能组中的错误，然后在文档中确定问题解决方案。