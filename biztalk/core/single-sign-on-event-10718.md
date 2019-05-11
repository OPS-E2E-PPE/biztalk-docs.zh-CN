---
title: 单一登录：Event 10718 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 331d78687d7948a4f37ab3b16e4a95e42c5e209c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397215"
---
# <a name="single-sign-on-event-10718"></a>单一登录：事件 10718
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                     企业单一登录                                                                     |
| 产品版本 |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    事件 ID     |                                                                               10718                                                                               |
|  事件源   |                                                                              ENTSSO                                                                               |
|    组件    |                                                                                N\A                                                                                |
|  符号名称  |                                                                SSO_ERROR_REPLAY_INCORRECT_ADAPTER                                                                 |
|  消息正文   | 在重播或进度 file.%r 中检测到损坏。<br /><br /> 文件名称: %1 %r<br /><br /> 清除适配器名称: %2 %r<br /><br /> 解密适配器名称： %3 |

## <a name="explanation"></a>解释  
 此错误事件表明重播或进度文件中检测到损坏。  

 重播文件存储特定的密码同步适配器，因此可以为该特定适配器重放。 适配器名称存储在明文和加密的窗体中。 此消息表示，如果重播文件已解密的播放已解密的适配器名称不匹配适配器名称。 这可以建议发生了一些损坏或与重播文件可能被篡改。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 确定为什么重播文件的内容可能已被修改，请参阅备份是否存在。  

- 检查是否 SSO 主密钥已更改或已更改 SSO 服务帐户，这可能会影响加密行为。  

- 删除重播文件。  

  有关详细信息，请参阅下列资源：  

- [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  

- [密码同步](../core/password-synchronization2.md)
