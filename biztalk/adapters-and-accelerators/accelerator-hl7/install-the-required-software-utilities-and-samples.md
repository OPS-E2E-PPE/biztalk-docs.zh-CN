---
title: 安装所需的软件、 实用程序和示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de0cb89d-08bd-48ec-a149-8929e2608df8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 678037cd050ae8375b3c9ec465860d939d48cccc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204869"
---
# <a name="install-the-required-software-utilities-and-samples"></a>安装所需的软件、 实用程序和示例
本教程需要[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 和自定义[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]包括 MLLP 测试工具的安装。 此外，你应熟悉[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]中的开发[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]和[了解 HL7 快捷键和提供的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。
  
 你必须具有以下实用程序和在计算机上安装的示例：  
  
-   **MllpSend 工具**  
  
     此命令行实用工具将发送一条消息通过最少的较低层协议 (MLLP) 到 MLLP 协议接收位置。 用于测试你的教程结果。 有关详细信息，请参阅[MllpSend 工具](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)。  
  
-   **MllpPReceive 工具**  
  
     此命令行实用工具通过 MLLP 协议，充当接收位置侦听器接收消息。 用于测试你的教程结果，显示消息和接收的确认。 有关详细信息，请参阅[MllpReceive 工具](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)。  
  
-   **示例应用程序接受 ACK.txt**  
  
     此示例文件包含文本的应用程序接受的确认消息。 示例适用于 MllpReceive 工具，它接收并显示消息，然后将返回 acknowledgment(s) 发送示例文件中。  
  
 你需要使用 BTAHL7 自定义安装过程中安装两个工具和示例文件。 典型的安装过程不会安装这些工具。 若要安装这些工具，请在运行 BTAHL7 自定义安装，**自定义安装**屏幕上，选择**MLLP 测试工具**从**适配器**文件夹，并选择**测试实例**从**项目**文件夹。 有关详细信息，请参阅[HL7 安装 BizTalk 快捷键](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  
  
## <a name="see-also"></a>另请参阅  
 [准备使用批处理教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)