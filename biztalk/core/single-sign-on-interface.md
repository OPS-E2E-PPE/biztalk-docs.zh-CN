---
title: 单一登录接口 |Microsoft 文档
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
ms.openlocfilehash: ee479a29a424228b31bc3fcd5752f8da7cc3ce28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276789"
---
# <a name="single-sign-on-interface"></a>单一登录接口

## <a name="interfaces"></a>界面
下表说明了构成单一登录接口的 COM 接口和 .NET Framework 接口。  
  
|.NET|COM|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin|ISSOAdmin 接口 (COM)|创建、更新和删除 SSO 应用程序。 还执行其他管理功能。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore|ISSOConfigStore 接口 (COM)|获取和设置 SSO 配置存储中的信息。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1|ISSOLookup1 接口 (COM)|允许您查找当前用户对指定应用程序的外部凭据。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2|ISSOLookup2 接口 (COM)|同上，但您还可查找指定外部用户的 Windows 凭据。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper|ISSOMapper 接口 (COM)|允许您设置当前用户对指定应用程序的外部凭据。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping|ISSOMapping 接口 (COM)|创建并维护用户与关联应用程序之间的映射。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket|ISSOTicket 接口 (COM)|创建包含相应安全信息的票证。 此票证随后与应用程序中的相应消息一起发送。|  


## <a name="password-sync-helper"></a>密码同步助手  
 此外，Host Integration Server 还支持密码同步助手（PS 助手）组件。 设计密码同步组件时可使用 PS 助手。 下表说明了 PS 助手公开的 COM 和 .NET Framework 接口。  
  
|.NET|COM|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper|ISSONotification 接口 (COM)|处理与非 Windows 操作系统之间的密码更改。|  
||SExternalAccount 结构 (COM)|描述外部帐户。|  
||SPasswordChange 结构 (COM)|描述密码更改。|  
||SPasswordChangeComplete 结构 (COM)|描述密码更改的完成过程。|  
||状态结构 (COM)|描述错误或事件。|  
||SAdapterInGroup 结构 (COM)|描述给定组中的适配器。|  
||SAdapter 结构 (COM)|描述特定的适配器。|

## <a name="see-also"></a>另请参阅
请参阅 SSO COM 对象[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 