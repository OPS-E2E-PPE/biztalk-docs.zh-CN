---
title: 包含在交换 TA1 出现以下错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bd7486d25e2c94fc809e6dc50c43359c152b70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278629"
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a>交换中包含的 TA1 发生了以下错误
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12TA1Error|  
|消息正文|{0} TA1 包含 id 为 {1} 发件人 id {2} 交换中，接收方 id {3} 出现以下错误：|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于指出的错误条件，接收管道无法处理传入的  TA1  确认。 此错误可能表明确认不符合 TA1Schema。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让确认的发送方解决确认中的问题，从而确保确认符合 TA1Schema，然后重新发送确认。