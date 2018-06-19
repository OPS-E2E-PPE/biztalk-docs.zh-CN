---
title: 如何登录到本地的应用程序的远程用户 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f638007c3c4eb1f85a5b5a701dd2b456c2d220d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254213"
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a>如何登录到本地的应用程序的远程用户
企业单一登录服务 (ENTSSO) 的另一主要功能是支持主机启动的进程 (HIP)。 当远程用户试图访问本地 Windows 资源时，ENTSSO 将与 HIP 进行交互。 使用 ENTSSO，可以接收主机用户的请求，并请求对本地 Windows 应用程序进行访问。  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a>登录到本地的 Windows 应用程序的远程用户  
  
1.  接收相应远程用户的请求。  
  
     您需要确定如何检索来自相应远程用户的请求。  
  
2.  使用 `ISSOLookup2.LogonExternalUser` 请求授予远程用户对指定的关联应用程序的访问权限。  
  
     `LogonExternalUser` 传入外部用户希望访问的应用程序的名称、该外部用户的名称、该用户的关联凭据以及所有相关标志。 如果成功，则 `LogonExternalUser` 会向 Windows 访问标记返回一个句柄。  
  
     该远程用户必须已在单一登录数据库中标识，已将其凭据存储到该数据库中，并且已经与关联应用程序相关联。 否则，`LogonExternalUser` 将返回错误。 您可以利用密码同步使用户名和凭据保持最新状态。  
  
     此外，您还必须启用协议转换。  
  
3.  使用从 `LogonExternalUser` 返回的 Windows 句柄来模拟该标记代表的用户。  
  
## <a name="see-also"></a>另请参阅  
 [如何登录到非 Windows 应用程序的本地用户](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md)   
 **ISSOLookup2.LogonExternalUser 方法**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]