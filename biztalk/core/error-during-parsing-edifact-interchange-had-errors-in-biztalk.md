---
title: 在解析过程中遇到错误。 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fa8f9d5-5b7c-47c9-96d3-77be280b78e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d891abe7ca75dbbe9052f221970e235b390269
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988206"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-had-the-following-errors"></a>在解析过程中遇到错误。 EDIFACT 交换发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                             |
| 产品版本 |                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                         |
|    事件 ID     |                                                                     -                                                                      |
|  事件源   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                           |
|    组件    |                                                                 EDI 引擎                                                                 |
|  符号名称  |                                                        EfactInterchangeReceiveError                                                        |
|  消息正文   | 在解析过程中遇到错误。 Edifact 交换中的 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明由于在交换中指出的错误，在分析传入的 EDIFACT 交换时 EDI 接收管道遇到错误。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。