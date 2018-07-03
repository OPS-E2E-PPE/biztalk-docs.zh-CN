---
title: 在序列化期间遇到错误。 X12 交换发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9ca3314-6c66-4400-816a-f9c7c7915122
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96c1a186e56fb5c04364187784522f0ba5832581
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008134"
---
# <a name="error-encountered-during-serialization-the-x12-interchange-had-the-following-errors"></a>在序列化期间遇到错误。 X12 交换发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                              |
| 产品版本 |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                          |
|    事件 ID     |                                                                      -                                                                      |
|  事件源   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                            |
|    组件    |                                                                 EDI 引擎                                                                  |
|  符号名称  |                                                           X12InterchangeSendError                                                           |
|  消息正文   | 在序列化期间遇到错误。 X12 交换具有 id{0}，发送方 id '{1}，接收方 id{2}发生以下错误 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于指明的错误，在序列化传出的 X12 交换期间 EDI 发送管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。