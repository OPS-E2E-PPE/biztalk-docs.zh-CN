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
# <a name="security-case-studies-company-a"></a>安全性案例研究：公司 A
公司 A 是材料和服务迁移到工业扇区的主要供应商。 其业务模式依赖于与主要客户和供应商的电子事务。 公司 A 使用 Microsoft BizTalk 应用程序来管理事务和内部和外部环境之间的通信。  
  
## <a name="potential-threats-and-security-concerns"></a>潜在的威胁和安全问题  
 公司 A 希望确保它能处理仅来自经过身份验证的源的消息。 某些 BizTalk Server 处理的文档可以包含敏感信息，例如财务数据和雇员数据。 公司 A 使用自定义加密 Api 来验证每个传入消息。 该公司还构建自己的物理结构来处理其安全性需要。  
  
 公司 A 使用文件传输协议 (FTP) 对于某些消息通信。 尽管 FTP 本质上是不是安全的但公司 A 将接受的风险，因为它有很多防火墙可帮助保护其他对外应用程序。 由于公司 A 接收某些传入数据通过 HTTPS，因此它被担心拒绝服务 (DoS) 攻击，从外部源。 如果发生 DoS 攻击，公司有机制立即向相应人员发出警报。  
  
## <a name="security-architecture"></a>安全体系结构  
 下图显示了公司 A 使用的安全体系结构。 请注意，它具有分段其环境使用防火墙，帮助保护其前端应用程序和内容服务器、 其后端数据库和业务逻辑服务器和其传出消息基础结构。  
  
 **图 1 公司 A 安全性体系结构**  
  
 ![公司的安全体系结构](../core/media/airproductsbiztalkinfrastructure.gif "AirProductsBizTalkInfrastructure")  
  
 公司 A 具有两种主要方法来发送和接收与 BizTalk Server 的信息。 第一种方法使用 FTP。 公司 A 支持电子数据交换 (EDI) 事务通过使用第三方转换服务提供商与供应商和合作伙伴进行通信。 此第三方转换服务提供商处理 BizTalk Server 必须处理采用 EDI 格式的传入和传出订单。  
  
 公司 A 使用第二种方法是 HTTPS。 公司 A 还可与第三方服务提供商可作为其行业中心并使采购和销售的产品公司的销售和变得更容易使用。  
  
## <a name="secure-digital-certificates"></a>安全数字证书  
 公司 A 实施其自己的安全数字证书。 它管理仅几个证书。 因为它使用第三方服务提供商，它不太关心数字证书。 公司 A 认识到数字证书是更加关注服务提供程序，因为服务提供商与很多不同的机构进行交互。  
  
## <a name="see-also"></a>请参阅  
 [小型和中型公司的安全性案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)    
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)