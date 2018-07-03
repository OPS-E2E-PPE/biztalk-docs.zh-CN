---
title: 保护 SAP 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
ms.assetid: 9f0fb2a2-d6e2-4561-8472-c0bf682a4798
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dade1433b0bd432b53e48da86d53d23be7512de7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005782"
---
# <a name="secure-your-sap-applications"></a><span data-ttu-id="b2059-102">保护 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="b2059-102">Secure your SAP applications</span></span>
<span data-ttu-id="b2059-103">SAP 系统可以包含敏感商业信息，例如客户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2059-103">The SAP system can contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="b2059-104">使用的应用程序[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]访问和修改此信息是本地或分布式网络中可能会无意中使私钥暴露访问未经授权的参与者，除非工作进行防护和保护期间数据传输。</span><span class="sxs-lookup"><span data-stu-id="b2059-104">Applications that use the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="b2059-105">数据保护和安全性是通常认为的按下列术语：</span><span class="sxs-lookup"><span data-stu-id="b2059-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="b2059-106">*授权*控制对基于请求者的标识的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="b2059-106">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
- <span data-ttu-id="b2059-107">*身份验证*提供了用于请求者的身份进行验证的机制。</span><span class="sxs-lookup"><span data-stu-id="b2059-107">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
- <span data-ttu-id="b2059-108">*数据保密性*提供了用于保护通过加密的数据的隐私的机制。</span><span class="sxs-lookup"><span data-stu-id="b2059-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="b2059-109">*数据完整性*提供机制以数字方式签署数据，以便接收方可以确保数据尚未更改传输中。</span><span class="sxs-lookup"><span data-stu-id="b2059-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="b2059-110">在本部分中的主题提供了指导原则来帮助你更好地保护使用开发解决方案[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b2059-110">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2059-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="b2059-111">In this section</span></span>  
  
-   [<span data-ttu-id="b2059-112">SAP 系统和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="b2059-112">Security between the SAP system and the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)
  
-   [<span data-ttu-id="b2059-113">SAP 适配器与 BizTalk Server 安全性</span><span class="sxs-lookup"><span data-stu-id="b2059-113">Security with the SAP adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="b2059-114">使用 SAP 适配器进行安全编程</span><span class="sxs-lookup"><span data-stu-id="b2059-114">Secure programming with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)
  
-   [<span data-ttu-id="b2059-115">最佳做法来保护 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="b2059-115">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)