---
title: 处理压缩的 AS2 消息时解压缩失败。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 424dded28973b2e113c959eacd9141fbaf2fb95d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390297"
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a>处理压缩的 AS2 消息时解压缩失败。
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       AS2 引擎                                       |
|  符号名称  |                                           -                                            |
|  消息正文   |       处理压缩的 AS2 消息时解压缩失败。 错误： {0}       |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法解压缩 AS2 消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作之一：  
  
-   验证 AS2 消息中的压缩包装有效。  
  
-   验证解压缩为 BizTalk Server 启用通过验证，"应对消息进行压缩"属性处于选中状态的参与方作为 AS2 消息发送方的 AS2 属性对话框的页 （是否替代入站消息属性属性处于选中状态）.  
  
-   使用错误消息文本中提供的错误说明来标识特定的问题。