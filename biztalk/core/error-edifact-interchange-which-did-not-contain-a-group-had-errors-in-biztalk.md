---
title: 在序列化期间遇到错误。 不包含组的 Edifact 交换发生了以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af693139-e4cd-4bcb-922c-79caa148d3b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2faef5b896440a6f412187016d145e33e2ab0868
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348885"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a>在序列化期间遇到错误。 不包含组的 Edifact 交换发生了以下错误
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                      |
| 产品版本 |                                                                 [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                  |
|    事件 ID     |                                                                                              -                                                                                              |
|  事件源   |                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                    |
|    组件    |                                                                                         EDI 引擎                                                                                          |
|  符号名称  |                                                                          EfactFunctionalGroupSendErrorWithoutGroup                                                                          |
|  消息正文   | 在序列化期间遇到错误。 Edifact 交换不包含组中的，交换 id 为 '{0}，发送方 id{1}，接收方 id{2}发生以下错误： |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 EDI 发送管道遇到错误，由于通过标识的交换指出的错误序列化传出的 EDIFACT 交换时。 请注意，交换不包含一组。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，需要使用错误消息中的信息来标识交换中的错误，然后确定问题解决方案产品帮助中。