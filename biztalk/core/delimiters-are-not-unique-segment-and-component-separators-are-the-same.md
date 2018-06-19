---
title: 分隔符不唯一，是相同的段和组件分隔符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13c41899-02af-4678-a4ad-f3dc48c1fdfb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69475949b404474ff4dc9fe53d553c24e125939c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238437"
---
# <a name="delimiters-are-not-unique-segment-and-component-separators-are-the-same"></a>分隔符不唯一，段和组件分隔符相同
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|-|  
|消息正文|分隔符不唯一，段和组件分隔符相同|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 发送管道无法处理传出交换，因为段终止符或组件分隔符是相同的值。 在 X12 交换中，段终止符是处于 ISA 段中最后一个字符位置的字符，组件分隔符是 ISA16 字段中的字符。 在 EDIFACT 交换中，段终止符是 UNA6 字段中的字符，组件分隔符是 UNA1 字段中的字符。 保留的批方案中可能会发生两个分隔符具有相同值的情况（但这会导致错误），或者如果交换通过直通传输接收，然后由发送端口选取作为 MessageBox 中的 XML 文件，也可能会发生这种情况。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请更改交换中段终止符或组件分隔符的值，然后重新提交交换。