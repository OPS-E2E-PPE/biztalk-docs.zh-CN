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
ms.openlocfilehash: cf61012de6ba864d6f0ff4e553b4c74e1d501c20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988166"
---
# <a name="number-of-included-groups-do-not-match"></a>包括的组的数目不匹配
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
 此错误/警告/信息事件表明交换中的组数不等于交换尾部（IEA01 字段）中的数量。 保留交换并且出错时挂起交换时会发生这种情况。 （如果保留交换并且出错时挂起事务集或者拆分交换，则不会发布此错误消息。）  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换尾部的 IEA01 字段中的数量与交换中的组数相同，然后重新发送交换。