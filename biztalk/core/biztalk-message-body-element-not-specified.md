---
title: "未指定 BizTalk 消息正文元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf79c8896169a06df66a8484377816c9897531e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-message-body-element-not-specified"></a>未指定 BizTalk 消息正文元素
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|未指定 BizTalk 消息正文元素|  
  
## <a name="explanation"></a>解释  
 此错误表示对出站 WCF 消息使用了模板选项。 但是，模板表达式不包含 BizTalk 消息正文元素。  
  
## <a name="user-action"></a>用户操作  
 确保模板表达式包含下列元素： \< **bts 消息正文 xmlns ="http://www.microsoft.com/schemas/bts2007"编码 ="[xml &#124; base64 &#124; 十六进制 &#124; 字符串]"/**>。