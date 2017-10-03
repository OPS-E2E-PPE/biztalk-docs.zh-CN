---
title: "处理压缩的 AS2 消息时解压缩失败。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4121fc3598913f4c3edab52655866c02b5a4fe86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a>处理压缩的 AS2 消息时解压缩失败。
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|-|  
|消息正文|处理压缩的 AS2 消息时解压缩失败。 错误： {0}|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法解压缩 AS2 消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   验证 AS2 消息中的压缩包装是否有效。  
  
-   验证是否为 BizTalk Server 启用了解压缩，方法是验证“AS2 属性”对话框的“作为 AS2 消息发送方的参与方”页上是否选中了“应对消息进行压缩”属性（如果选中了“替代入站消息属性”属性）。  
  
-   使用错误消息文本中提供的错误说明来确定具体问题。