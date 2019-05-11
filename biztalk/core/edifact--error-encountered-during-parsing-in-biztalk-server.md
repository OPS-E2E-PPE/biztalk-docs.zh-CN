---
title: 解析期间遇到错误。 不包含组的 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ace43a641e08265852212d25750977ba5f95398c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350188"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a>解析期间遇到错误。 不包含组的 Edifact 交换发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| 产品版本 |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    事件 ID     |                                                                                           -                                                                                           |
|  事件源   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                 |
|    组件    |                                                                                      EDI 引擎                                                                                       |
|  符号名称  |                                                                     EfactFunctionalGroupReceiveErrorWithoutGroup                                                                      |
|  消息正文   | 解析期间遇到错误。 Edifact 交换不包含组中的，交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 接收管道遇到错误时分析传入的 EDIFACT 交换不包含一组由于指出的错误。 请注意，组在 EDIFACT 交换中为可选。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，需要使用错误消息中的信息来标识错误然后确定问题解决方案产品帮助中。