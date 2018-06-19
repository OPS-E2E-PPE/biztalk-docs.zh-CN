---
title: 无效的日期 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41da9c5-9dcf-44cd-be5b-922e6c267ec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 259456e781f5f5255f9fed8a51c8eb0569dd57b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257389"
---
# <a name="invalid-date"></a>日期无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12DeInvalidDateDescription|  
|消息正文|日期无效|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传出的交换，因为数据元素中的某个日期值不符合 EDI 架构指定的数据类型或者 X12 交换中 GS04 字段标头的此日期值不符合服务架构（BaseArtifacts.dll 中的 X12ServiceSchema）。 对于 X12，服务架构在 GS04 字段中定义了一个 X12_DT 数据类型的日期，字符长度介于 6 和 8 个字符之间。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保数据元素中的时间值符合 EDI 架构指定的数据类型或 X12 交换的 GS04 标头中的日期值符合服务架构，然后重新发送交换。