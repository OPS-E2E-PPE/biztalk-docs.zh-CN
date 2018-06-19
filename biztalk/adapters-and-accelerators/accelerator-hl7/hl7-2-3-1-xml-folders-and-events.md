---
title: HL7 2.3.1 XML 文件夹和事件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: b3598cc5-46d6-489a-84a7-266ee3c40276
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b25e0563f404d0f8b0600829398729a6c80e65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204317"
---
# <a name="hl7-231-xml-folders-and-events"></a>HL7 2.3.1 XML 文件夹和事件
下表列出由 XML 编码消息的 HL7 版本 2.3.1 文件夹中安装程序向导创建的子文件夹。 这些子文件夹还包含所使用的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，并序列化此表的事件列中列出的事件。 子文件夹名称描述的这些架构支持的事件的类型。  
  
|子文件夹|事件|  
|---------------|------------|  
|患者管理|A01 A51|  
|订单条目|O01、 O02、 Q06、 R0R、 RAR、 RDR、 RER、 RGR、 V01 V04|  
|Query|CNQ，Q01 Q03，Q05，Q07 Q09，R07，R08，R09|  
|财务管理|P01 P06|  
|观察 Reporting|C01 C12、 P06、 P07、 P09、 R01 R06、 W01、 W02|  
|主文件|M01 M11 MFA|  
|医疗记录/信息管理|T01 T12|  
|计划|S01 S26|  
|患者的引用|I01 I15|  
|患者治疗|PC1 PCH，PCJ，PCK PCL|  
|网络管理|N01 N02|  
  
## <a name="see-also"></a>另请参阅  
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)