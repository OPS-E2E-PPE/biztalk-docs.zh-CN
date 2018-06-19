---
title: 布尔属性值不是有效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62b6c178-f8ea-451a-b2dc-9396c24c0f5b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6aa8d79c2c3b4ce9033a164a664e27effdd2b63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279157"
---
# <a name="the-boolean-property-value-is-not-valid"></a>boolean 属性值无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|InvalidBooleanPropertyValue|  
|消息正文|boolean 属性值无效|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示，输入批处理筛选器对话框中的行中的属性的值无效，因为该属性需要布尔值，但输入的值不是一个布尔值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。 请确保为需要 boolean 值的属性输入的值确实是 boolean 值。