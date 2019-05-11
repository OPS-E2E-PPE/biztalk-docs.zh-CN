---
title: 单一登录接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2e3c2d3-a7e9-4a45-965d-bfe4bf200c34
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be71b6be0baa733748552f59067b0b3678bed4af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247293"
---
# <a name="single-sign-on-interface"></a>单一登录接口

## <a name="interfaces"></a>界面
下表介绍了构成单一登录接口的 COM 和.NET Framework 接口。  
  
|.NET|COM|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin|ISSOAdmin 接口 (COM)|创建、 更新和删除 SSO 应用程序。 此外执行其他管理功能。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore|ISSOConfigStore 接口 (COM)|获取和设置 SSO 配置存储区中的信息。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1|ISSOLookup1 接口 (COM)|使您能够查找当前用户对指定应用程序的外部凭据。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2|ISSOLookup2 接口 (COM)|如上所示，而且还使您能够查找指定外部用户的 Windows 凭据。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper|ISSOMapper 接口 (COM)|可以为指定的应用程序的当前用户设置外部凭据。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping|ISSOMapping 接口 (COM)|创建并维护用户与关联应用程序之间的映射。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket|ISSOTicket 接口 (COM)|创建包含相应的安全信息的票证。 此票证然后发送的相应消息一起从你的应用程序。|  


## <a name="password-sync-helper"></a>密码同步助手  
 此外，Host Integration Server 还支持密码同步助手 （PS 助手） 组件。 设计密码同步组件时，可以使用 PS 助手。 下表描述了 PS 助手公开的 COM 和.NET Framework 接口。  
  
|.NET|COM|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper|ISSONotification 接口 (COM)|处理从非 Windows 操作系统中的密码更改。|  
||SExternalAccount 结构 (COM)|描述外部帐户。|  
||SPasswordChange 结构 (COM)|描述密码更改。|  
||SPasswordChangeComplete 结构 (COM)|描述密码更改的完成。|  
||SStatus 结构 (COM)|描述错误或事件。|  
||SAdapterInGroup 结构 (COM)|描述给定组中的适配器。|  
||SAdapter 结构 (COM)|描述特定的适配器。|

## <a name="see-also"></a>另请参阅
请参阅 SSO COM 对象[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 