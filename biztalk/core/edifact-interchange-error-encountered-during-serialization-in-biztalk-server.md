---
title: 在序列化期间遇到错误。 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebc933ac-161a-41e5-b67d-9f15e569d5c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb97be1be3c623673d2429a20598c748a8d73de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000822"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-had-the-following-errors"></a>在序列化期间遇到错误。 EDIFACT 交换发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
| 产品版本 |                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                            |
|    事件 ID     |                                                                        -                                                                         |
|  事件源   |                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                              |
|    组件    |                                                                    EDI 引擎                                                                    |
|  符号名称  |                                                            EfactInterchangeSendError                                                             |
|  消息正文   | 在序列化期间遇到错误。 Edifact 交换中的 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过标识的交换指明的错误，在序列化传出的 EDIFACT 交换期间 EDI 发送管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。