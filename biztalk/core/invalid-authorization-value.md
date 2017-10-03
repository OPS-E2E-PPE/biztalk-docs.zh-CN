---
title: "无效的授权值 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70d0dd75-b045-4b67-ba23-78551493f074
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4e83d35e379babeedca783fa8eb00774ccf05ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-authorization-value"></a>授权值无效
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12Ta1InvalidAuthorizationValueDescription|  
|消息正文|授权值无效|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为 ISA02 中的“授权信息”的值不符合架构指定的数据类型 (X12_AN)，或者没有架构所需的位数 (10)。 架构是 BaseArtifacts.dll 中的 X12ServiceSchema。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保 ISA02 标头中的值符合 X12:AN 数据类型并且具有 10 位数（具有尾随空格），然后重新发送交换。