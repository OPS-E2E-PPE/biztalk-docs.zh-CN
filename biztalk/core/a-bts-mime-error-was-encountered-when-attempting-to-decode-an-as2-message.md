---
title: "当尝试进行解码 AS2 消息时遇到 BTS MIME 错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 660a9e3a6ca5834448dd64815b031e00a0b2942a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a>尝试对 AS2 消息进行解码时遇到 BTS MIME 错误
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|-|  
|消息正文|尝试对 AS2 消息进行解码时遇到 BTS MIME 错误。  AS2-从: {0}，AS2-到： {1}，MessageId: {2}，错误： {3}|  
  
## <a name="explanation"></a>解释  
 使用 BizTalk MIME 组件处理 MIME 处理的一部分时遇到此错误。  
  
## <a name="user-action"></a>用户操作  
 完整错误消息提供有关遇到的 MIME 组件的问题的信息。 请参阅 （这是因为 AS2 组件将 BizTalk MIME 组件用于 MIME 处理的一部分） 问题诊断的 BTS MIME 错误信息。