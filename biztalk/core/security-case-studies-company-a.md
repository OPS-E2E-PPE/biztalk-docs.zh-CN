---
title: 安全性案例研究：公司 A |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 9417ecf9-e340-479f-b120-552c62f3b189
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 213dfa9cb7664b96a867beed944698f71da9bb4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251049"
---
# <a name="security-case-studies-company-a"></a><span data-ttu-id="a5a7f-102">安全性案例研究：公司 A</span><span class="sxs-lookup"><span data-stu-id="a5a7f-102">Security Case Studies: Company A</span></span>
<span data-ttu-id="a5a7f-103">公司 A 是材料和服务迁移到工业扇区的主要供应商。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-103">Company A is a major supplier of material and services to the industrial sector.</span></span> <span data-ttu-id="a5a7f-104">其业务模式依赖于与主要客户和供应商的电子事务。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-104">Its business model relies on electronic transactions with key customers and suppliers.</span></span> <span data-ttu-id="a5a7f-105">公司 A 使用 Microsoft BizTalk 应用程序来管理事务和内部和外部环境之间的通信。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-105">Company A uses Microsoft BizTalk Application to manage transactions and communications between internal and external environments.</span></span>  
  
## <a name="potential-threats-and-security-concerns"></a><span data-ttu-id="a5a7f-106">潜在的威胁和安全问题</span><span class="sxs-lookup"><span data-stu-id="a5a7f-106">Potential Threats and Security Concerns</span></span>  
 <span data-ttu-id="a5a7f-107">公司 A 希望确保它能处理仅来自经过身份验证的源的消息。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-107">Company A wants to make sure that it processes only messages from authenticated sources.</span></span> <span data-ttu-id="a5a7f-108">某些 BizTalk Server 处理的文档可以包含敏感信息，例如财务数据和雇员数据。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-108">Some of the documents BizTalk Server processes can contain sensitive information such as financial and personnel data.</span></span> <span data-ttu-id="a5a7f-109">公司 A 使用自定义加密 Api 来验证每个传入消息。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-109">Company A verifies each incoming message by using custom cryptographic APIs.</span></span> <span data-ttu-id="a5a7f-110">该公司还构建自己的物理结构来处理其安全性需要。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-110">It has also built its physical architecture to handle its security needs.</span></span>  
  
 <span data-ttu-id="a5a7f-111">公司 A 使用文件传输协议 (FTP) 对于某些消息通信。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-111">Company A uses file transfer protocol (FTP) for some of its message traffic.</span></span> <span data-ttu-id="a5a7f-112">尽管 FTP 本质上是不是安全的但公司 A 将接受的风险，因为它有很多防火墙可帮助保护其他对外应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-112">Although FTP is inherently not secure, Company A accepts the associated risks because it has many firewalls to help secure other outward-facing applications.</span></span> <span data-ttu-id="a5a7f-113">由于公司 A 接收某些传入数据通过 HTTPS，因此它被担心拒绝服务 (DoS) 攻击，从外部源。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-113">Because Company A receives some of its incoming data through HTTPS, it is concerned about denial of service (DoS) attacks from external sources.</span></span> <span data-ttu-id="a5a7f-114">如果发生 DoS 攻击，公司有机制立即向相应人员发出警报。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-114">If a DoS attack does occur, the company has mechanisms to alert the appropriate people immediately.</span></span>  
  
## <a name="security-architecture"></a><span data-ttu-id="a5a7f-115">安全体系结构</span><span class="sxs-lookup"><span data-stu-id="a5a7f-115">Security Architecture</span></span>  
 <span data-ttu-id="a5a7f-116">下图显示了公司 A 使用的安全体系结构。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-116">The following figure shows the security architecture that Company A uses.</span></span> <span data-ttu-id="a5a7f-117">请注意，它具有分段其环境使用防火墙，帮助保护其前端应用程序和内容服务器、 其后端数据库和业务逻辑服务器和其传出消息基础结构。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-117">Notice that it has segmented its environment with firewalls to help protect its front-end application and content servers, its back-end database and business logic servers, and its outgoing message infrastructure.</span></span>  
  
 <span data-ttu-id="a5a7f-118">**图 1 公司 A 安全性体系结构**</span><span class="sxs-lookup"><span data-stu-id="a5a7f-118">**Figure 1 Company A security architecture**</span></span>  
  
 <span data-ttu-id="a5a7f-119">![公司的安全体系结构](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span><span class="sxs-lookup"><span data-stu-id="a5a7f-119">![Company A security architecture](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span></span>  
  
 <span data-ttu-id="a5a7f-120">公司 A 具有两种主要方法来发送和接收与 BizTalk Server 的信息。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-120">Company A has two main methods to send and receive information to and from BizTalk Server.</span></span> <span data-ttu-id="a5a7f-121">第一种方法使用 FTP。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-121">The first method uses FTP.</span></span> <span data-ttu-id="a5a7f-122">公司 A 支持电子数据交换 (EDI) 事务通过使用第三方转换服务提供商与供应商和合作伙伴进行通信。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-122">Company A supports electronic data interchange (EDI) transactions by using a third-party translation service provider to communicate with its suppliers and partners.</span></span> <span data-ttu-id="a5a7f-123">此第三方转换服务提供商处理 BizTalk Server 必须处理采用 EDI 格式的传入和传出订单。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-123">This third-party translation service provider handles incoming and outgoing orders that BizTalk Server must process in an EDI format.</span></span>  
  
 <span data-ttu-id="a5a7f-124">公司 A 使用第二种方法是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-124">The second method that Company A uses is HTTPS.</span></span> <span data-ttu-id="a5a7f-125">公司 A 还可与第三方服务提供商可作为其行业中心并使采购和销售的产品公司的销售和变得更容易使用。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-125">Company A also works with a third-party service provider that serves as a hub for its industry and makes the purchase and sale of products Company A sells and consumes easier.</span></span>  
  
## <a name="secure-digital-certificates"></a><span data-ttu-id="a5a7f-126">安全数字证书</span><span class="sxs-lookup"><span data-stu-id="a5a7f-126">Secure Digital Certificates</span></span>  
 <span data-ttu-id="a5a7f-127">公司 A 实施其自己的安全数字证书。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-127">Company A implements its own secure digital certificates.</span></span> <span data-ttu-id="a5a7f-128">它管理仅几个证书。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-128">It manages only a few certificates.</span></span> <span data-ttu-id="a5a7f-129">因为它使用第三方服务提供商，它不太关心数字证书。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-129">Because it uses a third-party service provider, it is less concerned about digital certificates.</span></span> <span data-ttu-id="a5a7f-130">公司 A 认识到数字证书是更加关注服务提供程序，因为服务提供商与很多不同的机构进行交互。</span><span class="sxs-lookup"><span data-stu-id="a5a7f-130">Company A realizes that digital certificates are a greater concern for the service provider, because the service provider interacts with many different institutions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a7f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5a7f-131">See Also</span></span>  
 <span data-ttu-id="a5a7f-132">[小型和中型公司的安全性案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span><span class="sxs-lookup"><span data-stu-id="a5a7f-132">[Security Case Studies for Small & Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span></span>  
 [<span data-ttu-id="a5a7f-133">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="a5a7f-133">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)