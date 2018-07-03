---
title: 在解析过程中遇到错误。 交换中的 Edifact 功能组发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5be4d7270aeac605c1e476db4089ea3089296bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004494"
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a>在解析过程中遇到错误。 交换中的 EDIFACT 功能组发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| 产品版本 |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                           |
|    事件 ID     |                                                                                       -                                                                                       |
|  事件源   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                             |
|    组件    |                                                                                  EDI 引擎                                                                                   |
|  符号名称  |                                                                       EfactFunctionalGroupReceiveError                                                                        |
|  消息正文   | 在解析过程中遇到错误。 Edifact 功能组 id 为 '{0}，交换中包含的 id{1}，发送方 id'{2}，接收方 id{3}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于通过标识的功能组指明的错误，在分析传入的 EDIFACT 交换时 EDI 接收管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识组中的错误，然后在产品帮助中确定问题解决方案。