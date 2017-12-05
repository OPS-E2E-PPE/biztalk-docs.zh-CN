---
title: "创建 QRY^Q01.txt 文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ac96587-264f-4743-a90b-4763d330e320
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3bc9de81259ba71547e3fb887e91872e9e549c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="create-the-qryq01txt-file"></a>创建 QRY^Q01.txt 文件
使用以下过程创建患者查询 QRY^Q01.txt 消息文件。 你将更高版本使用此文件来验证教程的方案。  
  
### <a name="to-create-the-qryq01txt-file"></a>若要创建 QRY^Q01.txt 文件  
  
1.  打开编辑器，如记事本，并将以下文本复制到编辑器：  
  
    ```  
    MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
    QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
    ```  
  
2.  将文件另存**QRY^Q01.txt**中\<*驱动器*:\>files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键Interrogative 的教程文件夹，然后关闭编辑器。  
  
 继续执行[创建 DSR.txt 文件](../../adapters-and-accelerators/accelerator-hl7/create-the-dsr-txt-file.md)。