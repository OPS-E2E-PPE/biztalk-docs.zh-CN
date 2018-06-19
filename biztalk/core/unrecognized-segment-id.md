---
title: 无法识别的分段 ID |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a00fe451-0a84-4dca-980c-682243fc9804
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a49de4c7f800d740d9219f787a325279eac4c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286645"
---
# <a name="unrecognized-segment-id"></a>无法识别的段 ID
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|EfactUnrecognizedSegmentIDDescription<br /><br /> X12UnrecognizedSegmentIDDescription|  
|消息正文|无法识别的段 ID|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中事务集的某个段不是由相应的文档架构定义的。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的发送方删除无法识别的段，然后重新发送交换。