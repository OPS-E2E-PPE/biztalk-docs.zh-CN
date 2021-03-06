---
title: 包含的段数不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c868de02-fda7-4d84-be50-2c08cde0450c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 418f81c895660c93ebdb26924d0a279ccd46e72f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325156"
---
# <a name="number-of-included-segments-do-not-match"></a>包括的段的数目不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                        X12TsIncludedSegCountMismatchDescription                        |
|  消息正文   |                        包括的段的数目不匹配                        |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 X12 交换的事务集中的段数不等于事务集尾部中的数量（SE01 字段）。 保留交换并且出错时挂起交换时会发生这种情况。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换尾部的 SE01 字段中的数量与事务集中的段数相同，然后重新发送交换。