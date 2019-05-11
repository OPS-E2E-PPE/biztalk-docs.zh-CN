---
title: 处理阶段数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3db73745d137486011c2b56031f64b41f59f8639
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323531"
---
# <a name="number-of-processing-stages"></a>处理阶段的数目
该解决方案，以便可以无需中断长时间运行的订单 （通过替换阶段） 修改该过程可分为若干阶段，将订单流程。 有关如何在过程已分为若干阶段的详细信息，请参阅"划分业务流程"中[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。  
  
 该解决方案的当前版本包含只有两个处理阶段。 但是，它可以包含更多。 多个阶段提供更多点可以版本进程并处理阶段的最新版本上继续工作。 但是，每个阶段都引起了额外的消息进行协调通过 MessageBox 数据库，这会增加处理时间的开销。 必须监视解决方案的性能，以确定多个阶段数是否过多。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [进程管理器逻辑](../core/process-manager-logic.md)