---
title: 值不能为空或 null 以外 Exists 运算符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44de42c8-eab7-4b13-b55a-d33eabe75c52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5e257b78df8bf872764542d711637d33714349
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279661"
---
# <a name="the-value-cannot-be-empty-or-null-for-an-operator-other-than-exists"></a>对于除 Exists 之外的运算符来说，值不能为空或为 Null
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|ValueCannotBeNullOrEmpty|  
|消息正文|对于除 Exists 之外的运算符来说，值不能为空或为 Null|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明在“批处理筛选器”对话框的某一行中为属性输入的值无效，因为该运算符不是 Exists，但输入的值为空或为 Null。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。 确保当某一行的运算符不是 Exists 时，输入的值不为空或不为 Null。