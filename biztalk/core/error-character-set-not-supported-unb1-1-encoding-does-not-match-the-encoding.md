---
title: 因为 UNB1.1 中的编码信息不匹配的实际编码不受支持的字符集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 085ea8e3-e0d8-45bd-9985-6787b00e4d5a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea2b1cd0831bb0194c9a5290c2c724bdd46c1714
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388968"
---
# <a name="character-set-not-supported-because-the-encoding-information-in-unb11-does-not-match-the-actual-encoding"></a>字符集不受支持，因为 UNB1.1 中的编码信息不匹配的实际编码
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| 产品版本 |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                              |
|    事件 ID     |                                                                          -                                                                          |
|  事件源   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                |
|    组件    |                                                                     EDI 引擎                                                                      |
|  符号名称  |                                                                          -                                                                          |
|  消息正文   | 不支持字符集。 可能是由于 UNB1.1 中的编码信息与交换中的实际编码不匹配。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为交换中使用的字符不符合交换的字段 UNB1.1 中标识的字符集。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   更改交换中使用的字符，以便这些字符符合交换的字段 UNB1.1 中指定的字符集。  
  
-   更改交换的字段 UNB1.1 中指定的字符集，以便交换中的所有字符都是该字符集的一部分。