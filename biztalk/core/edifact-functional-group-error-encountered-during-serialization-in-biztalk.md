---
title: 在序列化期间遇到错误。 Edifact 功能组发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed81bc79-d99c-4305-805f-ab38eae91ea0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cd5ce1a94a47c5094862decfe1bb1dbb9c1efb0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977598"
---
# <a name="error-encountered-during-serialization-the-edifact-functional-group-had-the-following-errors"></a>在序列化期间遇到错误。 EDIFACT 功能组发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                  |
| 产品版本 |                                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                              |
|    事件 ID     |                                                                                          -                                                                                          |
|  事件源   |                                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                |
|    组件    |                                                                                     EDI 引擎                                                                                      |
|  符号名称  |                                                                            EfactFunctionalGroupSendError                                                                            |
|  消息正文   | 在序列化期间遇到错误。 Edifact 功能组 id 为 '{0}，交换中包含的 id{1}，发送方 id'{2}，接收方 id{3}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过组指明的错误，在序列化传出的 EDIFACT 交换中的某个功能组时 EDI 发送管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识功能组中的错误，然后在文档中确定问题解决方案。