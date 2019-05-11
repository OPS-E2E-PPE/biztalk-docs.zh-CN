---
title: 贸易合作伙伴管理使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f31a5e49-ef19-41a3-9cf3-cf85d0685a59
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e78055229a522afcc0af02e5ea4ff0ea66b6189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313339"
---
# <a name="trading-partner-management-using-biztalk-server"></a>使用 BizTalk Server 贸易合作伙伴管理
## <a name="introduction-to-tpm"></a>TPM 简介
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]贸易合作伙伴管理 (TPM) 的重建基本概念围绕如何管理和存储有关合作伙伴及其业务的信息。 增强的 TPM 解决方案反映了业务实体和关系的字段中，从而使组织能够更好地管理与贸易合作伙伴的业务伙伴关系。 TPM 解决方案如何塑造 BizTalk 环境中的贸易伙伴关系的详细信息，请参阅[贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括对电子数据交换 (EDI) 数据交换和 AS2 数据传输的本机支持。 这种支持使得企业可以扩展其基于 EDI 的业务流程管理解决方案，利用 EDI 事务的自动化的交换提供的工作效率改进。 BizTalk Server 提供了这些企业更安全可靠地将合作伙伴连接到关键的供应链业务流程使用 EDI 和 ediint/as2 的手段。  
  
 TPM 解决方案结合了 EDI 和 AS2 支持中管理贸易合作伙伴提供功能强大且可扩展的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此部分中的主题和下面列出，其他主题提供 TPM 和如何使用 TPM 管理贸易合作伙伴的高级概述。 该主题还提供说明如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]执行 EDI 和 AS2 处理。  
  
## <a name="in-this-section-and-more-good-info"></a>在本部分和良好的详细信息

**了解，开始，和教程**  

-   [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)  
  
-   [BizTalk Server EDI 功能](../core/biztalk-server-edi-functionality.md)  
  
-   [BizTalk Server AS2 功能](../core/biztalk-server-as2-functionality.md)  

- [EDI 和 AS2 解决方案体系结构](../core/edi-and-as2-solution-architecture.md)

-   [用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md) 

- [EDI、AS2 和 EDIFACT 的教程和演练](../core/tutorials-and-walkthroughs-for-edi-as2-and-edifact.md)


**在创建 EDI 和 AS2 解决方案的深入探讨**
- [创建 EDI 和 AS2 项目](../core/managing-edi-and-as2-solutions.md)

- [开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)

- [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)

-   [EDI 和 AS2 SDK 示例）](../core/edi-and-as2-biztalk-server-samples-folder.md)  


 **使用绑定文件**  

- [使用绑定文件导入或导出的新 BizTalk Server 2016 中](../core/use-binding-files-to-import-or-export.md)  

-   [如何导出 EDI-AS2 解决方案的绑定](../core/how-to-export-bindings-for-an-edi-as2-solution.md)  
  
-   [如何导入 EDI-AS2 解决方案的绑定](../core/how-to-import-bindings-for-an-edi-as2-solution.md)  
  
-   [自定义绑定文件](../core/customizing-binding-files.md)  


**监视和故障排除**

- [监视 EDI 和 AS2 解决方案](../core/monitoring-edi-and-as2-solutions.md)

- [EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)
  
- 查看 UI 详细信息 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
  
- [EDI 和 AS2 事件和错误](../core/edi-and-as2-events-and-errors.md)
 


  
