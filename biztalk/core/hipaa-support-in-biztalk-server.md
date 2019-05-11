---
title: BizTalk Server 中的 HIPAA 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1ad8c64-6375-4364-80ce-440db943c222
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d59b485553f2a994dc3dcc47ce14f58a469735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344359"
---
# <a name="hipaa-support-in-biztalk-server"></a>BizTalk Server 中的 HIPAA 支持
本主题提供了 HIPAA 的简要概述以及如何[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]支持 HIPAA。  
  
## <a name="introduction-to-hipaa"></a>HIPAA 简介  
 健康保险流通与责任法案 (HIPAA) 1996年要求涵盖的实体时它们以电子方式执行事务如声明、 汇款、 资格、 声明状态请求和响应，使用强制的标准和其他人。 Hipaa 涵盖的实体是运行状况计划、 交换所和大多数医疗保健提供商。  
  
## <a name="hipaa-support-in-biztalk-server"></a>BizTalk Server 中的 HIPAA 支持  
 Microsoft 还致力于帮助医疗保健和联盟的组织改进医疗保健及进行融资的方法。 Microsoft 致力于减少的时间和金钱，组织必须花费符合 HIPAA 法规。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可帮助组织解决的挑战创建自动化的业务流程的连接，并在不同的医疗保健系统之间进行互操作。 受 HIPAA 影响的组织可以使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的功能，可帮助在开发、 实现和集成符合事务的解决方案同时也符合联邦法律。  
  
[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 包括提供对 HIPAA 的支持的固有功能。 它不是外接程序对产品，例如适配器或加速器。 它是内置于产品。 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 包括 EDI 组件和功能所需同时遵守 HIPAA 要求，并需要将 hipaa 作为管理良好且经过测定的业务流程。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 支持 HIPAA 5010 和 4010 版本。  
  
## <a name="hipaa-documentation-in-biztalk-server"></a>BizTalk Server 中的 HIPAA 文档  
 主要的 EDI 标准包括 X12 （由 ANSI 进行标准化，主要在北美地区） 和 EDIFACT （由联合国进行标准化，主要在美国以外）。 HIPAA 是从 X12 派生的标准。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作为本地 X12 的一部分提供的 HIPAA 支持 EDI 功能。 因此，将出现在支持对 X12 引用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档，这一支持也适用于 HIPAA 处理，除非明确声明。  
  
 中的以下节[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]具有关于 HIPAA 的特定信息。  
  
 **入门**  
  
- [HIPAA 事务集](../core/hipaa-transaction-sets.md)  
  
  **规划和体系结构**  
  
- [HIPAA 文档架构版本 5010](../core/hipaa-document-schema-version-5010.md)  
  
- [HIPAA 架构触发器字段批注](../core/hipaa-schema-trigger-field-annotations.md)  
  
- [拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)  
  
  **开发**  
  
- [修改 EDI 架构](../core/modifying-edi-schemas.md) 

- [在信封架构中自定义枚举](../core/customizing-enumerations-in-the-envelope-schema.md)

- [配置跨字段验证](../core/configuring-cross-field-validation.md)

  
 **故障排除**  
  
-   [EDI 接收处理的已知问题](../core/known-issues-with-edi-receive-processing.md)  
  
-   [XML 工具与 EDI 解决方案一起使用时的已知问题](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)  
  
## <a name="more-information-about-hipaa"></a>有关 HIPAA 的详细信息  
  
-   有关美国国家标准协会，转到的电子数据交换的公认标准委员会[ASC X12 主页](http://www.x12.org/)。  
  
-   有关 HIPAA 采用的指南有关 X12 的保险小组委员会和其实现的信息，请转到[华盛顿发布公司的 HIPAA EDI 指导](http://www.wpc-edi.com/)。
  
-   有关电子数据交换工作组的信息，请转到[电子数据交换主页上的工作组](http://www.wedi.org/)。