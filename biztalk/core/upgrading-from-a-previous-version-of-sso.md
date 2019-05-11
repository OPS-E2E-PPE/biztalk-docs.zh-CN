---
title: 从早期版本的 SSO 升级 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb758aea5910f14ff345ecd8408e52218cc6860c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398574"
---
# <a name="upgrading-from-a-previous-version-of-sso"></a>从早期版本的 SSO 升级
如果在安装企业单一登录功能，并且已有以前的版本 （例如，从 Microsoft BizTalk Server 2009) 在计算机上部署，则必须完成以下步骤。  
  
1. SSO 数据库备份到安全的位置  
  
2. 在主服务器上备份主密钥  
  
3. 通过运行更新主密钥服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，选择**自定义安装**，然后选择**企业单一登录**。  
  
4. 选择后**在此计算机上启用企业单一登录**，选择**加入现有 SSO 系统**。  
  
   不需要更新与其他 SSO 服务器 （非主密钥服务器） 从您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 但是，如果所需的新企业单一登录功能在这些服务器上可用，则必须更新它们通过使用上面所述的相同过程。  
  
> [!NOTE]
>  这些注意事项也适用如果您正在安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]想要更新的服务器与主机集成 Server 2009 Enterprise Single Sign-On 和你的现有安装的计算机上。  
  
 如果要在计算机上安装 Host Integration Server 其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是已安装，不要选择企业单一登录功能。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用主机启动的 SSO 功能](../core/using-host-initiated-sso-functionality.md)  
  
-   [用于 SSO 的处理服务器](../core/processing-servers-for-sso.md)