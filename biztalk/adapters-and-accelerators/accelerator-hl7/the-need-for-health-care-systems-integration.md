---
title: 对卫生保健系统集成的需求 |Microsoft Docs
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
ms.openlocfilehash: b2527b3174b0497025e070a9228f420a31523f24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972878"
---
# <a name="the-need-for-health-care-systems-integration"></a>对卫生保健系统集成需求
Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]医疗保健提供商提供的解决方案用于其应用程序集成和业务流程自动化需求。 本主题介绍了一些业务挑战面临的医疗保健组织，以及如何将 Microsoft 的系统[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]可帮助组织应对这些挑战。 此外看一看演示一个示例业务方案使用一种常见方案[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]。  
  
## <a name="health-care-business-challenge"></a>卫生保健业务挑战

医疗保健组织将许多不同，但连接部分具有复杂的业务实体。 对于医院，这些部门可以包括许可、 实验室、 护理工作站、 医生和计费。 所有这些部门生成和使用数据。 数据可以包括有关患者、 计费、 过程和药品的信息。 通常情况下，组织需要此数据在许多部门。 医疗机构常见难题是如何有效地处理部门之间的数据交换。  
  
 下图显示了多少部门可能相互通信，创建复杂的系统。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-no-btahl7.gif "hl7_no_btahl7")  
  
 其中许多这些部门也有不同的业务流程。 部门中的人员可能已创建、 实现，并维护其自身的进程。 这些进程可能会影响其他部门，但人员可能不具有设计它们记住的其他部门。  
  
 在组织的完全程度之间获得更好地控制进程是很多医疗保健组织的问题。  
  
## <a name="health-care-business-solution"></a>卫生保健业务解决方案

技术可以帮助解决与业务流程和数据相关的业务挑战。 信息技术 (IT) 系统可以帮助医疗保健组织转换为集成，从断开连接、 不兼容的进程，其内部操作标准化的。  
  
### <a name="integration"></a>集成  
 即使医疗保健组织的不同部分的进程不是本质上是兼容的可以将其集成。 您可以将其转换特征是点对点连接 （如图所示卫生保健业务挑战 （在本主题中） 为一种基于中心辐射型结构，如下图中所示系统技术。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-yes-btahl7.gif "hl7_yes_btahl7")  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 通过将连接到每个单独的部门或实体，并提供将进程绑定在一起的机制，解决存在的差异，从而实现这种集成。 它还可自动执行数据交换，以便业务流程可以运行最少的人工干预。  
  
### <a name="standardization"></a>标准化  
 如果已连接的业务流程，进程可以交换数据。 但是，如果维护单独的部门的数据在不同的格式，而系统传输但不同的数据的协议，数据交换可能需要大量精力进行系统设计和自定义。 如果每个已连接的部门标准化格式并使用与数据交换协议，极大地提高此过程的效率。  
  
 这是 HL7 组织已完成的操作。 他们已在平面文件架构的窗体中创建常用的格式为医疗保健数据。 他们的工作都已非常成功，到较高百分比的大医院已采用其标准的点。  
  
### <a name="solutions-specific-to-the-health-care-industry"></a>特定于卫生保健行业的解决方案  
 集成的 IT 系统和标准的数据交换提供了基础的效率更高的运行状况服务进程。 卫生保健系统的一个真正有效的 IT 解决方案是重点介绍该行业中的问题，并提供功能、 功能和工具可满足的医疗保健组织的需求。  
  
[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 提供了该解决方案。 在安装[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]顶部的[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 适用于架构创建和维护由 HL7 组织。 此外，它还提供功能和工具专为卫生保健应用程序。 [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] 可实现批量处理，确认数据验证、 审核和日志记录所需的医疗保健组织。  
  
## <a name="next"></a>Next
读取[示例业务方案](../../adapters-and-accelerators/accelerator-hl7/sample-business-scenario.md)。
