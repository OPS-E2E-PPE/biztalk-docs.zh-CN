---
title: 由于结构无效，无 transactionSet 或 UNE，Edifact 交换 Xml 序列化失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ce1c219-f2ed-46c1-ae4b-8a4206f7cd01
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55bb6d0f5959a53781e7f48e69b89762a104377
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388919"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-transactionset-or-une"></a>由于结构无效，无 transactionSet 或 UNE，Edifact 交换 Xml 序列化失败
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| 产品版本 |                               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    事件 ID     |                                                            -                                                            |
|  事件源   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                  |
|    组件    |                                                       EDI 引擎                                                        |
|  符号名称  |                                            EfactTransactionSetOrUneNotFound                                             |
|  消息正文   | 由于结构无效，Edifact 交换 Xml 序列化失败。 查找 TransactionSet 或 UNE，但没有找到 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为第一个段既不是 UNA 段也不是 UNB 段。 UNA 段是可选的；UNB 段是必需的。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保交换的发送方结构化消息，以便组中的事务集后面跟随另一个事务集或 UNE 段。 然后，让发送方重新发送交换。