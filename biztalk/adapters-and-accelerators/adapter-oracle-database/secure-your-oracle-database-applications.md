---
title: "保护 Oracle 数据库应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8601463c02e32221c369023f05ed2fd3731bb4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-oracle-database-applications"></a><span data-ttu-id="dd51e-102">保护 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="dd51e-102">Secure your Oracle Database applications</span></span>
## <a name="data-protection-and-security-overview"></a><span data-ttu-id="dd51e-103">数据保护和安全概述</span><span class="sxs-lookup"><span data-stu-id="dd51e-103">Data protection and security overview</span></span>
<span data-ttu-id="dd51e-104">数据库通常包含敏感商业信息，例如客户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="dd51e-104">A database often contains sensitive business information such as customer account details.</span></span> <span data-ttu-id="dd51e-105">应用程序使用[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]访问和修改此信息是本地或分布式网络可能会无意中公开其能够访问未经授权的参与者，除非努力保护且安全的过程的数据传输。</span><span class="sxs-lookup"><span data-stu-id="dd51e-105">Applications that use the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="dd51e-106">数据保护和安全是通常认为按下列术语：</span><span class="sxs-lookup"><span data-stu-id="dd51e-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="dd51e-107">*授权*控制对基于请求者的标识的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="dd51e-107">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
-   <span data-ttu-id="dd51e-108">*身份验证*提供用于请求者的身份进行验证的机制。</span><span class="sxs-lookup"><span data-stu-id="dd51e-108">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
-   <span data-ttu-id="dd51e-109">*数据保密性*提供用于保护通过加密的数据的隐私的机制。</span><span class="sxs-lookup"><span data-stu-id="dd51e-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="dd51e-110">*数据完整性*提供了数据，进行数字签名的机制，以便接收方可以确保数据尚未更改在传输过程。</span><span class="sxs-lookup"><span data-stu-id="dd51e-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="dd51e-111">需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd51e-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="dd51e-112">适配器使用这些凭据打开与 Oracle 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="dd51e-112">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="dd51e-113">可以在连接 URI; 中提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。</span><span class="sxs-lookup"><span data-stu-id="dd51e-113">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
 <span data-ttu-id="dd51e-114">本部分中的主题提供了一些指南，可以帮助你更好地保护你开发的解决方案[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dd51e-114">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd51e-115">在本节中</span><span class="sxs-lookup"><span data-stu-id="dd51e-115">In this section</span></span>  
  
-   [<span data-ttu-id="dd51e-116">Oracle 数据库和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="dd51e-116">Security between the Oracle Database and the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [<span data-ttu-id="dd51e-117">使用 Oracle 数据库适配器和 BizTalk Server 的安全</span><span class="sxs-lookup"><span data-stu-id="dd51e-117">Security with the Oracle Database adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [<span data-ttu-id="dd51e-118">Oracle 数据库适配器使用的安全编程</span><span class="sxs-lookup"><span data-stu-id="dd51e-118">Secure programming with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="dd51e-119">最佳做法</span><span class="sxs-lookup"><span data-stu-id="dd51e-119">Best practices</span></span>](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)