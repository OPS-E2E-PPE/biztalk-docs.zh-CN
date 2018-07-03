---
title: HL7 2.4 XML 文件夹和事件 |Microsoft Docs
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
ms.assetid: bc6c5d75-66c7-4269-bfb9-59cab5999a73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7665a5101f5b49abd9ba087bd07cf799384c2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993286"
---
# <a name="hl7-24-xml-folders-and-events"></a>HL7 2.4 XML 文件夹和事件
下表列出了安装程序向导 XML 编码的消息的 HL7 版本 2.4 文件夹中创建的子文件夹。 这些子文件夹中包含所使用的 Microsoft BizTalk Accelerator for HL7 架构 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 若要验证，分析，，和序列化此表的事件列中列出的事件。 子文件夹名称描述的这些架构支持的事件的类型。  
  
|子文件夹|事件|  
|----------------|------------|  
|患者管理|A01 A62、 K21、 K22、 K23、 K24、 Q21 Q24|  
|订单录入|O01 O22、 Q06、 Q26 Q30、 RAR、 RDR、 RER、 RGR、 ROR、 V01 V04、 Z73、 Z74|  
|查询|J01、 J02、 K11、 K13、 K15、 Q01 Q05、 Q07 Q09、 Q11、 Q13、 Q15 Q17、 R07 R09、 Z75 Z99|  
|财务管理|P01 ~ P06、 P10|  
|观察报告|C01 C12、 P07、 P08、 P09、 R01、 R02、 R04、 R21、 W01、 W02|  
|主文件|M01 M12 MFA|  
|医疗记录/信息管理|T01 T12|  
|计划|S01 S26|  
|患者的引用|I01 I15|  
|病人护理|PC1 PCH，PCJ，这是 PCL|  
|临床实验室自动化|U01 U13|  
|应用程序管理|N01 N02|  
|人员管理|B01 B06，K25，Q25|  
  
## <a name="see-also"></a>请参阅  
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)