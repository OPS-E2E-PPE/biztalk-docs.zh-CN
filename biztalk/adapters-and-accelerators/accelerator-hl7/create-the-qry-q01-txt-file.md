---
title: 创建 QRY^Q01.txt 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac96587-264f-4743-a90b-4763d330e320
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e0c3c1667fc0f329f1402ebcd2aba545a007b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251255"
---
# <a name="create-the-qryq01txt-file"></a>创建 QRY^Q01.txt 文件
使用以下过程创建患者查询 QRY^Q01.txt 消息文件。 您将更高版本使用此文件以验证教程的方案。  
  
### <a name="to-create-the-qryq01txt-file"></a>若要创建 QRY^Q01.txt 文件  
  
1. 打开编辑器 （如记事本），并将以下文本复制到编辑器：  
  
   ```  
   MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
   QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
   ```  
  
2. 将该文件作为**QRY^Q01.txt**中\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\ 的快捷键询问教程文件夹，然后再关闭编辑器。  
  
   请继续执行[创建 DSR.txt 文件](../../adapters-and-accelerators/accelerator-hl7/create-the-dsr-txt-file.md)。