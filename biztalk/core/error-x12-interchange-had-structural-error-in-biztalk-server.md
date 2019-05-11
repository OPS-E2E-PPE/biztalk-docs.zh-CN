---
title: '交换发生了结构错误。 最后一个具有有效结构的功能组 ID 为: |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23055c421a847835ceac3ea96286794e73cb5dcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346224"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a>交换发生了结构错误。 上一个具有有效结构的功能组 ID 为：
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                 |
| 产品版本 |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                             |
|    事件 ID     |                                                                         -                                                                          |
|  事件源   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                               |
|    组件    |                                                                     EDI 引擎                                                                     |
|  符号名称  |                                                     X12InterchangeStructuralErrorAfter1stGroup                                                     |
|  消息正文   | 交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生了结构错误。 最后一个具有有效结构的功能组 ID 为{3} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为指明功能组后，在交换中发生了结构错误。 这可能会发生的事务集被挂起的错误，正在保留交换。 此错误，事务集 （或集） 的结果，包括错误被挂起，但是其余事务设置为已处理保留的批处理的一部分。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请让交换的修复方法结构错误，发送方，然后重新发送交换。