---
title: 确定安全要求 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, configuring
- planning, security
- security, planning
ms.assetid: 5a12c959-59b5-4d44-b2f4-e1ed7053ffd5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea9b21cfdfe722d80779dcf9098355b9a5ae3727
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257629"
---
# <a name="identifying-your-security-requirements"></a>确定安全要求
您可以利用以下问题的回答来帮助规划在环境中部署 BizTalk Server 的最佳方式：  
  
|问题|建议|  
|--------------|--------------------|  
|在安全环境中部署 BizTalk Server 的建议方式是什么？|此问题的回答实际上取决于您的环境的特定需求、您的公司资产、这些资产受到的潜在威胁程度，以及您希望采取的保护方式。 若要了解需保护的主要资产，进行威胁模型分析是非常必要的。<br /><br /> [大型分布式体系结构](../core/large-distributed-architecture.md)提供保护您的 BizTalk Server 环境的建议。 在进行威胁模型分析之后，您可以运用本部分中的信息来设计自己的安全部署 BizTalk Server 的方式。|  
|是否计划使用业务活动监视 (BAM)？|BAM 要求公司网络中的业务用户能够访问 BizTalk Server 资源。 如果您使用此功能，那么，在设计自己的 BizTalk Server 部署方式时还必须牢记其他一些安全建议。 有关详细信息，请参阅[大型分布式体系结构与信息辅助服务](../core/large-distributed-architecture-with-information-worker-services.md)。|  
|如何确保计划使用的 BizTalk Server 功能的安全？|有关如何帮助保护 BizTalk Server 环境的常规建议，请参阅[BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)。<br /><br /> 有关如何保证 BizTalk Server 其他功能的安全的建议，请参阅该功能的相应安全主题。|  
|BizTalk 环境面临的潜在威胁有哪些？|有关详细信息，请参阅[标识潜在威胁](../core/identifying-potential-threats.md)。|  
|BizTalk Server 实施的潜在威胁有哪些？如何缓解这些潜在威胁？|若要确定您的环境所面临的潜在威胁以及缓解这些威胁的措施，则应进行威胁模型分析。 有关威胁建模的详细信息，请参阅 Microsoft MSDN 网站在[http://go.microsoft.com/fwlink/?LinkId=25224](http://go.microsoft.com/fwlink/?LinkId=25224)。|  
|如何防止环境遭到拒绝服务的攻击？|拒绝服务攻击是必须要缓解的最严重威胁之一。 尽管您无法完全防止您的环境遭到这些攻击，但您可以采取一些措施来减轻它们对环境的影响。 有关详细信息，请参阅[减少拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。|  
|应该为 BizTalk 服务打开防火墙上的哪些端口？|有关详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。|  
|应为分布式 BizTalk Server 部署使用哪些帐户？|尽管在您的环境中使用的具体帐户取决于所使用的服务，但是我们仍建议您对不同的服务使用不同的组和帐户。 有关详细信息，请参阅[安全分布式 BizTalk Server 部署的 Windows 帐户](../core/windows-accounts-for-a-secure-distributed-biztalk-server-deployment.md)。|  
  
## <a name="see-also"></a>另请参阅  
 [规划安全性](../core/planning-for-security.md)   
 [BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [识别潜在的威胁](../core/identifying-potential-threats.md)   
 [减少拒绝服务攻击](../core/mitigating-denial-of-service-attacks.md)