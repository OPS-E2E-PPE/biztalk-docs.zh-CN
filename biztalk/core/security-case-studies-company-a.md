---
title: 安全案例研究： 公司 A |Microsoft 文档
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
ms.openlocfilehash: 3c1f48edfc2ab2228d910a0729025fd7b4da117f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269941"
---
# <a name="security-case-studies-company-a"></a><span data-ttu-id="0261e-102">安全性案例研究：公司 A</span><span class="sxs-lookup"><span data-stu-id="0261e-102">Security Case Studies: Company A</span></span>
<span data-ttu-id="0261e-103">公司 A 是为工业区提供物料和服务的主要供应商。</span><span class="sxs-lookup"><span data-stu-id="0261e-103">Company A is a major supplier of material and services to the industrial sector.</span></span> <span data-ttu-id="0261e-104">其业务模式依赖于与主要客户和主要供应商之间的电子事务。</span><span class="sxs-lookup"><span data-stu-id="0261e-104">Its business model relies on electronic transactions with key customers and suppliers.</span></span> <span data-ttu-id="0261e-105">公司 A 使用 Microsoft BizTalk 应用程序来管理内部环境与外部环境之间的事务和通信。</span><span class="sxs-lookup"><span data-stu-id="0261e-105">Company A uses Microsoft BizTalk Application to manage transactions and communications between internal and external environments.</span></span>  
  
