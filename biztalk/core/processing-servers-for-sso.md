---
title: 用于 SSO 的处理服务器 |Microsoft Docs
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
ms.openlocfilehash: e2676de4e698f3ea9221b35c349819f163b74b3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255136"
---
# <a name="processing-servers-for-sso"></a>用于 SSO 的处理服务器
在多计算机环境中，已创建主密钥服务器和 SSO 数据库后，你可以安装企业单一登录在随后的计算机上。 这些通常是 BizTalk Server 或 Host Integration Server 也在其安装的计算机。  
  
 初始安装过程是第一台计算机上相同。 但是，配置中，将成为略有不同。 由于主密钥服务器和 SSO 数据库均已就位，选择**加入**时配置向导询问**创建新的 SSO 系统**或**加入现有系统**.  
  
 请注意，它可能在一台计算机上要加入不是为该组配置的数据库的其他计算机上的 SSO 数据库的组的配置过程。 虽然这可能，但不建议。  
  
## <a name="see-also"></a>请参阅  
 [从早期版本的 SSO 升级](../core/upgrading-from-a-previous-version-of-sso.md)