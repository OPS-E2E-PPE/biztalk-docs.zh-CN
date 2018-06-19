---
title: Siebel 系统和适配器之间的安全性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, IPsec
- connection URI
- security considerations, between the Siebel system and the adapter
ms.assetid: 40b03d4e-f489-4dce-ba7b-6b6f394275ac
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb9ced17c00432039ff3b85ac85d56e1b6031049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222253"
---
# <a name="security-between-the-siebel-system-and-the-adapter"></a>Siebel 系统和适配器之间的安全性
## <a name="encryption-and-authentication"></a>加密和身份验证
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以支持 rsa 或 mscrypto 加密与 Siebel 系统交换的数据。 配置连接 URI 中的通过的查询字符串参数加密模式。 有关 Siebel 连接 URI 的详细信息，请参阅[创建的 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。 有关通过 Siebel rsa 和 mscrypto 加密支持的详细信息，请参阅 Siebel 文档。  
  
 指定加密模式可以帮助确保的适配器和 Siebel 系统之间交换的数据隐私但是，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不提供此类交换支持授权、 身份验证或数据完整性的机制。 如果你的环境中的关注这些问题，必须提供一种安全机制来帮助缓解的方式。  
  
 帮助提供更高的安全性跨网络的一个可能的机制是 Internet 协议安全性 (IPsec)。 IPsec 是一种开放标准的保护通过 Internet 协议 (IP) 网络的通信框架。 有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章"IPsec"在[http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851)。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持它与你提供的用户名称密码凭据通过 Siebel 系统建立的连接上的授权和身份验证。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用这些凭据进行身份验证 Siebel 系统上的用户，在打开连接时。 这些凭据连接上 Siebel 系统提供的授权级别。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供多种方法可以通过其提供这些凭据。 有关如何更安全地提供 Siebel 凭据 BizTalk 解决方案中的信息，请参阅[Siebel 适配器和 BizTalk Server 使用的安全](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。 有关如何更安全地提供 Siebel 系统凭据编程解决方案中的信息，请参阅[Siebel 适配器使用的安全编程](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)。  
  
> [!NOTE]
>  使用的凭据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]来建立连接到 Siebel 系统不提供消息级别或传输级别的身份验证或授权进行数据在网络传输。 它们仅用于打开连接并进行身份验证 Siebel 系统上的用户。  
  
## <a name="see-also"></a>另请参阅  
[保护 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)