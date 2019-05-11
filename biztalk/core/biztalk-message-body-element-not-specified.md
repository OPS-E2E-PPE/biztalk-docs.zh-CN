---
title: 未指定 BizTalk 消息正文元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a5f39c6bdfd281ae96fe488ae71fa5c4032adc
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528307"
---
# <a name="biztalk-message-body-element-not-specified"></a>未指定 BizTalk 消息正文元素
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                     未指定 BizTalk 消息正文元素                     |
  
## <a name="explanation"></a>解释  
 此错误表示出站 WCF 消息使用了模板选项。 但是，模板表达式不包含 BizTalk 消息正文元素。  
  
## <a name="user-action"></a>用户操作  
 请确保模板表达式包含以下元素： \< **bts 消息正文 xmlns ="<http://www.microsoft.com/schemas/bts2007>"编码 ="[xml&#124;base64&#124;hex&#124;字符串]"/**\>。