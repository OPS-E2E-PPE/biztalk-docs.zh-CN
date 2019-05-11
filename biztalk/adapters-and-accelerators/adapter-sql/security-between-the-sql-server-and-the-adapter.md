---
title: SQL Server 和适配器之间的安全 |Microsoft Docs
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
ms.openlocfilehash: 3414cb5ed82cc9003e6207c4a58150dd914d2a19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367948"
---
# <a name="security-between-the-sql-server-and-the-adapter"></a><span data-ttu-id="a3f79-102">SQL Server 和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="a3f79-102">Security between the SQL Server and the adapter</span></span>
<span data-ttu-id="a3f79-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是符合标准的方法，例如，使用 SSO 和 IPSEC 来保护与数据库服务器的数据交换。</span><span class="sxs-lookup"><span data-stu-id="a3f79-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is compatible with the standard methods, such as SSO and IPSEC used to secure data exchanges with the database server.</span></span> <span data-ttu-id="a3f79-104">不安全的数据交换可以公开到未经授权的执行组件的数据。</span><span class="sxs-lookup"><span data-stu-id="a3f79-104">Unsecured data exchanges can expose data to unauthorized actors.</span></span> <span data-ttu-id="a3f79-105">有关使用 SQL Server 的安全问题的信息，请参阅[有关 SQL Server 的安全注意事项](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL 文档中。</span><span class="sxs-lookup"><span data-stu-id="a3f79-105">For information about security issues with SQL Server, see [Security Considerations for SQL Server](http://go.microsoft.com/fwlink/p/?LinkId=196954) in the SQL documentation.</span></span>  
  
 <span data-ttu-id="a3f79-106">可以通过使用 Internet 协议安全性 (IPsec) 来提高数据交换的安全性。</span><span class="sxs-lookup"><span data-stu-id="a3f79-106">You can improve the security of data exchanges by using Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="a3f79-107">IPsec 是一种开放标准来保护通过 Internet 协议 (IP) 网络的通信框架。</span><span class="sxs-lookup"><span data-stu-id="a3f79-107">IPsec is a framework of open standards for protecting communications over Internet Protocol (IP) networks.</span></span> <span data-ttu-id="a3f79-108">任何数据之间使用 IPSec，交换[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]和 SQL server 通过网络进行加密，使其针对未经授权的执行组件使用的数据变得困难。</span><span class="sxs-lookup"><span data-stu-id="a3f79-108">With IPSec, any data exchanged between the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and the SQL server over the network is encrypted, making it difficult for unauthorized actors to use the data.</span></span> <span data-ttu-id="a3f79-109">有关 IPsec 以及与 Microsoft 产品使用 IPsec 的详细信息，请参阅 Microsoft TechNet 文章[IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)。</span><span class="sxs-lookup"><span data-stu-id="a3f79-109">For more information about IPsec and about using IPsec with Microsoft products, see the Microsoft TechNet article [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955).</span></span>  
  
 <span data-ttu-id="a3f79-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上它与数据库建立的连接进行身份验证支持 SSO 和集成安全性。</span><span class="sxs-lookup"><span data-stu-id="a3f79-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports SSO and Integrated Security for authentication on the connections that it establishes with the database.</span></span> <span data-ttu-id="a3f79-111">通过 SSO，凭据进行加密和存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="a3f79-111">With SSO, the credentials are encrypted and stored in the registry.</span></span> <span data-ttu-id="a3f79-112">系统使用这些凭据来确定而不是要求用户输入其位置可能会看到这些功能由未经授权的参与者访问权限。</span><span class="sxs-lookup"><span data-stu-id="a3f79-112">The system uses these credentials to determine access instead of requiring the user to enter them where they might be seen by unauthorized actors.</span></span> <span data-ttu-id="a3f79-113">集成的安全性使用登录用户的凭据来访问 SQL server。</span><span class="sxs-lookup"><span data-stu-id="a3f79-113">Integrated Security uses the credentials of the logged on user to access the SQL server.</span></span> <span data-ttu-id="a3f79-114">这还消除了需要用户输入凭据。</span><span class="sxs-lookup"><span data-stu-id="a3f79-114">This also eliminates the need for users to enter credentials.</span></span> <span data-ttu-id="a3f79-115">数据库管理员必须配置 SQL 以接受集成安全性才能正常工作的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="a3f79-115">The database administrator must configure SQL to accept the users credentials for Integrated Security to work correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f79-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3f79-116">See Also</span></span>  
[<span data-ttu-id="a3f79-117">保护 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="a3f79-117">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)