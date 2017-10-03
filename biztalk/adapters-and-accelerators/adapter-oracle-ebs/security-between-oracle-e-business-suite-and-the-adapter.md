---
title: "Oracle E-business Suite 和适配器之间的安全性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88f5f8ed-48d5-4420-9fdb-0a6860b95ac4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ceac01c8d495374470bf2a78912908338611180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-oracle-e-business-suite-and-the-adapter"></a>Oracle E-business Suite 和适配器之间的安全性
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]未提供对它和 Oracle 数据库之间的通信安全帮助支持。 必须提供一种安全机制，以帮助确保适当的授权、 身份验证、 保护数据隐私和数据适配器和 Oracle 数据库之间的交换的数据完整性级别。  
  
 帮助提供更高的安全性跨网络的一个可能的机制是 Internet 协议安全性 (IPsec)。 IPsec 是一种开放标准的保护通过 Internet 协议 (IP) 网络的通信框架。 有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章"IPsec"在[http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851)。  
  
 但是，在没有象 IPsec 这样的安全机制的情况下，管理员必须配置本机 Oracle 数据加密和完整性，以确保适配器客户端和 Oracle E-business Suite 之间的安全数据交换。  
  
 必须提供用户名凭据密码到[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用这些凭据来在打开连接时，对 Oracle 数据库用户进行身份验证。 这些凭据用于连接 Oracle 数据库上提供授权的级别。  
  
> [!NOTE]
>  使用的凭据[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]建立对 Oracle 数据库的连接不提供消息级别或传输级别的身份验证或授权进行数据在网络传输。 它们仅用于打开连接并对 Oracle 数据库用户进行身份验证。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供多种方法可以通过其提供这些凭据。 有关如何更安全地提供 BizTalk 解决方案中的 Oracle 凭据的信息，请参阅[安全性与 Oracle E-business Suite 适配器和 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)。 若要了解如何更安全地提供编程解决方案中的 Oracle 数据库凭据，请参阅[适配器的安全注意事项](../../core/security-considerations-for-adapters.md)。  
  
## <a name="managing-audit-logs"></a>管理审核日志  
 审核日志，可以将存储在你的企业软件，并可帮助使用情况监视和问题跟踪的各种客户端执行的操作有关的信息。 但是，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不提供任何方式来管理 Oracle E-business Suite 中的适配器客户端执行的操作的审核日志。 这可能带来的安全威胁，因为适配器客户端可以 repudiate Oracle E-business Suite 中执行它们的操作。 若要缓解此问题，必须启用 Oracle 记录中 Oracle E-business Suite 的适配器客户端执行的操作中的审核记录。 有关如何设置 Oracle 审计跟踪，请参阅网址的"Oracle 工作流-Oracle E-business Suite 进程"白皮书[http://go.microsoft.com/fwlink/?LinkId=136388](http://go.microsoft.com/fwlink/?LinkId=136388)。  
  
## <a name="see-also"></a>另请参阅  
 [保护 Oracle EBS 应用程序](secure-your-oracle-ebs-applications.md)  
 [最佳做法来保护 Oracle E-business Suite 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)