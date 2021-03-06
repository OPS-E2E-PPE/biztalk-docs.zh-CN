---
title: Oracle 数据库和适配器之间的安全 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- credentials, supplying user name password
- authentication
- IPsec
ms.assetid: 09d40a05-3678-4002-9e08-2f97c2d5c686
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54325612ce61ca3d351e33223924c9b899e11902
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376018"
---
# <a name="security-between-the-oracle-database-and-the-adapter"></a>Oracle 数据库和适配器之间的安全性
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不提供支持，可帮助向它与 Oracle 数据库之间安全通信。 必须提供一种安全机制来帮助确保适当的授权、 身份验证、 数据隐私和数据适配器和 Oracle 数据库之间交换的数据完整性级别。  
  
 帮助提供更高的安全性网络上的一个可能的机制是 Internet 协议安全性 (IPsec)。 IPsec 是一种开放标准来保护通过 Internet 协议 (IP) 网络的通信框架。 有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章"IPsec"处[ http://go.microsoft.com/fwlink/?LinkId=196851 ](http://go.microsoft.com/fwlink/?LinkId=196851)。  
  
 但是，如果没有象 IPsec 这样的安全机制，管理员必须配置本机 Oracle 数据加密和完整性，以确保适配器客户端与 Oracle 数据库之间的安全数据交换。 有关配置本机 Oracle 数据加密和完整性的详细信息，请参阅[ http://go.microsoft.com/fwlink/p/?LinkId=140032 ](http://go.microsoft.com/fwlink/p/?LinkId=140032)。  
  
 必须提供用户名凭据密码到[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用这些凭据来打开连接时，对 Oracle 数据库用户进行身份验证。 这些凭据用于连接 Oracle 数据库上提供授权的级别。  
  
> [!NOTE]
>  使用的凭据[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]来建立对 Oracle 数据库的连接不提供消息级或传输级别的身份验证或授权在网络上传输的数据。 它们仅用于打开连接和对 Oracle 数据库用户进行身份验证。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供了多种方法可以通过其提供这些凭据。 有关如何更安全地提供 BizTalk 解决方案中的 Oracle 凭据的信息，请参阅[Oracle 数据库适配器与 Biztalk Server 安全性](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)。 若要了解如何更安全地提供编程解决方案中的 Oracle 数据库凭据，请参阅[安全使用 Oracle 数据库适配器编程](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md)。  
  
## <a name="managing-audit-logs"></a>管理审核日志  
 审核日志，可以将存储在你的企业软件，并可帮助使用情况监视和问题跟踪的各种客户端执行的操作有关的信息。 但是，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不提供任何方式来管理对 Oracle 数据库适配器客户端执行的操作的审核日志。 这可能会带来安全威胁，因为适配器客户端可以否认 Oracle 数据库上执行它们的操作。 若要缓解此问题，必须启用 Oracle 来记录对 Oracle 数据库适配器客户端执行的操作中的审核线索。  
  
## <a name="see-also"></a>请参阅  
[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[最佳实践](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)