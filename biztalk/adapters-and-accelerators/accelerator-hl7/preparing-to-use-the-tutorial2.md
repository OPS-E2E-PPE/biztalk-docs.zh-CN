---
title: 准备使用 Tutorial2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, pre-requisites
ms.assetid: 88e6c0b5-5f7d-4fee-a4de-7922cfba917f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b90c23c9b67a25c7f7ef48b0fb51e1a361025b15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290002"
---
# <a name="preparing-to-use-the-tutorial"></a>为使用教程做准备
使用本教程之前，需要创建一个 ADT^A03.txt 文件。  
  
### <a name="to-create-the-adta03txt-file"></a>若要创建 ADT^A03.txt 文件  
  
1. 打开编辑器 （如记事本），并将以下文本复制到编辑器：  
  
   ```  
   MSH|^~\&|Tutorial_ADTSystem|MCM|BTAHL7InterfaceEngine||199601121005||ADT^A03|000001|P|2.3.1  
   EVN|A03|199601121005||01||199601121000  
   PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||  
       123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
   PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|  
      NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P  
      ^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString  
      ^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString  
      ^Test^Test^NormalString^Test|N  
   PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
   ```  
  
   > [!NOTE]
   >  应该有五个行中的.txt 文件，分别与"MSH"、"EVN"、"PID"、"PD1"和"PV1"正在启动。 你将需要删除"PID"行和"PD1"行中的空间。 如有必要，请关闭记事本中的自动换行。  
  
2. 将该文件作为**ADT^A03.txt**中\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator forHL7\SDK\End 端到端教程文件夹，然后关闭记事本。  
  
   请继续执行[步骤 1:创建和部署标头及确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)。