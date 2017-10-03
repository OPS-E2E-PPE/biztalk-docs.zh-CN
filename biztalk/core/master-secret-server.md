---
title: "主密钥服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, about Master Secret server
- Master Secret server, SSO
- SSO, encryption key
- Master Secret server, encryption key
- SSO, Master Secret server
ms.assetid: 93685a19-6c27-45db-bfc1-957574362687
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d02d5608546e86801bfc4a2281c42f902594e79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="master-secret-server"></a>主密钥服务器
主密钥服务器是存储主密钥（加密密钥）的企业单一登录 (SSO) 服务器。 主密钥服务器可在 SSO 管理员请求主密钥时生成主密钥。 主密钥服务器将加密主密钥存储在注册表中。 只有单一登录管理员才可以访问主密钥。  
  
 其他单一登录服务器将每 30 秒检查一次主密钥是否已更改。 如果主密钥已更改，这些服务器将安全地读取该密钥；否则，它们会继续使用内存中缓存的主密钥。 SSO 服务使用主密钥对用户凭据进行加密和解密。  
  
 只有在 SSO 管理员配置主密钥服务器并生成主密钥后，您才可以使用 SSO 系统。 主密钥服务器将在配置过程中生成主密钥。 只有 SSO 管理员才可以生成主密钥。 SSO 管理员必须配置主密钥服务器和 SSO 数据库，应用程序才可以使用 SSO 服务。  
  
> [!IMPORTANT]
>  在您生成主密钥后，强烈建议您在安全的位置备份并存储该密钥。  
  
 当 SSO 管理员需要重新生成主密钥时，例如，如果 SSO 管理员希望定期更改主密钥，则可设置主密钥服务器同时存储旧的主密钥和新的主密钥。 这样，主密钥服务器就会检查所有映射，使用旧的主密钥来将这些映射解密，再使用新的主密钥进行加密。  
  
 如果主密钥服务器发生故障，所有已运行的运行时操作将继续运行，但 SSO 服务器将无法对新凭据进行加密。  
  
> [!IMPORTANT]
>  在 SSO 系统中只能有一台主密钥服务器。 因此，强烈建议您群集主密钥服务器。 有关详细信息，请参阅[如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SSO](../core/using-sso.md)