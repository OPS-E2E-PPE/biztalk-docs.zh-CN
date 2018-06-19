---
title: 比较运算符不是有效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8383230d-9bf6-4bc5-9300-4cfd0ad38f28
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12652fbd59fde08d8321c6fdd85bb0998ce8ccc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279221"
---
# <a name="the-comparison-operator-is-not-valid"></a>比较运算符无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|批处理引擎|  
|符号名称|InvalidComparisonOperator|  
|消息正文|比较运算符无效。 异常消息 = {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示输入批处理筛选器对话框中的行的比较运算符对属性和值无效。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。 确保为“批处理筛选器”网格中的行输入的比较运算符对于该属性和值来说无效。