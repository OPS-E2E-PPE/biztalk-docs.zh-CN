---
title: 保护 Oracle 数据库应用程序 |Microsoft Docs
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
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c935906761b69797a5407cedffcf2a41c0e25d6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529489"
---
# <a name="secure-your-oracle-database-applications"></a><span data-ttu-id="2e10d-102">保护 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="2e10d-102">Secure your Oracle Database applications</span></span>
## <a name="data-protection-and-security-overview"></a><span data-ttu-id="2e10d-103">数据保护和安全性概述</span><span class="sxs-lookup"><span data-stu-id="2e10d-103">Data protection and security overview</span></span>
<span data-ttu-id="2e10d-104">数据库通常包含敏感商业信息，例如客户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e10d-104">A database often contains sensitive business information such as customer account details.</span></span> <span data-ttu-id="2e10d-105">使用的应用程序[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]访问和修改此信息是本地或分布式网络中可能会无意中使私钥暴露访问未经授权的参与者，除非工作进行防护和保护期间数据传输。</span><span class="sxs-lookup"><span data-stu-id="2e10d-105">Applications that use the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="2e10d-106">数据保护和安全性是通常认为的按下列术语：</span><span class="sxs-lookup"><span data-stu-id="2e10d-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="2e10d-107">*授权*控制对基于请求者的标识的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="2e10d-107">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
- <span data-ttu-id="2e10d-108">*身份验证*提供了用于请求者的身份进行验证的机制。</span><span class="sxs-lookup"><span data-stu-id="2e10d-108">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
- <span data-ttu-id="2e10d-109">*数据保密性*提供了用于保护通过加密的数据的隐私的机制。</span><span class="sxs-lookup"><span data-stu-id="2e10d-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="2e10d-110">*数据完整性*提供机制以数字方式签署数据，以便接收方可以确保数据尚未更改传输中。</span><span class="sxs-lookup"><span data-stu-id="2e10d-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="2e10d-111">需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2e10d-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="2e10d-112">适配器使用这些凭据打开与 Oracle 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="2e10d-112">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="2e10d-113">可以在连接 URI; 提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。</span><span class="sxs-lookup"><span data-stu-id="2e10d-113">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
  <span data-ttu-id="2e10d-114">在本部分中的主题提供了指导原则来帮助你更好地保护使用开发解决方案[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2e10d-114">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e10d-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="2e10d-115">In this section</span></span>  
  
-   [<span data-ttu-id="2e10d-116">Oracle 数据库和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="2e10d-116">Security between the Oracle Database and the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [<span data-ttu-id="2e10d-117">Oracle 数据库适配器与 BizTalk Server 安全性</span><span class="sxs-lookup"><span data-stu-id="2e10d-117">Security with the Oracle Database adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [<span data-ttu-id="2e10d-118">使用 Oracle 数据库适配器进行安全编程</span><span class="sxs-lookup"><span data-stu-id="2e10d-118">Secure programming with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="2e10d-119">最佳做法</span><span class="sxs-lookup"><span data-stu-id="2e10d-119">Best practices</span></span>](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)