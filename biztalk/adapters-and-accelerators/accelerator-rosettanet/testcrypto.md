---
title: TestCrypto | Microsoft Docs
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
ms.openlocfilehash: 881cd9ee8729a18f5829490e42c0795aa1267e43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280513"
---
# <a name="testcrypto"></a>TestCrypto
TestCrypto 实用程序用于解决在解密消息的失败。 该实用工具指明解密是否失败。 如果解密成功，该实用工具指明证书是什么，并显示解密的消息。  
  
 包含仅加密的消息的一部分，而无需未加密的标头的文件运行 TestCrypto。 加密的二进制大型对象 (BLOB) 从消息中提取到文本文件中，通过探查传入消息或检索来自消息`MessageStorageIn`。  
  
 有关检索来自消息详细信息`MessageStorageIn`，请参阅[GetMessages 示例](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK  
  
## <a name="running-testcrypto"></a>运行 TestCrypto  
  
#### <a name="to-run-testcrypto"></a>若要运行 TestCrypto  
  
1.  单击**启动**，指向**所有程序**，指向**附件**，然后单击**命令提示符下**。  
  
2.  将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK。  
  
3.  在命令提示符处，键入**TestCrypto.exe\<文件名\>**，然后按 ENTER。  
  
## <a name="remarks"></a>备注  
 如果找到该证书不是必需的和有效证书，或该实用工具找不到该证书将解密失败。  
  
## <a name="see-also"></a>请参阅  
 [实用工具](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
