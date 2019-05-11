---
title: 安装所需的软件、 实用工具和示例 |Microsoft Docs
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
ms.openlocfilehash: 8b7eac14a49abbaa3044b1f051cfb23c2f504950
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296268"
---
# <a name="install-the-required-software-utilities-and-samples"></a>安装所需的软件、 实用工具和示例
本教程需要安装 Microsoft Windows Server 和自定义 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]包括 MLLP 测试工具的安装。 此外，您应熟悉[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]在 Microsoft 中的进行开发[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]并[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。
  
 您必须具有以下实用程序和在计算机上安装的示例：  
  
- **MllpSend 工具**  
  
   此命令行实用程序将发送一条消息通过最少的较低层协议 (MLLP) 协议向 MLLP 接收位置。 用于测试您的教程结果。 有关详细信息，请参阅[MllpSend 工具](../../adapters-and-accelerators/accelerator-hl7/mllpsend-tool.md)。  
  
- **MllpPReceive 工具**  
  
   此命令行实用程序通过 MLLP 协议，充当接收位置侦听程序接收消息。 用于测试您的教程结果，显示消息和接收的确认。 有关详细信息，请参阅[MllpReceive 工具](../../adapters-and-accelerators/accelerator-hl7/mllpreceive-tool.md)。  
  
- **示例应用程序接受 ACK.txt**  
  
   此示例文件包含文本的应用程序接受确认消息。 此示例适用 MllpReceive 工具，它接收并显示消息，然后在示例文件中发送回确认。  
  
  您需要通过 BTAHL7 自定义安装过程中安装的两个工具和示例文件。 典型安装过程不会安装这些工具。 若要安装这些工具，请在运行 BTAHL7 自定义安装，**自定义安装**屏幕上，选择**MLLP 测试工具**从**适配器**文件夹，然后选择**测试实例**从**项目**文件夹。 有关详细信息，请参阅[安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  
  
## <a name="see-also"></a>请参阅  
 [为使用批处理教程做准备](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)