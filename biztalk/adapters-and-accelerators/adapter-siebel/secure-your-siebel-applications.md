---
title: 保护 Siebel 应用程序 |Microsoft Docs
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
ms.openlocfilehash: 1ad63e44e4d2dde5ffee743e0758a37e48a3d4d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012054"
---
# <a name="secure-your-siebel-applications"></a>保护 Siebel 应用程序
Siebel 系统通常包含敏感商业信息，例如客户帐户详细信息。 使用的应用程序[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]访问和修改此信息是本地或分布式网络中可能会无意中使私钥暴露访问未经授权的参与者，除非工作进行防护和保护期间数据传输。 数据保护和安全性是通常认为的按下列术语：  
  
- *授权*控制对基于请求者的标识的资源的访问。  
  
- *身份验证*提供了用于请求者的身份进行验证的机制。  
  
- *数据保密性*提供了用于保护通过加密的数据的隐私的机制。  
  
- *数据完整性*提供机制以数字方式签署数据，以便接收方可以确保数据尚未更改传输中。  
  
  需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 适配器使用这些凭据以打开到 Siebel 系统的连接。 可以在连接 URI; 提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。  
  
  在本部分中的主题提供了指导原则来帮助你更好地保护使用开发解决方案[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [Siebel 系统与适配器之间的安全性](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [Siebel 适配器与 BizTalk Server 的安全性](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [使用 Siebel 适配器进行安全编程](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [保护 Siebel 适配器的最佳做法](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)