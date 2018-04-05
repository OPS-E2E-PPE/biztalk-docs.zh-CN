---
title: 对卫生保健系统集成的需求 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- health care organizations
ms.assetid: e747b633-c898-473c-be7d-ba00bfdbdc21
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7674cff1c9c1e787c0ab9638e0abad407adafea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-need-for-health-care-systems-integration"></a>对卫生保健系统集成的需求
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]其应用程序集成和业务流程自动化需要与解决方案提供卫生保健的提供程序。 本主题介绍了一些业务挑战面临的卫生保健的组织，以及如何合并的系统[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]可以帮助克服这些难题这些组织。 此外看一看演示使用示例业务方案中很常见[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]。  
  
## <a name="health-care-business-challenge"></a>卫生保健的业务挑战

卫生保健的组织是通过多个不同的但连接部件的复杂的业务实体。 对于医院，这些部门可以包括许可、 实验室、 护理工作站、 医生和计费。 所有这些部门生成和使用数据。 数据可以包括有关患者、 计费、 过程和药物的信息。 通常情况下，组织需要此数据跨许多其部门。 为卫生保健的组织常见的难题是如何有效地处理部门之间的数据交换。  
  
 下图显示多少部门可能相互之间进行通信，创建复杂的系统。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-no-btahl7.gif "hl7_no_btahl7")  
  
 其中许多这些部门也有不同的业务流程。 部门中的人员可能创建、 实现和维护其自己的过程。 这些进程可能会影响其他部门，但人员可能不具有设计它们与其他部门记住。  
  
 跨组织的完全程度获得更好地控制进程是许多卫生保健的组织的问题。  
  
## <a name="health-care-business-solution"></a>卫生保健的业务解决方案

技术可帮助解决与业务流程和数据相关的业务挑战。 信息技术 (IT) 系统可帮助转换从断开连接、 不兼容的进程，到集成，其内部操作的卫生保健组织标准化的。  
  
### <a name="integration"></a>集成  
 即使卫生保健的组织的独立的部分流程不本质上是兼容，你可以将其集成。 您可以将它们链接以及技术转换系统表征点对点连接 （如图所示卫生保健业务质询 （本主题中） 到一个基于为中心辐射排列下, 图中所示。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-yes-btahl7.gif "hl7_yes_btahl7")  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]通过连接到每个不同的部门或实体，并提供将进程绑定在一起的机制，解决它们之间的差异来实现这种集成。 它还会自动数据交换，以便业务流程可以运行最少的人工干预。  
  
### <a name="standardization"></a>标准化  
 如果已连接业务流程，进程可以交换数据。 但是，如果所维护的单独部门数据位于不同的格式，且系统传输它但不同的数据协议，数据交换可能需要系统设计和自定义项中的大量精力。 如果每个连接的部门标准化格式和协议用于其数据交换，可以极大地提高此过程的效率。  
  
 这是 HL7 组织的用途。 它们已在平面文件架构的形式创建卫生保健的数据，常见的格式。 已成功地，较高百分比的大型医院已采用其标准的点到其工作。  
  
### <a name="solutions-specific-to-the-health-care-industry"></a>特定于卫生保健行业的解决方案  
 集成的 IT 系统和标准化的数据交换提供 foundation 用于更高效的运行状况服务进程。 卫生保健系统一个真正有效 IT 解决方案是指重点放在该行业中的问题并提供功能、 功能和满足卫生保健的组织的需求的工具。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]提供了该解决方案。 你安装[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]之上[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]适用于架构创建和维护由 HL7 组织。 此外，它提供了功能和工具专为卫生保健的应用程序。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]启用批处理时，确认，数据验证、 审核和日志记录所需卫生保健的组织。  
  
## <a name="next"></a>Next
读取[示例业务方案](../../adapters-and-accelerators/accelerator-hl7/sample-business-scenario.md)。
