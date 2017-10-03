---
title: "保护 Oracle EBS 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76147120-57a8-4959-a0ff-77d04dee06a6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9a7427d36ead6ba91e0d68b1080c9ab4f5155fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-oracle-ebs-applications"></a>保护 Oracle EBS 应用程序
Oracle 电子商务应用程序处理敏感商业信息，例如客户帐户详细信息。 应用程序使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]访问和修改此信息是本地或分布式网络可能会无意中公开其能够访问未经授权的参与者，除非努力保护且安全的过程的数据传输。 数据保护和安全是通常认为按下列术语：  
  
-   *授权*控制对基于请求者的标识的资源的访问。  
  
-   *身份验证*提供用于请求者的身份进行验证的机制。  
  
-   *数据保密性*提供用于保护通过加密的数据的隐私的机制。  
  
-   *数据完整性*提供了数据，进行数字签名的机制，以便接收方可以确保数据尚未更改在传输过程。  
  
 需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 适配器使用这些凭据打开与 Oracle 数据库的连接。 可以在连接 URI; 中提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。  
  
 本部分中的主题提供了一些指南，可以帮助你更好地保护你开发的解决方案[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
