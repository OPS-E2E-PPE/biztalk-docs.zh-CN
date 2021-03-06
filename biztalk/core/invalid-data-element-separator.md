---
title: 数据元素分隔符无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c50a8b-274f-4f4a-9826-4f6f8123e9d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3be5a09ddbacb119072f4d9a6e4d25acbed21b39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381468"
---
# <a name="invalid-data-element-separator"></a>数据元素分隔符无效
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                      X12Ta1InvalidDataElementSeparatorDescription                      |
|  消息正文   |                             数据元素分隔符无效                             |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中段终止符的值不限于 ASCII 字符集中的字符。 在 X12 中，段终止符被定义为 ISA 段中的第四个字符。 在 EDIFACT 中，段终止符为 UNA2 字段。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保段终止符（X12 交换中 ISA 段的第四个字符或者 EDIFACT 交换中的 UNA2 字段）仅限于 ASCII 字符集中的字符。 然后重新发送交换。