---
title: 对 BRE DB 连接进行加密 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63edd2bb-97f1-4b8b-8cdc-f4792909ca86
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a51d2468f31b316a9ab9ac2d8a3fa8ee57f11320
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997694"
---
# <a name="encrypt-the-connection-to-the-bre-database"></a><span data-ttu-id="97039-102">加密与 BRE 数据库的连接</span><span class="sxs-lookup"><span data-stu-id="97039-102">Encrypt the Connection to the BRE Database</span></span>
<span data-ttu-id="97039-103">根据你的公司的安全策略，请考虑加密：</span><span class="sxs-lookup"><span data-stu-id="97039-103">Based on the security policy of your company, consider encrypting:</span></span>  
  
- <span data-ttu-id="97039-104">在登录过程中传输的凭据。</span><span class="sxs-lookup"><span data-stu-id="97039-104">The credentials transmitted during the logon process.</span></span>  
  
- <span data-ttu-id="97039-105">业务规则引擎 (BRE) 策略在其中运行的客户端计算机和规则引擎数据库之间的网络传输的数据。</span><span class="sxs-lookup"><span data-stu-id="97039-105">The data transmitted across a network between the client computer where the Business Rule Engine (BRE) policy runs and the Rule Engine database.</span></span>  
  
  <span data-ttu-id="97039-106">本主题介绍如何为 SQL Server 上托管的 BRE 数据库的连接进行加密。</span><span class="sxs-lookup"><span data-stu-id="97039-106">This topic describes how to encrypt the connections to BRE databases hosted on SQL Server.</span></span>  
  
