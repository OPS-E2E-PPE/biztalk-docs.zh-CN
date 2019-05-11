---
title: 为 BizTalk Server 设计系统体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- security, deploying
ms.assetid: b7ded72a-2487-4bb7-9894-cd13235a52c7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e201f408303ef5a45d512bfbdcafda4c4732a73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351687"
---
# <a name="designing-the-system-architectures-for-biztalk-server"></a>为 BizTalk Server 设计系统体系结构
Microsoft® BizTalk® Server 部署的安全、 性能、 可用性和操作要求都高度依赖于你的业务需求、 要求、 合作伙伴、 公司规模等。 本部分中有关如何配置中的不同 BizTalk Server 功能时很难与典型的 BizTalk Server 组件的单个配置，并提供它的说明性指南，提供指导和建议用于大型企业在生产环境的分布式、 安全配置。  
  
 本部分中介绍的体系结构旨在为您提供有关在其中您考虑到考虑深层防御的高度分布式环境中部署 BizTalk Server 的参考信息。 BizTalk Server 的每个应用程序很可能具有其自己独特的安全要求根据问题领域、 所使用的协议，并在运行特定环境解决方案。 性能、 可用性和成本因素也会进一步影响这些要求。 应使用这些体系结构和本文档中的建议作为构建基块创建您自己根据需求、 威胁和您的公司资产量身定制的 BizTalk Server 部署。  
  
 本部分包含有关如何设计 BizTalk 服务器以便保护 BizTalk Server 中的不同功能的系统体系结构并因此，保护数据的服务器处理和存储，以及如何将放置在服务器的信息分布式的环境中的最小化对关键数据和服务器发生攻击或灾难时遭到入侵的可能性。 本部分中并未提供建议以配置开发或测试环境中或部署到生产环境中的程序集的详细信息。 有关部署程序集的详细信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [设计安全的体系结构](../core/designing-a-secure-architecture.md)  
  
-   [设计分布式体系结构](../core/designing-a-distributed-architecture.md)  
  
-   [示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)