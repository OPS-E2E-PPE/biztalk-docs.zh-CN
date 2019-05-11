---
title: 如何远程用户登录到本地应用程序 |Microsoft Docs
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
ms.openlocfilehash: 9fa3e3251961cb4d58d07026948a09fee94c2942
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336810"
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a>如何远程用户登录到本地应用程序
企业单一登录服务 (ENTSSO) 的其他主要功能支持主机启动的进程 (HIP)。 当远程用户尝试访问本地 Windows 资源时，与 HIP 进行交互 ENTSSO。 使用 ENTSSO，可以接收从主机用户并请求访问权限的请求到本地 Windows 应用程序。  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a>远程用户登录到本地的 Windows 应用程序  
  
1.  接收来自远程用户的请求。  
  
     它由你负责确定如何检索来自远程用户的请求。  
  
2.  请求远程用户授予对指定的关联应用程序的访问权限使用`ISSOLookup2.LogonExternalUser`。  
  
     `LogonExternalUser` 传入应用程序的外部用户希望访问，外部用户，以及所有相关标志的外部用户，关联的凭据的名称。 如果成功，`LogonExternalUser`向 Windows 访问标记返回一个句柄。  
  
     必须已为远程用户实现单一登录数据库中，已在数据库中，将其凭据以及与关联应用程序相关联。 否则为`LogonExternalUser`返回错误。 可以保留的用户名称和最新使用密码同步的凭据。  
  
     此外，您必须启用协议转换。  
  
3.  使用从返回的 Windows 句柄`LogonExternalUser`来模拟该标记代表的用户。  
  
## <a name="see-also"></a>请参阅  
 [如何登录的本地用户身份登录到非 Windows 应用程序](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md)   
 **ISSOLookup2.LogonExternalUser 方法** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]