---
title: 如何映射项数据 |Microsoft Docs
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
ms.openlocfilehash: cc3e5c4c4d2ddd4b0051ef5c8b838a0882baa5d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336600"
---
# <a name="how-to-map-item-data"></a>如何映射项数据
映射项数据可以定义从业务流程的数据提取。  
  
> [!NOTE]
>  您必须确保映射的数据类型值创建跟踪配置文件时与活动项兼容的。 如果数据类型不兼容将收到 BAM 运行时错误。  
  
> [!NOTE]
>  在映射里程碑，如日期/时间戳时被映射的数据必须符合日期时间戳的 SQL 字符串表示形式。 按以下方式，YYYY 格式的 XML DateTime 格式的日期时间数据-MM-DDTHH:MM:SS.mmm-hh: mm，不受支持。  
>   
>  例如，以下日期字符串时，1999年-05-31T13:20:00.000-05:00，不受支持。  
  
## <a name="prerequisites"></a>先决条件  
 已部署的 BAM 活动定义和业务流程进行连接。  
  
### <a name="how-to-map-item-data"></a>如何映射项数据  
  
1.  打开现有的跟踪配置文件或创建新的跟踪配置文件。 有关创建跟踪配置文件的详细信息，请参阅[如何创建跟踪配置文件](../core/how-to-create-a-tracking-profile.md)。  
  
2.  在方案中，导入名为 LoanProcessBamDef 的活动定义。 它包含**LoanProcess**活动节点，而且客户**SSN**作为 ActivityID。 有关详细信息，请参阅[活动和 ActivityID 节点](../core/activity-and-activityid-nodes.md)。  
  
3.  请确保每个活动具有 ActivityID 或 ContinuationID 数据项，如客户 SSN 来跟踪。  
  
4.  将业务流程操作映射到相应的业务事件文件夹，以指示要跟踪的事件。例如，在处理贷款的方案中的以下项，等等，会被拖到下**LoanProcess**活动文件夹：  
  
    -   **LoanApplicationReceived**  
  
    -   **CreditHistoryRequest**  
  
    -   **CreditHistoryResponse**  
  
## <a name="see-also"></a>请参阅  
 [数据项节点](../core/data-item-nodes.md)   
 [创建跟踪配置文件](../core/creating-tracking-profiles.md)