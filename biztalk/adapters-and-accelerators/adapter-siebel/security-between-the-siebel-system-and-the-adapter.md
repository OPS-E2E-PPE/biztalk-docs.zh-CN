---
title: Siebel 系统与适配器之间的安全 |Microsoft Docs
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
ms.openlocfilehash: 2f150e0bb7518d1ce52ed664c63371c48a8b58b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370914"
---
# <a name="security-between-the-siebel-system-and-the-adapter"></a>Siebel 系统与适配器之间的安全性
## <a name="encryption-and-authentication"></a>加密和身份验证
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以支持 rsa 或 mscrypto 加密交换与 Siebel 系统的数据。 在连接 URI 配置通过查询字符串参数的加密模式。 Siebel 连接 URI 的详细信息，请参阅[创建的 Siebel 系统连接 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)。 有关通过 Siebel 的 rsa 和 mscrypto 加密支持的详细信息，请参阅 Siebel 文档。  
  
 指定加密模式可以帮助确保适配器和 Siebel 系统之间交换数据的隐私性但是，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不提供支持这种交换的授权、 身份验证或数据完整性的机制。 如果这些问题是您的环境中问题在于，必须提供一种安全机制来帮助缓解这些。  
  
 帮助提供更高的安全性网络上的一个可能的机制是 Internet 协议安全性 (IPsec)。 IPsec 是一种开放标准来保护通过 Internet 协议 (IP) 网络的通信框架。 有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章"IPsec"处[ http://go.microsoft.com/fwlink/?LinkID=196851 ](http://go.microsoft.com/fwlink/?LinkID=196851)。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持它在建立与 Siebel 系统通过所提供的用户名称密码凭据的连接上的授权和身份验证。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用这些凭据时打开的连接上的 Siebel 系统的用户进行身份验证。 这些凭据用于连接上的 Siebel 系统提供授权的级别。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供了多种方法可以通过其提供这些凭据。 有关如何更安全地提供 BizTalk 解决方案中的 Siebel 凭据的信息，请参阅[Siebel 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)。 有关如何更安全地提供编程解决方案中的 Siebel 系统凭据的信息，请参阅[使用 Siebel 适配器进行安全编程](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)。  
  
> [!NOTE]
>  使用的凭据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]以建立与 Siebel 系统不提供消息级或传输级别的身份验证或授权在网络上传输的数据。 它们仅用于打开连接和 Siebel 系统的用户进行身份验证。  
  
## <a name="see-also"></a>请参阅  
[保护 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)