## <a name="potential-threats-and-security-concerns"></a><span data-ttu-id="0261e-106">潜在的威胁和安全性问题</span><span class="sxs-lookup"><span data-stu-id="0261e-106">Potential Threats and Security Concerns</span></span>  
 <span data-ttu-id="0261e-107">公司 A 希望确保只处理来自已验证源的消息。</span><span class="sxs-lookup"><span data-stu-id="0261e-107">Company A wants to make sure that it processes only messages from authenticated sources.</span></span> <span data-ttu-id="0261e-108">BizTalk Server 处理的某些文档可包含诸如财务数据和雇员数据之类的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="0261e-108">Some of the documents BizTalk Server processes can contain sensitive information such as financial and personnel data.</span></span> <span data-ttu-id="0261e-109">公司 A 使用自定义的加密 API 来验证每个传入消息。</span><span class="sxs-lookup"><span data-stu-id="0261e-109">Company A verifies each incoming message by using custom cryptographic APIs.</span></span> <span data-ttu-id="0261e-110">该公司还构建了自己的物理结构来处理其安全性需要。</span><span class="sxs-lookup"><span data-stu-id="0261e-110">It has also built its physical architecture to handle its security needs.</span></span>  
  
 <span data-ttu-id="0261e-111">公司 A 使用文件传输协议 (FTP) 来处理该公司的某些消息通信。</span><span class="sxs-lookup"><span data-stu-id="0261e-111">Company A uses file transfer protocol (FTP) for some of its message traffic.</span></span> <span data-ttu-id="0261e-112">尽管 FTP 本质上不安全，但由于公司 A 具有很多防火墙可帮助保护其他对外应用程序，因此该公司接受与 FTP 关联的风险。</span><span class="sxs-lookup"><span data-stu-id="0261e-112">Although FTP is inherently not secure, Company A accepts the associated risks because it has many firewalls to help secure other outward-facing applications.</span></span> <span data-ttu-id="0261e-113">由于公司 A 通过 HTTPS 接收某些传入数据，因此该公司关心来自外部源的拒绝服务 (DoS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="0261e-113">Because Company A receives some of its incoming data through HTTPS, it is concerned about denial of service (DoS) attacks from external sources.</span></span> <span data-ttu-id="0261e-114">如果发生 DoS 攻击，公司具有相应机制可立即向相关人员发出警报。</span><span class="sxs-lookup"><span data-stu-id="0261e-114">If a DoS attack does occur, the company has mechanisms to alert the appropriate people immediately.</span></span>  
  
## <a name="security-architecture"></a><span data-ttu-id="0261e-115">安全体系结构</span><span class="sxs-lookup"><span data-stu-id="0261e-115">Security Architecture</span></span>  
 <span data-ttu-id="0261e-116">下图显示了公司 A 使用的安全性结构。</span><span class="sxs-lookup"><span data-stu-id="0261e-116">The following figure shows the security architecture that Company A uses.</span></span> <span data-ttu-id="0261e-117">请注意，该公司已使用防火墙对其环境进行分段，以便有助于保护其前端应用程序和内容服务器、其后端数据库和业务逻辑服务器以及其传出消息基础结构。</span><span class="sxs-lookup"><span data-stu-id="0261e-117">Notice that it has segmented its environment with firewalls to help protect its front-end application and content servers, its back-end database and business logic servers, and its outgoing message infrastructure.</span></span>  
  
 <span data-ttu-id="0261e-118">**图 1 公司的安全体系结构**</span><span class="sxs-lookup"><span data-stu-id="0261e-118">**Figure 1 Company A security architecture**</span></span>  
  
 <span data-ttu-id="0261e-119">![公司的安全体系结构](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span><span class="sxs-lookup"><span data-stu-id="0261e-119">![Company A security architecture](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")</span></span>  
  
 <span data-ttu-id="0261e-120">公司 A 采用两种主要方法与 BizTalk Server 之间收发信息。</span><span class="sxs-lookup"><span data-stu-id="0261e-120">Company A has two main methods to send and receive information to and from BizTalk Server.</span></span> <span data-ttu-id="0261e-121">第一种方法使用 FTP。</span><span class="sxs-lookup"><span data-stu-id="0261e-121">The first method uses FTP.</span></span> <span data-ttu-id="0261e-122">通过使用第三方转换服务提供商来与其供应商和合作伙伴进行通信，公司 A 支持电子数据交换 (EDI) 事务。</span><span class="sxs-lookup"><span data-stu-id="0261e-122">Company A supports electronic data interchange (EDI) transactions by using a third-party translation service provider to communicate with its suppliers and partners.</span></span> <span data-ttu-id="0261e-123">此第三方转换服务提供商以 EDI 格式处理 BizTalk Server 必须处理的传入和传出订单。</span><span class="sxs-lookup"><span data-stu-id="0261e-123">This third-party translation service provider handles incoming and outgoing orders that BizTalk Server must process in an EDI format.</span></span>  
  
 <span data-ttu-id="0261e-124">公司 A 使用的第二种方法是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="0261e-124">The second method that Company A uses is HTTPS.</span></span> <span data-ttu-id="0261e-125">公司 A 还使用作为其行业中心的第三方服务提供商，并且使该公司销售和消耗的产品更易于采购和销售。</span><span class="sxs-lookup"><span data-stu-id="0261e-125">Company A also works with a third-party service provider that serves as a hub for its industry and makes the purchase and sale of products Company A sells and consumes easier.</span></span>  
  
## <a name="secure-digital-certificates"></a><span data-ttu-id="0261e-126">安全数字证书</span><span class="sxs-lookup"><span data-stu-id="0261e-126">Secure Digital Certificates</span></span>  
 <span data-ttu-id="0261e-127">公司 A 实施其自己的安全数字证书。</span><span class="sxs-lookup"><span data-stu-id="0261e-127">Company A implements its own secure digital certificates.</span></span> <span data-ttu-id="0261e-128">该公司只管理几个证书。</span><span class="sxs-lookup"><span data-stu-id="0261e-128">It manages only a few certificates.</span></span> <span data-ttu-id="0261e-129">由于该公司使用第三方服务提供商，因此不太关心数字证书。</span><span class="sxs-lookup"><span data-stu-id="0261e-129">Because it uses a third-party service provider, it is less concerned about digital certificates.</span></span> <span data-ttu-id="0261e-130">公司 A 认识到数字证书是服务提供商应考虑的重要因素，因为服务提供商将与很多不同的机构进行交互。</span><span class="sxs-lookup"><span data-stu-id="0261e-130">Company A realizes that digital certificates are a greater concern for the service provider, because the service provider interacts with many different institutions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0261e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0261e-131">See Also</span></span>  
 <span data-ttu-id="0261e-132">[对于小型和中型公司的安全案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span><span class="sxs-lookup"><span data-stu-id="0261e-132">[Security Case Studies for Small & Medium-Sized Companies](../core/security-case-studies-for-small-to-medium-sized-companies.md)  </span></span>  
 [<span data-ttu-id="0261e-133">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="0261e-133">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)