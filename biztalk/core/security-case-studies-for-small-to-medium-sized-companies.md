---
title: 对于小型到中型公司的安全性案例研究 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
- security, examples
- security, architecture
- architecture, medium distributions
ms.assetid: b33e3f2a-ddc4-47a8-92d7-511ae0cc880e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738a36f096155ac89cf0c01258d69a3704048066
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251076"
---
# <a name="security-case-studies-for-small-to-medium-sized-companies"></a><span data-ttu-id="45508-102">对于小型到中型公司的安全性案例研究</span><span class="sxs-lookup"><span data-stu-id="45508-102">Security Case Studies for Small to Medium-Sized Companies</span></span>
<span data-ttu-id="45508-103">安全是所有公司重视确保仅选择的一组人员或应用程序可以访问其数据和资源的一个问题。</span><span class="sxs-lookup"><span data-stu-id="45508-103">Security is a concern of any company that is serious about making sure that only a select group of people or applications can access its data and resources.</span></span> <span data-ttu-id="45508-104">公司处理和在不同的方式实现安全性。</span><span class="sxs-lookup"><span data-stu-id="45508-104">Companies approach and implement security in a variety of ways.</span></span>  
  
 <span data-ttu-id="45508-105">此部分提供了部署 Microsoft 的指导原则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在安全环境中。</span><span class="sxs-lookup"><span data-stu-id="45508-105">This section provides guidelines for deploying Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a secure environment.</span></span> <span data-ttu-id="45508-106">它提供信息来帮助您评估您的 BizTalk Server 实现，用于小型和中型公司的示例体系结构的潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="45508-106">It provides information to help you assess the potential threats to your BizTalk Server implementation, a sample architecture for small and medium-size companies.</span></span>  
  
 <span data-ttu-id="45508-107">很难运行业务今天而不必考虑安全性。</span><span class="sxs-lookup"><span data-stu-id="45508-107">It is difficult to run a business today without thinking about security.</span></span> <span data-ttu-id="45508-108">如果您提供在线交易，您想要保护你的客户的信用卡信息。</span><span class="sxs-lookup"><span data-stu-id="45508-108">If you carry out online transactions, you want to protect the credit card information of your customers.</span></span> <span data-ttu-id="45508-109">如果您为财富 500 强公司工作，你想要让恶意用户远离您的网络。</span><span class="sxs-lookup"><span data-stu-id="45508-109">If you work for a Fortune 500 company, you want to keep malicious users away from your networks.</span></span> <span data-ttu-id="45508-110">如果你是桌面的用户，你想要防止损坏您的数据和妨碍来完成工作的病毒和蠕虫。</span><span class="sxs-lookup"><span data-stu-id="45508-110">If you are a desktop user, you want to keep viruses and worms from damaging your data and limiting your ability to do your work.</span></span> <span data-ttu-id="45508-111">几乎每天您都会听到或阅读有关新的软件漏洞;有关新蠕虫和病毒的速度提高分布，更难彻底，和更多具有破坏力比前面的;和有关公司的网站： 被恶意用户。</span><span class="sxs-lookup"><span data-stu-id="45508-111">Almost every day you hear or read about new software vulnerabilities; about new worms and viruses that are faster spreading, harder to eradicate, and more damaging than the previous ones; and about the Web sites of companies being defaced by malicious users.</span></span> <span data-ttu-id="45508-112">无论是您的业务-大或小，几个客户还是数百万客户、 一台计算机或数百台计算机 — 您需要阻止恶意用户及程序 （病毒、 蠕虫） 破坏数据、 计算机和您的工作的能力。</span><span class="sxs-lookup"><span data-stu-id="45508-112">Whatever your business is—large or small, a few customers or millions of customers, one computer or hundreds of computers—you need to keep malicious users and programs (viruses, worms) from compromising your data, computers, and ability to do your job.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45508-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="45508-113">In This Section</span></span>  
  
-   [<span data-ttu-id="45508-114">安全性案例研究：公司 A</span><span class="sxs-lookup"><span data-stu-id="45508-114">Security Case Studies: Company A</span></span>](../core/security-case-studies-company-a.md)  
  
-   [<span data-ttu-id="45508-115">安全性案例研究：公司 B</span><span class="sxs-lookup"><span data-stu-id="45508-115">Security Case Studies: Company B</span></span>](../core/security-case-studies-company-b.md)  
  
-   [<span data-ttu-id="45508-116">威胁模型分析</span><span class="sxs-lookup"><span data-stu-id="45508-116">Threat Model Analysis</span></span>](../core/threat-model-analysis.md)  
  
-   [<span data-ttu-id="45508-117">中小型公司的示例体系结构</span><span class="sxs-lookup"><span data-stu-id="45508-117">Sample Architectures for Small & Medium-Sized Companies</span></span>](../core/sample-architectures-for-small-medium-sized-companies.md)  
  
-   [<span data-ttu-id="45508-118">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="45508-118">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)