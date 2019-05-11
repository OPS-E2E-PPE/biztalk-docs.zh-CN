---
title: 消息架构的轮询 Operations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c572c4ec-0a3f-42b8-bebd-40eb584438ad
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0475c94ef6838e02e4f81f27df7ee9b2df70bfc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375994"
---
# <a name="message-schemas-for-the-polling-operations"></a>轮询操作的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]轮询，具体取决于 Oracle E-business Suite 中的目标对象与相关的各种入站的操作的图面。 界面表、 界面视图、 表和视图，而可以具有的 PL/SQL Api、 函数和存储的过程的多个自定义轮询操作显示一次轮询操作。  
  
 通过设置绑定属性来配置轮询操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关这些绑定属性的详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 您设置**PollingStatement**绑定属性来指定 SQL 语句、 存储的过程、 函数或轮询查询的包中的过程。 此查询的结果集作为数据返回到轮询操作中的代码。  
  
## <a name="message-structure-for-the-polling-operations"></a>轮询操作的消息结构  
 下表显示了各种轮询操作的 XML 消息结构。  
  
> [!NOTE]
>  实体说明表后进行查看。  
  
|操作|目标对象|XML 消息|Description|  
|---------------|-------------------|-----------------|-----------------|  
|轮询|-接口表<br /><br /> 界面视图<br /><br /> -表<br /><br /> 视图|`<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/[TargetObject]/[Schema]/[TargetObject_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|例如，接口表上的轮询操作的 XML 消息将如下所示：<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/InterfaceTables/[Schema]/[InterfaceTable_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|  
|[CustomPollingOperation]|-PL/SQL Api<br /><br /> -存储过程<br /><br /> -函数|**PL/SQL Api**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingPackageAPis/[Schema]/[PL/SQL API]">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **函数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **存储过程**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`|轮询操作中的结果集的结构取决于目标对象中的元素的数据类型。|  
  
 实体说明：  
  
 [Version] = http://schemas.microsoft.com/OracleEBS/2008/05。  
  
 [CustomPollingOperation] = 自定义轮询操作的名称。  
  
 [架构] = Oracle 架构的名称。 例如，SCOTT。  
  
 [PL/SQL API] = PL/SQL API 对其执行自定义轮询操作的名称。  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)