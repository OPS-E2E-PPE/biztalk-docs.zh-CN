---
title: MllpSend 工具 |Microsoft 文档
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
ms.openlocfilehash: ed9b666b019fe7dc415f28c0dd01522b728b149c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960723"
---
# <a name="mllpsend-tool"></a>MllpSend 工具
MllpSend 工具可用于发送数据到 MLLP 接收位置。  
  
 在安装此工具通过[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]自定义安装过程。 如果执行典型的安装，以安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装的测试工具。 在自定义安装屏幕中，选择**MLLP 测试工具**从**适配器**文件夹，并选择**测试实例**从**项目**文件夹。 有关详细信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。  
  
 BTAHL7 安装程序将安装在此工具*\<驱动器\>*: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用程序。  
  
 使用此工具中的[端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)，和[消息扩充教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). 如果你安装[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通过默认安装中，且不安装你将不能测试您的教程结果 MLLP Testtools （包括 MllpSend 和 MllpReceive）。  
  
## <a name="tool-usage"></a>工具使用情况  
 下面演示使用来调用此命令行工具的语法：  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 下表介绍每个部分的 MllpSend 工具使用的语法。  
  
|语法|Description|  
|------------|-----------------|  
|**/?**|在命令提示符窗口中显示帮助。|  
|**/I \<IP\>**|表示要将发送到的地址。 默认值为 localhost。|  
|**/ P\<端口\>**|表示要将发送到的端口号。 默认值是**11000**。|  
|**/F**|将发送文件 FILENAME 的内容。|  
|**/ 重复\<n\>**|将发送同一消息*n*时间。 包装字符将应用到每条消息。|  
|**/ 双向**|发件人将等待来自接收方的响应。 SB 和 EB 需要指定。 CR 是可选的。 在文件模式下，响应存储在文件的文件。响应。|  
|**/SB**|设置启动块分隔符字节的 ASCII 值。 默认值为 none。|  
|**/EB**|设置结束块分隔符字节的 ASCII 值。 默认值为 none。|  
|**/CR**|设置回车符返回分隔符字节的 ASCII 值。 默认值为 none。|  
  
## <a name="examples-of-tool-use"></a>工具使用的示例  
 下面的示例演示如何使用 MllpSend 工具。  
  
 **示例 1。** 以下命令可用于将消息发送到单向适配器侦听端口 13000 服务器"myserver"上。 包装字符的 ASCII 值是 SB 11、 EB 28 和 CR 13。  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 **示例 2。** 可以使用以下命令以向侦听端口 11000 服务器"localhost"上的双向适配器 100 次发送消息。 包装字符的 ASCII 值是 SB 11、 EB 28 和 CR 13。  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a>另请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)