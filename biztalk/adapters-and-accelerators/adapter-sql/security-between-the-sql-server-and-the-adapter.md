---
title: SQL Server 和适配器之间的安全性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b0fd11-6753-4f52-9be7-3b6fa330fb8b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8673aee316a8a2ef83011ab3dd85016a99df1162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222493"
---
# <a name="security-between-the-sql-server-and-the-adapter"></a><span data-ttu-id="bb924-102">SQL Server 和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="bb924-102">Security between the SQL Server and the adapter</span></span>
<span data-ttu-id="bb924-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是符合标准的方法中，例如，使用 SSO 和 IPSEC 来保护与数据库服务器的数据交换。</span><span class="sxs-lookup"><span data-stu-id="bb924-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is compatible with the standard methods, such as SSO and IPSEC used to secure data exchanges with the database server.</span></span> <span data-ttu-id="bb924-104">不安全的数据交换可以公开到未经授权的 actor 的数据。</span><span class="sxs-lookup"><span data-stu-id="bb924-104">Unsecured data exchanges can expose data to unauthorized actors.</span></span> <span data-ttu-id="bb924-105">有关与 SQL Server 的安全问题的信息，请参阅[的 SQL Server 的安全注意事项](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL 文档中。</span><span class="sxs-lookup"><span data-stu-id="bb924-105">For information about security issues with SQL Server, see [Security Considerations for SQL Server](http://go.microsoft.com/fwlink/p/?LinkId=196954) in the SQL documentation.</span></span>  
  
 <span data-ttu-id="bb924-106">可以通过使用 Internet 协议安全性 (IPsec) 来提高数据交换的安全性。</span><span class="sxs-lookup"><span data-stu-id="bb924-106">You can improve the security of data exchanges by using Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="bb924-107">IPsec 是一种开放标准的保护通过 Internet 协议 (IP) 网络的通信框架。</span><span class="sxs-lookup"><span data-stu-id="bb924-107">IPsec is a framework of open standards for protecting communications over Internet Protocol (IP) networks.</span></span> <span data-ttu-id="bb924-108">任何数据之间使用 IPSec，交换[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL server 通过网络进行加密，这使得困难未经授权的参与者，要使用的数据。</span><span class="sxs-lookup"><span data-stu-id="bb924-108">With IPSec, any data exchanged between the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and the SQL server over the network is encrypted, making it difficult for unauthorized actors to use the data.</span></span> <span data-ttu-id="bb924-109">有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章[IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)。</span><span class="sxs-lookup"><span data-stu-id="bb924-109">For more information about IPsec and about using IPsec with Microsoft products, see the Microsoft TechNet article [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955).</span></span>  
  
 <span data-ttu-id="bb924-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上与数据库建立的连接进行身份验证支持实现 SSO 和集成安全性。</span><span class="sxs-lookup"><span data-stu-id="bb924-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports SSO and Integrated Security for authentication on the connections that it establishes with the database.</span></span> <span data-ttu-id="bb924-111">使用 SSO，凭据进行加密和存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="bb924-111">With SSO, the credentials are encrypted and stored in the registry.</span></span> <span data-ttu-id="bb924-112">系统使用这些凭据来确定而不是要求用户输入其中他们可能看到未经授权的参与者的访问权限。</span><span class="sxs-lookup"><span data-stu-id="bb924-112">The system uses these credentials to determine access instead of requiring the user to enter them where they might be seen by unauthorized actors.</span></span> <span data-ttu-id="bb924-113">集成的安全性使用登录用户的凭据来访问 SQL server。</span><span class="sxs-lookup"><span data-stu-id="bb924-113">Integrated Security uses the credentials of the logged on user to access the SQL server.</span></span> <span data-ttu-id="bb924-114">这还消除了对用户输入凭据的需要。</span><span class="sxs-lookup"><span data-stu-id="bb924-114">This also eliminates the need for users to enter credentials.</span></span> <span data-ttu-id="bb924-115">数据库管理员必须配置 SQL 接受集成安全性才能正常工作的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="bb924-115">The database administrator must configure SQL to accept the users credentials for Integrated Security to work correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb924-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb924-116">See Also</span></span>  
[<span data-ttu-id="bb924-117">保护 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="bb924-117">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)