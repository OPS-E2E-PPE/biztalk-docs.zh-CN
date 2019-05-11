---
title: 包含的组的数目不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d61ac17-92cd-4a5e-81e6-e2c6fc4085bb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7d64c575f3be0fb3a4d69c56e9509dcb66699b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263445"
---
# <a name="number-of-included-groups-do-not-match"></a>包含的组的数目不匹配
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                     X12Ta1InvalidNumberOfIncludedGroupsDescription                     |
|  消息正文   |                         组的包含的数目不匹配                         |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明交换中的组数不等于交换尾部 （IEA01 字段） 中的数量。 保留交换并且出错时挂起交换时会发生这种情况。 （如果保留交换并且出错时挂起事务集或者拆分交换，则不会发布此错误消息。）  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换尾部的 IEA01 字段中数量与交换中的组数相同，然后重新发送交换。