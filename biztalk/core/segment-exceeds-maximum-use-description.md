---
title: 段超过最大使用说明 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1704a-5d49-4549-af50-d1a89a1e70f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f5e5a0ae590be850a4560324814c756d51e9fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269429"
---
# <a name="segment-exceeds-maximum-use-description"></a>段超过最大使用说明
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12SegmentExceedsMaximumUseDescription|  
|消息正文|段超过最大使用说明|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示接收管道不无法处理传入的交换，因为该交换包含段的更多实例不是架构所允许的。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中的段数未超过所允许的最大段数，然后重新发送交换。