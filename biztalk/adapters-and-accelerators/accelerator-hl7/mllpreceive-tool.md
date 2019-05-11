---
title: MllpReceive 工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e2684ef0d2ae7ee678e11f7b03541499b5f4c7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290298"
---
# <a name="mllpreceive-tool"></a>MllpReceive 工具
MllpReceive 工具可用于从 MLLP 发送端口接收数据。  
  
 安装此工具通过[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]自定义安装过程。 如果您执行典型安装中安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装测试工具。 在自定义设置屏幕中，选择**MLLP 测试工具**从**适配器**文件夹，然后选择**测试实例**从**项目**文件夹。 有关详细信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。  
  
 BTAHL7 安装程序将安装在此工具*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用程序。  
  
 使用此工具中的[端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)，则[询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)，则[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)，和[消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). 如果您安装了[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通过默认安装中，且尚未安装和使用的 MLLPTest 工具 （包括 MllpReceive MllpSend），您将不能测试您的教程结果。  
  
## <a name="tool-usage"></a>工具使用情况  
 下面显示了用于调用此命令行工具的语法：  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 下表描述 MllpReceive 工具使用的语法的各个部分。  
  
|语法|含义|  
|------------|-------------|  
|/?|显示此帮助。|  
|/I \<IP\>|表示要侦听的地址。 默认值为所有可用的 Ip。|  
|/P\<端口\>|表示要侦听的端口号。 默认值为 12000。|  
|/D\<目录\>|存储中的目录中的所有已接收的消息\<DIRECTORY\>。 如果未指定\<DIRECTORY\>，默认目录为 %TEMP%。|  
|/SPLIT|将接收到的数据拆分为单独的消息根据分隔符。 SB 和 EB 是必需的。 CR 是可选的。|  
|/ STATICACK|静态确认返回给发件人。 将强制执行拆分模式。|  
|/ HL7ACK|HL7 确认返回给发件人。 文件名指示包含 HL7 确认的文件的名称 将强制执行拆分模式。|  
|/SB|设置开始块分隔符字节的 ASCII 值。 默认值为 none。|  
|/EB|设置结束块分隔符字节的 ASCII 值。 默认值为 none。|  
|/CR|设置回车符返回分隔符字节的 ASCII 值。 默认值为 none。|  
  
## <a name="example-of-tool-use"></a>工具使用的示例  
 可以使用以下命令来侦听端口 10000 上 localhost，并保存消息以便分离 C:\TEMP 上的文件：  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)