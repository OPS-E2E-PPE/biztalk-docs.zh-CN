---
title: EDI 发送组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9afcc401b800fab7b549ac9bc4c53ae7502b8caa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350276"
---
# <a name="edi-send-components"></a>EDI 发送组件
管道和 EDI/AS2 消息不是此主题处理 EDI 消息中所述的管道组件。 有关发送 EDI/AS2 或 EDI/AS2 消息的信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。 请注意，AS2 发送组件还执行 EDI 处理除 AS2 处理。  
  
## <a name="edi-send-pipeline"></a>EDI 发送管道  
 EDI 发送处理工作都在下列 EDISend 管道。 此管道安装在`Microsoft.BizTalk.Edi.EdiPipelines.dll`在[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]。  
  
 **EDISend 管道**  
  
 此管道生成和发送 EDI 消息。 它不会处理通过 HTTP 接收 AS2 编码的 EDI 消息。 通过 AS2 管道执行 AS2 编码的 EDI 消息的处理。 AS2 发送管道使用相同的组件来处理和 EDI 管道使用 EDI 消息。  
  
> [!NOTE]
>  不支持从业务流程中运行 EDISend 管道。  
  
> [!NOTE]
>  AS2EDISend 管道生成，并通过 AS2 传输发送 EDI 消息。 有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。  
  
 管道由 EDI 组装器管道组件组成：  
  
## <a name="edi-send-pipeline-component"></a>EDI 发送管道组件  
 EDISend 管道使用 EDI 组装器管道组件。 此组件安装在`Microsoft.BizTalk.Edi.PipelineComponents.dll`中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]管道组件\\。  
  
 EDI 组装器 EDISend 管道中执行的大多数处理 EDI 编码的交换。 有关 EDI 组装器如何处理 EDI 消息的信息，请参阅[EDI 组装器的工作原理](../core/how-the-edi-assembler-works.md)。