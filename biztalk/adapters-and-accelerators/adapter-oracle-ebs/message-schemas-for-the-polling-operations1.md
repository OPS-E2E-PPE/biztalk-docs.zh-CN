---
title: 轮询 Operations1 的消息架构 |Microsoft 文档
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
ms.openlocfilehash: ee61aa47a7f991c140e0c0659b67da658a11a7ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216141"
---
# <a name="message-schemas-for-the-polling-operations"></a>轮询操作的消息架构
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]面，具体取决于 Oracle E-business Suite 中的目标对象的轮询与相关的各种入站的操作。 接口表、 界面视图、 表和视图，而你可以为 PL/SQL Api、 函数和存储的过程的多个自定义轮询操作显示单个轮询操作。  
  
 通过设置绑定属性配置的轮询操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。 有关这些绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。 你设置**PollingStatement**绑定属性指定 SQL 语句、 存储的过程、 函数或轮询查询的包内的一个过程。 此查询的结果集都会返回作为数据轮询操作中的代码。  
  
## <a name="message-structure-for-the-polling-operations"></a>轮询操作的消息结构  
 下表显示各种轮询操作的 XML 消息结构。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|目标对象|XML 消息|Description|  
|---------------|-------------------|-----------------|-----------------|  
|轮询|界面表<br /><br /> 界面视图<br /><br /> -表<br /><br /> -视图|`<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/[TargetObject]/[Schema]/[TargetObject_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|例如，界面表上的轮询操作的 XML 消息将如下所示：<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <Poll xmlns="[Version]/InterfaceTables/[Schema]/[InterfaceTable_Name]">    <DATA>      <SelectRecord>        <Column1>[Value]</Column1>        <Column2>[Value]</Column2>        …        </SelectRecord>    </DATA> </Poll>`|  
|[CustomPollingOperation]|-PL/SQL Api<br /><br /> -存储过程<br /><br /> 函数|**PL/SQL Api**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingPackageAPis/[Schema]/[PL/SQL API]">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **函数**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **存储过程**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/PollingFunctions/[Schema]">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`|轮询操作中的结果集的结构取决于目标对象中的元素的数据类型。|  
  
 实体说明：  
  
 [Version] = http://schemas.microsoft.com/OracleEBS/2008/05。  
  
 [CustomPollingOperation] = 自定义轮询操作的名称。  
  
 [架构] = Oracle 架构的名称。 例如，SCOTT。  
  
 [PL/SQL API] = 对其执行自定义轮询操作的 PL/SQL api 的名称。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)