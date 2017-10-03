---
title: "字段分隔符后分段标记 id 未找到 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f6f0a74-3560-4d6d-9893-85e8426e6b17
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 818a061cd723c0d8f8c58570c9e6df94a670942b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="field-separator-not-found-after-segment-tag-id"></a>在段标记 id 后找不到字段分隔符
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12SeFsNotFoundAfterTagIdDescription|  
|消息正文|在段标记 id 后找不到字段分隔符|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理交换，因为交换包含一个段，该段具有端标识符，但之后没有紧跟数据元素分隔符。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换中的所有段标识符之后紧跟数据元素分隔符，然后重新发送交换。