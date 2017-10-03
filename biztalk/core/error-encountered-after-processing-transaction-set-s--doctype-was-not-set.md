---
title: "在处理事务集，因为未设置 DocType 之后遇到错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 874b0229eecdd5fe9c046f69789c4708b9280031
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a>在处理事务集，因为未设置 DocType 后遇到的错误
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|DocTypeNotSet|  
|消息正文|事务集处理 {0} 后遇到错误。 未设置 DocType|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示 EDI 接收管道无法处理设置，因为一个传入事务 ST01 (对于 X12 交换) 或 （对于 EDIFACT 交换） UNH2.1 未设置为事务集。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，验证在错误中设置事务的 ST01 或 UNH1 段设置为有效的文档类型。