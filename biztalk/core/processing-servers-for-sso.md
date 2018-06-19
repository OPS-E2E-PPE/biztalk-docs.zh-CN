---
title: 处理 SSO 服务器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972e1a3b01394cbf63fb0c8094586d2beda73c3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263661"
---
# <a name="processing-servers-for-sso"></a>SSO 的处理服务器
在多计算机环境中，在创建了主密钥服务器和 SSO 数据库之后，即可在随后的计算机上安装企业单一登录。 通常，这些计算机还是用来安装 BizTalk Server 或 Host Integration Server 的计算机。  
  
 初始安装过程与在第一台计算机上的安装相同。 但是，配置则略有不同。 因为主密钥服务器和 SSO 数据库均已到位，请选择**加入**时配置向导将询问你，**创建新的 SSO 系统**或**加入现有系统**.  
  
 请注意，在配置过程中，某台计算机上的组可以加入另一台计算机上并非为该组配置的 SSO 数据库。 虽然允许，但不建议这样做。  
  
## <a name="see-also"></a>另请参阅  
 [升级从早期版本的 SSO](../core/upgrading-from-a-previous-version-of-sso.md)