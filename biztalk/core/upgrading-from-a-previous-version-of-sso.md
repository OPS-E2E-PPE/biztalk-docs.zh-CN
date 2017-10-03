---
title: "从以前版本的 SSO 升级 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf36c33b9480c0e8658089fdc9d996b3701d7660
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="upgrading-from-a-previous-version-of-sso"></a>升级从早期版本的 SSO
如果您要安装企业单一登录功能，并且计算机中已部署了一个早期版本（例如，Microsoft BizTalk Server 2009），则必须完成以下步骤：  
  
1.  将 SSO 数据库备份到安全的位置  
  
2.  备份主密钥服务器中的主密钥  
  
3.  通过运行更新主密钥服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装过程中，选择**自定义安装**，然后选择**企业单一登录**。  
  
4.  选择后**启用企业单一登录此计算机上**，选择**加入现有 SSO 系统**。  
  
 不需要从更新其他 SSO 服务器 （非主机密服务器） 你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 但是，如果希望在这些服务器上使用新的企业单一登录功能，则必须通过使用与上述过程相同的过程来更新这些服务器。  
  
> [!NOTE]
>  这些注意事项也适用如果正在安装 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]想要更新的服务器在与主机集成 Server 2009 Enterprise Single Sign-On 和你的现有安装的计算机上。  
  
 如果在已安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上安装 Host Integration Server，则不要选择企业单一登录功能。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用主机启动的 SSO 功能](../core/using-host-initiated-sso-functionality.md)  
  
-   [SSO 的处理服务器](../core/processing-servers-for-sso.md)