## <a name="encrypt-the-connection-to-the-bre-database"></a><span data-ttu-id="97039-107">加密与 BRE 数据库的连接</span><span class="sxs-lookup"><span data-stu-id="97039-107">Encrypt the Connection to the BRE Database</span></span>
 <span data-ttu-id="97039-108">默认情况下，当客户端应用程序连接到 SQL Server 时在登录过程中传输的凭据进行加密。</span><span class="sxs-lookup"><span data-stu-id="97039-108">By default, credentials that are transmitted during the logon process when a client application connects to SQL Server are encrypted.</span></span> <span data-ttu-id="97039-109">如果没有设置证书的服务器上，在启动时，SQL Server 将生成自签名的证书用于加密登录包。</span><span class="sxs-lookup"><span data-stu-id="97039-109">If no certificate has been provisioned on the server, when it starts up, SQL Server generates a self-signed certificate that is used to encrypt logon packets.</span></span>  
  
 <span data-ttu-id="97039-110">若要支持的 SQL Server 实例的 SQL Server 和客户端之间跨网络传输的数据进行加密，应设置**强制加密**到服务器上的选项**是**或设置**强制协议加密**选项设为**是**客户端上。</span><span class="sxs-lookup"><span data-stu-id="97039-110">To enable encryption of data that is transmitted across a network between SQL Server and the client for an instance of SQL Server, you should set the **Force Encryption** option on the server to **Yes** or set the **Force Protocol Encryption** option to **Yes** on the client.</span></span>  
  
 <span data-ttu-id="97039-111">当**强制加密**选项设置为**是**在服务器端 SQL Server 使用 SSL 来加密所有通信*之间的所有客户端和数据库服务器*.</span><span class="sxs-lookup"><span data-stu-id="97039-111">When the **Force Encryption** option is set to **Yes** on the server side, SQL Server uses SSL to encrypt all the communication *between all the clients and the database server*.</span></span> <span data-ttu-id="97039-112">换而言之，加密到服务器的所有传入连接。</span><span class="sxs-lookup"><span data-stu-id="97039-112">In other words, all the incoming connections to the server are encrypted.</span></span> <span data-ttu-id="97039-113">若要在服务器启用此选项，建议您使用 SQL Server 配置管理器在服务器上安装证书。</span><span class="sxs-lookup"><span data-stu-id="97039-113">To enable this option on the server, it is recommended that you install a certificate on the server by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="97039-114">如果在服务器上未安装证书，服务器自动生成自签名的证书时该实例已启动。</span><span class="sxs-lookup"><span data-stu-id="97039-114">If a certificate is not installed on the server, the server auto-generates a self-signed certificate when the instance is started.</span></span>  
  
 <span data-ttu-id="97039-115">此自我签署的证书可代替受信任证书颁发机构颁发的证书使用，但不能抵御身份欺骗威胁的侵袭。</span><span class="sxs-lookup"><span data-stu-id="97039-115">This self-signed certificate can be used instead of a certificate from a trusted certificate authority, but it does not provide any protection against spoofing identity threats.</span></span> <span data-ttu-id="97039-116">在生产环境中或在连接到 Internet 的服务器上，不应依赖使用自签名证书的 SSL。</span><span class="sxs-lookup"><span data-stu-id="97039-116">You should not rely on SSL using self-signed certificates in a production environment or on servers that are connected to the Internet.</span></span> <span data-ttu-id="97039-117">该选项设置好之后，不支持加密的客户端将被拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="97039-117">When the option is set, any client that cannot support encryption is denied access.</span></span> <span data-ttu-id="97039-118">在设置后必须重新启动 SQL Server**强制加密**选项。</span><span class="sxs-lookup"><span data-stu-id="97039-118">SQL Server must be restarted after setting the **Force Encryption** option.</span></span> <span data-ttu-id="97039-119">可以通过使用 SQL Server 配置管理器 （SQL Server 网络配置） 来设置此选项。</span><span class="sxs-lookup"><span data-stu-id="97039-119">You can set this option by using the SQL Server Configuration Manager (SQL Server Network Configuration).</span></span>  
  
 <span data-ttu-id="97039-120">当**强制协议加密**在客户端，SQL Server 使用 SSL 以加密所有通信设置*该客户端和所有服务器之间*。</span><span class="sxs-lookup"><span data-stu-id="97039-120">When the **Force Protocol Encryption** is set on the client side, SQL Server uses SSL to encrypt all the communication *between that client and all the servers*.</span></span> <span data-ttu-id="97039-121">换而言之，从客户端的所有传出连接进行加密。</span><span class="sxs-lookup"><span data-stu-id="97039-121">In other words, all the outgoing connections from the client are encrypted.</span></span> <span data-ttu-id="97039-122">若要启用此选项在客户端上的，您应证书如果服务器上安装**信任服务器证书**客户端上的选项设置为**否**。</span><span class="sxs-lookup"><span data-stu-id="97039-122">To enable this option on the client side, you should install a certificate on the server if the **Trust Server Certificate** option on the client is set to **No**.</span></span> <span data-ttu-id="97039-123">如果**信任服务器证书**客户端上的选项设置为**是**，客户端不会验证服务器证书，而是使用自签名证书。</span><span class="sxs-lookup"><span data-stu-id="97039-123">If the **Trust Server Certificate** option on the client is set to **Yes**, the client does not validate the server certificate, thereby enabling the use of a self-signed certificate.</span></span> <span data-ttu-id="97039-124">您可通过使用 SQL Server 配置管理器（SQL Native Client 配置）来设置此选项。</span><span class="sxs-lookup"><span data-stu-id="97039-124">You can set this option by using the SQL Server Configuration Manager (SQL Native Client Configuration).</span></span>  
  
 <span data-ttu-id="97039-125">SQL Server 还允许您启用加密*客户端到服务器的特定连接*通过设置**加密/为使用加密数据**标记，用于**是**中连接字符串中。</span><span class="sxs-lookup"><span data-stu-id="97039-125">SQL Server also allows you to enable the encryption for a *specific connection from a client to the server* by setting the **Encrypt/Use Encryption for Data** flag to **Yes** in the connection string.</span></span> <span data-ttu-id="97039-126">不过，BRE 将自动生成连接字符串而不加密选项设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="97039-126">However, the BRE automatically generates the connection strings without setting the encryption option to **Yes**.</span></span> <span data-ttu-id="97039-127">因此，您不能加密的特定连接到规则引擎数据库服务器从客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="97039-127">Hence, you cannot encrypt a specific connection to the Rule Engine database server from the client computer.</span></span> <span data-ttu-id="97039-128">相反，应设置**强制协议加密**选项在客户端上一段中所述。</span><span class="sxs-lookup"><span data-stu-id="97039-128">Instead, you should set the **Force Protocol Encryption** option on the client as mentioned in the previous paragraph.</span></span>