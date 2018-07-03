---
title: 由于结构无效，X12 交换 Xml 序列化失败。 查找 TransactionSet 或 GE，但找不到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d058fdbb-6be5-499f-86f7-0eb8a85c5fb2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05608a6e38d90a9e18004fa650ee6d5f7911109c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977550"
---
# <a name="x12-interchange-xml-serialization-failed-due-to-invalid-structure-looking-for-transactionset-or-ge-but-not-found"></a>由于结构无效，X12 交换 Xml 序列化失败。 查找 TransactionSet 或 GE，但没有找到
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 产品版本 |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    事件 ID     |                                                         -                                                          |
|  事件源   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI               |
|    组件    |                                                     EDI 引擎                                                     |
|  符号名称  |                                           X12TransactionSetOrGeNotFound                                            |
|  消息正文   | 由于结构无效，X12 交换 Xml 序列化失败。 查找 TransactionSet 或 GE，但没有找到 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明发送管道无法序列化传出的交换，因为交换的结构无效。 原因可能是所需的标头或尾部不存在或者无效。 如果组中的事务集后没有另一个事务集或组尾部，则可能会发生此错误。 如果结构完整性检查失败，也可能会发生此错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请验证交换的结构，确保组或事务集标头和尾部有效，然后重新发送交换。