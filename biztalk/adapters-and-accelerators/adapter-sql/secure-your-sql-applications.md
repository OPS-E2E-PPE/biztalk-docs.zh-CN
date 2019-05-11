---
title: 保护 SQL 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ec6222c68e37ab85414a5b6eb8137b5cba13f3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367884"
---
# <a name="secure-your-sql-applications"></a><span data-ttu-id="a747e-102">保护 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="a747e-102">Secure your SQL applications</span></span>
## <a name="overview"></a><span data-ttu-id="a747e-103">概述</span><span class="sxs-lookup"><span data-stu-id="a747e-103">Overview</span></span>
<span data-ttu-id="a747e-104">SQL Server 数据库通常包含敏感商业信息，例如客户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="a747e-104">SQL Server databases often contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="a747e-105">使用的应用程序[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]访问和修改此信息是本地或分布式网络中可能会无意中使私钥暴露访问未经授权的参与者，除非工作进行防护和保护期间数据传输。</span><span class="sxs-lookup"><span data-stu-id="a747e-105">Applications that use the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="a747e-106">数据保护和安全性是通常认为的按下列术语：</span><span class="sxs-lookup"><span data-stu-id="a747e-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="a747e-107">*授权*控制对基于请求者的标识的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="a747e-107">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
- <span data-ttu-id="a747e-108">*身份验证*提供了用于请求者的身份进行验证的机制。</span><span class="sxs-lookup"><span data-stu-id="a747e-108">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
- <span data-ttu-id="a747e-109">*数据保密性*提供了用于保护通过加密的数据的隐私的机制。</span><span class="sxs-lookup"><span data-stu-id="a747e-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="a747e-110">*数据完整性*提供机制以数字方式签署数据，以便接收方可以确保数据尚未更改传输中。</span><span class="sxs-lookup"><span data-stu-id="a747e-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="a747e-111">需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a747e-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="a747e-112">适配器使用这些凭据以打开到 SQL 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="a747e-112">The adapter uses these credentials to open connections to the SQL system.</span></span> <span data-ttu-id="a747e-113">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不允许要在连接 URI 中提供的凭据。</span><span class="sxs-lookup"><span data-stu-id="a747e-113">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not allow credentials to be supplied in the connection URI.</span></span> <span data-ttu-id="a747e-114">这可以防止凭据获取无意中公开。</span><span class="sxs-lookup"><span data-stu-id="a747e-114">This prevents the credentials from getting exposed inadvertently.</span></span> <span data-ttu-id="a747e-115">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]提供两种替代方法，以更安全的方式提供这些凭据：</span><span class="sxs-lookup"><span data-stu-id="a747e-115">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides two alternative methods to supply these credentials in a more secure manner:</span></span>  
  
  <span data-ttu-id="a747e-116">集成的安全性。</span><span class="sxs-lookup"><span data-stu-id="a747e-116">Integrated Security.</span></span> <span data-ttu-id="a747e-117">在这种情况下，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用 Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]凭据。</span><span class="sxs-lookup"><span data-stu-id="a747e-117">In this case, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credentials.</span></span> <span data-ttu-id="a747e-118">必须配置为接受这些凭据，以便此方法运行的 SQL server。</span><span class="sxs-lookup"><span data-stu-id="a747e-118">You must configure the SQL server to accept these credentials for this method to work.</span></span>  
  
  <span data-ttu-id="a747e-119">企业单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="a747e-119">Enterprise Single Sign-on (SSO).</span></span> <span data-ttu-id="a747e-120">有关使用 SSO 的详细信息，请参阅[SQL 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a747e-120">For more information about using SSO, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span></span>  
  
  <span data-ttu-id="a747e-121">在本部分中的主题提供了指导原则来帮助你更好地保护使用开发解决方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a747e-121">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a747e-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="a747e-122">In This Section</span></span>  
  
-   [<span data-ttu-id="a747e-123">SQL Server 与适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="a747e-123">Security between the SQL Server and the adapter</span></span>](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [<span data-ttu-id="a747e-124">SQL 适配器与 BizTalk Server 之间的安全性</span><span class="sxs-lookup"><span data-stu-id="a747e-124">Security with the SQL adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [<span data-ttu-id="a747e-125">使用 SQL 适配器进行安全编程</span><span class="sxs-lookup"><span data-stu-id="a747e-125">Secure programming with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [<span data-ttu-id="a747e-126">最佳做法</span><span class="sxs-lookup"><span data-stu-id="a747e-126">Best practices</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)