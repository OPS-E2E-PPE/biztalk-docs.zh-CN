---
title: 处理事务集，因为未设置 DocType 后遇到错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f106a100aa73234e364cbf0071a705dd47502f52
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348582"
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a>处理事务集，因为未设置 DocType 后遇到错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                     DocTypeNotSet                                      |
|  消息正文   |     在处理后遇到错误{0}事务集。 未设置 DocType     |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的事务集，因为 ST01 (对于 X12 交换) 或 UNH2.1 （对于 EDIFACT 交换） 未设置为事务集。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，验证中错误的事务集的 ST01 或 UNH1 段设置为有效的文档类型。