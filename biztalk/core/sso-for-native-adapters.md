---
title: 本地适配器的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, SSO
- SSO, adapters
ms.assetid: d8527f0f-910c-42ce-9bd3-83ab6d4349c0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d526f9b3cfc0e6b749469151606f4ae19ce454f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258599"
---
# <a name="sso-for-native-adapters"></a>本地适配器的 SSO
企业单一登录 (SSO)，可只登录一次使用不同的计算机系统或网站进行互操作时。 Microsoft 的这一功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使 BizTalk 适配器能够提供适当的用户 ID 和多个应用程序在网络中使用基于 Microsoft Windows 凭据的常见身份验证机制的凭据。 Windows 对你的凭据进行身份验证后，您不需要提供其他凭据即可连接到应用程序。  
  
 SSO 是可用于 HTTP 和 SOAP 适配器，尽管默认情况下禁用。 HTTP 适配器，您可以配置发送端口和接收位置以使用 SSO;对于 SOAP 适配器，可以配置仅接收位置以使用 SSO。 对于这两个适配器，使用 BizTalk Server 管理控制台来配置 SSO。  
  
 SSO 中的身份验证主要依赖于 Windows 身份验证和 Active Directory 中创建的 Windows 组。 由用户或管理员使用 SSO 完成的所有操作都要求，Windows 先进行身份验证的用户或管理员。  
  
 有关使用 HTTP 和 SOAP 适配器的 SSO 工作原理的详细信息，请参阅另请参阅中的相应主题。  
  
## <a name="see-also"></a>请参阅  
 [使用 SSO](../core/using-sso.md)   
 [HTTP 适配器](../core/http-adapter.md)   
 [SOAP 适配器](../core/soap-adapter.md)