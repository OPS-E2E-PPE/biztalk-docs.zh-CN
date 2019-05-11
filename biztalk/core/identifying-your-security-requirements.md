---
title: 确定安全要求 |Microsoft Docs
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
ms.openlocfilehash: 80810f6c93102539091076a7b27fb1b4730a3ee0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382828"
---
# <a name="identifying-your-security-requirements"></a>确定安全要求
对以下问题的回答将帮助你规划在环境中部署 BizTalk Server 的最佳方式。  
  
|问题|建议|  
|--------------|--------------------|  
|建议的方法，在安全环境中部署 BizTalk Server 是什么？|此问题的答案取决于你的环境、 您的公司资产、 如何受到的潜在威胁这些资产是和你想要对其进行保护的特定需求。 请务必进行威胁模型分析以了解你想要保护的主要资产。<br /><br /> [大型分布式体系结构](../core/large-distributed-architecture.md)提供有关保护您的 BizTalk Server 环境的建议。 威胁模型分析完成操作后，使用在本部分中的信息来设计您自己的 BizTalk Server 的安全部署。|  
|是否打算使用业务活动监视 (BAM)？|BAM 要求公司网络中的业务用户能够访问 BizTalk Server 资源。 如果使用此功能，有其他一些安全建议请记住，当您设计您的 BizTalk Server 部署。 有关详细信息，请参阅[具有信息工作者服务的大型分布式结构](../core/large-distributed-architecture-with-information-worker-services.md)。|  
|最佳的方式来保护你打算使用的 BizTalk Server 功能是什么？|有关如何帮助保护 BizTalk Server 环境的常规建议，请参阅[BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)。<br /><br /> 有关如何帮助保护不同的 BizTalk Server 功能的建议，请参阅该功能的适当的安全主题。|  
|BizTalk 环境面临的潜在威胁有哪些？|有关详细信息，请参阅[标识的潜在威胁](../core/identifying-potential-threats.md)。|  
|什么是 BizTalk Server 中，您实现的潜在威胁以及如何缓解这些？|若要确定你的环境，以及如何缓解这些问题的潜在威胁，应进行威胁模型分析。 有关威胁模型的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkId=25224 ](http://go.microsoft.com/fwlink/?LinkId=25224)。|  
|如何从拒绝服务攻击保护你的环境？|拒绝服务攻击是最严重的威胁缓解之一。 虽然从这些攻击，不能完全保护您的环境，有一些可以采取的措施来缓解其影响您的环境中。 有关详细信息，请参阅[缓解拒绝的服务攻击](../core/mitigating-denial-of-service-attacks.md)。|  
|您应在 BizTalk 服务的防火墙上打开哪些端口？|有关详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。|  
|为分布式 BizTalk Server 部署，您应该使用什么帐户？|在环境中使用的具体帐户取决于哪些服务时使用，但建议对不同的服务使用不同的组和帐户。 有关详细信息，请参阅[安全分布式 BizTalk Server 部署的 Windows 帐户](../core/windows-accounts-for-a-secure-distributed-biztalk-server-deployment.md)。|  
  
## <a name="see-also"></a>请参阅  
 [规划安全性](../core/planning-for-security.md)   
 [BizTalk Server 部署的安全建议](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [标识潜在威胁](../core/identifying-potential-threats.md)   
 [缓解拒绝服务攻击](../core/mitigating-denial-of-service-attacks.md)