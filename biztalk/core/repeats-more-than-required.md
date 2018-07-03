---
title: 重复多个所需 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac4649ea88756ba63393155ca8910437567fbd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024035"
---
# <a name="repeats-more-than-required"></a>重复次数大于必需次数
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                        X12FeRepeatsMoreThanRequiredDescription                         |
|  消息正文   |                               重复次数大于必需次数                               |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 X12 交换中位于循环内外的段的重复次数大于文档架构所需的次数。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保位于交换中某个循环内外的段重复架构中指定的次数，然后重新发送交换。