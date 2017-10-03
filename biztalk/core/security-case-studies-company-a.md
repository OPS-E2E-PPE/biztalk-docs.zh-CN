---
title: "安全案例研究： 公司 A |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, examples
- security, architecture
- architecture, security
- security, case studies
ms.assetid: 9417ecf9-e340-479f-b120-552c62f3b189
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1f48edfc2ab2228d910a0729025fd7b4da117f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-case-studies-company-a"></a>安全性案例研究：公司 A
公司 A 是为工业区提供物料和服务的主要供应商。 其业务模式依赖于与主要客户和主要供应商之间的电子事务。 公司 A 使用 Microsoft BizTalk 应用程序来管理内部环境与外部环境之间的事务和通信。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的威胁和安全性问题  
 公司 A 希望确保只处理来自已验证源的消息。 BizTalk Server 处理的某些文档可包含诸如财务数据和雇员数据之类的敏感信息。 公司 A 使用自定义的加密 API 来验证每个传入消息。 该公司还构建了自己的物理结构来处理其安全性需要。  
  
 公司 A 使用文件传输协议 (FTP) 来处理该公司的某些消息通信。 尽管 FTP 本质上不安全，但由于公司 A 具有很多防火墙可帮助保护其他对外应用程序，因此该公司接受与 FTP 关联的风险。 由于公司 A 通过 HTTPS 接收某些传入数据，因此该公司关心来自外部源的拒绝服务 (DoS) 攻击。 如果发生 DoS 攻击，公司具有相应机制可立即向相关人员发出警报。  
  
## <a name="security-architecture"></a>安全体系结构  
 下图显示了公司 A 使用的安全性结构。 请注意，该公司已使用防火墙对其环境进行分段，以便有助于保护其前端应用程序和内容服务器、其后端数据库和业务逻辑服务器以及其传出消息基础结构。  
  
 **图 1 公司的安全体系结构**  
  
 ![公司的安全体系结构](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")  
  
 公司 A 采用两种主要方法与 BizTalk Server 之间收发信息。 第一种方法使用 FTP。 通过使用第三方转换服务提供商来与其供应商和合作伙伴进行通信，公司 A 支持电子数据交换 (EDI) 事务。 此第三方转换服务提供商以 EDI 格式处理 BizTalk Server 必须处理的传入和传出订单。  
  
 公司 A 使用的第二种方法是 HTTPS。 公司 A 还使用作为其行业中心的第三方服务提供商，并且使该公司销售和消耗的产品更易于采购和销售。  
  
## <a name="secure-digital-certificates"></a>安全数字证书  
 公司 A 实施其自己的安全数字证书。 该公司只管理几个证书。 由于该公司使用第三方服务提供商，因此不太关心数字证书。 公司 A 认识到数字证书是服务提供商应考虑的重要因素，因为服务提供商将与很多不同的机构进行交互。  
  
## <a name="see-also"></a>另请参阅  
 [对于小型和中型公司的安全案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)    
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)