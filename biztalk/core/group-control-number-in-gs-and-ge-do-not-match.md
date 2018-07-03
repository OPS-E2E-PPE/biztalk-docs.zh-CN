---
title: GS 和 GE 中的组控制编号不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2419f61-2717-4347-a4be-54362330c7e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f162bdcfd76d25a37e196c37c25cbb970fb27155
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993630"
---
# <a name="group-control-number-in-gs-and-ge-do-not-match"></a>GS 和 GE 中的组控制编号不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                         X12FaControlNumberMismatchDescription                          |
|  消息正文   |                     GS 和 GE 中的组控制编号不匹配                     |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换的 GS06 和 GE02 字段中包含的控制编号具有不同的值。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换的 GS06 和 GE02 字段中包含的组控制编号具有相同的值，然后重新发送交换。