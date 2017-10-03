---
title: "创建和使用业务规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Editor
- Business Rules Editor
ms.assetid: a15fd09b-ff4e-4c26-8cb6-5ffd258a2182
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76a6b51c72f04d5c7918da637f4266567f92e8bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-using-business-rules"></a>创建和使用业务规则
业务规则（或业务策略）定义并控制着组织的结构、运作和策略。 业务规则可能在操作程序手册、合同或协议中正式定义，也可能作为知识或员工所拥有的专门技术存在着。 业务规则是动态的，可能随时间的推移而不断变更，并存在于各种类型的应用程序中。 金融和保险、电子商务、运输、电信、基于 Web 的服务以及个性化只是受业务规则支配的众多业务领域中的几种。 这些业务领域中的每一种都需要将业务战略、策略和规章传递给信息技术 (IT) 人员，以便使之包括在软件应用程序中。  
  
 传统的过程编程语言和面向对象的编程语言，如 C、C++ 和 Microsoft Visual Basic，都是面向程序员的。 即使是面向对象的高级语言，如 Java 和 C#，仍然主要是程序员的语言。 包括设计、开发、编译和测试在内的传统软件开发周期需要大量时间和协调，无法使非程序员参与自动化的业务策略的维护。 业务规则框架提供的开发环境可以迅速创建应用程序，无需像传统应用程序那样经历冗长的编程周期，从而解决了这一问题。 例如，使用此框架构建的业务策略无需重新编译和重新部署相关联的业务流程就可以更新。  
  
 业务规则框架与 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 紧密集成，开发人员可以使用以下功能来构建和管理业务规则：  
  
-   实施干预机制来评价业务规则的高性能规则引擎。  
  
-   用于开发基于规则的应用程序的各种各样的应用程序编程接口 (API)。  
  
-   图形用户界面、业务规则编辑器，开发人员业务分析员和管理员可以通过各种方式来使用它们，以便有效地开发和应用规则和策略。  
  
-   与 BizTalk 业务流程的无缝集成，使您能够从 BizTalk 业务流程调用业务策略或一组业务规则。  
  
-   规则引擎部署向导，使您能够迅速地导入或导出业务规则或规则使用的词汇，以及部署或取消部署这些规则。  
  
 使用业务规则框架创建的业务规则（策略）可以在已编排为业务流程的业务程序中使用，如下图所示。  
  
 ![显示 buisness 策略过程中的图示。] (../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")  
业务策略  
  
 本部分提供有关如何利用业务规则框架和使用的工具的概念性信息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供开发业务规则。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [创建业务规则](../core/creating-business-rules-using-the-business-rule-composer.md)  
  
-   [业务规则 Framework 安全性](../core/business-rules-framework-security.md)  
  
-   [使用业务规则框架编程](../core/programming-with-business-rules-framework.md)  
  
-   [规则引擎配置和优化参数](../core/rule-engine-configuration-and-tuning-parameters.md)