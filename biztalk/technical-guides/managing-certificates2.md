---
title: 管理 Certificates2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e3bc75f-1a58-49d8-8a1d-6936b1a4105b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50b9542a6199b065a9c6d65f4adda9f8b52306ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008510"
---
# <a name="managing-certificates"></a><span data-ttu-id="41d17-102">管理证书</span><span class="sxs-lookup"><span data-stu-id="41d17-102">Managing Certificates</span></span>
<span data-ttu-id="41d17-103">本部分介绍如何管理与 BizTalk Server 使用的数字证书。</span><span class="sxs-lookup"><span data-stu-id="41d17-103">This section describes how to manage digital certificates used with BizTalk Server.</span></span> <span data-ttu-id="41d17-104">其主题描述如何安装证书 （以及将其安装到哪个文件夹），以及如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 MIME/SMIME 和 AS2，并使用 BizTalk 适配器使用的证书。</span><span class="sxs-lookup"><span data-stu-id="41d17-104">Its topics describe how to install certificates (and which folder to install them into), and how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use the certificate for MIME/SMIME and AS2, and for use with BizTalk adapters.</span></span> <span data-ttu-id="41d17-105">Microsoft BizTalk Server 可以使出于文档加密和解密的目的使用的公钥基础结构 (PKI) 数字证书，文档签名和验证 （不可否认性），并且方解析。</span><span class="sxs-lookup"><span data-stu-id="41d17-105">Microsoft BizTalk Server can make use of public key infrastructure (PKI) digital certificates for purposes of document encryption and decryption, document signing and verification (non-repudiation), and party resolution.</span></span>  
  
 <span data-ttu-id="41d17-106">有关安装证书的步骤清单，请参阅[清单： 安装和配置证书](~/technical-guides/checklist-installing-and-configuring-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="41d17-106">For a checklist of steps to install the certificates, see [Checklist: Installing and Configuring Certificates](~/technical-guides/checklist-installing-and-configuring-certificates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41d17-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="41d17-107">In This Section</span></span>  
  
-   [<span data-ttu-id="41d17-108">管理 Certificates2 最佳实践</span><span class="sxs-lookup"><span data-stu-id="41d17-108">Best Practices for Managing Certificates2</span></span>](../technical-guides/best-practices-for-managing-certificates2.md)  
  
-   [<span data-ttu-id="41d17-109">BizTalk Server 中证书的已知问题</span><span class="sxs-lookup"><span data-stu-id="41d17-109">Known Issues with Certificates in BizTalk Server</span></span>](../technical-guides/known-issues-with-certificates-in-biztalk-server.md)  
  
-   [<span data-ttu-id="41d17-110">安装和配置数字证书</span><span class="sxs-lookup"><span data-stu-id="41d17-110">Installing and Configuring Digital Certificates</span></span>](~/technical-guides/installing-and-configuring-digital-certificates.md)