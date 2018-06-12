---
title: TestCrypto |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, TestCrypto utility
- troubleshooting, TestCrypto utility
- TestCrypto utility
ms.assetid: 02768794-64ac-4d99-930c-738bed9626c5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6948d3883797369c98ad51683cbc59536b9d8fd
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855664"
---
# <a name="testcrypto"></a>TestCrypto
使用 TestCrypto 实用工具可以排除解密消息时的故障。 该实用工具指明解密是否失败。 如果解密成功，则该实用工具指明证书是什么，并显示解密的消息。  
  
 对只包含消息的加密部分而不包含未加密头的文件运行 TestCrypto。 通过探查传入消息或从 `MessageStorageIn` 中检索消息，可以将消息中加密的二进制大对象 (BLOB) 提取到文本文件中。  
  
 有关检索从消息详细信息`MessageStorageIn`，请参阅[GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*驱动器*\>\Program Files (x86) \Microsoft BizTalk\<版本\>RosettaNet\SDK 快捷键  
  
## <a name="running-testcrypto"></a>运行 TestCrypto  
  
#### <a name="to-run-testcrypto"></a>运行 TestCrypto  
  
1.  单击**启动**，指向**所有程序**，指向**附件**，然后单击**命令提示符**。  
  
2.  将移动到\<*驱动器*\>\Program Files (x86) \Microsoft BizTalk\<版本\>RosettaNet\SDK 快捷键。  
  
3.  在命令提示符处，键入**TestCrypto.exe \<filename\>**，然后按 ENTER。  
  
## <a name="remarks"></a>Remarks  
 如果该实用工具找到的证书不是所需的、有效的证书，或者该实用工具找不到证书，则解密失败。  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
