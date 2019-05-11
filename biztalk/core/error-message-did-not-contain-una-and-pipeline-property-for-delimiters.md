---
title: 消息不包含 UNA 和管道属性的分隔符使用了不正确的格式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b761d820-e09d-4949-bb41-da9e66054c60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db522cf5278bb599b56a33c29a2572755d45eae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388962"
---
# <a name="message-did-not-contain-una-and-pipeline-property-for-delimiters-was-incorrect-format"></a>消息不包含 UNA 和管道属性的分隔符使用了不正确的格式
## <a name="details"></a>详细信息  
  
|                 |                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------|
|  产品名称   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| 产品版本 |                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                  |
|    事件 ID     |                                              -                                              |
|  事件源   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI    |
|    组件    |                                         EDI 引擎                                          |
|  符号名称  |                                EfactDelimiterIncorrectFormat                                |
|  消息正文   | 消息不包含 UNA 和管道属性分隔符使用了格式不正确{0} |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道无法处理传入的I EDIFACT 交换，因为它无法确定处理该交换所需的分隔符。 如果交换没有 UNA 段并且 EfactDelimiters 管道属性没有定义足够的分隔符，则会发生此错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
1.  确保交换具有为交换定义分隔符的 UNA 段，然后重新发送交换。  
  
2.  通过打开 BizTalk Server 管理控制台，右键单击将接收交换的接收位置，单击“属性”，单击管道的省略号，然后输入包含分隔符值的字符串来为发送管道设置 EfactDelimiters 管道属性。