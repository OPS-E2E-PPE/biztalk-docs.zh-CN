---
title: HL7 2.3.1 XML 文件夹和事件 |Microsoft Docs
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
ms.openlocfilehash: 6bbe1d472f844d57c7770ec4ae425fc6aef44a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991726"
---
# <a name="hl7-231-xml-folders-and-events"></a>HL7 2.3.1 XML 文件夹和事件
下表列出了安装程序向导 XML 编码的消息的 HL7 2.3.1 文件夹中创建的子文件夹。 这些子文件夹中包含所使用的 Microsoft BizTalk Accelerator for HL7 架构 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，，和序列化此表的事件列中列出的事件。 子文件夹名称描述的这些架构支持的事件的类型。  
  
|子文件夹|事件|  
|---------------|------------|  
|患者管理|A01 A51|  
|订单录入|O01、 O02、 Q06、 R0R、 RAR、 RDR、 RER、 RGR、 V01 V04|  
|查询|CNQ，Q01-Q03 Q05，Q07-Q09 R07，R08，R09|  
|财务管理|P01 P06|  
|观察报告|C01 C12、 P06、 P07、 P09、 R01 R06、 W01、 W02|  
|主文件|M01 M11 MFA|  
|医疗记录/信息管理|T01 T12|  
|“计划”|S01 S26|  
|患者的引用|I01 I15|  
|病人护理|PC1 PCH，PCJ，这是 PCL|  
|网络管理|N01 N02|  
  
## <a name="see-also"></a>请参阅  
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)