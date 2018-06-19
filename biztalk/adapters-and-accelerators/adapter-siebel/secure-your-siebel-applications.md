---
title: 保护 Siebel 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b597120de91b6a09fdc26b90a2cb357cdc7dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221965"
---
# <a name="secure-your-siebel-applications"></a><span data-ttu-id="494f6-102">保护 Siebel 应用程序</span><span class="sxs-lookup"><span data-stu-id="494f6-102">Secure your Siebel applications</span></span>
<span data-ttu-id="494f6-103">Siebel 系统通常包含敏感商业信息，例如客户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="494f6-103">The Siebel system often contains sensitive business information such as customer account details.</span></span> <span data-ttu-id="494f6-104">应用程序使用[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]访问和修改此信息是本地或分布式网络可能会无意中公开其能够访问未经授权的参与者，除非努力保护且安全的过程的数据传输。</span><span class="sxs-lookup"><span data-stu-id="494f6-104">Applications that use the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="494f6-105">数据保护和安全是通常认为按下列术语：</span><span class="sxs-lookup"><span data-stu-id="494f6-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="494f6-106">*授权*控制对基于请求者的标识的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="494f6-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
-   <span data-ttu-id="494f6-107">*身份验证*提供用于请求者的身份进行验证的机制。</span><span class="sxs-lookup"><span data-stu-id="494f6-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
-   <span data-ttu-id="494f6-108">*数据保密性*提供用于保护通过加密的数据的隐私的机制。</span><span class="sxs-lookup"><span data-stu-id="494f6-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="494f6-109">*数据完整性*提供了数据，进行数字签名的机制，以便接收方可以确保数据尚未更改在传输过程。</span><span class="sxs-lookup"><span data-stu-id="494f6-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="494f6-110">需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="494f6-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="494f6-111">适配器使用这些凭据打开到 Siebel 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="494f6-111">The adapter uses these credentials to open connections to the Siebel system.</span></span> <span data-ttu-id="494f6-112">可以在连接 URI; 中提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。</span><span class="sxs-lookup"><span data-stu-id="494f6-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
 <span data-ttu-id="494f6-113">本部分中的主题提供了一些指南，可以帮助你更好地保护你开发的解决方案[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="494f6-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="494f6-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="494f6-114">In This Section</span></span>  
  
-   [<span data-ttu-id="494f6-115">Siebel 系统和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="494f6-115">Security between the Siebel system and the adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [<span data-ttu-id="494f6-116">Siebel 适配器和 BizTalk Server 使用的安全</span><span class="sxs-lookup"><span data-stu-id="494f6-116">Security with Siebel adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="494f6-117">Siebel 适配器使用的安全编程</span><span class="sxs-lookup"><span data-stu-id="494f6-117">Secure programming with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [<span data-ttu-id="494f6-118">最佳做法来保护在 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="494f6-118">Best practices to secure the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)