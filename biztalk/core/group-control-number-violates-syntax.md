---
title: "组控制编号违反了语法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e173c914-cb5c-4369-ac2f-8f9abee420cb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c9364260d9c90b9935f894eb3a0ada882057ea5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="group-control-number-violates-syntax"></a>组控制编号违反了语法
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|X12FaInvalidControlNumberDescription|  
|消息正文|组控制编号违反了语法|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为该交换的 GS06 和 GE02 字段中的组控制编号不符合服务架构中指定的数据类型或长度。 服务架构是 BaseArtifacts.dll 中的 X12ServiceSchema。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换的 GS06 和 GE02 字段中包含的组控制编号符合服务架构中指定的数据类型 (X12_N0) 和长度（介于 1 和 9 位之间），然后重新发送交换。 