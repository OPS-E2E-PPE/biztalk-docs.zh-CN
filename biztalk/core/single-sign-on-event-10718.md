---
title: "单一登录： 事件 10718 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de075c59-8396-48d1-be55-79303f83f984
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4bf86f4db59033b1ee4202c739ffeda43a587e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10718"></a>单一登录： 事件 10718
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10718|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_REPLAY_INCORRECT_ADAPTER|  
|消息正文|重播文件或进度 file.%r 中检测到损坏<br /><br /> 文件名: %1 %r<br /><br /> 清除适配器名称: %2 %r<br /><br /> 解密的适配器名称： %3|  
  
## <a name="explanation"></a>解释  
 此错误事件指示在重播文件或进度文件中检测到损坏。  
  
 重播文件都存储为特定的密码同步适配器，因此可以为该特定的适配器重放。 适配器名称以明文和加密两种形式存储。 此消息表示解密重播文件进行播放时，解密的适配器名称与该适配器名称不匹配。 这可以建议已一些损坏或可能篡改重播文件。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   确定重播文件内容被修改的原因，查看是否存在备份。  
  
-   检查是否更改了 SSO 主密钥或 SSO 服务帐户，这可能会影响加密行为。  
  
-   删除重播文件。  
  
 有关详细信息，请参阅下列资源：  
  
-   [如何配置密码同步](../core/how-to-configure-password-synchronization.md)  
  
-   [密码同步](../core/password-synchronization2.md)