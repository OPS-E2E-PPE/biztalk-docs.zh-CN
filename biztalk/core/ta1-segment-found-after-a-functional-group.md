---
title: TA1 段后功能组找到 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3d090a-0916-4a0e-82dc-2c9af9f97683
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86e9ac6e1e0c3a3b76dbc144739f3a16fddd0d67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278517"
---
# <a name="ta1-segment-found-after-a-functional-group"></a>在功能组后发现 TA1 段
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|TA1FoundAfterFunctionalGroup|  
|消息正文|在功能组后发现 TA1 段。 因此，消息被拒绝|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的确认，因为确认包含一个功能组并且在该功能组之后是一个 TA1 段。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让 TA1 确认的发送方确保交换在 TA1 段之前不包含功能组，然后重新发送确认。