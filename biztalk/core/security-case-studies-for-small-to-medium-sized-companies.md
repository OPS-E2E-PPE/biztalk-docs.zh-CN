---
title: "对于小型到中型公司的安全案例研究 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
- security, examples
- security, architecture
- architecture, medium distributions
ms.assetid: b33e3f2a-ddc4-47a8-92d7-511ae0cc880e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9af0f013960e882ffe6b5c081ae1452df4aaecf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-case-studies-for-small-to-medium-sized-companies"></a><span data-ttu-id="54c86-102">对于小型到中型公司的安全案例研究</span><span class="sxs-lookup"><span data-stu-id="54c86-102">Security Case Studies for Small to Medium-Sized Companies</span></span>
<span data-ttu-id="54c86-103">对于重视确保仅有选定的一组人员或应用程序可访问其数据和资源的任何公司，安全性是至关重要的。</span><span class="sxs-lookup"><span data-stu-id="54c86-103">Security is a concern of any company that is serious about making sure that only a select group of people or applications can access its data and resources.</span></span> <span data-ttu-id="54c86-104">公司可通过多种方式处理和实现安全性。</span><span class="sxs-lookup"><span data-stu-id="54c86-104">Companies approach and implement security in a variety of ways.</span></span>  
  
 <span data-ttu-id="54c86-105">本部分提供了在安全环境中部署 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的准则。</span><span class="sxs-lookup"><span data-stu-id="54c86-105">This section provides guidelines for deploying Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a secure environment.</span></span> <span data-ttu-id="54c86-106">其中提供的信息可帮助您评估对 BizTalk Server 实施的潜在威胁，并提供了针对中小型公司的示例结构。</span><span class="sxs-lookup"><span data-stu-id="54c86-106">It provides information to help you assess the potential threats to your BizTalk Server implementation, a sample architecture for small and medium-size companies.</span></span>  
  
 <span data-ttu-id="54c86-107">如今，要经营企业而不必考虑安全性是难以实现的。</span><span class="sxs-lookup"><span data-stu-id="54c86-107">It is difficult to run a business today without thinking about security.</span></span> <span data-ttu-id="54c86-108">如果提供在线交易，您会希望保护客户的信用卡信息。</span><span class="sxs-lookup"><span data-stu-id="54c86-108">If you carry out online transactions, you want to protect the credit card information of your customers.</span></span> <span data-ttu-id="54c86-109">如果您为财富 500 强公司工作，您会希望让恶意用户远离您的网络。</span><span class="sxs-lookup"><span data-stu-id="54c86-109">If you work for a Fortune 500 company, you want to keep malicious users away from your networks.</span></span> <span data-ttu-id="54c86-110">如果您是台式计算机用户，您会希望阻止病毒和蠕虫，以免损坏您的数据和妨碍您的正常工作。</span><span class="sxs-lookup"><span data-stu-id="54c86-110">If you are a desktop user, you want to keep viruses and worms from damaging your data and limiting your ability to do your work.</span></span> <span data-ttu-id="54c86-111">几乎每天您都会听到或读到这样的信息：发现新的软件漏洞；发现新的蠕虫和病毒，它们正在快速传播，很难清除，与以前的蠕虫和病毒相比，会造成更大的损害；公司网站被恶意用户破坏等。</span><span class="sxs-lookup"><span data-stu-id="54c86-111">Almost every day you hear or read about new software vulnerabilities; about new worms and viruses that are faster spreading, harder to eradicate, and more damaging than the previous ones; and about the Web sites of companies being defaced by malicious users.</span></span> <span data-ttu-id="54c86-112">不管你的业务有-大或小，少数客户或数以百万计的客户，一台计算机或数百台计算机-你需要破坏数据、 计算机和能够执行你的作业保留恶意用户和程序 （病毒，蠕虫病毒）。</span><span class="sxs-lookup"><span data-stu-id="54c86-112">Whatever your business is—large or small, a few customers or millions of customers, one computer or hundreds of computers—you need to keep malicious users and programs (viruses, worms) from compromising your data, computers, and ability to do your job.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54c86-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="54c86-113">In This Section</span></span>  
  
-   [<span data-ttu-id="54c86-114">安全案例研究： 公司 A</span><span class="sxs-lookup"><span data-stu-id="54c86-114">Security Case Studies: Company A</span></span>](../core/security-case-studies-company-a.md)  
  
-   [<span data-ttu-id="54c86-115">安全案例研究： 公司 B</span><span class="sxs-lookup"><span data-stu-id="54c86-115">Security Case Studies: Company B</span></span>](../core/security-case-studies-company-b.md)  
  
-   [<span data-ttu-id="54c86-116">威胁模型分析</span><span class="sxs-lookup"><span data-stu-id="54c86-116">Threat Model Analysis</span></span>](../core/threat-model-analysis.md)  
  
-   [<span data-ttu-id="54c86-117">对于小型和中型公司示例体系结构</span><span class="sxs-lookup"><span data-stu-id="54c86-117">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)  
  
-   [<span data-ttu-id="54c86-118">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="54c86-118">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)