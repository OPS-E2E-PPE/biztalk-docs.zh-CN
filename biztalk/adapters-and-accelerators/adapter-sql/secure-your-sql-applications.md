---
title: "保护 SQL 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d631bc3ad87e9a8ec8ac51850b7dbe1eb244c140
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-sql-applications"></a><span data-ttu-id="5e2f7-102">保护 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="5e2f7-102">Secure your SQL applications</span></span>
## <a name="overview"></a><span data-ttu-id="5e2f7-103">概述</span><span class="sxs-lookup"><span data-stu-id="5e2f7-103">Overview</span></span>
<span data-ttu-id="5e2f7-104">SQL Server 数据库通常包含敏感业务信息，例如客户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-104">SQL Server databases often contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="5e2f7-105">应用程序使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]访问和修改此信息是本地或分布式网络可能会无意中公开其能够访问未经授权的参与者，除非努力保护且安全的过程的数据传输。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-105">Applications that use the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="5e2f7-106">数据保护和安全是通常认为按下列术语：</span><span class="sxs-lookup"><span data-stu-id="5e2f7-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="5e2f7-107">*授权*控制对基于请求者的身份的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-107">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
-   <span data-ttu-id="5e2f7-108">*身份验证*提供验证身份的请求者的机制。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-108">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
-   <span data-ttu-id="5e2f7-109">*数据保密性*提供用于保护通过加密的数据的隐私的机制。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="5e2f7-110">*数据完整性*提供了数据，进行数字签名的机制，以便接收方可以确保数据尚未更改在传输过程。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="5e2f7-111">需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="5e2f7-112">适配器使用这些凭据打开与 SQL 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-112">The adapter uses these credentials to open connections to the SQL system.</span></span> <span data-ttu-id="5e2f7-113">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不允许在连接 URI 中提供的凭据。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-113">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not allow credentials to be supplied in the connection URI.</span></span> <span data-ttu-id="5e2f7-114">这可以防止凭据获取无意中公开。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-114">This prevents the credentials from getting exposed inadvertently.</span></span> <span data-ttu-id="5e2f7-115">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]提供两种替代方法，以更安全的方式提供这些凭据：</span><span class="sxs-lookup"><span data-stu-id="5e2f7-115">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides two alternative methods to supply these credentials in a more secure manner:</span></span>  
  
 <span data-ttu-id="5e2f7-116">集成的安全性。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-116">Integrated Security.</span></span> <span data-ttu-id="5e2f7-117">在这种情况下，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]凭据。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-117">In this case, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credentials.</span></span> <span data-ttu-id="5e2f7-118">你必须配置 SQL server 以接受这些凭据才能使用此方法。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-118">You must configure the SQL server to accept these credentials for this method to work.</span></span>  
  
 <span data-ttu-id="5e2f7-119">企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-119">Enterprise Single Sign-on (SSO).</span></span> <span data-ttu-id="5e2f7-120">有关使用 SSO 的详细信息，请参阅[SQL 适配器与 BizTalk Server 的安全](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-120">For more information about using SSO, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span></span>  
  
 <span data-ttu-id="5e2f7-121">本部分中的主题提供了一些指南，可以帮助你更好地保护你开发的解决方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5e2f7-121">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e2f7-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="5e2f7-122">In This Section</span></span>  
  
-   [<span data-ttu-id="5e2f7-123">SQL Server 和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="5e2f7-123">Security between the SQL Server and the adapter</span></span>](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [<span data-ttu-id="5e2f7-124">使用 SQL 适配器和 BizTalk Server 的安全</span><span class="sxs-lookup"><span data-stu-id="5e2f7-124">Security with the SQL adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [<span data-ttu-id="5e2f7-125">使用 SQL 适配器安全编程</span><span class="sxs-lookup"><span data-stu-id="5e2f7-125">Secure programming with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [<span data-ttu-id="5e2f7-126">最佳做法</span><span class="sxs-lookup"><span data-stu-id="5e2f7-126">Best practices</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)