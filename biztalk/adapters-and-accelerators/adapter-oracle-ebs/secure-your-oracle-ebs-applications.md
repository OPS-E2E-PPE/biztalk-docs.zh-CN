---
title: 保护 Oracle EBS 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76147120-57a8-4959-a0ff-77d04dee06a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bf79d6a1324658101c2f12de758848ce7794fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996942"
---
# <a name="secure-your-oracle-ebs-applications"></a>保护 Oracle EBS 应用程序
Oracle 电子商务应用程序处理敏感商业信息，例如客户帐户详细信息。 使用的应用程序[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]访问和修改此信息是本地或分布式网络中可能会无意中使私钥暴露访问未经授权的参与者，除非工作进行防护和保护期间数据传输。 数据保护和安全性是通常认为的按下列术语：  
  
- *授权*控制对基于请求者的标识的资源的访问。  
  
- *身份验证*提供了用于请求者的身份进行验证的机制。  
  
- *数据保密性*提供了用于保护通过加密的数据的隐私的机制。  
  
- *数据完整性*提供机制以数字方式签署数据，以便接收方可以确保数据尚未更改传输中。  
  
  需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 适配器使用这些凭据打开与 Oracle 数据库的连接。 可以在连接 URI; 提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。  
  
  在本部分中的主题提供了指导原则来帮助你更好地保护使用开发解决方案[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
