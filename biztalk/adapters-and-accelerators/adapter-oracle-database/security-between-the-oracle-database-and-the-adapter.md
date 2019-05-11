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
# <a name="security-between-the-oracle-database-and-the-adapter"></a><span data-ttu-id="7d18d-102">Oracle 数据库和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="7d18d-102">Security between the Oracle Database and the adapter</span></span>
<span data-ttu-id="7d18d-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不提供支持，可帮助向它与 Oracle 数据库之间安全通信。</span><span class="sxs-lookup"><span data-stu-id="7d18d-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] provides no support for helping to secure communication between it and the Oracle database.</span></span> <span data-ttu-id="7d18d-104">必须提供一种安全机制来帮助确保适当的授权、 身份验证、 数据隐私和数据适配器和 Oracle 数据库之间交换的数据完整性级别。</span><span class="sxs-lookup"><span data-stu-id="7d18d-104">You must provide a security mechanism to help ensure appropriate levels of authorization, authentication, data privacy, and data integrity for data exchanges between the adapter and the Oracle database.</span></span>  
  
 <span data-ttu-id="7d18d-105">帮助提供更高的安全性网络上的一个可能的机制是 Internet 协议安全性 (IPsec)。</span><span class="sxs-lookup"><span data-stu-id="7d18d-105">One possible mechanism for helping to provide more security across the network is Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="7d18d-106">IPsec 是一种开放标准来保护通过 Internet 协议 (IP) 网络的通信框架。</span><span class="sxs-lookup"><span data-stu-id="7d18d-106">IPsec is a framework of open standards for protecting communications over Internet Protocol (IP) networks.</span></span> <span data-ttu-id="7d18d-107">有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章"IPsec"处[ http://go.microsoft.com/fwlink/?LinkId=196851 ](http://go.microsoft.com/fwlink/?LinkId=196851)。</span><span class="sxs-lookup"><span data-stu-id="7d18d-107">For more information about IPsec and about using IPsec with Microsoft products, see the Microsoft TechNet article "IPsec" at [http://go.microsoft.com/fwlink/?LinkId=196851](http://go.microsoft.com/fwlink/?LinkId=196851).</span></span>  
  
 <span data-ttu-id="7d18d-108">但是，如果没有象 IPsec 这样的安全机制，管理员必须配置本机 Oracle 数据加密和完整性，以确保适配器客户端与 Oracle 数据库之间的安全数据交换。</span><span class="sxs-lookup"><span data-stu-id="7d18d-108">However, in the absence of security mechanisms like IPsec, the administrator must configure native Oracle data encryption and integrity to ensure secure data exchanges between the adapter client and the Oracle database.</span></span> <span data-ttu-id="7d18d-109">有关配置本机 Oracle 数据加密和完整性的详细信息，请参阅[ http://go.microsoft.com/fwlink/p/?LinkId=140032 ](http://go.microsoft.com/fwlink/p/?LinkId=140032)。</span><span class="sxs-lookup"><span data-stu-id="7d18d-109">For detailed information about configuring native Oracle data encryption and integrity, see [http://go.microsoft.com/fwlink/p/?LinkId=140032](http://go.microsoft.com/fwlink/p/?LinkId=140032).</span></span>  
  
 <span data-ttu-id="7d18d-110">必须提供用户名凭据密码到[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7d18d-110">You must supply user name password credentials to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="7d18d-111">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用这些凭据来打开连接时，对 Oracle 数据库用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7d18d-111">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses these credentials to authenticate the user on the Oracle database when it opens a connection.</span></span> <span data-ttu-id="7d18d-112">这些凭据用于连接 Oracle 数据库上提供授权的级别。</span><span class="sxs-lookup"><span data-stu-id="7d18d-112">These credentials provide a level of authorization on the Oracle database for the connection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d18d-113">使用的凭据[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]来建立对 Oracle 数据库的连接不提供消息级或传输级别的身份验证或授权在网络上传输的数据。</span><span class="sxs-lookup"><span data-stu-id="7d18d-113">The credentials used by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to establish a connection on the Oracle database do not provide message-level or transport-level authentication or authorization for data traveling across the network.</span></span> <span data-ttu-id="7d18d-114">它们仅用于打开连接和对 Oracle 数据库用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7d18d-114">They are only used to open a connection and authenticate the user on the Oracle database.</span></span>  
  
 <span data-ttu-id="7d18d-115">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供了多种方法可以通过其提供这些凭据。</span><span class="sxs-lookup"><span data-stu-id="7d18d-115">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] provides a number of methods through which you can supply these credentials.</span></span> <span data-ttu-id="7d18d-116">有关如何更安全地提供 BizTalk 解决方案中的 Oracle 凭据的信息，请参阅[Oracle 数据库适配器与 Biztalk Server 安全性](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7d18d-116">For information about how to more securely provide Oracle credentials in BizTalk solutions, see [Security with the Oracle Database adapter and Biztalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).</span></span> <span data-ttu-id="7d18d-117">若要了解如何更安全地提供编程解决方案中的 Oracle 数据库凭据，请参阅[安全使用 Oracle 数据库适配器编程](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7d18d-117">For information about how to more securely provide Oracle database credentials in programming solutions, see [Secure programming with the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md).</span></span>  
  
## <a name="managing-audit-logs"></a><span data-ttu-id="7d18d-118">管理审核日志</span><span class="sxs-lookup"><span data-stu-id="7d18d-118">Managing Audit Logs</span></span>  
 <span data-ttu-id="7d18d-119">审核日志，可以将存储在你的企业软件，并可帮助使用情况监视和问题跟踪的各种客户端执行的操作有关的信息。</span><span class="sxs-lookup"><span data-stu-id="7d18d-119">Audit logs enable you to store information about the actions performed by various clients on your enterprise software, and helps usage monitoring and problem tracking.</span></span> <span data-ttu-id="7d18d-120">但是，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不提供任何方式来管理对 Oracle 数据库适配器客户端执行的操作的审核日志。</span><span class="sxs-lookup"><span data-stu-id="7d18d-120">However, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not provide any way to manage audit logs for the actions performed by the adapter clients on the Oracle database.</span></span> <span data-ttu-id="7d18d-121">这可能会带来安全威胁，因为适配器客户端可以否认 Oracle 数据库上执行它们的操作。</span><span class="sxs-lookup"><span data-stu-id="7d18d-121">This might pose a security threat as the adapter clients can repudiate the actions performed by them on the Oracle database.</span></span> <span data-ttu-id="7d18d-122">若要缓解此问题，必须启用 Oracle 来记录对 Oracle 数据库适配器客户端执行的操作中的审核线索。</span><span class="sxs-lookup"><span data-stu-id="7d18d-122">To mitigate this issue, you must enable audit trail in Oracle to log the actions performed by the adapter clients on the Oracle database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d18d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d18d-123">See Also</span></span>  
<span data-ttu-id="7d18d-124">[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md) </span><span class="sxs-lookup"><span data-stu-id="7d18d-124">[Secure your Oracle Database applications](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md) </span></span>  
[<span data-ttu-id="7d18d-125">最佳实践</span><span class="sxs-lookup"><span data-stu-id="7d18d-125">Best Practices</span></span>](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)