---
title: 如何将映射项数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data extraction
- orchestrations, data extraction
- orchestrations, tracking profiles
- tracking profiles, orchestrations
- tracking profiles, data extraction
ms.assetid: ae8b395e-152a-4e08-af31-3c9276f52711
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdfd722e1610be02c06dd6e2a9597e13c0f1e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253949"
---
# <a name="how-to-map-item-data"></a>如何映射项数据
映射项数据可以定义如何从业务流程中提取数据。  
  
> [!NOTE]
>  在创建跟踪配置文件时，必须确保映射的数据类型值与活动项兼容。 如果数据类型不兼容，将出现 BAM 运行时错误。  
  
> [!NOTE]
>  在映射里程碑（如日期/时间戳）时，被映射的数据必须符合日期时间戳的 SQL 字符串表示形式。 XML DateTime 格式的 DateTime 数据如果采用 YYYY-MM-DDTHH:MM:SS.mmm-HH:MM 格式，则不受支持。  
>   
>  例如，不支持 1999-05-31T13:20:00.000-05:00 日期字符串。  
  
## <a name="prerequisites"></a>先决条件  
 部署要连接的 BAM 活动定义和业务流程。  
  
### <a name="how-to-map-item-data"></a>如何将映射项数据  
  
1.  打开现有的跟踪配置文件，或创建一个新跟踪配置文件。 有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  在这种情况下，将导入一个名为 LoanProcessBamDef 的活动定义。 它包含**LoanProcess**活动节点，与客户的**SSN**作为 ActivityID。 有关详细信息，请参阅[活动和 ActivityID 节点](../core/activity-and-activityid-nodes.md)。  
  
3.  确保每个活动都有一个要跟踪的 ActivityID 或 ContinuationID 数据项，如客户 SSN。  
  
4.  将业务流程操作映射到相应的业务事件文件夹，以指示要跟踪的事件。例如，在贷款处理方案中的以下项，及其他将拖动下**LoanProcess**活动文件夹：  
  
    -   **LoanApplicationReceived**  
  
    -   **CreditHistoryRequest**  
  
    -   **CreditHistoryResponse**  
  
## <a name="see-also"></a>另请参阅  
 [数据项节点](../core/data-item-nodes.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)