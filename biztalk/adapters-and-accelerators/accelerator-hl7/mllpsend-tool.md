---
title: MllpSend 工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MllpSend tool
- MLLP-encoded messages, receive adapters
- MLLP-encoded messages, MllpSend tool
ms.assetid: b1723d52-4909-4543-8215-4f73802b6c4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f86f814710f48aa0c8795e00bcf5c2f9be8e1a14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290195"
---
# <a name="mllpsend-tool"></a>MllpSend 工具
MllpSend 工具可用于发送数据到 MLLP 接收位置。  
  
 安装此工具通过[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]自定义安装过程。 如果您执行典型安装中安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装测试工具。 在自定义设置屏幕中，选择**MLLP 测试工具**从**适配器**文件夹，然后选择**测试实例**从**项目**文件夹。 有关详细信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。  
  
 BTAHL7 安装程序将安装在此工具*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用程序。  
  
 使用此工具中的[端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)，则[询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)，则[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)，和[消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). 如果您安装了[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通过默认安装中，且尚未安装将无法测试您的教程结果 MLLP Testtools （包括 MllpSend 和 MllpReceive）。  
  
## <a name="tool-usage"></a>工具使用情况  
 下面显示了用于调用此命令行工具的语法：  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 下表描述 MllpSend 工具使用的语法的各个部分。  
  
|语法|Description|  
|------------|-----------------|  
|**/?**|在命令提示符窗口中显示的帮助。|  
|**/I \<IP\>**|表示要发送到的地址。 默认值为 localhost。|  
|**/P \<PORT\>**|表示要发送到的端口号。 默认值是**11000**。|  
|**/F**|将文件名的文件的内容发送。|  
|**/ 重复\<n\>**|将同一消息发送*n*时间。 包装器字符将应用到每条消息。|  
|**/TWOWAY**|发件人将等待来自接收方的响应。 SB 和 EB 需要指定。 CR 是可选的。 在文件模式下，响应存储在文件的文件。响应。|  
|**/SB**|设置开始块分隔符字节的 ASCII 值。 默认值为 none。|  
|**/EB**|设置结束块分隔符字节的 ASCII 值。 默认值为 none。|  
|**/CR**|设置回车符返回分隔符字节的 ASCII 值。 默认值为 none。|  
  
## <a name="examples-of-tool-use"></a>工具使用的示例  
 以下示例演示如何使用 MllpSend 工具。  
  
 **示例 1。** 可以使用以下命令以将消息发送到单向适配器在服务器 myserver 上 13000 端口上侦听。 SB 11、 EB 28 和 CR 13，包装器字符的 ASCII 值。  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 **示例 2。** 可以使用以下命令以将消息发送到服务器"localhost"上 11000 端口上侦听的双向适配器 100 倍。 SB 11、 EB 28 和 CR 13，包装器字符的 ASCII 值。  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)