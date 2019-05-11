---
title: 发送管道发送保留的批与 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ea7a208942895c11a633fa0a67ae583952db0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399049"
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a>发送保留的批使用 XML 发送管道
通常，使用 EDI 发送管道发送保留批。 但是，也可以使用 XML 发送管道发送保留批。 因为由 EDI 接收管道生成并放置在 MessageBox 中的保留批是 XML 格式的，XML 发送管道将以 XML 格式传递批。  
  
 若要使用 XML 发送管道发送保留批，必须部署一个项目，同时为交换中的每种消息类型设置适用的批架构和文档架构。 此外，还必须更改要在项目中部署的批架构的命名空间。 如果不这样做，保留批 XML 文件中的命名空间将与批架构的命名空间不相符。 您必须按照下表所示，更改批架构的命名空间：  
  
|对于此编码类型：|更改批架构中的此命名空间：|更改为以下命名空间：|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|EDIFACT|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|X12|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 对于 EDI 组装器不存在此问题。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 批](../core/configuring-edi-batches.md)