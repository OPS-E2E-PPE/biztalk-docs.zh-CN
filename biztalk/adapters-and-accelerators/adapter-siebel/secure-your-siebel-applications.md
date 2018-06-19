---
title: 保护 Siebel 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b597120de91b6a09fdc26b90a2cb357cdc7dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221965"
---
# <a name="secure-your-siebel-applications"></a>保护 Siebel 应用程序
Siebel 系统通常包含敏感商业信息，例如客户帐户详细信息。 应用程序使用[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]访问和修改此信息是本地或分布式网络可能会无意中公开其能够访问未经授权的参与者，除非努力保护且安全的过程的数据传输。 数据保护和安全是通常认为按下列术语：  
  
-   *授权*控制对基于请求者的标识的资源的访问。  
  
-   *身份验证*提供用于请求者的身份进行验证的机制。  
  
-   *数据保密性*提供用于保护通过加密的数据的隐私的机制。  
  
-   *数据完整性*提供了数据，进行数字签名的机制，以便接收方可以确保数据尚未更改在传输过程。  
  
 需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 适配器使用这些凭据打开到 Siebel 系统的连接。 可以在连接 URI; 中提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。  
  
 本部分中的主题提供了一些指南，可以帮助你更好地保护你开发的解决方案[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Siebel 系统和适配器之间的安全性](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [Siebel 适配器和 BizTalk Server 使用的安全](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [Siebel 适配器使用的安全编程](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [最佳做法来保护在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)