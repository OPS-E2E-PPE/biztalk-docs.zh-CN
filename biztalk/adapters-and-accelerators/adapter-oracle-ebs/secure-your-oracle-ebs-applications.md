---
title: 保护 Oracle EBS 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76147120-57a8-4959-a0ff-77d04dee06a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3033c038febae4dc13cb0681947eb55135b6e6f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374587"
---
# <a name="secure-your-oracle-ebs-applications"></a><span data-ttu-id="fcf29-102">保护 Oracle EBS 应用程序</span><span class="sxs-lookup"><span data-stu-id="fcf29-102">Secure your Oracle EBS applications</span></span>
<span data-ttu-id="fcf29-103">Oracle 电子商务应用程序处理敏感商业信息，例如客户帐户详细信息。</span><span class="sxs-lookup"><span data-stu-id="fcf29-103">Oracle E-Business applications deal with sensitive business information such as customer account details.</span></span> <span data-ttu-id="fcf29-104">使用的应用程序[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]访问和修改此信息是本地或分布式网络中可能会无意中使私钥暴露访问未经授权的参与者，除非工作进行防护和保护期间数据传输。</span><span class="sxs-lookup"><span data-stu-id="fcf29-104">Applications that use the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="fcf29-105">数据保护和安全性是通常认为的按下列术语：</span><span class="sxs-lookup"><span data-stu-id="fcf29-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="fcf29-106">*授权*控制对基于请求者的标识的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="fcf29-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
- <span data-ttu-id="fcf29-107">*身份验证*提供了用于请求者的身份进行验证的机制。</span><span class="sxs-lookup"><span data-stu-id="fcf29-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
- <span data-ttu-id="fcf29-108">*数据保密性*提供了用于保护通过加密的数据的隐私的机制。</span><span class="sxs-lookup"><span data-stu-id="fcf29-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="fcf29-109">*数据完整性*提供机制以数字方式签署数据，以便接收方可以确保数据尚未更改传输中。</span><span class="sxs-lookup"><span data-stu-id="fcf29-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="fcf29-110">需要关注的另一个重要方面是提供给的用户名称密码凭据[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fcf29-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="fcf29-111">适配器使用这些凭据打开与 Oracle 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="fcf29-111">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="fcf29-112">可以在连接 URI; 提供这些凭据但是，因为用户名和密码是明文形式[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]提供可用于以更安全的方式提供这些凭据的替代方法。</span><span class="sxs-lookup"><span data-stu-id="fcf29-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
  <span data-ttu-id="fcf29-113">在本部分中的主题提供了指导原则来帮助你更好地保护使用开发解决方案[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fcf29-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
