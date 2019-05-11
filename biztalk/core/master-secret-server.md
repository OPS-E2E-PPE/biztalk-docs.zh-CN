---
title: 主密钥服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1cc7cfdd23db46f574bf57ccc97ef5959391d0b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531107"
---
# <a name="master-secret-server"></a>主密钥服务器
主密钥服务器是存储主密钥 （加密密钥） 的企业单一登录 (SSO) 服务器。 当 SSO 管理员请求它时，主密钥服务器生成主密钥。 主密钥服务器将加密的主密钥存储在注册表中。 只有单一登录管理员才可以访问主密钥。  
  
 其他单一登录服务器请每隔 30 秒检查主密钥是否已更改。 如果已更改，它们读取它安全地;否则，它们继续使用他们已有缓存在内存中的主密钥。 SSO 服务使用主密钥进行加密和解密的用户凭据。  
  
 只有 SSO 管理员配置主密钥服务器并生成主密钥，才能使用 SSO 系统。 在配置期间，主密钥服务器生成主密钥。 只有 SSO 管理员才可以生成主密钥。 应用程序可以使用 SSO 服务之前，SSO 管理员必须配置主密钥服务器和 SSO 数据库。  
  
> [!IMPORTANT]
>  生成主密钥后，强烈建议您将其备份并将其存储在安全的位置。  
  
 当 SSO 管理员需要重新生成主密钥时，例如，如果 SSO 管理员希望定期更改主密钥对主密钥服务器同时存储旧的和新的主密钥。 主密钥服务器然后经历的所有映射、 进行解密使用旧的主密钥，并再次使用新的主密钥对其进行加密。  
  
 如果主密钥服务器发生故障，已在运行的所有运行时操作将继续运行，但 SSO 服务器将无法再新凭据进行加密。  
  
> [!IMPORTANT]
>  SSO 系统中可以有一个主密钥服务器。 因此，强烈建议您群集主密钥服务器。 有关详细信息，请参阅[如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 SSO](../core/using-sso.md)