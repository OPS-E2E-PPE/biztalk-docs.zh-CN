---
title: 步骤 10： 验证 Interrogative 方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, verifying solution
ms.assetid: 1f28800b-4a1d-4f29-8123-5cdea4b4a365
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b932ab2f179faab1381609c007dcdd148f200f7e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25961243"
---
# <a name="step-10-verify-the-interrogative-scenario"></a>步骤 10： 验证 Interrogative 方案
在此步骤中，你可以出于本教程验证端到端方案。  
  
### <a name="to-send-the-query-message"></a>若要发送查询邮件  
  
1.  開啟命令提示字元。  
  
2.  在命令提示符下，将移到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用工具**。  
  
3.  在命令提示符下键入**MllpReceive/P 24000**，然后按**Enter**。 这运行侦听端口 24000 MLLP 侦听器应用程序，并显示到屏幕接收任何消息。 此应用程序模拟医院信息系统。  
  
4.  打开其他的命令提示符。  
  
5.  在第二个命令提示符窗口中，将移到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\MLLP 实用工具快捷键**.  
  
6.  在第二个命令提示符处，键入**MllpSend /SB 11 /EB 28 /CR 13/双向/P 22000 /F"\<*驱动器*\>: files\microsoft BizTalk\<版本\>快捷键 HL7\SDK\Interrogative Tutorial\QRY^Q01.txt**，然后按**enter 键。**  
  
    > [!NOTE]
    >  此命令将发送到 MLLP 端口 22000 并等待响应 （确认） 本教程开头创建查询电子邮件。 ADT 接收端口选取此消息并处理它。  
  
7.  请验证您具有以下结果：  
  
    -   MLLP 侦听器应用程序应显示一条消息具有以下值：  
  
        ```  
        MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        ```  
  
    -   此外，MllpSend 实用工具可用于创建中的确认文件\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键名为 QRY^Q01.txt.RESPONSE interrogative 教程文件夹。 此文件包含以下信息作为该确认：  
  
        ```  
        MSH|^~\&|HIS||ADT||20040331154031.2222-0800||ACK^Q01^ACK|10000GSM|P|2.4  
        MSA|CA|MSG00001  
        ****END ACK****  
        ```  
  
### <a name="to-send-the-response-message"></a>若要发送响应消息  
  
1.  在命令提示符下运行 MllpReceive 应用程序后，按**CTRL-C**取消以前的操作。  
  
2.  在命令提示符处，键入**MllpReceive/P 25000**，然后按**Enter**。  
  
    > [!NOTE]
    >  步骤 2 运行侦听端口 25000 MLLP 侦听器应用程序，并显示到屏幕收到任何消息。 此应用程序模拟 ADT 系统。  
  
3.  在第二个命令提示符处，键入**MllpSend /SB 11 /EB 28 /CR 13/P 23000 /F"\<*驱动器*\>: files\microsoft BizTalk\<版本\>快捷键HL7\SDK\Interrogative Tutorial\DSR.txt"**，然后按**Enter**。  
  
    > [!NOTE]
    >  步骤 3 将发送到 MLLP 端口 23000 本教程开头创建响应消息。 HIS 接收端口选取此消息并处理它。  
  
4.  请验证您具有以下结果：  
  
    -   MLLP 侦听器应用程序应显示一条消息具有以下值：  
  
        ```  
        MSH|^~\&|HIS||ADT||19990505||DSR^Q01|ZXT23469|P|2.4  
        MSA|AA|MSG00003  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        DSP|||RESULTS FOR PATIENT#12233 SMITH, JOHN H. 07/23/03  
        DSP|||SPECIMEN#H85 COLLECTED 07/22/03 /07/0/0  
        DSP|||ELECTROLYTES  
        DSP||| SODIUM 136 [135-148] MEQ/L STAT  
        DSP||| POTASSIUM 4.2 [3.5-5.0] MEQ/L STAT  
        DSP||| CHLORIDE 91 [95-111] MEQ/L STAT  
        DSP||| CO2 25 [20-30] MEQ/L STAT  
        DSP|||CO2 25 [20-30] MEQ/L STAT|LB  
        ```  
  
    > [!NOTE]
    >  如果未正确出现上述消息，使用运行状况和活动跟踪 (HAT) 工具解决此错误。  
  
 恭喜！ 你已成功完成 BTAHL7 Interrogative 教程。  
  
## <a name="see-also"></a>另请参阅  
 [批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)   
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)